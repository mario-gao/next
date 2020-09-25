{"title":"嵌套浮层问题","meta":{"title":"嵌套浮层问题","description":"\n<p>浮层中如果又有浮层，比如在<code>Balloon</code>中有<code>DatePicker/Select</code>的浮层, <code>DatePicker</code>选择时，<code>Balloon</code>浮层也会关闭。可以用 <code>followTrigger</code>解决。</p>\n","order":"6"},"codes":{"jsx":"import { Button, Balloon, DatePicker, Select } from '@alifd/next';\nimport moment from 'moment';\n\nconst showSelect = <Button className=\"btrigger\">Show Select</Button>;\nconst showDatePicker = <Button className=\"btrigger\">Show DatePicker</Button>;\nconst innerButton = <Button className=\"btrigger\">Show Inner Balloon</Button>;\nconst dateValue = moment('2018-01-01', 'YYYY-MM-DD', true);\n\nconst App = () => (\n    <div className=\"container nested\">\n        <Balloon type=\"primary\" autoFocus trigger={showSelect} closable={false} triggerType=\"click\">\n            <Select dataSource={['apple', 'banana', 'orange']} followTrigger />\n        </Balloon>\n        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\n        <Balloon type=\"primary\" autoFocus trigger={showDatePicker} closable={false} triggerType=\"click\">\n            <DatePicker defaultValue={dateValue} followTrigger />\n        </Balloon>\n        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\n        <Balloon type=\"primary\" autoFocus trigger={innerButton} closable={false} triggerType=\"click\">\n            <Balloon trigger={<Button type=\"primary\">please click</Button>} followTrigger triggerType=\"click\">\n                nesting balloon content\n            </Balloon>\n        </Balloon>\n    </div>\n);\n\nReactDOM.render(<App />, mountNode);\n\n","css":"\n.container.nested {\n    margin-bottom: 50px;\n}\n\n"},"body":"\n\n````jsx\nimport { Button, Balloon, DatePicker, Select } from '@alifd/next';\nimport moment from 'moment';\n\nconst showSelect = <Button className=\"btrigger\">Show Select</Button>;\nconst showDatePicker = <Button className=\"btrigger\">Show DatePicker</Button>;\nconst innerButton = <Button className=\"btrigger\">Show Inner Balloon</Button>;\nconst dateValue = moment('2018-01-01', 'YYYY-MM-DD', true);\n\nconst App = () => (\n    <div className=\"container nested\">\n        <Balloon type=\"primary\" autoFocus trigger={showSelect} closable={false} triggerType=\"click\">\n            <Select dataSource={['apple', 'banana', 'orange']} followTrigger />\n        </Balloon>\n        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\n        <Balloon type=\"primary\" autoFocus trigger={showDatePicker} closable={false} triggerType=\"click\">\n            <DatePicker defaultValue={dateValue} followTrigger />\n        </Balloon>\n        &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\n        <Balloon type=\"primary\" autoFocus trigger={innerButton} closable={false} triggerType=\"click\">\n            <Balloon trigger={<Button type=\"primary\">please click</Button>} followTrigger triggerType=\"click\">\n                nesting balloon content\n            </Balloon>\n        </Balloon>\n    </div>\n);\n\nReactDOM.render(<App />, mountNode);\n\n````\n\n```css\n\n.container.nested {\n    margin-bottom: 50px;\n}\n\n```","html":"<script>(function(){'use strict';\n\nvar _next = require('@alifd/next');\n\nvar _moment = require('moment');\n\nvar _moment2 = _interopRequireDefault(_moment);\n\nfunction _interopRequireDefault(obj) { return obj && obj.__esModule ? obj : { default: obj }; }\n\nvar showSelect = React.createElement(\n    _next.Button,\n    { className: 'btrigger' },\n    'Show Select'\n);\nvar showDatePicker = React.createElement(\n    _next.Button,\n    { className: 'btrigger' },\n    'Show DatePicker'\n);\nvar innerButton = React.createElement(\n    _next.Button,\n    { className: 'btrigger' },\n    'Show Inner Balloon'\n);\nvar dateValue = (0, _moment2.default)('2018-01-01', 'YYYY-MM-DD', true);\n\nvar App = function App() {\n    return React.createElement(\n        'div',\n        { className: 'container nested' },\n        React.createElement(\n            _next.Balloon,\n            { type: 'primary', autoFocus: true, trigger: showSelect, closable: false, triggerType: 'click' },\n            React.createElement(_next.Select, { dataSource: ['apple', 'banana', 'orange'], followTrigger: true })\n        ),\n        '\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0',\n        React.createElement(\n            _next.Balloon,\n            { type: 'primary', autoFocus: true, trigger: showDatePicker, closable: false, triggerType: 'click' },\n            React.createElement(_next.DatePicker, { defaultValue: dateValue, followTrigger: true })\n        ),\n        '\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0\\xA0',\n        React.createElement(\n            _next.Balloon,\n            { type: 'primary', autoFocus: true, trigger: innerButton, closable: false, triggerType: 'click' },\n            React.createElement(\n                _next.Balloon,\n                { trigger: React.createElement(\n                        _next.Button,\n                        { type: 'primary' },\n                        'please click'\n                    ), followTrigger: true, triggerType: 'click' },\n                'nesting balloon content'\n            )\n        )\n    );\n};\n\nReactDOM.render(React.createElement(App, null), mountNode);})()</script><div class=\"highlight\"><pre class=\"language-jsx\"><code class=\"language-jsx\"><span class=\"token keyword\">import</span> <span class=\"token punctuation\">{</span> Button<span class=\"token punctuation\">,</span> Balloon<span class=\"token punctuation\">,</span> DatePicker<span class=\"token punctuation\">,</span> Select <span class=\"token punctuation\">}</span> <span class=\"token keyword\">from</span> <span class=\"token string\">'@alifd/next'</span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">import</span> moment <span class=\"token keyword\">from</span> <span class=\"token string\">'moment'</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> showSelect <span class=\"token operator\">=</span> <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>btrigger<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Show Select</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> showDatePicker <span class=\"token operator\">=</span> <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>btrigger<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Show DatePicker</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> innerButton <span class=\"token operator\">=</span> <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>btrigger<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">Show Inner Balloon</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">;</span>\n<span class=\"token keyword\">const</span> dateValue <span class=\"token operator\">=</span> <span class=\"token function\">moment</span><span class=\"token punctuation\">(</span><span class=\"token string\">'2018-01-01'</span><span class=\"token punctuation\">,</span> <span class=\"token string\">'YYYY-MM-DD'</span><span class=\"token punctuation\">,</span> <span class=\"token boolean\">true</span><span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\n<span class=\"token keyword\">const</span> <span class=\"token function-variable function\">App</span> <span class=\"token operator\">=</span> <span class=\"token punctuation\">(</span><span class=\"token punctuation\">)</span> <span class=\"token operator\">=></span> <span class=\"token punctuation\">(</span>\n    <span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span>div</span> <span class=\"token attr-name\">className</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>container nested<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Balloon</span></span> <span class=\"token attr-name\">type</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>primary<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">autoFocus</span> <span class=\"token attr-name\">trigger</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>showSelect<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">closable</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token boolean\">false</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">triggerType</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>click<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Select</span></span> <span class=\"token attr-name\">dataSource</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token punctuation\">[</span><span class=\"token string\">'apple'</span><span class=\"token punctuation\">,</span> <span class=\"token string\">'banana'</span><span class=\"token punctuation\">,</span> <span class=\"token string\">'orange'</span><span class=\"token punctuation\">]</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">followTrigger</span> <span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Balloon</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Balloon</span></span> <span class=\"token attr-name\">type</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>primary<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">autoFocus</span> <span class=\"token attr-name\">trigger</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>showDatePicker<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">closable</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token boolean\">false</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">triggerType</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>click<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">DatePicker</span></span> <span class=\"token attr-name\">defaultValue</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>dateValue<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">followTrigger</span> <span class=\"token punctuation\">/></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Balloon</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        &amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;&amp;nbsp;\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Balloon</span></span> <span class=\"token attr-name\">type</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>primary<span class=\"token punctuation\">\"</span></span> <span class=\"token attr-name\">autoFocus</span> <span class=\"token attr-name\">trigger</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span>innerButton<span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">closable</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token boolean\">false</span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">triggerType</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>click<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Balloon</span></span> <span class=\"token attr-name\">trigger</span><span class=\"token script language-javascript\"><span class=\"token script-punctuation punctuation\">=</span><span class=\"token punctuation\">{</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">Button</span></span> <span class=\"token attr-name\">type</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>primary<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">please click</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Button</span></span><span class=\"token punctuation\">></span></span><span class=\"token punctuation\">}</span></span> <span class=\"token attr-name\">followTrigger</span> <span class=\"token attr-name\">triggerType</span><span class=\"token attr-value\"><span class=\"token punctuation attr-equals\">=</span><span class=\"token punctuation\">\"</span>click<span class=\"token punctuation\">\"</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n                nesting balloon content\n            </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Balloon</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n        </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span><span class=\"token class-name\">Balloon</span></span><span class=\"token punctuation\">></span></span><span class=\"token plain-text\">\n    </span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;/</span>div</span><span class=\"token punctuation\">></span></span>\n<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n\nReactDOM<span class=\"token punctuation\">.</span><span class=\"token function\">render</span><span class=\"token punctuation\">(</span><span class=\"token tag\"><span class=\"token tag\"><span class=\"token punctuation\">&lt;</span><span class=\"token class-name\">App</span></span> <span class=\"token punctuation\">/></span></span><span class=\"token punctuation\">,</span> mountNode<span class=\"token punctuation\">)</span><span class=\"token punctuation\">;</span>\n</code></pre></div><style type=\"text/css\">\n.container.nested {\n    margin-bottom: 50px;\n}\n</style><div class=\"highlight\"><pre class=\"language-css\"><code class=\"language-css\">\n<span class=\"token selector\">.container.nested</span> <span class=\"token punctuation\">{</span>\n    <span class=\"token property\">margin-bottom</span><span class=\"token punctuation\">:</span> 50px<span class=\"token punctuation\">;</span>\n<span class=\"token punctuation\">}</span>\n</code></pre></div>"}