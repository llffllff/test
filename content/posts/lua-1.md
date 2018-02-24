---
title: Lua開発記1
date: 2018-02-24T03:41:46.792Z
description: lua-1
image: null
---
左ボタン（左クリック）押下と同時に右ボタン押下
左ボタンを離した時に同時に右ボタンを離す単純なスクリプト
<pre>EnablePrimaryMouseButtonEvents(true)
function OnEvent(event, arg)
	if event=="MOUSE_BUTTON_PRESSED" and arg==1 then
		PressMouseButton(3)
	elseif event=="MOUSE_BUTTON_RELEASED" and arg==1 then
		ReleaseMouseButton(3)
	end
end
</pre>

