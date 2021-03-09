# javascript-image-slideshow









<%@ Page Language="C#" AutoEventWireup="true" CodeBehind="WebForm1.aspx.cs" Inherits="WebApplication43.WebForm1" %>

<!DOCTYPE html>

<html xmlns="http://www.w3.org/1999/xhtml">
<head runat="server">
    <title></title>
</head>
<body>
    <form id="form1" runat="server">
        <div>
            <img id="image" src="/Images/1.jpg" style="width: 150px; height: 150px" />
<br />
<input type="button" value="Start Slide Show" onclick="startImageSlideShow()" />
<input type="button" value="Stop Slide Show" onclick="stopImageSlideShow()" />
                <script type="text/javascript">
                    var intervalId;
                    function startImageSlideShow() {
                        intervalId = setInterval(setImage, 500);
                    }

                    function stopImageSlideShow() {
                        clearInterval(intervalId);
                    }

                    function setImage() {
                        
                        var imageSrc = document.getElementById("image").getAttribute("src");
                        var currentImageNumber = imageSrc.substring(imageSrc.lastIndexOf("/") + 1, imageSrc.lastIndexOf("/") + 2);
                        if (currentImageNumber == 8) {
                            currentImageNumber = 0;
                        }
                        document.getElementById("image").setAttribute("src", "/Images/" + (Number(currentImageNumber) + 1) + ".jpg");
                    }
</script>
        </div>
    </form>
</body>
</html>
