# gitview
gitview image viewer
```


var url="https://pinkromeo18.github.io/gitview/img/view.html?aaa=vvvv";

function githubInfo(d){
  var ary=d.split('.github.io/');
  var owner = ary[0].split('/').slice(-1).join('')
  var repo = ary[1].split('/').slice(0,-1).join('/')
  var path =''
  var p = '?per_page=100'
  if(/\//.test(repo)){
    var wk=repo.split('/');
    repo = wk[0];
    path = wk[1];
  }
  const e ="https://api.github.com";
  var url = `${e}/repos/${owner}/${repo}/contents/${path}${p}`;
  return {owner,repo,path,url}
}

var ret = githubInfo(url)
fn.q('pre').textContent = JSON.stringify(ret,null,2);

```

```
https://pinkromeo18.github.io/gitview/img/view.html
```

```
https://pinkromeo18.github.io/gitview/
```
```
<html><script src="gitview.js"></script></html>
```
