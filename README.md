<div class="container">
            <h2 id="介绍">介绍</h2>
            <p>
                proto.js 是一个js增强库，提供许多实用的链式方法，使数据操作更加方便。
                同时还提供了许多 polyfill ，如 array.forEach, array.map 等。
            </p>
            <div>
                <h3>
                    日期运算与格式化：
                </h3>
                <pre>                    <code>
Date.<span class="js-function">today</span>().<span class="js-function">addDate</span>(<span class="js-operator">-</span><span class="js-number">3</span>).<span class="js-function">format</span>(<span class="js-string">'yyyy-MM-dd'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"2017-11-26"</span></code></p>
                <h3>
                    数组CRUD，增insert, 查select, 改update, 删delete ：
                </h3>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>}, {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>}, {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf'</span>}
]

list.<span class="js-function">select</span>({name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">3</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  }
]<span class="js-"></span></code></p>
                <h3>
                    集合运算，并集union, 交集same, 异或集xor, 差集difference：
                </h3>
                <pre>                    <code>
[<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>].<span class="js-function">same</span>([<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>])
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">3</span>,
  <span class="js-number">4</span>
]<span class="js-"></span></code></p>
                <h3>
                    方便的分页 page, pageCount, limit, top：
                </h3>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>,<span class="js-number">11</span>,<span class="js-number">12</span>]

list.<span class="js-function">page</span>(<span class="js-number">2</span>, <span class="js-number">10</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">11</span>,
  <span class="js-number">12</span>
]<span class="js-"></span></code></p>
                <h3>
                    避免js小数运算精度不准的方法 add ['+'], subtrack ['-'], multiply ['*'], divide ['/']：
                </h3>
                <pre>                    <code>
<span class="js-number">0.1</span><span class="js-operator">+</span><span class="js-number">0.2</span>; <span class="js-comment">//=&gt; 0.30000000000000004</span>

(<span class="js-number">0.1</span>)[<span class="js-string">'+'</span>](<span class="js-number">0.2</span>) <span class="js-comment">//=&gt; 0.3</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.3</span></code></p>
                <h3>
                    链式类型转换 *.to*：
                </h3>
                <pre>                    <code>
<span class="js-string">'3.14159'</span>.<span class="js-function">toNumber</span>().<span class="js-function">toFixed</span>(<span class="js-number">2</span>).<span class="js-function">toNumber</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">3.14</span></code></p>
                <h3>
                    避免IOS系统中 <code><span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'yyyy-MM-dd HH:mm:ss'</span>)<span class="js-"></span></code> 返回 <code>Invalid Date<span class="js-"></span></code> 的方法（当有Hms时，IOS中不能用'-'，只能用'/'）：
                </h3>
                <pre>                    <code>
