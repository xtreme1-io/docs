# Page 1

xtreme1.api — xtreme1 0.0.1 documentation

```html
    <script data-url_root="../../" id="documentation_options" src="../../_static/documentation_options.js"></script>
    <script src="../../_static/jquery.js"></script>
    <script src="../../_static/underscore.js"></script>
    <script src="../../_static/_sphinx_javascript_frameworks_compat.js"></script>
    <script src="../../_static/doctools.js"></script>
    <script src="../../_static/sphinx_highlight.js"></script>
<script src="../../_static/js/theme.js"></script>
<link rel="index" title="Index" href="../../genindex.html" />
<link rel="search" title="Search" href="../../search.html" /> 
```

xtreme1 &#x20;

Contents:

* xtreme1
* xtreme1 package

```html
    </div>
  </div>
</nav>

<section data-toggle="wy-nav-shift" class="wy-nav-content-wrap"><nav class="wy-nav-top" aria-label="Mobile navigation menu" >
      <i data-toggle="wy-nav-top" class="fa fa-bars"></i>
      <a href="../../index.html">xtreme1</a>
  </nav>

  <div class="wy-nav-content">
    <div class="rst-content">
      <div role="navigation" aria-label="Page navigation">
```

*
* Module code
* xtreme1.api
*

***

## Source code for xtreme1.api

