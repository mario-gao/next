{"title":"Set whether to only select leaf items","meta":{"title":"Set whether to only select leaf items","description":"\n<p>Demo the controlled single select and whether it can only select leaf items.</p>\n","order":"3"},"codes":{"jsx":"import { Checkbox, CascaderSelect } from '@alifd/next';\n\nclass Demo extends React.Component {\n    constructor(props) {\n        super(props);\n\n        this.state = {\n            value: null,\n            changeOnSelect: false,\n            data: []\n        };\n\n        this.handleCheck = this.handleCheck.bind(this);\n        this.handleChange = this.handleChange.bind(this);\n    }\n\n    componentDidMount() {\n        fetch('https://os.alipayobjects.com/rmsportal/ODDwqcDFTLAguOvWEolX.json')\n            .then(response => response.json())\n            .then(data => this.setState({ data, value: '2975' }))\n            .catch(e => console.log(e));\n    }\n\n    handleCheck() {\n        this.setState({\n            changeOnSelect: !this.state.changeOnSelect,\n            value: null\n        });\n    }\n\n    handleChange(value, data, extra) {\n        console.log(value, data, extra);\n\n        this.setState({\n            value\n        });\n    }\n\n    render() {\n        return (\n            <div className=\"control-single-demo\">\n                <label className=\"change-check\">\n                    <Checkbox value={!this.state.changeOnSelect} onChange={this.handleCheck} />\n                    <span className=\"change-text\">Enable changeOnSelect</span>\n                </label>\n                <CascaderSelect style={{ width: '302px' }} changeOnSelect={this.state.changeOnSelect} value={this.state.value} dataSource={this.state.data} onChange={this.handleChange} />\n            </div>\n        );\n    }\n}\n\nReactDOM.render(<Demo />, mountNode);\n","css":".control-single-demo .change-check {\n    display: block;\n    margin-bottom: 10px;\n}\n\n.control-single-demo .change-text {\n    display: inline-block;\n    margin-left: 10px;\n    vertical-align: middle;\n    color: #666;\n    font-size: 14px;\n}\n"},"body":"\n````jsx\nimport { Checkbox, CascaderSelect } from '@alifd/next';\n\nclass Demo extends React.Component {\n    constructor(props) {\n        super(props);\n\n        this.state = {\n            value: null,\n            changeOnSelect: false,\n            data: []\n        };\n\n        this.handleCheck = this.handleCheck.bind(this);\n        this.handleChange = this.handleChange.bind(this);\n    }\n\n    componentDidMount() {\n        fetch('https://os.alipayobjects.com/rmsportal/ODDwqcDFTLAguOvWEolX.json')\n            .then(response => response.json())\n            .then(data => this.setState({ data, value: '2975' }))\n            .catch(e => console.log(e));\n    }\n\n    handleCheck() {\n        this.setState({\n            changeOnSelect: !this.state.changeOnSelect,\n            value: null\n        });\n    }\n\n    handleChange(value, data, extra) {\n        console.log(value, data, extra);\n\n        this.setState({\n            value\n        });\n    }\n\n    render() {\n        return (\n            <div className=\"control-single-demo\">\n                <label className=\"change-check\">\n                    <Checkbox value={!this.state.changeOnSelect} onChange={this.handleCheck} />\n                    <span className=\"change-text\">Enable changeOnSelect</span>\n                </label>\n                <CascaderSelect style={{ width: '302px' }} changeOnSelect={this.state.changeOnSelect} value={this.state.value} dataSource={this.state.data} onChange={this.handleChange} />\n            </div>\n        );\n    }\n}\n\nReactDOM.render(<Demo />, mountNode);\n````\n\n```` css\n.control-single-demo .change-check {\n    display: block;\n    margin-bottom: 10px;\n}\n\n.control-single-demo .change-text {\n    display: inline-block;\n    margin-left: 10px;\n    vertical-align: middle;\n    color: #666;\n    font-size: 14px;\n}\n````","html":"<script>(function(){'use strict';\n\nvar _createClass = function () { function defineProperties(target, props) { for (var i = 0; i < props.length; i++) { var descriptor = props[i]; descriptor.enumerable = descriptor.enumerable || false; descriptor.configurable = true; if (\"value\" in descriptor) descriptor.writable = true; Object.defineProperty(target, descriptor.key, descriptor); } } return function (Constructor, protoProps, staticProps) { if (protoProps) defineProperties(Constructor.prototype, protoProps); if (staticProps) defineProperties(Constructor, staticProps); return Constructor; }; }();\n\nvar _next = require('@alifd/next');\n\nfunction _classCallCheck(instance, Constructor) { if (!(instance instanceof Constructor)) { throw new TypeError(\"Cannot call a class as a function\"); } }\n\nfunction _possibleConstructorReturn(self, call) { if (!self) { throw new ReferenceError(\"this hasn't been initialised - super() hasn't been called\"); } return call && (typeof call === \"object\" || typeof call === \"function\") ? call : self; }\n\nfunction _inherits(subClass, superClass) { if (typeof superClass !== \"function\" && superClass !== null) { throw new TypeError(\"Super expression must either be null or a function, not \" + typeof superClass); } subClass.prototype = Object.create(superClass && superClass.prototype, { constructor: { value: subClass, enumerable: false, writable: true, configurable: true } }); if (superClass) Object.setPrototypeOf ? Object.setPrototypeOf(subClass, superClass) : subClass.__proto__ = superClass; }\n\nvar Demo = function (_React$Component) {\n    _inherits(Demo, _React$Component);\n\n    function Demo(props) {\n        _classCallCheck(this, Demo);\n\n        var _this = _possibleConstructorReturn(this, (Demo.__proto__ || Object.getPrototypeOf(Demo)).call(this, props));\n\n        _this.state = {\n            value: null,\n            changeOnSelect: false,\n            data: []\n        };\n\n        _this.handleCheck = _this.handleCheck.bind(_this);\n        _this.handleChange = _this.handleChange.bind(_this);\n        return _this;\n    }\n\n    _createClass(Demo, [{\n        key: 'componentDidMount',\n        value: function componentDidMount() {\n            var _this2 = this;\n\n            fetch('https://os.alipayobjects.com/rmsportal/ODDwqcDFTLAguOvWEolX.json').then(function (response) {\n                return response.json();\n            }).then(function (data) {\n                return _this2.setState({ data: data, value: '2975' });\n            }).catch(function (e) {\n                return console.log(e);\n            });\n        }\n    }, {\n        key: 'handleCheck',\n        value: function handleCheck() {\n            this.setState({\n                changeOnSelect: !this.state.changeOnSelect,\n                value: null\n            });\n        }\n    }, {\n        key: 'handleChange',\n        value: function handleChange(value, data, extra) {\n            console.log(value, data, extra);\n\n            this.setState({\n                value: value\n            });\n        }\n    }, {\n        key: 'render',\n        value: function render() {\n            return React.createElement(\n                'div',\n                { className: 'control-single-demo' },\n                React.createElement(\n                    'label',\n                    { className: 'change-check' },\n                    React.createElement(_next.Checkbox, { value: !this.state.changeOnSelect, onChange: this.handleCheck }),\n                    React.createElement(\n                        'span',\n                        { className: 'change-text' },\n                        'Enable changeOnSelect'\n                    )\n                ),\n                React.createElement(_next.CascaderSelect, { style: { width: '302px' }, changeOnSelect: this.state.changeOnSelect, value: this.state.value, dataSource: this.state.data, onChange: this.handleChange })\n            );\n        }\n    }]);\n\n    return Demo;\n}(React.Component);\n\nReactDOM.render(React.createElement(Demo, null), mountNode);})()</script><div class=\"highlight\"><pre class=\"language-jsx\"><code class=\"language-jsx\"><span class=\"token keyword\">import</span> <span class=\"token punctuation\">{</span> Checkbox<span class=\"token punctuation\">,</span> CascaderSelect <span class=\"token punctuation\">}</span> <span class=\"token keyword\">from</span> <span class=\"token string\">'@alifd/next'</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">class</span> <span class=\"token class-name\">Demo</span> <span class=\"token keyword\">extends</span> <span class=\"token class-name\">React<span class=\"token punctuation\">.</span>Component</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token function\">constructor</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">props</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">super</span><span class=\"token punctuation\">(</span>props<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state <span class=\"token operator\">=</span> <span class=\"token punctuation\">{</span>\n            value<span class=\"token operator\">:</span> <span class=\"token keyword\">null</span><span class=\"token punctuation\">,</span>\n            changeOnSelect<span class=\"token operator\">:</span> <span class=\"token boolean\">false</span><span class=\"token punctuation\">,</span>\n            data<span class=\"token operator\">:</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">]</span>\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">;</span>\n\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>handleCheck <span class=\"token operator\">=</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">handleCheck</span><span class=\"token punctuation\">.</span><span class=\"token function\">bind</span><span class=\"token punctuation\">(</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>handleChange <span class=\"token operator\">=</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">handleChange</span><span class=\"token punctuation\">.</span><span class=\"token function\">bind</span><span class=\"token punctuation\">(</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">componentDidMount</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token function\">fetch</span><span class=\"token punctuation\">(</span><span class=\"token string\">'https://os.alipayobjects.com/rmsportal/ODDwqcDFTLAguOvWEolX.json'</span><span class=\"token punctuation\">)</span>\n            <span class=\"token punctuation\">.</span><span class=\"token function\">then</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">response</span> <span class=\"token operator\">=></span> response<span class=\"token punctuation\">.</span><span class=\"token function\">json</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">)</span>\n            <span class=\"token punctuation\">.</span><span class=\"token function\">then</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">data</span> <span class=\"token operator\">=></span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">setState</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span> data<span class=\"token punctuation\">,</span> value<span class=\"token operator\">:</span> <span class=\"token string\">'2975'</span> <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">)</span>\n            <span class=\"token punctuation\">.</span><span class=\"token function\">catch</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">e</span> <span class=\"token operator\">=></span> console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>e<span class=\"token punctuation\">)</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">handleCheck</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">setState</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span>\n            changeOnSelect<span class=\"token operator\">:</span> <span class=\"token operator\">!</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>changeOnSelect<span class=\"token punctuation\">,</span>\n            value<span class=\"token operator\">:</span> <span class=\"token keyword\">null</span>\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">handleChange</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">value<span class=\"token punctuation\">,</span> data<span class=\"token punctuation\">,</span> extra</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>value<span class=\"token punctuation\">,</span> data<span class=\"token punctuation\">,</span> extra<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\n        <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span><span class=\"token function\">setState</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">{</span>\n            value\n        <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">return</span> <span class=\"token punctuation\">(</span>\n            <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>div</span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>control-single-demo<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>label</span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>change-check<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Checkbox</span></span> <span class=\"token attr-name\">value</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token operator\">!</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>changeOnSelect<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">onChange</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>handleCheck<span class=\"token punctuation\">}</span></span> <span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n                    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>span</span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>change-text<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Enable changeOnSelect</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>span</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>label</span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">CascaderSelect</span></span> <span class=\"token attr-name\">style</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span> width<span class=\"token operator\">:</span> <span class=\"token string\">'302px'</span> <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">changeOnSelect</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>changeOnSelect<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">value</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>value<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">dataSource</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>state<span class=\"token punctuation\">.</span>data<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">onChange</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>handleChange<span class=\"token punctuation\">}</span></span> <span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>div</span><span class=\"token punctuation\">></span></span>\n        <span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n<span class=\"token punctuation\">}</span>\n\nReactDOM<span class=\"token punctuation\">.</span><span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Demo</span></span> <span class=\"token punctuation\">/></span></span><span class=\"token punctuation\">,</span> mountNode<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span></code></pre></div><style type=\"text/css\">.control-single-demo .change-check {\n    display: block;\n    margin-bottom: 10px;\n}\n\n.control-single-demo .change-text {\n    display: inline-block;\n    margin-left: 10px;\n    vertical-align: middle;\n    color: #666;\n    font-size: 14px;\n}</style><div class=\"highlight\"><pre class=\"language-css\"><code class=\"language-css\"><span class=\"token selector\">.control-single-demo .change-check</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token property\">display</span><span class=\"token punctuation\">:</span> block<span class=\"token punctuation\">;</span>\n    <span class=\"token property\">margin-bottom</span><span class=\"token punctuation\">:</span> 10px<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span>\n\n<span class=\"token selector\">.control-single-demo .change-text</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token property\">display</span><span class=\"token punctuation\">:</span> inline-block<span class=\"token punctuation\">;</span>\n    <span class=\"token property\">margin-left</span><span class=\"token punctuation\">:</span> 10px<span class=\"token punctuation\">;</span>\n    <span class=\"token property\">vertical-align</span><span class=\"token punctuation\">:</span> middle<span class=\"token punctuation\">;</span>\n    <span class=\"token property\">color</span><span class=\"token punctuation\">:</span> #666<span class=\"token punctuation\">;</span>\n    <span class=\"token property\">font-size</span><span class=\"token punctuation\">:</span> 14px<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span></code></pre></div>"}