# Alimobstyle

- order: 1

---

<script type="text/template" id="alice-module">
    <div class="alice-module">
        <div class="alice-module-head">
            <h2 class="alice-module-title">
                <a href="#"></a>
            </h2>
            <span class="alice-module-family"></span>            
            <span class="alice-module-version"></span>
            <p class="alice-module-description"></p>
        </div>
        <img class="alice-loading" src="data:image/gif;base64,R0lGODlhEAALAPQAAP///z2LqeLt8dvp7u7090GNqz2LqV+fuJ/F1IW2ycrf51aatHWswaXJ14i4ys3h6FmctUCMqniuw+vz9eHs8fb5+meku+Tu8vT4+cfd5bbT3tbm7PH2+AAAAAAAAAAAACH/C05FVFNDQVBFMi4wAwEAAAAh/hpDcmVhdGVkIHdpdGggYWpheGxvYWQuaW5mbwAh+QQJCwAAACwAAAAAEAALAAAFLSAgjmRpnqSgCuLKAq5AEIM4zDVw03ve27ifDgfkEYe04kDIDC5zrtYKRa2WQgAh+QQJCwAAACwAAAAAEAALAAAFJGBhGAVgnqhpHIeRvsDawqns0qeN5+y967tYLyicBYE7EYkYAgAh+QQJCwAAACwAAAAAEAALAAAFNiAgjothLOOIJAkiGgxjpGKiKMkbz7SN6zIawJcDwIK9W/HISxGBzdHTuBNOmcJVCyoUlk7CEAAh+QQJCwAAACwAAAAAEAALAAAFNSAgjqQIRRFUAo3jNGIkSdHqPI8Tz3V55zuaDacDyIQ+YrBH+hWPzJFzOQQaeavWi7oqnVIhACH5BAkLAAAALAAAAAAQAAsAAAUyICCOZGme1rJY5kRRk7hI0mJSVUXJtF3iOl7tltsBZsNfUegjAY3I5sgFY55KqdX1GgIAIfkECQsAAAAsAAAAABAACwAABTcgII5kaZ4kcV2EqLJipmnZhWGXaOOitm2aXQ4g7P2Ct2ER4AMul00kj5g0Al8tADY2y6C+4FIIACH5BAkLAAAALAAAAAAQAAsAAAUvICCOZGme5ERRk6iy7qpyHCVStA3gNa/7txxwlwv2isSacYUc+l4tADQGQ1mvpBAAIfkECQsAAAAsAAAAABAACwAABS8gII5kaZ7kRFGTqLLuqnIcJVK0DeA1r/u3HHCXC/aKxJpxhRz6Xi0ANAZDWa+kEAA7AAAAAAAAAAAA">
    </div>
</script>

<script type="text/template" id="alice-module-demo">
    <div class="alice-module-demo">
        <h3 class="alice-module-subtitle"></h3>
        <a class="alice-module-sourcecode" href="javascript:;">查看源码</a>
        <div class="alice-module-dom"></div>
        <pre class="alice-module-code prettyprint"></pre>
    </div>
</script>

<style>
.alice-module {
    border-bottom: 1px solid #eee;    
    padding: 0;
    margin-top: 20px;
    margin-bottom: 50px;
    font:12px/1.5 tahoma,arial,Hiragino Sans GB,\5b8b\4f53;
}
.alice-module-head {
    overflow: hidden;
}
.alice-module-title {
    margin: 0;
    font-size: 28px;
    font-family: Trebuchet MS;
    display: inline;
}
.alice-module-title a {
    color: #7CAE23;
    cursor: pointer;
    padding-top: 70px;
}
.alice-module-link {
    font-size: 14px;
}
.alice-module-family,
.alice-module-version {
    font-size: 12px;
    font-weight: normal;
    margin-left: 0.5em;
    color: #888;
    font-family: Menlo,Monaco,"Courier New",monospace;
}
.alice-module-description {
    font-size: 14px;
    color: #888;
    margin: 10px 0 20px;
}
.alice-module-demo {
    border: 1px solid #eee;
    border-bottom: none;
    padding: 20px 130px 20px 20px;
    position: relative;
    zoom: 1;
}
.alice-module-demo:hover {
    background: #fdfdfd;
}
.alice-module-code {
    display: none;
}
h3.alice-module-subtitle {
    position: absolute;
    top: 0;
    right: 0;
    border-radius: 3px;
    margin: 0;
    color: #777;
    font-size: 12px;
    background: #F8F8F8;
    border-bottom: 1px solid #ddd;
    border-left: 1px solid #ddd;
    display: block;
    font-size: 12px;
    width: 100px;
    padding: 5px 10px;
    opacity: 0.8;
}
.alice-module-sourcecode {
    position: absolute;
    right: 125px;
    top: 0;
    font-size: 12px;
    padding: 5px 10px;
    background: #EFFFE4;
    border-radius: 3px;    
    display: none;
    z-index: 99;
    opacity: 0.8;   
}
a {
    color: #08c;
}
.alice-loading {
    margin-bottom: 20px;
}

