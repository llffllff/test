---
title: Lua開発記3
date: 2018-02-28T14:25:25.552Z
description: lua-3
image: null
---
R6Sでの操作簡易化
覗き込み＋方向キーで自動リーンを行う。
<pre>
function OnEvent(event, arg)
	if IsMouseButtonPressed(3) then
		i=0
		j=0
		repeat
			if IsModifierPressed("shift") and i<1 then
				Sleep(50);
				PressKey("n");
				Sleep(150);
				ReleaseKey("n");
				i=i\+1
				j=0
			elseif IsModifierPressed("alt") and j<1 then
				Sleep(50);
				PressKey("m");
				Sleep(150);
				ReleaseKey("m");
				j=j\+1
				i=0
			end
		until not IsMouseButtonPressed(3)
	end
end

</pre>

<iframe width="560" height="315" src="https://www.youtube.com/embed/z6TDWlgDiEE?rel=0" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

試作品-不動
<pre>
function OnEvent(event, arg)
	if IsMouseButtonPressed(3)then
		i=0
		j=0
		repeat
			Sleep(50);
			x=GetMousePosition()
			Sleep(50);
			a=GetMousePosition()
			if(x\+500<a and i<1)then
				OutputLogMessage("right\\n")
				PressKey("m");
				Sleep(200);
				ReleaseKey("m");
				i=i\+1
				j=0
			elseif(x-500>a and j<1)then
				OutputLogMessage("left\\n")
				PressKey("n");
				Sleep(200);
				ReleaseKey("n");
				j=j\+1
				i=0
			end
					Sleep(50);
		until not IsMouseButtonPressed(3)
	end
end

</pre>