Date.<span class="js-function">toDate</span>(<span class="js-string">'2017-10-1 00:00:00'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-01 00:00:00"</span></code></p>
                <pre>                    <code>
<span class="js-string">'2017-10-1 00:00:00'</span>.<span class="js-function">toDate</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-01 00:00:00"</span></code></p>
                <h3>
                    还有许多实用的方法。
                </h3>
            </div>
            <div>
                <h2 id="Object.getType">Object.getType</h2>
                <p>
                    可返回以下类型：
                    <code><span class="js-string">"undefined"</span></code>
                    <code><span class="js-string">"null"</span></code>
                    <code><span class="js-string">"string"</span></code>
                    <code><span class="js-string">"number"</span></code>
                    <code><span class="js-string">"boolean"</span></code>
                    <code><span class="js-string">"object"</span></code>
                    <code><span class="js-string">"array"</span></code>
                    <code><span class="js-string">"function"</span></code>
                    <code><span class="js-string">"date"</span></code>
                    <code><span class="js-string">"regexp"</span></code>
                </p>
                <pre>                    <code>
Object.<span class="js-function">getType</span>(<span class="js-reg">/reg/</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"regexp"</span></code></p>
                <h2 id="Object.isType">Object.isType</h2>
                <pre>                    <code>
Object.<span class="js-function">isType</span>(<span class="js-string">'array'</span>, [])
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <h2 id="Object.is[Type]">Object.is[Type]</h2>
                <pre>                    <code>
Object.<span class="js-function">isArray</span>([])
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <h2 id="Object.assign">Object.assign</h2>
                <pre>                    <code>
Object.<span class="js-function">assign</span>({a:<span class="js-number">1</span>, b:<span class="js-number">1</span>}, {b:<span class="js-number">2</span>, c:<span class="js-number">3</span>})
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"a"</span>: <span class="js-number">1</span>,
  <span class="js-string">"b"</span>: <span class="js-number">2</span>,
  <span class="js-string">"c"</span>: <span class="js-number">3</span>
}<span class="js-"></span></code></p>
                <h2 id="Object.keys">Object.keys</h2>
                <pre>                    <code>
Object.<span class="js-function">keys</span>({id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-string">"id"</span>,
  <span class="js-string">"name"</span>
]<span class="js-"></span></code></p>
                <h2 id="Object.values">Object.values</h2>
                <pre>                    <code>
Object.<span class="js-function">values</span>({id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-string">"wsf"</span>
]<span class="js-"></span></code></p>
                <h2 id="Object.isEmpty">Object.isEmpty</h2>
                <p>
                    <code>[]<span class="js-"></span></code>
                    <code>{}<span class="js-"></span></code>
                    <code>null<span class="js-"></span></code>
                    <code>undefined<span class="js-"></span></code>
                    <code><span class="js-keyword">false</span></code>
                    <code><span class="js-string">''</span></code>
                    <code><span class="js-number">0</span></code>
                    返回
                    <code><span class="js-keyword">true</span></code>
                </p>
                <pre>                    <code>
<span class="js-type">var</span> response <span class="js-operator">=</span> {}
Object.<span class="js-function">isEmpty</span>(response.data)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <h2 id="Array.range">Array.range</h2>
                <pre>                    <code>
Array.<span class="js-function">range</span>(<span class="js-number">3</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">0</span>,
  <span class="js-number">1</span>,
  <span class="js-number">2</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
Array.<span class="js-function">range</span>(<span class="js-number">3</span>, <span class="js-number">10</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
Array.<span class="js-function">range</span>(<span class="js-number">3</span>, <span class="js-number">10</span>, <span class="js-number">3</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">3</span>,
  <span class="js-number">6</span>,
  <span class="js-number">9</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.each">Array.prototype.each</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>]

list.<span class="js-function">each</span>(<span class="js-function">function</span>(item, i, list){
    list[i] <span class="js-operator">=</span> i<span class="js-operator">+</span><span class="js-string">':'</span><span class="js-operator">+</span>item
})
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-string">"0:1"</span>,
  <span class="js-string">"1:2"</span>,
  <span class="js-string">"2:3"</span>,
  <span class="js-string">"3:4"</span>,
  <span class="js-string">"4:5"</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.select">Array.prototype.select</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf'</span>},
]

list.<span class="js-function">select</span>({name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">3</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.get">Array.prototype.get</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">get</span>({id:<span class="js-number">1</span>})
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"id"</span>: <span class="js-number">1</span>,
  <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
}<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">get</span>({id:<span class="js-number">1</span>}).name
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"wsf"</span></code></p>
                <pre>                    <code>
list.<span class="js-function">get</span>({id:<span class="js-number">4</span>})
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">false</span></code></p>
                <pre>                    <code>
list.<span class="js-function">get</span>({id:<span class="js-number">4</span>}).name
                    <span class="js-"></span></code>
                </pre><p><code>undefined<span class="js-"></span></code></p>
                <h2 id="Array.prototype.update">Array.prototype.update</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf'</span>},
]

list.<span class="js-function">update</span>({id:<span class="js-number">2</span>}, {name:<span class="js-string">'wsf2'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">update</span>({name:<span class="js-string">'all'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"all"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"all"</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">select</span>({id:<span class="js-number">1</span>}).<span class="js-function">update</span>({name:<span class="js-string">'new name'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"new name"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.delete">Array.prototype.delete</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf'</span>},
]

list.<span class="js-function">delete</span>({name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf'</span>},
]

list.<span class="js-function">delete</span>([{id:<span class="js-number">2</span>}, {id:<span class="js-number">3</span>}])
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">delete</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[]<span class="js-"></span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    <span class="js-number">0</span>, <span class="js-number">1</span>, <span class="js-number">2</span>, NaN,
    <span class="js-keyword">true</span>, <span class="js-keyword">false</span>,
    undefined, null,
    <span class="js-string">''</span>, <span class="js-string">'0'</span>, <span class="js-string">'1'</span>, <span class="js-string">'NaN'</span>, <span class="js-string">'true'</span>, <span class="js-string">'null'</span>, <span class="js-string">'undefined'</span>, <span class="js-string">'string'</span>, [],
    [<span class="js-number">0</span>, <span class="js-number">1</span>, <span class="js-number">2</span>],
    {},
    { id: <span class="js-number">1</span>, name: <span class="js-string">'wsf'</span> },
    { id: <span class="js-number">2</span>, name: <span class="js-string">'wsf2'</span> },
];

list.<span class="js-function">delete</span>(<span class="js-number">0</span>, NaN, <span class="js-keyword">false</span>, undefined, null, <span class="js-string">''</span>, [], {})
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-keyword">true</span>,
  <span class="js-string">"1"</span>,
  <span class="js-string">"true"</span>,
  <span class="js-string">"string"</span>,
  [
    <span class="js-number">0</span>,
    <span class="js-number">1</span>,
    <span class="js-number">2</span>
  ],
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.insert">Array.prototype.insert</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>]

list.<span class="js-function">insert</span>(<span class="js-number">6</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">insert</span>(<span class="js-number">99</span>, <span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">99</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">insert</span>([<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>])
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">99</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.orderBy">Array.prototype.orderBy</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">2</span>},
    {id:<span class="js-string">'11'</span>},
    {id:<span class="js-number">1</span>},
]

list.<span class="js-function">orderBy</span>(<span class="js-string">'id'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-string">"11"</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">orderBy</span>(<span class="js-string">'id'</span>, <span class="js-string">'desc'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-string">"11"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>
  }
]<span class="js-"></span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">3</span>,<span class="js-number">2</span>,<span class="js-number">5</span>,<span class="js-number">4</span>]

list.<span class="js-function">orderBy</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">orderBy</span>(null, <span class="js-string">'desc'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">5</span>,
  <span class="js-number">4</span>,
  <span class="js-number">3</span>,
  <span class="js-number">2</span>,
  <span class="js-number">1</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.groupBy">Array.prototype.groupBy</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">2</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">3</span>, country:<span class="js-string">'美国'</span>},
]

list.<span class="js-function">groupBy</span>(<span class="js-string">'country'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"中国"</span>: [
    {
      <span class="js-string">"id"</span>: <span class="js-number">1</span>,
      <span class="js-string">"country"</span>: <span class="js-string">"中国"</span>
    },
    {
      <span class="js-string">"id"</span>: <span class="js-number">2</span>,
      <span class="js-string">"country"</span>: <span class="js-string">"中国"</span>
    }
  ],
  <span class="js-string">"美国"</span>: [
    {
      <span class="js-string">"id"</span>: <span class="js-number">3</span>,
      <span class="js-string">"country"</span>: <span class="js-string">"美国"</span>
    }
  ]
}<span class="js-"></span></code></p>
                <h2 id="Array.prototype.groupCount">Array.prototype.groupCount</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">2</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">3</span>, country:<span class="js-string">'美国'</span>},
]

list.<span class="js-function">groupCount</span>(<span class="js-string">'country'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2</span></code></p>
                <h2 id="Array.prototype.fields">Array.prototype.fields</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">2</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">3</span>, country:<span class="js-string">'美国'</span>},
]

list.<span class="js-function">fields</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-string">"id"</span>,
  <span class="js-string">"country"</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.column">Array.prototype.column</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">2</span>, country:<span class="js-string">'中国'</span>},
    {id:<span class="js-number">3</span>, country:<span class="js-string">'美国'</span>},
]

list.<span class="js-function">column</span>(<span class="js-string">'id'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.limit">Array.prototype.limit</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">limit</span>(<span class="js-number">1</span>,<span class="js-number">3</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.top">Array.prototype.top</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">top</span>(<span class="js-number">5</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.page">Array.prototype.page</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> Array.<span class="js-function">range</span>(<span class="js-number">1</span>, <span class="js-number">101</span>)

list.<span class="js-function">page</span>(<span class="js-number">2</span>, <span class="js-number">20</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">21</span>,
  <span class="js-number">22</span>,
  <span class="js-number">23</span>,
  <span class="js-number">24</span>,
  <span class="js-number">25</span>,
  <span class="js-number">26</span>,
  <span class="js-number">27</span>,
  <span class="js-number">28</span>,
  <span class="js-number">29</span>,
  <span class="js-number">30</span>,
  <span class="js-number">31</span>,
  <span class="js-number">32</span>,
  <span class="js-number">33</span>,
  <span class="js-number">34</span>,
  <span class="js-number">35</span>,
  <span class="js-number">36</span>,
  <span class="js-number">37</span>,
  <span class="js-number">38</span>,
  <span class="js-number">39</span>,
  <span class="js-number">40</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.pageCount">Array.prototype.pageCount</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> Array.<span class="js-function">range</span>(<span class="js-number">1</span>, <span class="js-number">101</span>)

list.<span class="js-function">pageCount</span>(<span class="js-number">20</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">5</span></code></p>
                <h2 id="Array.prototype.nth">Array.prototype.nth</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">nth</span>(<span class="js-number">0</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">1</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">nth</span>(<span class="js-operator">-</span><span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">10</span></code></p>
                <h2 id="Array.prototype.first">Array.prototype.first</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">first</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">1</span></code></p>
                <h2 id="Array.prototype.last">Array.prototype.last</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">last</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">10</span></code></p>
                <h2 id="Array.prototype.uniq">Array.prototype.uniq</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    <span class="js-number">1</span>, <span class="js-number">2</span>, <span class="js-number">3</span>,
    <span class="js-number">1</span>, <span class="js-number">2</span>, <span class="js-number">4</span>,
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
]

list.<span class="js-function">uniq</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.has">Array.prototype.has</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    <span class="js-number">1</span>, <span class="js-number">2</span>, <span class="js-number">3</span>,
    <span class="js-number">1</span>, <span class="js-number">2</span>, <span class="js-number">4</span>,
]

list.<span class="js-function">has</span>(<span class="js-number">2</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">has</span>({id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>})
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <pre>                    <code>
list.<span class="js-function">has</span>({id:<span class="js-number">1</span>})
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <pre>                    <code>
list.<span class="js-function">has</span>({id:<span class="js-number">1</span>, name:<span class="js-string">'xxx'</span>})
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">false</span></code></p>
                <pre>                    <code>
list.<span class="js-function">has</span>([{id:<span class="js-number">1</span>}, {id:<span class="js-number">2</span>}])
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <pre>                    <code>
list.<span class="js-function">has</span>([{id:<span class="js-number">2</span>}, {id:<span class="js-number">4</span>}])
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">false</span></code></p>
                <h2 id="Array.prototype.add">Array.prototype.add</h2>
                <pre>                    <code>
[<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>].<span class="js-function">add</span>(<span class="js-number">4</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.eq">Array.prototype.eq</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [{id:<span class="js-number">1</span>},{id:<span class="js-number">2</span>}]
<span class="js-type">var</span> checkedList <span class="js-operator">=</span> [{id:<span class="js-number">1</span>},{id:<span class="js-number">2</span>}]

isAllChecked <span class="js-operator">=</span> list.<span class="js-function">eq</span>(checkedList)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-keyword">true</span></code></p>
                <h2 id="Array.prototype.ensure">Array.prototype.ensure</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    <span class="js-number">1</span>, <span class="js-number">2</span>, <span class="js-number">3</span>,
]

list.<span class="js-function">ensure</span>(<span class="js-number">4</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">ensure</span>([<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>, <span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>])
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">ensure</span>([
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf3'</span>},
])
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">3</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf3"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.same">Array.prototype.same</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">same</span>([
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf3'</span>},
])
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.xor">Array.prototype.xor</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">xor</span>([
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">3</span>, name:<span class="js-string">'wsf3'</span>},
])
                    <span class="js-"></span></code>
                </pre><p><code>[
  {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  },
  {
    <span class="js-string">"id"</span>: <span class="js-number">3</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf3"</span>
  }
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.removeIndex">Array.prototype.removeIndex</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">removeIndex</span>(<span class="js-number">2</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>,
  <span class="js-number">10</span>
]<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">removeIndex</span>(<span class="js-operator">-</span><span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.empty">Array.prototype.empty</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">empty</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.min">Array.prototype.min</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">min</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">1</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, age:<span class="js-number">18</span>},
    {id:<span class="js-number">2</span>, age:<span class="js-number">28</span>},
]

list.<span class="js-function">min</span>(<span class="js-string">'age'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"id"</span>: <span class="js-number">1</span>,
  <span class="js-string">"age"</span>: <span class="js-number">18</span>
}<span class="js-"></span></code></p>
                <h2 id="Array.prototype.max">Array.prototype.max</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">max</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">10</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, age:<span class="js-number">18</span>},
    {id:<span class="js-number">2</span>, age:<span class="js-number">28</span>},
]

list.<span class="js-function">max</span>(<span class="js-string">'age'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"id"</span>: <span class="js-number">2</span>,
  <span class="js-string">"age"</span>: <span class="js-number">28</span>
}<span class="js-"></span></code></p>
                <h2 id="Array.prototype.max">Array.prototype.sum</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">sum</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">55</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, age:<span class="js-number">18</span>},
    {id:<span class="js-number">2</span>, age:<span class="js-number">28</span>},
]

