title: 总结了下json的遍历
date: 2014-07-15 14:54:14
tags: js
category: javascript
---
```javascript
 /*js的遍历json*/
    window.onload=function(){
        var dzTab = {
            "zd": [
                {
                    "id": "1",
                    "ip": "192.168.2.10",
                    "name":"yyyyyy",
                    "mac": "00-12-34-89-99-01"
                },
                {
                    "id": "2",
                    "ip": "192.168.2.11",
                    "name":"ssssss",
                    "mac": "00-12-34-89-99-02"
                }]
        }
        var data=dzTab.zd;
        /*传统for循环*/
        /*for(var i=0;i<data.length;i++){

         alert("id="+data[i].id+",ip="+data[i].ip+",name="+data[i].name+",mac="+data[i].mac)
         }*/
        /*for in循环*/
        /*for(i in data){

         alert("id="+data[i].id+",ip="+data[i].ip+",name="+data[i].name+",mac="+data[i].mac)
         }*/

        /*jquery遍历	*/
        $.each(data, function(i,items){

            alert("id="+items.id+",ip="+items.ip+",name="+items.name+",mac="+items.mac)

        })
    }
```