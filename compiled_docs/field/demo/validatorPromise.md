{"title":"校验 promise","meta":{"title":"校验 promise","description":"\n<p>使用 Promise 的方式作为校验返回</p>\n","order":"4"},"codes":{"jsx":"import ReactDOM from 'react-dom';\nimport React from 'react';\nimport { Input, Button, Checkbox, Field } from '@alifd/next';\n\nconst CheckboxGroup = Checkbox.Group;\n\nconst list = [\n    {\n        value: 'apple',\n        label: 'apple'\n    }, {\n        value: 'pear',\n        label: 'pear'\n    }, {\n        value: 'orange',\n        label: 'orange'\n    }\n];\n\nclass App extends React.Component {\n    state = {\n        checkboxStatus: true\n    }\n    field = new Field(this, {scrollToFirstError: -10});\n\n    isChecked(rule, value) {\n        if (!value) {\n            return Promise.reject('consent agreement not checked ');\n        } else {\n            return Promise.resolve(null);\n        }\n    }\n\n    userName(rule, value) {\n        if (value === 'frank') {\n            return new Promise((resolve, reject) => {\n                setTimeout(() => reject('name existed'), 200);\n            });\n        } else {\n            return new Promise((resolve) => {\n                setTimeout(() => resolve(null), 200);\n            });\n        }\n    }\n\n    render() {\n        const init = this.field.init;\n\n        return (<div className=\"demo\">\n            <Input defaultValue=\"\" placeholder=\"try frank\" {...init('username', {\n                rules: [{\n                    validator: this.userName,\n                    trigger: ['onBlur', 'onChange']\n                }]\n            })} />\n            {this.field.getState('username') === 'loading' ? 'validating...' : ''}\n            {this.field.getError('username') ?\n                <span style={{color: 'red'}}>{this.field.getError('username').join(',')}</span> : ''}\n\n            <br/>\n            <br/>\n\n            agreement:\n            <Checkbox {...init('checkbox', {\n                valueName: 'checked',\n                rules: [{validator: this.isChecked}]\n            })} />\n            {this.field.getError('checkbox') ?\n                <span style={{color: 'red'}}>{this.field.getError('checkbox').join(',')}</span> : ''}\n\n            <br/>\n            <br/>\n\n            <Button type=\"primary\" onClick={() => {\n                this.field.validatePromise().then(({errors, values}) => {\n                    console.log(errors, values);\n                });\n            }}>validate</Button>\n            <Button onClick={() => {\n                this.field.reset();\n            }}>reset</Button>\n        </div>);\n    }\n}\n\nReactDOM.render(<App/>, mountNode);\n","css":".demo .next-btn {\n    margin-right: 5px;\n}\n"},"body":"\n\n````jsx\nimport ReactDOM from 'react-dom';\nimport React from 'react';\nimport { Input, Button, Checkbox, Field } from '@alifd/next';\n\nconst CheckboxGroup = Checkbox.Group;\n\nconst list = [\n    {\n        value: 'apple',\n        label: 'apple'\n    }, {\n        value: 'pear',\n        label: 'pear'\n    }, {\n        value: 'orange',\n        label: 'orange'\n    }\n];\n\nclass App extends React.Component {\n    state = {\n        checkboxStatus: true\n    }\n    field = new Field(this, {scrollToFirstError: -10});\n\n    isChecked(rule, value) {\n        if (!value) {\n            return Promise.reject('consent agreement not checked ');\n        } else {\n            return Promise.resolve(null);\n        }\n    }\n\n    userName(rule, value) {\n        if (value === 'frank') {\n            return new Promise((resolve, reject) => {\n                setTimeout(() => reject('name existed'), 200);\n            });\n        } else {\n            return new Promise((resolve) => {\n                setTimeout(() => resolve(null), 200);\n            });\n        }\n    }\n\n    render() {\n        const init = this.field.init;\n\n        return (<div className=\"demo\">\n            <Input defaultValue=\"\" placeholder=\"try frank\" {...init('username', {\n                rules: [{\n                    validator: this.userName,\n                    trigger: ['onBlur', 'onChange']\n                }]\n            })} />\n            {this.field.getState('username') === 'loading' ? 'validating...' : ''}\n            {this.field.getError('username') ?\n                <span style={{color: 'red'}}>{this.field.getError('username').join(',')}</span> : ''}\n\n            <br/>\n            <br/>\n\n            agreement:\n            <Checkbox {...init('checkbox', {\n                valueName: 'checked',\n                rules: [{validator: this.isChecked}]\n            })} />\n            {this.field.getError('checkbox') ?\n                <span style={{color: 'red'}}>{this.field.getError('checkbox').join(',')}</span> : ''}\n\n            <br/>\n            <br/>\n\n            <Button type=\"primary\" onClick={() => {\n                this.field.validatePromise().then(({errors, values}) => {\n                    console.log(errors, values);\n                });\n            }}>validate</Button>\n            <Button onClick={() => {\n                this.field.reset();\n            }}>reset</Button>\n        </div>);\n    }\n}\n\nReactDOM.render(<App/>, mountNode);\n````\n\n````css\n.demo .next-btn {\n    margin-right: 5px;\n}\n````","html":"<script>(function(){'use strict';\n\nvar _extends = Object.assign || function (target) { for (var i = 1; i < arguments.length; i++) { var source = arguments[i]; for (var key in source) { if (Object.prototype.hasOwnProperty.call(source, key)) { target[key] = source[key]; } } } return target; };\n\nvar _createClass = function () { function defineProperties(target, props) { for (var i = 0; i < props.length; i++) { var descriptor = props[i]; descriptor.enumerable = descriptor.enumerable || false; descriptor.configurable = true; if (\"value\" in descriptor) descriptor.writable = true; Object.defineProperty(target, descriptor.key, descriptor); } } return function (Constructor, protoProps, staticProps) { if (protoProps) defineProperties(Constructor.prototype, protoProps); if (staticProps) defineProperties(Constructor, staticProps); return Constructor; }; }();\n\nvar _reactDom = require('react-dom');\n\nvar _reactDom2 = _interopRequireDefault(_reactDom);\n\nvar _react = require('react');\n\nvar _react2 = _interopRequireDefault(_react);\n\nvar _next = require('@alifd/next');\n\nfunction _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }\n\nfunction _classCallCheck(instance, Constructor) { if (!(instance instanceof Constructor)) { throw new TypeError(\"Cannot call a class as a function\"); } }\n\nfunction _possibleConstructorReturn(self, call) { if (!self) { throw new ReferenceError(\"this hasn't been initialised - super() hasn't been called\"); } return call && (typeof call === \"object\" || typeof call === \"function\") ? call : self; }\n\nfunction _inherits(subClass, superClass) { if (typeof superClass !== \"function\" && superClass !== null) { throw new TypeError(\"Super expression must either be null or a function, not \" + typeof superClass); } subClass.prototype = Object.create(superClass && superClass.prototype, { constructor: { value: subClass, enumerable: false, writable: true, configurable: true } }); if (superClass) Object.setPrototypeOf ? Object.setPrototypeOf(subClass, superClass) : subClass.__proto__ = superClass; }\n\nvar CheckboxGroup = _next.Checkbox.Group;\n\nvar list = [{\n    value: 'apple',\n    label: 'apple'\n}, {\n    value: 'pear',\n    label: 'pear'\n}, {\n    value: 'orange',\n    label: 'orange'\n}];\n\nvar App = function (_React$Component) {\n    _inherits(App, _React$Component);\n\n    function App() {\n        var _ref;\n\n        var _temp, _this, _ret;\n\n        _classCallCheck(this, App);\n\n        for (var _len = arguments.length, args = Array(_len), _key = 0; _key < _len; _key++) {\n            args[_key] = arguments[_key];\n        }\n\n        return _ret = (_temp = (_this = _possibleConstructorReturn(this, (_ref = App.__proto__ || Object.getPrototypeOf(App)).call.apply(_ref, [this].concat(args))), _this), _this.state = {\n            checkboxStatus: true\n        }, _this.field = new _next.Field(_this, { scrollToFirstError: -10 }), _temp), _possibleConstructorReturn(_this, _ret);\n    }\n\n    _createClass(App, [{\n        key: 'isChecked',\n        value: function isChecked(rule, value) {\n            if (!value) {\n                return Promise.reject('consent agreement not checked ');\n            } else {\n                return Promise.resolve(null);\n            }\n        }\n    }, {\n        key: 'userName',\n        value: function userName(rule, value) {\n            if (value === 'frank') {\n                return new Promise(function (resolve, reject) {\n                    setTimeout(function () {\n                        return reject('name existed');\n                    }, 200);\n                });\n            } else {\n                return new Promise(function (resolve) {\n                    setTimeout(function () {\n                        return resolve(null);\n                    }, 200);\n                });\n            }\n        }\n    }, {\n        key: 'render',\n        value: function render() {\n            var _this2 = this;\n\n            var init = this.field.init;\n\n            return _react2.default.createElement(\n                'div',\n                { className: 'demo' },\n                _react2.default.createElement(_next.Input, _extends({ defaultValue: '', placeholder: 'try frank' }, init('username', {\n                    rules: [{\n                        validator: this.userName,\n                        trigger: ['onBlur', 'onChange']\n                    }]\n                }))),\n                this.field.getState('username') === 'loading' ? 'validating...' : '',\n                this.field.getError('username') ? _react2.default.createElement(\n                    'span',\n                    { style: { color: 'red' } },\n                    this.field.getError('username').join(',')\n                ) : '',\n                _react2.default.createElement('br', null),\n                _react2.default.createElement('br', null),\n                'agreement:',\n                _react2.default.createElement(_next.Checkbox, init('checkbox', {\n                    valueName: 'checked',\n                    rules: [{ validator: this.isChecked }]\n                })),\n                this.field.getError('checkbox') ? _react2.default.createElement(\n                    'span',\n                    { style: { color: 'red' } },\n                    this.field.getError('checkbox').join(',')\n                ) : '',\n                _react2.default.createElement('br', null),\n                _react2.default.createElement('br', null),\n                _react2.default.createElement(\n                    _next.Button,\n                    { type: 'primary', onClick: function onClick() {\n                            _this2.field.validatePromise().then(function (_ref2) {\n                                var errors = _ref2.errors,\n                                    values = _ref2.values;\n\n                                console.log(errors, values);\n                            });\n                        } },\n                    'validate'\n                ),\n                _react2.default.createElement(\n                    _next.Button,\n                    { onClick: function onClick() {\n                            _this2.field.reset();\n                        } },\n                    'reset'\n                )\n            );\n        }\n    }]);\n\n    return App;\n}(_react2.default.Component);\n\n_reactDom2.default.render(_react2.default.createElement(App, null), mountNode);})()</script><div class=\"highlight\"><pre class=\"language-jsx\"><code class=\"language-jsx\"><span class=\"token keyword\">import</span> ReactDOM <span class=\"token keyword\">from</span> <span class=\"token string\">'react-dom'</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">import</span> React <span class=\"token keyword\">from</span> <span class=\"token string\">'react'</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">import</span> <span class=\"token punctuation\">{</span> Input<span class=\"token punctuation\">,</span> Button<span class=\"token punctuation\">,</span> Checkbox<span class=\"token punctuation\">,</span> Field <span class=\"token punctuation\">}</span> <span class=\"token keyword\">from</span> <span class=\"token string\">'@alifd/next'</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> CheckboxGroup <span class=\"token operator\">=</span> Checkbox<span class=\"token punctuation\">.</span>Group<span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> list <span class=\"token operator\">=</span> <span class=\"token punctuation\">[</span>\n    <span class=\"token punctuation\">{</span>\n        value<span class=\"token operator\">:</span> <span class=\"token string\">'apple'</span><span class=\"token punctuation\">,</span>\n        label<span class=\"token operator\">:</span> <span class=\"token string\">'apple'</span>\n    <span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span> <span class=\"token punctuation\">{</span>\n        value<span class=\"token operator\">:</span> <span class=\"token string\">'pear'</span><span class=\"token punctuation\">,</span>\n        label<span class=\"token operator\">:</span> <span class=\"token string\">'pear'</span>\n    <span class=\"token punctuation\">}</span><span class=\"token punctuation\">,</span> <span class=\"token punctuation\">{</span>\n        value<span class=\"token operator\">:</span> <span class=\"token string\">'orange'</span><span class=\"token punctuation\">,</span>\n        label<span class=\"token operator\">:</span> <span class=\"token string\">'orange'</span>\n    <span class=\"token punctuation\">}</span>\n<span class=\"token punctuation\">]</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">class</span> <span class=\"token class-name\">App</span> <span class=\"token keyword\">extends</span> <span class=\"token class-name\">React<span class=\"token punctuation\">.</span>Component</span> <span class=\"token punctuation\">{</span>\n    state <span class=\"token operator\">=</span> <span class=\"token punctuation\">{</span>\n        checkboxStatus<span class=\"token operator\">:</span> <span class=\"token boolean\">true</span>\n    <span class=\"token punctuation\">}</span>\n    field <span class=\"token operator\">=</span> <span class=\"token keyword\">new</span> <span class=\"token class-name\">Field</span><span class=\"token punctuation\">(</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">,</span> <span class=\"token punctuation\">{</span>scrollToFirstError<span class=\"token operator\">:</span> <span class=\"token operator\">-</span><span class=\"token number\">10</span><span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\n    <span class=\"token function\">isChecked</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">rule<span class=\"token punctuation\">,</span> value</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">if</span> <span class=\"token punctuation\">(</span><span class=\"token operator\">!</span>value<span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> Promise<span class=\"token punctuation\">.</span><span class=\"token function\">reject</span><span class=\"token punctuation\">(</span><span class=\"token string\">'consent agreement not checked '</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span> <span class=\"token keyword\">else</span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> Promise<span class=\"token punctuation\">.</span><span class=\"token function\">resolve</span><span class=\"token punctuation\">(</span><span class=\"token keyword\">null</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">userName</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">rule<span class=\"token punctuation\">,</span> value</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">if</span> <span class=\"token punctuation\">(</span>value <span class=\"token operator\">===</span> <span class=\"token string\">'frank'</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> <span class=\"token keyword\">new</span> <span class=\"token class-name\">Promise</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">resolve<span class=\"token punctuation\">,</span> reject</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n                <span class=\"token function\">setTimeout</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token function\">reject</span><span class=\"token punctuation\">(</span><span class=\"token string\">'name existed'</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">,</span> <span class=\"token number\">200</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span> <span class=\"token keyword\">else</span> <span class=\"token punctuation\">{</span>\n            <span class=\"token keyword\">return</span> <span class=\"token keyword\">new</span> <span class=\"token class-name\">Promise</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">(</span><span class=\"token parameter\">resolve</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n                <span class=\"token function\">setTimeout</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token function\">resolve</span><span class=\"token punctuation\">(</span><span class=\"token keyword\">null</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">,</span> <span class=\"token number\">200</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n        <span class=\"token punctuation\">}</span>\n    <span class=\"token punctuation\">}</span>\n\n    <span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token punctuation\">{</span>\n        <span class=\"token keyword\">const</span> init <span class=\"token operator\">=</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span>init<span class=\"token punctuation\">;</span>\n\n        <span class=\"token keyword\">return</span> <span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>div</span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>demo<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            &lt;Input defaultValue=\"\" placeholder=\"try frank\" </span><span class=\"token punctuation\">{</span><span class=\"token operator\">...</span><span class=\"token function\">init</span><span class=\"token punctuation\">(</span><span class=\"token string\">'username'</span><span class=\"token punctuation\">,</span> <span class=\"token punctuation\">{</span>\n                rules<span class=\"token operator\">:</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">{</span>\n                    validator<span class=\"token operator\">:</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>userName<span class=\"token punctuation\">,</span>\n                    trigger<span class=\"token operator\">:</span> <span class=\"token punctuation\">[</span><span class=\"token string\">'onBlur'</span><span class=\"token punctuation\">,</span> <span class=\"token string\">'onChange'</span><span class=\"token punctuation\">]</span>\n                <span class=\"token punctuation\">}</span><span class=\"token punctuation\">]</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span><span class=\"token plain-text\"> />\n            </span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">getState</span><span class=\"token punctuation\">(</span><span class=\"token string\">'username'</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">===</span> <span class=\"token string\">'loading'</span> <span class=\"token operator\">?</span> <span class=\"token string\">'validating...'</span> <span class=\"token operator\">:</span> <span class=\"token string\">''</span><span class=\"token punctuation\">}</span><span class=\"token plain-text\">\n            </span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">getError</span><span class=\"token punctuation\">(</span><span class=\"token string\">'username'</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">?</span>\n                <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>span</span> <span class=\"token attr-name\">style</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>color<span class=\"token operator\">:</span> <span class=\"token string\">'red'</span><span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">getError</span><span class=\"token punctuation\">(</span><span class=\"token string\">'username'</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">.</span><span class=\"token function\">join</span><span class=\"token punctuation\">(</span><span class=\"token string\">','</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>span</span><span class=\"token punctuation\">></span></span> <span class=\"token operator\">:</span> <span class=\"token string\">''</span><span class=\"token punctuation\">}</span><span class=\"token plain-text\">\n\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>br</span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>br</span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n\n            agreement:\n            &lt;Checkbox </span><span class=\"token punctuation\">{</span><span class=\"token operator\">...</span><span class=\"token function\">init</span><span class=\"token punctuation\">(</span><span class=\"token string\">'checkbox'</span><span class=\"token punctuation\">,</span> <span class=\"token punctuation\">{</span>\n                valueName<span class=\"token operator\">:</span> <span class=\"token string\">'checked'</span><span class=\"token punctuation\">,</span>\n                rules<span class=\"token operator\">:</span> <span class=\"token punctuation\">[</span><span class=\"token punctuation\">{</span>validator<span class=\"token operator\">:</span> <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>isChecked<span class=\"token punctuation\">}</span><span class=\"token punctuation\">]</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span><span class=\"token plain-text\"> />\n            </span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">getError</span><span class=\"token punctuation\">(</span><span class=\"token string\">'checkbox'</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">?</span>\n                <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>span</span> <span class=\"token attr-name\">style</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">{</span>color<span class=\"token operator\">:</span> <span class=\"token string\">'red'</span><span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">{</span><span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">getError</span><span class=\"token punctuation\">(</span><span class=\"token string\">'checkbox'</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">.</span><span class=\"token function\">join</span><span class=\"token punctuation\">(</span><span class=\"token string\">','</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">}</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>span</span><span class=\"token punctuation\">></span></span> <span class=\"token operator\">:</span> <span class=\"token string\">''</span><span class=\"token punctuation\">}</span><span class=\"token plain-text\">\n\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>br</span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>br</span><span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">type</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>primary<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">onClick</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n                <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">validatePromise</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">.</span><span class=\"token function\">then</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">(</span><span class=\"token parameter\"><span class=\"token punctuation\">{</span>errors<span class=\"token punctuation\">,</span> values<span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n                    console<span class=\"token punctuation\">.</span><span class=\"token function\">log</span><span class=\"token punctuation\">(</span>errors<span class=\"token punctuation\">,</span> values<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n                <span class=\"token punctuation\">}</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">validate</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">onClick</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">{</span>\n                <span class=\"token keyword\">this</span><span class=\"token punctuation\">.</span>field<span class=\"token punctuation\">.</span><span class=\"token function\">reset</span><span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n            <span class=\"token punctuation\">}</span><span class=\"token punctuation\">}</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">reset</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>div</span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n    <span class=\"token punctuation\">}</span>\n<span class=\"token punctuation\">}</span>\n\nReactDOM<span class=\"token punctuation\">.</span><span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">App</span></span><span class=\"token punctuation\">/></span></span><span class=\"token punctuation\">,</span> mountNode<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span></code></pre></div><style type=\"text/css\">.demo .next-btn {\n    margin-right: 5px;\n}</style><div class=\"highlight\"><pre class=\"language-css\"><code class=\"language-css\"><span class=\"token selector\">.demo .next-btn</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token property\">margin-right</span><span class=\"token punctuation\">:</span> 5px<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span></code></pre></div>"}