.ali-button{
    margin: 2px 0;
}
.demo {
    padding: 1rem;
    color: #fff;
    background-color: #6C97C2;
}
.ali-loading{
    position: static;
    margin: 0;
}
.ali-flexbox-vertical .ali-flexbox-item{
    margin: 2px 0;
    background: #6C97C2;
}
</style>

<div class="alice-modules"></div>

<script>
window.addEventListener('load', function () {
    var interval = 500, begin = Date.now(), img = new Image(), timer = setTimeout(handler, interval);
    window.removeEventListener('load', arguments.callee);
    img.addEventListener('load', handler, false);
    img.src = 'https://i.alipayobjects.com/e/201305/Q9jNoeIir.gif?t=' + begin;

    function handler() {
        clearTimeout(timer);
        img.removeEventListener('load', handler);
        //响应在500ms以内算高速网络 高清（HD）标清（SD）
        document.body.className = (document.body.className + (Date.now() - begin < interval ? ' ali-hd' : ' ali-sd')).trim();
    }
}, false);

seajs.use(['$', 'gallery/underscore/1.4.4/underscore'], function($, _) {
    $('.alice-modules').on('mouseenter', '.alice-module-demo', function() {
        $(this).find('.alice-module-sourcecode').fadeIn(200);
    }).on('mouseleave', '.alice-module-demo', function() {
        $(this).find('.alice-module-sourcecode').fadeOut(200);
    });

    $('.alice-modules').on('click', '.alice-module-sourcecode', function() {
        var code = $(this).parent().find('.alice-module-code');
        if (code.is(':hidden')) {
            code.animate({
                opacity: 1,
                height: 'toggle'
            }, 300);
        } else {
            code.animate({
                opacity: 0,
                height: 'toggle'
            }, 300);
        }
    });

    $.getJSON('package.json', function(data) {
        var alias;
        if (data.spm && data.spm.alias) {
            alias = data.spm.alias;
        } else {
            alias = data.dependencies;
        }
        var deps = _.pairs(alias);
        _.each(deps, function(dep) {
            var reg = /(.*)\/(.*)\/(.*)\/(.*)\.css/i;
            var match = dep[1].match(reg);

            // 解析 name 和 family
            var family = match[1];
            var name = match[2];
            var version = match[3];

            // 得到子模块的文档地址
            var ajaxUrl = '';
            if (location.href.indexOf('alipay.im') > 0) {
                ajaxUrl = 'http://arale.alipay.im/' + family + '/' + name + '/';
            } else {
                ajaxUrl = '/' + name;
            }

            // 生成模块的小标题
            var moduleNode = $($('#alice-module').html());
            moduleNode.find('.alice-module-title a')
                .attr('href', ajaxUrl)
                .attr('id', 'modules-' + family + '-' + name)
                .html(name);
            moduleNode.find('.alice-module-family').html(family);
            moduleNode.find('.alice-module-version').html(version);
            moduleNode.appendTo('.alice-modules');
            var list = substractTitle(moduleNode.find('h2'));

            $.ajax({
                url: ajaxUrl,
                dataType: 'html',
                success: function(data) {
                    data = $(data);
                    moduleNode.find('.alice-module-description')
                        .html(data.find('.entry-content > p:first-child').html());

                    data.find('.nico-insert-code').each(function(index, item) {
                        var demoNode = $($('#alice-module-demo').html());
                        item = $(item);
                        var subtitle = item.prev().html();
                        if (item.prev()[0].tagName !== 'H3' || !subtitle) {
                            subtitle = '默认';
                        }
                        
                        demoNode.find('.alice-module-subtitle').html(subtitle);
                        demoNode.find('.alice-module-dom').html(item.html());

                        // 直接使用目标页面生成的高亮代码，不再动态渲染
                        var codeHtml = item.next('.highlight').find('pre').html();
                        demoNode.find('.alice-module-code').html(codeHtml); 

                        moduleNode.find('.alice-loading').remove();
                        demoNode.appendTo(moduleNode);
                    });

                    // 中文关键词，一般放在 keywords 数组的第一个
                    // 在这里写到左边索引栏中
                    moduleNode.find('.alice-module-version')
                    var keywords = data.find('#sidebar-wrapper .keywords').html();
                    if (keywords) {
                        list.find('i').html(keywords);
                    }
                }
            });
        });
        seajs.use('./static/side', function(side) {
            side.init();
        });
    });

    function substractTitle(item) {
        $('.nav-loading').remove();
        item = item.find('a');
        var list = $($('#list-template').html());
        list.find('a').html(item.html() + list.find('a').html());
        list.find('a').attr('href', '#' + item.attr('id'));
        list.appendTo('.nav-area ul');
        return list;
    }
});
</script>
