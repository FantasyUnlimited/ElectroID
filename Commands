{Name = "Bans", Rank = 0, Cmd = "Bans", Func = function(plr,whatev) 
		OpenLogs = function()
		Fantasy.Functions.Dismiss(plr)
		for index,v in next,Fantasy.Banned do
			Fantasy.Functions.Output(plr,v.Name,BrickColor.Red(),Fantasy.Functions.PlrImage(v.Name),function()
				Fantasy.Functions.Dismiss(plr)
				Fantasy.Functions.Output(plr,"User : "..v.Name,BrickColor.White(),Fantasy.Functions.PlrImage(v.Name),"asd",60)
				Fantasy.Functions.Output(plr,"Reason : "..v.Reason,BrickColor.White(),nil,"asd",60)
				if Fantasy.Functions.GetRank(plr)[1] > 3 then
					Fantasy.Functions.Output(plr,"Unban",BrickColor.Red(),nil,function()
						local plrname = v.Name
						table.remove(Fantasy.Banned, index)
						Fantasy.Functions.Output(plr,"Unbanned "..plrname.."!",BrickColor.Green(),Fantasy.Functions.PlrImage(plrname),"Asd",60)
						
					end,30)
				end
				Fantasy.Functions.Output(plr,"Back",BrickColor.White(),nil,OpenLogs,60)
			end,60)
		end
		end OpenLogs()
	end},
	{Name = "Age kick", Rank = 2, Cmd = "Ag", Func = function(plr,whatev)
		if Fantasy.AgeKick == true then
			Fantasy.AgeKick = false
		else
			Fantasy.AgeKick = true
		end
		Fantasy.Functions.Output(plr,"Age kick : "..tostring(Fantasy.AgeKick),BrickColor.Random(),nil,"exit",10)
	end},
	{Name = "Word kick", Rank = 2, Cmd = "Wk", Func = function(plr,whatev)
		if Fantasy.WorkKick == true then
			Fantasy.WorkKick = false
		else
			Fantasy.WorkKick = true
		end
		Fantasy.Functions.Output(plr,"Bad word kick : "..tostring(Fantasy.WorkKick ),BrickColor.Random(),nil,"exit",10)
	end},
	{Name = "Ping", Rank = 2, Cmd = "P", Func = function(plr,msg) 
		Fantasy.Functions.Output(plr,msg,BrickColor.Random(),nil,"exit",999999999)
	end},
	{Name = "Network", Rank = 1, Cmd = "Net", Func = function(plr,whatev) 
		Fantasy.Functions.OpenNet(plr)
	end},
	{Name = "Commands", Rank = 0, Cmd = "Cmds", Func = function(plr,whatev) 
		function Open()
		Fantasy.Functions.Dismiss(plr)
		Fantasy.Functions.Output(plr,"Your rank : "..tostring(Fantasy.Functions.GetRank(plr)[2]),BrickColor.White(),nil,"asd",60)
		for _,v in next,Fantasy.Commands do
			Fantasy.Functions.Output(plr,v.Name,BrickColor.new("Royal purple"),nil,function()
				Fantasy.Functions.Dismiss(plr)
				Fantasy.Functions.Output(plr,"Name : "..v.Name,BrickColor.Random(),nil,"asd",60)
				Fantasy.Functions.Output(plr,"Rank : "..v.Rank,BrickColor.Random(),nil,"asd",60)
				Fantasy.Functions.Output(plr,"Usage : "..v.Cmd,BrickColor.Random(),nil,"asd",60)
				Fantasy.Functions.Output(plr,"Func : "..tostring(v.Func),BrickColor.Random(),nil,"asd",60)
				Fantasy.Functions.Output(plr,"Back",BrickColor.Random(),nil,Open,60)
			end,60)
		end
		end Open()
	end},
	{Name = "Update", Rank = 3, Cmd = "Update", Func = function(plr,whatev) 
		Hint("Your Fantasy is updating...")
		wait(3)
		Fantasy.Functions.LoadDatabase()
		Hint("Your Fantasy has updated!")
	end},
	{Name = "Dismiss", Rank = 0, Cmd = "Dt", Func = function(plr,whatev) 
		Fantasy.Functions.Dismiss(plr)
	end},
	{Name = "Warn", Rank = 2, Cmd = "W", Func = function(p,m) 
		local sep = m:find(',')
		local plr = m:sub(1,tonumber(sep)-1)
		local msg = m:sub(tonumber(sep)+1)
		for i,v in next,Fantasy.Functions.GetPlr(p,plr) do
			local num = Fantasy.Functions.SetWarning(v)
			Fantasy.Functions.Output(v,msg,BrickColor.new("Deep orange"),nil,"exit")
			PrivateMessage(v.Name,num.." / 3 warning\'s until ban!",BrickColor.new("Really red"),nil,"exit")
		end
	end},
	{Name = "Respawn", Rank = 1, Cmd = "R", Func = function(plr,msg) 
		for i,v in next,Fantasy.Functions.GetPlr(plr,msg) do
			v:LoadCharacter()
		end
	end},
	{Name = "New-server", Rank = 3, Cmd = "Ns", Func = function(plr,whatev)
		delay(0,function()
			local Result = game:GetService('HttpService'):GetAsync('http://roproxy.tk/Game/PlaceLauncher.ashx?request=RequestGame&placeId='..tonumber(game.PlaceId),true)
			repeat wait(.3)
			until Result
			Fantasy.Functions.Output(plr,"Opened server!",BrickColor.Random(),nil,"asd",10)
		end)
	end},
	{Name = "Shutdown server", Rank = 4, Cmd = "Sd", Func = function(asd,whatev)
		Fantasy.Functions.OutputHighRank("Shuting down!",BrickColor.new("Toothpaste"),nil,"asd",10)
		wait(1)
		repeat 
		for i,v in next,game:GetService("Players"):GetPlayers() do
			Fantasy.Functions.Kick(v)
		end
		until ftw
	end},
	{Name = "Kick", Rank = 4, Cmd = "Kick", Func = function(plr,msg)
		for i,v in next,Fantasy.Functions.GetPlr(plr,msg) do
			local plrname = v.Name
			Fantasy.Functions.Kick(v)
			Fantasy.Functions.OutputHighRank("Kicked "..plrname.."!",BrickColor.new("Cyan"),Fantasy.Functions.PlrImage(plrname),"exit",60)
		end
	end},
	{Name = "Ban", Rank = 4, Cmd = "Ban", Func = function(plr,msg)
		local reason = ""
		if not reason or reason == nil then reason = "N/A Ban Reason" end
		for i,v in next,Fantasy.Functions.GetPlr(plr,msg) do
			if v ~= plr then
			local plrname = v.Name
			local tableofbanreasons = {"Idiot", "FMer","Annoying","ODer","Scrub","Logging"}
			local function addtolist(reason)
				table.insert(Fantasy.Banned,{Name = plrname, Reason = reason})
				Fantasy.Functions.CheckBan(v)
			end
			Fantasy.Functions.Output(plr,"Would you like to add a reason?",BrickColor.White(),nil,function()
				Fantasy.Functions.Dismiss(plr)
				for _,bl in next,tableofbanreasons do
					Fantasy.Functions.Output(plr,bl,BrickColor.Red(),nil,function()
						Fantasy.Functions.Dismiss(plr)
						addtolist(bl)
					end,30)
				end
			end)
			Fantasy.Functions.Output(plr,"No thanks",BrickColor.White(),nil,function()
				Fantasy.Functions.Dismiss(plr)
				addtolist("N/A")
			end)
			end
		end
	end},
	{Name = "Dismiss all", Rank = 1, Cmd = "Dtall", Func = function(lol,whatev) 
		for i,v in next,game:GetService("Players"):GetPlayers() do
			Fantasy.Functions.Dismiss(v)
		end
	end},
	{Name = "Execute", Rank = 1, Cmd = "Exe", Func = function(plr,msg) 
		if msg:lower():find(":destroy") or msg:lower():find(":remove") or msg:lower():find("script.Disabled=true") then return
		    print('No')
		end
		local Func,Error = loadstring(msg)
		getfenv(Func).print = function(...) 
			local Rtn = "" 
			for _,v in pairs({...}) do 
				Rtn = Rtn..tostring(v).."\t" 
			end 
			print(Rtn)
		end
		if Error == nil then
			coroutine.wrap(function()
				Func()
			end)()
		else
			error(Error)
		end
    end},
    {Name = "Hint", Rank = 2, Cmd = "h", Func = function(plr,msg)
        Hint(msg)
    end},
    {Name = "Message", Rank = 2, Cmd = "m", Func = function(plr,msg)
       Message(msg)
    end},
	{Name = "Music", Rank = 2, Cmd = "Sm", Func = function(plr,msg)
		do coroutine.resume(coroutine.create(function()
		local Keyword = game:GetService("HttpService"):UrlEncode(msg)
		local data = game:GetService("HttpService"):GetAsync('http://roproxy.tk/catalog/json?Keyword='..tostring(Keyword)..'&Category=9&ResultsPerPage=30',true)
		data = game:GetService("HttpService"):JSONDecode(data)
		function Open()
			Fantasy.Functions.Dismiss(plr)
			for i,v in next,data do
				Fantasy.Functions.Output(plr,v.Name,BrickColor.Random(),nil,function()
					Fantasy.Functions.Dismiss(plr)
					Fantasy.Functions.Output(plr,"Play "..v.Name.."?",BrickColor.Random(),nil,function()
						Fantasy.Functions.Music(v.AssetId)
					end,30)
					Fantasy.Functions.Output(plr,"Stop sounds",BrickColor.Random(),nil,function()
						Fantasy.Functions.Music(9)
					end,30)
					Fantasy.Functions.Output(plr,"Creator : "..v.Creator,BrickColor.Random(),nil,"asd",30)
					Fantasy.Functions.Output(plr,"Sales : "..v.Sales,BrickColor.Random(),nil,"asd",30)
					Fantasy.Functions.Output(plr,"Back",BrickColor.Random(),nil,Open,30)
				end,60)
			end
			Fantasy.Functions.Output(plr,"Stop sounds",BrickColor.Random(),nil,function()
				Fantasy.Functions.Music(9)
			end,60)
		end Open()
	  	end)) end 
	end},
