---
title: Lua開発記2
date: 2018-02-24T03:45:01.477Z
description: lua-2
image: null
---
<h3>MHW弓操作簡易化</h3>
マウスボタンに構えと溜めが振ってあり、マウスのサイドボタンはステップであるため、狩り中の操作が簡易化できる。更に△ボタンと〇ボタンの同時押しをマウスボタンに振ってあるため、1ボタンで竜の一矢を放つことができる。
<pre>

EnablePrimaryMouseButtonEvents\(true\)
function OnEvent\(event, arg\)
	if event=="MOUSE\_BUTTON\_PRESSED" and arg==1 then
		PressMouseButton\(3\)
	elseif event=="MOUSE\_BUTTON\_RELEASED" and arg==1 then
		ReleaseMouseButton\(3\)
	end
	if event=="MOUSE\_BUTTON\_PRESSED" and arg==8 then
		PressKey\("f12"\)
		Sleep\(50\)
		ReleaseKey\("f12"\)	
	end
end
</pre>


