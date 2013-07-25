$(function(){
  var Quizlist = [
	            {
	            	"question":"AKBにいたアニメキャラは？",
	            	"selection":["シュレック","プーさん","シャークテイル","ドラえもん"],
	            	"answer":"シャークテイル"
	            },
	            {
	            	"question":"最高のスマートフォンは？",
	            	"selection":["iPhone5","iPhone4s","Xperia","GALAXY"],
	            	"answer":"iPhone5"
	            },
	            {
	            	"question":"現在放送中の仮面ライダーの名前は？",
	            	"selection":["仮面ライダーフォーゼ","仮面ライダークウガ","仮面ライダーウィザード","仮面ライダービースト","仮面ライダーピザ"],
	            	"answer":"仮面ライダーウィザード"
	            },
	           ];
	Quizlist = shaffle(Quizlist);
	for(var i=0;i<Quizlist.length;i++){
		var quiz = Quizlist[i];
		var title = "第" + (i+1) + "問：" + quiz["question"];
		var ok = false;
		while(ok==false){
			var a = droid.dialogList(title,quiz["selection"]);
			ok = droid.dialogYesNo("回答の確認","回答は「" + a + "」でよろしいですか？");
			if(ok){
				if(a == quiz["answer"]){
					alert("正解です！");
				}else{
					alert("残念！不正解です。正解は「" + quiz["answer"] + "」でした。");
				}
			}
		}
	}
    function shaffle(arr){
		for(var i=0;i<arr.length;i++){
			
			var num = Math.floor(Math.random()*arr.length);
			var temp = arr[num];
			arr[num] = arr[i];
			arr[i] = temp;
		}
		return arr;
	}
	
});
