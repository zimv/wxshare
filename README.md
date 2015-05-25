#js微信封装

##使用帮助
var wxshare = require('wxshare.js');

###如果分享的内容都一致(all the same)
	wxshare.link = '';
    wxshare.desc = '';
    wxshare.imgUrl = '';
    wxshare.type = '';
    wxshare.dataUrl = '';
    wxshare.start();

###如果有不一致,针对不一致的地方进行修改(some different)
	
	wxshare.link = '';
    wxshare.title = '';
    wxshare.desc = '';
    wxshare.imgUrl = '';

    wxshare.setData();//必须加上
    wxshare.TimeLineData.title = ''; 
    wxshare.QQData.desc = '';
    wxshare.start();

###重点说明: setData();

如果全部的分享内容都一样，直接执行start(), 判断data参数空为true，会执行setData()，
为四个分享赋值:QQData data TimeLineData WeiboData, 而后初始化

如果有不一致，首次赋值后，直接调用setData(),为四个参数赋值，之后再根据需求修改不同的对应参数，最后start()初始化。
        