//随机验证码
function code(size){
		var arr=[];
		for(var i=48; i<=57; i++){
			arr.push(String.fromCharCode(i))
		}
		for(var i=97; i<=122; i++){
			arr.push(String.fromCharCode(i))
		}
		var arrcode=[];
		for(var i=0;i<size;i++){
			arrcode.push(arr[parseInt(Math.random()*arr.length)]);
		}
		return arrcode.join("").toUpperCase();
	}



//把数组中重复的元素去掉
function removeRepeat(str){
	var arr = str.split("");
	var gap = [];
	for(var i in arr){
		flag = true;
		for(var j in gap){
			if(arr[i] == gap[j]){
				flag = false;
				break;
			}
		}
		if(flag) gap.push(arr[i]);
	}
	return gap;
}

/**
	将一个日期对象转换成一个字符串
	参数：
		d 日期对象
		sep 转换字符串以后的分隔符
	例：date2String(new Date(2008,12,9), "/")
	结果： 返回字符串 "2008/12/09 00:00:00"
*/
function date2string(d, sep){
	sep = sep || "-";
	function toDouble(num){
		return num<10?"0"+num:num;
	}
	return d.getFullYear()+sep+ toDouble(d.getMonth()+1) + sep + toDouble(d.getDate()) + " " + toDouble(d.getHours()) + ":" + toDouble(d.getMinutes()) + ":" + toDouble(d.getSeconds());
}

/**
	根据指定的范围大小生成一个随机整数
	参数 min表示下限  max表示上限
	例： randomInt(5,18); 生成一个5-18的随机数，包含5和18
*/
function randomInt(min, max){
	return Math.round(Math.random()*(max-min)) + min;
}


/**
	将一个日期字符串转成一个日期对象
	参数:
		datestr 日期字符串
		sep 日期字符串使用的分隔符
	例： string2Date("1989.5.26",".");
	结果： 返回一个日期对象
*/
function string2date(datestr,sep) {
	//2016-08-09 || 2016/09/12
	var str = datestr.replace(new RegExp(sep,"g"),"-");
	return new Date(str);
}

//父元素下所以节点找元素节点
function findElementNode(elet){
	//console.log(elet);
	var nodeElet = elet.childNodes;
	var arr = [];
	for(var i=0; i<nodeElet.length; i++){
		if(nodeElet[i].nodeType == 1){
			arr.push(nodeElet[i])
		}
	}
	return arr;
}

//获取ie的class
function getclassname4ie(classname){
	var allname = document.getElementsByTagName("*");
	//console.log(allname.join(" "))
	var arr = [];
	for(var i=0; i<allname.length; i++){
		var brr = allname[i].className.split(" ");
		for(var j in brr){
			if(brr[j] == classname){
				arr.push(allname[i])
			}			
		}
	}
	return arr;
}

//事件捕获
function addEvent(ele,eventname,func,isCaptrue){
	if(ele.attachEvent){
		ele.attachEvent("on"+eventname,func)
	}else{
		ele.addEventListener(eventname,func,isCaptrue)
	}
}

//随机颜色
function randomColor(){
	var R = Math.round(Math.random()*255);
	var G = Math.round(Math.random()*255);
	var B = Math.round(Math.random()*255);
	return "rgb"+"("+R+","+G+","+B+")";
}

//获取非行内样式
//window.getComputedStyle(obj,null)	非IE
//obj.currentStyle	IE
function getStyle(obj,attr){
	if(obj.currentStyle){
		return obj.currentStyle[attr];
	}else{
		return getComputedStyle(obj,null)[attr];
	}
}

//getCookie
function getCookie(key){
	var str = document.cookie;
	if(str != ""){
		var kvs = str.split("; ");
		for(var i=0; i<kvs.length; i++){
			if(kvs[i].split("=")[0] == key){
				return kvs[i].split("=")[1];
			}
		}
	}
	return "";
}

//设置cookie
function setCookie(key,value,days,path){
	var now = new Date();
	now.setDate(now.getDate()+days);
	document.cookie = key+"="+value+"; expires="+now+"; path="+(path || "/");
}
	
//缓冲运动
function move(ele,attr,val){
	clearInterval(ele.t);
	ele.t = setInterval(function(){
		if(parseInt(getstyle(ele)[attr]) == val){
			clearInterval(ele.t);
			return;
		}
		var speed = (val-parseInt(getstyle(ele)[attr]))/8;
		speed = speed>0?Math.ceil(speed):Math.floor(speed);
		ele.style[attr] = parseInt(getstyle(ele)[attr]) + speed + "px";
	},30)
	
	
}

//获取非行间样式
function getstyle(ele){
	if(ele.currentStyle){
		return ele.currentStyle;
	}else{
		return getComputedStyle(ele,null);
	}
}













