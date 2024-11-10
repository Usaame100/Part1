<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Kaamiro Fur</title>
</head>
<body>
    <h1>Fur Kaamiro</h1>
    <button onclick="furKaamiro()">Fur Kaamiro</button>
    <video id="kaamiro" width="320" height="240" autoplay></video>

    <script>
        function furKaamiro() {
            // Hubi in browserka taageerayo Media Devices API
            if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
                navigator.mediaDevices.getUserMedia({ video: true })
                    .then(function (stream) {
                        let video = document.getElementById('kaamiro');
                        video.srcObject = stream;
                        video.play();
                    })
                    .catch(function (err) {
                        alert("Kaamiro waa la heli waayey: " + err.message);
                    });
            } else {
                alert("Browser-kaagu ma taageerayo kaamiro furis!");
            }
        }
    </script>
</body>
</html>
