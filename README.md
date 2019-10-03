In this website , image sizes have been reduced and java script files combined and applied "Defer" on the combined one. Moved script codes to the end of the body tag which leads to speed up of the website in desktop 99 and mobile 94 based on google speed test.

Also you can use Bootstrap cdn to help it as well:

<head>
  <!-- Bootstrap CSS CDN -->
  <link rel="stylesheet" href="~https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/3.4.1/css/bootstrap.min.css">
  <!-- Bootstrap CSS local fallback -->
  <script>
    var test = document.createElement("div")
    test.className = "hidden d-none"

    document.head.appendChild(test)
    var cssLoaded = window.getComputedStyle(test).display === "none"
    document.head.removeChild(test)

    if (!cssLoaded) {
        var link = document.createElement("link");

        link.type = "text/css";
        link.rel = "stylesheet";
        link.href = "lib/bootstrap.min.css";

        document.head.appendChild(link);
    }
  </script>
</head>
<body>
    <!-- APP CONTENT -->

    <!-- jQuery CDN -->
    <script src="~https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.0/jquery.min.js"></script>
    <!-- jQuery local fallback -->
    <script>window.jQuery || document.write('<script src="lib/jquery.min.js"><\/script>')</script>

    <!-- Bootstrap JS CDN -->
    <script src="~https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/3.4.1/js/bootstrap.min.js"></script>
    <!-- Bootstrap JS local fallback -->
    <script>if(typeof($.fn.modal) === 'undefined') {document.write('<script src="lib/bootstrap.min.js"><\/script>')}</script>
</body>

source: https://stackoverflow.com/questions/26192897/should-i-use-bootstrap-from-cdn-or-make-a-copy-on-my-server
