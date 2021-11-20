
# 链接格式化
```javascript
function makeLink(str) {
    if (!str || Object.prototype.toString.call(str) != '[object String]') {
        return '';
    }
    var reg = /(http:\/\/|https:\/\/|www\.)((\w|=|\?|\.|\/|&|%|-|:|#|×)+)/g;
    return str.replace(reg, function() {
        console.log(arguments);
        var prefix = arguments[1];
        if (prefix.toLowerCase() == 'www.') {
            prefix = 'http://';
        } else {
            prefix = '';
        }
        return '<a target="_blank" href="' + (prefix + arguments[0]).trim() + '">' + (arguments[0]).trim() + '</a>';
    });
}
```

