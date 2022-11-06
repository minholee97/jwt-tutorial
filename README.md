# jwt-tutorial
jwt-tutorial with spring-boot

```
	<script>
		$(document).ajaxError(function(event, xhr, setting, error){
    		if(xhr.status === 401) {
    			if (xhr.responseJSON.code != "ACCESS_TOKEN_EXPIRED") {
                    opener.location.href = '/';
                    close();
    			}
    			else {
				    $.ajax({
                	    type: "GET",
                        url: "/auth/reissue",
                        contentType: "application/json; charset=utf-8",
                        async: false,
                        complete : function(jqXHR, textStatus) {
                    	switch (jqXHR.status) {
                    		case 200:
                    		    $.ajax(setting);
                        		break;
                    		default:
                    		    opener.location.href = '/';
                    		    close();
                    	    }
                        }
                    });
                }
    		}
    	});
    </script>
```