```
from typing import List, Dict, Optional, Union
import requests
from .exceptions import SDKException, EXCEPTIONS
[docs]class Api:
<span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span>        <span class="bp">self</span><span class="p">,</span>        <span class="n">access_token</span><span class="p">:</span> <span class="nb">str</span><span class="p">,</span>        <span class="n">base_url</span><span class="p">:</span> <span class="nb">str</span><span class="p">):</span>    <span class="bp">self</span><span class="o">.</span><span class="n">access_token</span> <span class="o">=</span> <span class="n">access_token</span>    <span class="bp">self</span><span class="o">.</span><span class="n">_headers</span> <span class="o">=</span> <span class="p">{</span>        <span class="s1">&#39;Authorization&#39;</span><span class="p">:</span> <span class="sa">f</span><span class="s1">&#39;Bearer </span><span class="si">{</span><span class="n">access_token</span><span class="si">}</span><span class="s1">&#39;</span>    <span class="p">}</span>    <span class="bp">self</span><span class="o">.</span><span class="n">base_url</span> <span class="o">=</span> <span class="n">base_url</span><span class="k">def</span> <span class="nf">_base_request</span><span class="p">(</span>        <span class="bp">self</span><span class="p">,</span>        <span class="n">method</span><span class="p">:</span> <span class="nb">str</span><span class="p">,</span>        <span class="n">headers</span><span class="p">:</span> <span class="n">Dict</span><span class="p">,</span>        <span class="n">endpoint</span><span class="p">:</span> <span class="nb">str</span><span class="p">,</span>        <span class="n">params</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="n">Dict</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span><span class="p">,</span>        <span class="n">files</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="n">Dict</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span><span class="p">,</span>        <span class="n">data</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="n">Dict</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span><span class="p">,</span>        <span class="n">json</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="n">Dict</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span><span class="p">,</span>        <span class="n">full_url</span><span class="p">:</span> <span class="n">Optional</span><span class="p">[</span><span class="nb">str</span><span class="p">]</span> <span class="o">=</span> <span class="kc">None</span><span class="p">):</span>    <span class="k">if</span> <span class="ow">not</span> <span class="n">full_url</span><span class="p">:</span>        <span class="n">full_url</span> <span class="o">=</span> <span class="sa">f</span><span class="s1">&#39;</span><span class="si">{</span><span class="bp">self</span><span class="o">.</span><span class="n">base_url</span><span class="si">}</span><span class="s1">/api/</span><span class="si">{</span><span class="n">endpoint</span><span class="si">}</span><span class="s1">&#39;</span>    <span class="n">resp</span> <span class="o">=</span> <span class="n">requests</span><span class="o">.</span><span class="n">request</span><span class="p">(</span>        <span class="n">method</span><span class="o">=</span><span class="n">method</span><span class="p">,</span>        <span class="n">url</span><span class="o">=</span><span class="n">full_url</span><span class="p">,</span>        <span class="n">headers</span><span class="o">=</span><span class="n">headers</span><span class="p">,</span>        <span class="n">params</span><span class="o">=</span><span class="n">params</span><span class="p">,</span>        <span class="n">files</span><span class="o">=</span><span class="n">files</span><span class="p">,</span>        <span class="n">data</span><span class="o">=</span><span class="n">data</span><span class="p">,</span>        <span class="n">json</span><span class="o">=</span><span class="n">json</span>    <span class="p">)</span>    <span class="k">if</span> <span class="n">resp</span><span class="o">.</span><span class="n">status_code</span> <span class="o">==</span> <span class="mi">200</span><span class="p">:</span>        <span class="n">info</span> <span class="o">=</span> <span class="n">resp</span><span class="o">.</span><span class="n">json</span><span class="p">()</span>        <span class="k">if</span> <span class="n">info</span><span class="p">[</span><span class="s1">&#39;code&#39;</span><span class="p">]</span> <span class="o">==</span> <span class="s1">&#39;OK&#39;</span><span class="p">:</span>            <span class="k">return</span> <span class="n">info</span><span class="p">[</span><span class="s1">&#39;data&#39;</span><span class="p">]</span>        <span class="k">else</span><span class="p">:</span>            <span class="n">cur_exception</span> <span class="o">=</span> <span class="n">EXCEPTIONS</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">info</span><span class="p">[</span><span class="s1">&#39;code&#39;</span><span class="p">],</span> <span class="n">SDKException</span><span class="p">)</span>            <span class="k">raise</span> <span class="n">cur_exception</span><span class="p">(</span><span class="n">code</span><span class="o">=</span><span class="n">info</span><span class="p">[</span><span class="s1">&#39;code&#39;</span><span class="p">],</span> <span class="n">message</span><span class="o">=</span><span class="n">info</span><span class="p">[</span><span class="s1">&#39;message&#39;</span><span class="p">])</span>    <span class="k">else</span><span class="p">:</span>        <span class="k">raise</span> <span class="n">EXCEPTIONS</span><span class="o">.</span><span class="n">get</span><span class="p">(</span><span class="n">resp</span><span class="o">.</span><span class="n">status_code</span><span class="p">,</span> <span class="n">SDKException</span><span class="p">(</span><span class="n">code</span><span class="o">=</span><span class="n">resp</span><span class="o">.</span><span class="n">status_code</span><span class="p">))</span>
[docs]    def get_request(
            self,
            endpoint: str,
            params: Optional[Dict] = None,
            headers: bool = True,
            full_url: Optional[str] = None
    ) -> Union[Dict, List[Dict]]:
        """
        An encapsulated 'GET' method.
        Parameters
        ----------
        endpoint: str
            The endpoint of current api url.
        params: Optional[Dict], default None
            Parameters to add in 'GET' request.
        headers: bool, default True
            Request with headers or not.
        full_url: Optional[str], default None
            A complete url. If this parameter is passed, 'self.base_url' and 'endpoint' will be invalid.
        Returns
        -------
        Union[Dict, List[Dict]]
            A dict or list of dict transformed from json.
        """
if headers:
headers = self._headers
return self._base_request(
method='GET',
headers=headers,
endpoint=endpoint,
params=params,
full_url=full_url
)
[docs]    def post_request(
            self,
            endpoint: str,
            payload: Optional[Dict] = None,
            files: Optional[Dict] = None,
            headers: bool = True,
            full_url: Optional[str] = None
    ) -> Union[str, Dict, None]:
        """
        An encapsulated 'POST' method.
        Parameters
        ----------
        endpoint: str
            The endpoint of current api url.
        payload: Optional[Dict], default None
            Parameters to add in 'POST' request.
        files: Optional[Dict], default None
            Files to upload.
        headers: bool, default True
            Request with headers or not.
        full_url: Optional[str], default None
            A complete url. If this parameter is passed, 'self.base_url' and 'endpoint' will be invalid.
        Returns
        -------
        Union[str, Dict, None]
            A simple message, a dict or null.
        """
if headers:
headers = self._headers
return self._base_request(
method='POST',
headers=headers,
endpoint=endpoint,
json=payload,
files=files,
full_url=full_url
)
```

```
       </div>
      </div>
      <footer>
```

***

© Copyright 2023, basicai.

Built with [Sphinx](https://www.sphinx-doc.org/) using a [theme](https://github.com/readthedocs/sphinx\_rtd\_theme) provided by [Read the Docs](https://readthedocs.org).

jQuery(function () { SphinxRtdTheme.Navigation.enable(true); });