list.<span class="js-function">sum</span>(<span class="js-string">'age'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">46</span></code></p>
                <h2 id="Array.prototype.avg">Array.prototype.avg</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">avg</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">5.5</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, age:<span class="js-number">18</span>},
    {id:<span class="js-number">2</span>, age:<span class="js-number">28</span>},
]

list.<span class="js-function">avg</span>(<span class="js-string">'age'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">23</span></code></p>
                <h2 id="Array.prototype.copy">Array.prototype.copy</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">copy</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">1</span>,
  <span class="js-number">2</span>,
  <span class="js-number">3</span>,
  <span class="js-number">4</span>,
  <span class="js-number">5</span>,
  <span class="js-number">6</span>,
  <span class="js-number">7</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>,
  <span class="js-number">10</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.shuffle">Array.prototype.shuffle</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [<span class="js-number">1</span>,<span class="js-number">2</span>,<span class="js-number">3</span>,<span class="js-number">4</span>,<span class="js-number">5</span>,<span class="js-number">6</span>,<span class="js-number">7</span>,<span class="js-number">8</span>,<span class="js-number">9</span>,<span class="js-number">10</span>]

list.<span class="js-function">shuffle</span>()
                    <span class="js-"></span></code>
                </pre><p><code>[
  <span class="js-number">3</span>,
  <span class="js-number">2</span>,
  <span class="js-number">7</span>,
  <span class="js-number">1</span>,
  <span class="js-number">4</span>,
  <span class="js-number">6</span>,
  <span class="js-number">5</span>,
  <span class="js-number">8</span>,
  <span class="js-number">9</span>,
  <span class="js-number">10</span>
]<span class="js-"></span></code></p>
                <h2 id="Array.prototype.random">Array.prototype.random</h2>
                <pre>                    <code>
[<span class="js-string">'一等奖'</span>, <span class="js-string">'二等奖'</span>, <span class="js-string">'三等奖'</span>].<span class="js-function">random</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"一等奖"</span></code></p>
                <h2 id="Array.prototype.toMap">Array.prototype.toMap</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">toMap</span>(<span class="js-string">'name'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"wsf"</span>: {
    <span class="js-string">"id"</span>: <span class="js-number">1</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
  },
  <span class="js-string">"wsf2"</span>: {
    <span class="js-string">"id"</span>: <span class="js-number">2</span>,
    <span class="js-string">"name"</span>: <span class="js-string">"wsf2"</span>
  }
}<span class="js-"></span></code></p>
                <pre>                    <code>
