# Hello
open music
public void AddNewCallOut(String message, Boolean ismsgResponse) {
		elementId = elementId + 1;
		StringBuilder messageBuilder = new StringBuilder();

		if (!message.contentEquals("")) {

			if (!ismsgResponse) {
				messageBuilder
						.append("&lt;table class='bubble-gray' cellspacing='0' cellpadding='0'>&lt;tr>&lt;td class='head'>&lt;/td>&lt;/tr>");
				messageBuilder
						.append("&lt;tr>&lt;td class='mid'>&lt;div class='txt shadow'>"
								+ message + "&lt;/div>&lt;/td>&lt;/tr>");
				messageBuilder
						.append("&lt;tr>&lt;td class='foot'>&lt;/td>&lt;/tr>&lt;/table>");
			} else {
				messageBuilder
						.append("&lt;table class='bubble-blue' cellspacing='0' cellpadding='0'>&lt;tr>&lt;td class='bhead'>&lt;/td>&lt;/tr>");
				messageBuilder
						.append("&lt;tr>&lt;td class='bmid'>&lt;div class='txt shadow'>"
								+ message + "&lt;/div>&lt;/td>&lt;/tr>");
				messageBuilder
						.append("&lt;tr>&lt;td class='bfoot'>&lt;/td>&lt;/tr>&lt;/table>");
			}

			loadUrl("javascript:document.getElementById(\"div" + elementId
					+ "\").innerHTML=\"" + messageBuilder.toString() + "\";");
		}
		StringBuilder jvscr = new StringBuilder();
		if (!ismsgResponse) {
			if (elementId != 1) {
				if (!ismsgResponse) {
					jvscr.append("var elem = document.getElementById('div"
							+ (elementId - 1)
							+ "');     var x = 0;     var y = 0;     while (elem != null) {         x += elem.offsetLeft;         y += elem.offsetTop;         elem = elem.offsetParent;     } ");
					jvscr.append("var endj=500; var i=window.scrollY; for(i=window.scrollY;i&lt;y;i++){ var j=0; var a=0; for(j=0;j&lt;endj;j++) {a=a+1; }  window.scrollTo(x, i); } ");
					loadUrl("javascript:" + jvscr.toString());
				}
			}
		}
	}
