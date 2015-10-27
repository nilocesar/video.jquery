# video.jquery
Criação de um Jquery com o controle de videos - local,  streaming, api youtube, api vimeo 

       $("#player").video_jquery({
                    control: "default", // default, youtube, vimeo
                    width: 800,
                    heigth: 600,
                    path: "http://xxx.com.br/vod/mp4:default/xxx/Bem_Vindo_ao_Segmento_Select.mp4/playlist.m3u8", // caminho default(local/streaminng-m3u8), videoId(youtube/vimeo)
                    autoplay: true,
                    skin: true
        });
        
        /*$("#player").video_jquery({
                    control: "default", // default, youtube, vimeo
                    width: 800,
                    heigth: 600,
                    path: "http://video-js.zencoder.com/oceans-clip.mp4", // caminho default(local/streaminng-m3u8), videoId(youtube/vimeo)
                    autoplay: true,
                    skin: true
        });*/

        /*$("#player").video_jquery({
             control: "youtube", // default, youtube, vimeo
             width: 800,
             heigth: 600,
             path: "dsUxvFNWb6w", // caminho default(local), videoId(youtube/vimeo)
             autoplay:false,
             skin:true
         });*/

        /*$("#player").video_jquery({
            control: "vimeo", // default, youtube, vimeo
            width: 638,
            heigth: 348,
            path: "76979871", // caminho default(local), videoId(youtube/vimeo)
            autoplay: false
                //skin:true --- Não funciona no vimeo
        });*/
        
       
        $("#player").on("start", function (e) {
            
            $("#controle").text("start");
            //console.log("start");
        });

        $("#player").on("paused", function (e) {
           $("#controle").text("paused");
        });

        $("#player").on("timeProgress", function (e) {
            $("#time").text("time " + e.timeCurrent + "/" +  e.timeTotal );
            //console.log(e.timeCurrent);
            //console.log(e.timeTotal);
        });

        $("#player").on("timeFinish", function (e) {
            
            $("#controle").text("timeFinish");
            //console.log("timeFinish");
            //console.log(e.timeCurrent);
            //console.log(e.timeTotal);
        });
        
        setTimeout(function(){
             $("#controle").text("currentTime");
             $("#player").currentTime(100);
            
        } , 1000 * 8)
        
        //
        //$("#player").pause(); 
        //$("#player").play();
        //$("#player").stop();    
        //$("#player").currentTime(30);