list.<span class="js-function">toMap</span>(<span class="js-string">'name'</span>)[<span class="js-string">'wsf'</span>]
                    <span class="js-"></span></code>
                </pre><p><code>{
  <span class="js-string">"id"</span>: <span class="js-number">1</span>,
  <span class="js-string">"name"</span>: <span class="js-string">"wsf"</span>
}<span class="js-"></span></code></p>
                <h2 id="Array.prototype.key">Array.prototype.key</h2>
                <pre>                    <code>
<span class="js-type">var</span> list <span class="js-operator">=</span> [
    {id:<span class="js-number">1</span>, name:<span class="js-string">'wsf'</span>},
    {id:<span class="js-number">2</span>, name:<span class="js-string">'wsf2'</span>},
]

list.<span class="js-function">select</span>({id:<span class="js-number">1</span>}).<span class="js-function">key</span>(<span class="js-string">'name'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"wsf"</span></code></p>
                <pre>                    <code>
list.<span class="js-function">select</span>({id:<span class="js-number">4</span>}).<span class="js-function">key</span>(<span class="js-string">'name'</span>)
                    <span class="js-"></span></code>
                </pre><p><code>undefined<span class="js-"></span></code></p>
                <h2 id="Date.today">Date.today</h2>
                <pre>                    <code>
Date.<span class="js-function">today</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-11-29 00:00:00"</span></code></p>
                <h2 id="Date.yesterday">Date.yesterday</h2>
                <pre>                    <code>
Date.<span class="js-function">yesterday</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-11-28 00:00:00"</span></code></p>
                <h2 id="Date.tomorrow">Date.tomorrow</h2>
                <pre>                    <code>
Date.<span class="js-function">tomorrow</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-11-30 00:00:00"</span></code></p>
                <h2 id="Date.prototype.format">Date.prototype.format</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>().<span class="js-function">format</span>(<span class="js-string">'yyyy-MM-dd HH:mm:ss .SSS'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"2017-11-29 19:51:06 .864"</span></code></p>
                <h2 id="Date.prototype.diff">Date.prototype.diff</h2>
                <pre>                    <code>
<span class="js-type">var</span> nextYear <span class="js-operator">=</span> <span class="js-keyword">new</span> <span class="js-function">Date</span>().<span class="js-function">getFullYear</span>()<span class="js-operator">+</span><span class="js-number">1</span>
<span class="js-type">var</span> date <span class="js-operator">=</span> <span class="js-keyword">new</span> <span class="js-function">Date</span>(nextYear<span class="js-operator">+</span><span class="js-string">'/10/1'</span>)
<span class="js-type">var</span> now <span class="js-operator">=</span> <span class="js-keyword">new</span> Date

date.<span class="js-function">diff</span>(now, <span class="js-string">'d天H时'</span>) <span class="js-comment">// 现在离明年国庆还有多久</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"305天4时"</span></code></p>
                <pre>                    <code>
<span class="js-type">var</span> date1 <span class="js-operator">=</span> <span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/1'</span>)
<span class="js-type">var</span> date2 <span class="js-operator">=</span> <span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/21 11:22:33'</span>)

date2.<span class="js-function">diff</span>(date1, <span class="js-string">'d天H时m分'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"20天11时22分"</span></code></p>
                <pre>                    <code>
date2.<span class="js-function">diff</span>(date1, <span class="js-string">'d'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">20.473993055555557</span></code></p>
                <h2 id="Date.prototype.addFullYear">Date.prototype.addFullYear</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addFullYear</span>(<span class="js-operator">-</span><span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2016-10-10 00:00:00"</span></code></p>
                <h2 id="Date.prototype.addMonth">Date.prototype.addMonth</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addMonth</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-11-10 00:00:00"</span></code></p>
                <h2 id="Date.prototype.addDate">Date.prototype.addDate</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addDate</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-11 00:00:00"</span></code></p>
                <h2 id="Date.prototype.addHours">Date.prototype.addHours</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addHours</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 01:00:00"</span></code></p>
                <h2 id="Date.prototype.addMinutes">Date.prototype.addMinutes</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addMinutes</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 00:01:00"</span></code></p>
                <h2 id="Date.prototype.addSeconds">Date.prototype.addSeconds</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addSeconds</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 00:00:01"</span></code></p>
                <h2 id="Date.prototype.addMilliseconds">Date.prototype.addMilliseconds</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">addMilliseconds</span>(<span class="js-number">1</span>).<span class="js-function">format</span>(<span class="js-string">'yyyy-MM-dd HH:mm:ss.SSS'</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"2017-10-10 00:00:00.001"</span></code></p>
                <h2 id="Date.prototype.fullyear">Date.prototype.fullyear</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">fullyear</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2017</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">fullyear</span>(<span class="js-number">2018</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2018-10-10 00:00:00"</span></code></p>
                <h2 id="Date.prototype.month">Date.prototype.month</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">month</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">9</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">month</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-02-10 00:00:00"</span></code></p>
                <h2 id="Date.prototype.date">Date.prototype.date</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">date</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">10</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">date</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-01 00:00:00"</span></code></p>
                <h2 id="Date.prototype.hours">Date.prototype.hours</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">hours</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">hours</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 01:00:00"</span></code></p>
                <h2 id="Date.prototype.minutes">Date.prototype.minutes</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">minutes</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">minutes</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 00:01:00"</span></code></p>
                <h2 id="Date.prototype.seconds">Date.prototype.seconds</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">seconds</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">seconds</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 00:00:01"</span></code></p>
                <h2 id="Date.prototype.milliseconds">Date.prototype.milliseconds</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">milliseconds</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">milliseconds</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 2017-10-10 00:00:00"</span></code></p>
                <h2 id="Date.prototype.time">Date.prototype.time</h2>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">time</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">1507564800000</span></code></p>
                <pre>                    <code>
<span class="js-keyword">new</span> <span class="js-function">Date</span>(<span class="js-string">'2017/10/10'</span>).<span class="js-function">time</span>(<span class="js-number">1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-string">"[Date] 1970-01-01 08:00:00"</span></code></p>
                <h2 id="Number.random">Number.random</h2>
                <pre>                    <code>
Number.<span class="js-function">random</span>(<span class="js-number">1</span>,<span class="js-number">5</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2</span></code></p>
                <pre>                    <code>
Number.<span class="js-function">random</span>(<span class="js-number">1</span>,<span class="js-number">5</span>, <span class="js-keyword">true</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2.1762744296938106</span></code></p>
                <h2 id="Number.prototype.add">Number.prototype.add</h2>
                <pre>                    <code>
<span class="js-number">0.1</span> <span class="js-operator">+</span> <span class="js-number">0.2</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.30000000000000004</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.1</span>).<span class="js-function">add</span>(<span class="js-number">0.2</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.3</span></code></p>
                <h2 id="Number.prototype.subtrack">Number.prototype.subtrack</h2>
                <pre>                    <code>
<span class="js-number">0.3</span> <span class="js-operator">-</span> <span class="js-number">0.1</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.19999999999999998</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.3</span>).<span class="js-function">subtrack</span>(<span class="js-number">0.1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.2</span></code></p>
                <h2 id="Number.prototype.multiply">Number.prototype.multiply</h2>
                <pre>                    <code>
<span class="js-number">0.1</span> <span class="js-operator">*</span> <span class="js-number">0.2</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.020000000000000004</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.1</span>).<span class="js-function">multiply</span>(<span class="js-number">0.2</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.02</span></code></p>
                <h2 id="Number.prototype.divide">Number.prototype.divide</h2>
                <pre>                    <code>
<span class="js-number">0.3</span> <span class="js-operator">/</span> <span class="js-number">0.1</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2.9999999999999996</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.3</span>).<span class="js-function">divide</span>(<span class="js-number">0.1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">3</span></code></p>
                <h2 id="Number.prototype['+']">Number.prototype['+']</h2>
                <pre>                    <code>
<span class="js-number">0.1</span> <span class="js-operator">+</span> <span class="js-number">0.2</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.30000000000000004</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.1</span>)[<span class="js-string">'+'</span>](<span class="js-number">0.2</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.3</span></code></p>
                <h2 id="Number.prototype['-']">Number.prototype['-']</h2>
                <pre>                    <code>
<span class="js-number">0.3</span> <span class="js-operator">-</span> <span class="js-number">0.1</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.19999999999999998</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.3</span>)[<span class="js-string">'-'</span>](<span class="js-number">0.1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.2</span></code></p>
                <h2 id="Number.prototype['*']">Number.prototype['*']</h2>
                <pre>                    <code>
<span class="js-number">0.1</span> <span class="js-operator">*</span> <span class="js-number">0.2</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.020000000000000004</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.1</span>)[<span class="js-string">'*'</span>](<span class="js-number">0.2</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">0.02</span></code></p>
                <h2 id="Number.prototype['/']">Number.prototype['/']</h2>
                <pre>                    <code>
<span class="js-number">0.3</span> <span class="js-operator">/</span> <span class="js-number">0.1</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">2.9999999999999996</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.3</span>)[<span class="js-string">'/'</span>](<span class="js-number">0.1</span>)
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">3</span></code></p>
                <h2 id="Number.prototype.fixed">Number.prototype.fixed</h2>
                <pre>                    <code>
<span class="js-number">0.5025</span> <span class="js-operator">*</span> <span class="js-number">100</span>
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">50.24999999999999</span></code></p>
                <pre>                    <code>
(<span class="js-number">0.5025</span><span class="js-operator">*</span><span class="js-number">100</span>).<span class="js-function">fixed</span>()
                    <span class="js-"></span></code>
                </pre><p><code><span class="js-number">50.25</span></code></p>
            </div>
        </div>
