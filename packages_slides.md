---
theme : "simple"
transition: "slide"
height: 1080
highlightTheme: "monokai"
#logoImg: "logo.png"
#slideNumber: false
title: "Using Packages and Channels"
---
<style>
  .reveal section p {
    font-size: 0.6em;
    line-height: 1.2em;
  }

  .ic {
    background: #ddd;
    font-family: monospace;
  }
  </style>
## Using Packages and Channels

---

<div class="highlight-bash notranslate"><div class="highlight"><pre><span></span>.
├── bin
│   └── convert-caffe2-to-onnx
│   └── convert-onnx-to-caffe2
├── info
│   ├── LICENSE.txt
│   ├── about.json
│   ├── files
│   ├── git
│   ├── has_prefix.json
│   ├── hash_input.json
│   ├── index.json
│   ├── paths.json
│   ├── recipe/
│   └── test/
└── lib
    └── python3.6
        └── site-packages
            ├── caffe2/
            ├── torch/
            └── torch-1.1.0-py3.6.egg-info/
</pre></div>
</div>


---
