---
title: Lua開発記2
date: 2018-02-24T03:45:01.477Z
description: lua-2
image: null
---
<h3>MHW弓操作簡易化</h3>
マウスボタンに構えと溜めが振ってあり、マウスのサイドボタンはステップであるため、狩り中の操作が簡易化できる。更に△ボタンと〇ボタンの同時押しをマウスボタンに振ってあるため、1ボタンで竜の一矢を放つことができる。
<pre>

EnablePrimaryMouseButtonEvents(true)
function OnEvent(event, arg)
	if event=="MOUSE_BUTTON_PRESSED" and arg==1 then
		PressMouseButton(3)
	elseif event=="MOUSE_BUTTON_RELEASED" and arg==1 then
		ReleaseMouseButton(3)
	end
	if event=="MOUSE_BUTTON_PRESSED" and arg==8 then
		PressKey("f12")
		Sleep(50)
		ReleaseKey("f12")	
	end
end
</pre>

<iframe width="560" height="315" src="https://www.youtube.com/embed/UGQ9a79_RWI?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

