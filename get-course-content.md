- Check for `subscriber-curriculum-items` request in developer toolbar
- Get the `results` response
- Use following methods

  Get simpler json
  ```
  function udemyLecturesToJson(results) {
  
      var finalResult = results.reduce((res, item) =>{
                      if(item._class =='chapter'){
                          res.push({title:item.title, lectures:[]})
                          return res;
                      }
                      var chapter = res[res.length-1];
                          chapter.lectures.push({title:`${item.object_index} - ${item.title}`})
                      return res;    
                  },[]);
  
      return finalResult;
  }
  ```

 Create mark down content
```
function udemyLecturesToMarkup(results) {
    var jsonResult = udemyLecturesToJson(results);
    
    var finalResult = jsonResult.reduce((res, item) =>{
                    res = res + `## ${item.title}`;
                    res = res + `\n`;
                    item.lectures.forEach(lecture=>{
                         res = res + `   - ${lecture.title}\n`
                    })
                    res = res + `\n`;
                    return res;
                },'');

    return finalResult;
}
```

Call method
```
udemyLecturesToMarkup (results)
```
  

