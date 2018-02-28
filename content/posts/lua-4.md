---
title: Lua開発記4
date: 2018-02-28T14:35:10.906Z
description: lua-4
image: null
---
cod4の射撃場での自動化

本来であれば、長々としたスクリプトで制御する予定であったが、どうしても制御に割り込む考えが浮かばなかったため、マクロファイルに操作を全記述した。
AbortMacro()で動き続けているマクロを停止できる。
<pre>
function OnEvent(event, arg)
	if event == "MOUSE_BUTTON_PRESSED" and arg == 3 then
		toggle = not toggle
		if toggle then
			PlayMacro("Macro1")
		else
			AbortMacro()
		end
	end
end
</pre>

<iframe width="560" height="315" src="https://www.youtube.com/embed/z6TDWlgDiEE?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
