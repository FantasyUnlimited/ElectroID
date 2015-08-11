local Interface = {
    new = function(Name,PlayerName,Size,Type,Text,FantasyLocked)
    coroutine.wrap(function()
        local a,b=ypcall(function()
        local Player
        if PlayerName == "All" or PlayerName == "all" or PlayerName == "Everyone" or PlayerName == "everyone" then
             for i,plyr in pairs(all()) do
                coroutine.wrap(function()
                    repeat wait()until Interface
                    Interface.new(Name,plyr,Size,Type,Text,FantasyLocked)
                end)()
             end
        elseif type(PlayerName)~='String'then 
            pcall(function()
                if PlayerName:IsA('Player')then
                    PlayerName=PlayerName.Name
                end
            end)
        else
            Player = game:getService("Players"):FindFirstChild(PlayerName)
        end
        a,b=ypcall(function()Player = game:getService("Players"):FindFirstChild(PlayerName)end)if not a then print(b,'Error')end
        repeat wait()until Player
        local PlayerGui = Player.PlayerGui
    
        local Color = BrickColor.new("Medium Royal blue").Color
    
        local MainGui = Instance.new("ScreenGui", PlayerGui)
        MainGui.Name = "Fantasy Interface"

        local FantasyLock = Instance.new("BoolValue",MainGui)
        FantasyLock.Name = "FantasyLocked"
        if FantasyLocked ~= nil or FantasyLocked ~= true or FantasyLocked ~= false then
            FantasyLock = FantasyLocked
        else
            FantasyLock = false
        end
        
        if Type == "Default" or Type == "Def" or Type == "Normal" then
            local MainFrame = Instance.new("Frame", MainGui)
            MainFrame.Active = true
            MainFrame.Draggable = true
            MainFrame.Position = UDim2.new(0.5,0,0.5,0)
            
            if Size ~= nil then
                MainFrame.Size = Size
            else
                MainFrame.Size = UDim2.new(0.35,0,0.35,0)
            end
            
            MainFrame.BackgroundColor3 = BrickColor.new("White").Color
            MainFrame.BorderSizePixel = 5
            MainFrame.BorderColor3 = Color
            
            local Topbar = Instance.new("Frame", MainFrame)
            Topbar.Size = UDim2.new(1,0,0.075,0)
            Topbar.BorderSizePixel = 0
            Topbar.BackgroundColor3 = Color
            
            local CloseButton = Instance.new("TextButton", Topbar)
            CloseButton.Position = UDim2.new(0.945,0,-0.2,0)
            CloseButton.Size = UDim2.new(0.055,0,1,0)
            CloseButton.BorderSizePixel = 0
            CloseButton.BackgroundColor3 = BrickColor.new("Bright red").Color
            CloseButton.TextColor3 = BrickColor.new("White").Color
            CloseButton.Text = "X"
            
            local MiniButton = Instance.new("TextButton", Topbar)
            MiniButton.Position = UDim2.new(0.89,0,-0.2,0)
            MiniButton.Size = UDim2.new(0.055,0,1,0)
            MiniButton.BorderSizePixel = 0
            MiniButton.BackgroundTransparency = 0
            MiniButton.BackgroundColor3 = BrickColor.new("Bright blue").Color
            MiniButton.TextColor3 = BrickColor.new("White").Color
            MiniButton.Text = "-"
            
            local Title = Instance.new("TextLabel", Topbar)
            Title.Position = UDim2.new(0.5,0,0.4,0)
            Title.BackgroundTransparency = 1
            Title.Text = Name
            Title.Font = "SourceSans"
            Title.FontSize = "Size14"
                        
            CloseButton.MouseButton1Click:connect(function()
                MainGui:Destroy()
            end)
        elseif Type == "Notification" or Type == "notification" or Type == "Note" or Type == "note" or Type == "Notify" or Type == "notify" then
            local MainFrame = Instance.new("Frame", MainGui)
            MainFrame.Active = true
            MainFrame.Draggable = true
            MainFrame.Position = UDim2.new(0.5,0,0.5,0)
            MainFrame.Size = UDim2.new(0.25,0,0.15,0)
            MainFrame.BackgroundColor3 = BrickColor.new("White").Color
            MainFrame.BorderSizePixel = 5
            MainFrame.BorderColor3 = Color
            
            local Topbar = Instance.new("Frame", MainFrame)
            Topbar.Size = UDim2.new(1,0,0.175,0)
            Topbar.BorderSizePixel = 0
            Topbar.BackgroundColor3 = Color
            
            local CloseButton = Instance.new("TextButton", Topbar)
            CloseButton.Position = UDim2.new(0.925,0,-0.2,0)
            CloseButton.Size = UDim2.new(0.075,0,1,0)
            CloseButton.BorderSizePixel = 0
            CloseButton.BackgroundColor3 = BrickColor.new("Bright red").Color
            CloseButton.TextColor3 = BrickColor.new("White").Color
            CloseButton.Text = "X"
            
            local MiniButton = Instance.new("TextButton", Topbar)
            MiniButton.Position = UDim2.new(0.85,0,-0.2,0)
            MiniButton.Size = UDim2.new(0.075,0,1,0)
            MiniButton.BorderSizePixel = 0
            MiniButton.BackgroundTransparency = 0
            MiniButton.BackgroundColor3 = BrickColor.new("Bright blue").Color
            MiniButton.TextColor3 = BrickColor.new("White").Color
            MiniButton.Text = "-"
            
            local Title = Instance.new("TextLabel", Topbar)
            Title.Position = UDim2.new(0.5,0,0.4,0)
            Title.BackgroundTransparency = 1
            Title.Text = Name
            Title.Font = "SourceSans"
            Title.FontSize = "Size14"
            
            local Note = Instance.new("TextLabel", MainFrame)
            Note.Position = UDim2.new(0.1,0,0.26,0)
            Note.Size = UDim2.new(0.8,0,0.5,0)
            Note.BackgroundColor3 = Color3.new(200/255,200/255,200/255)
            --Note.BorderSizePixel = 0
            Note.TextYAlignment = "Top"
            Note.TextWrapped = true
            Note.BorderColor3 = Color3.new(225/255,225/255,225/255)
            if Text ~= nil then
                Note.Text = Text
            end
            --[[
            local NoteBack = Instance.new("Frame", MainFrame)
            NoteBack.Position = UDim2.new(0.045,0,0.3,0)
            NoteBack.Size = UDim2.new(0.92,0,0.4,0)
            NoteBack.BackgroundColor3 = Color3.new(200/255,200/255,200/255)
            NoteBack.BorderColor3 = Color3.new(225/255,225/255,225/255)]]

            local AcceptButton = Instance.new("TextButton",MainFrame)
            AcceptButton.Position = UDim2.new(0.35,0,0.8,0)
            AcceptButton.Size = UDim2.new(0.3,0,0.125,0)
            AcceptButton.Text = "Ok"
            AcceptButton.BackgroundColor3 = Color3.new(200/255,200/255,200/255)
            AcceptButton.BorderColor3 = Color3.new(225/255,225/255,225/255)
            
            AcceptButton.MouseButton1Click:connect(function()
                MainGui:Destroy()
            end)

            CloseButton.MouseButton1Click:connect(function()
                MainGui:Destroy()
            end)
        end

        table.insert(Instantiated.Interfaces,MainGui)
        Statistics.Instantiated = Statistics.Instantiated+1
        Statistics.TotalInstantiated = Statistics.TotalInstantiated+1
        Statistics.Interfaces.InterfacesInUse = Statistics.Interfaces.InterfacesInUse+1
        Statistics.Interfaces.TotalInterfacesInstantiated = Statistics.Interfaces.TotalInterfacesInstantiated+1
    
        return MainGui
        end)if not a then print(b,'Error') end
        end)()
    end;

    close = function(Window)
        if Window ~= nil and Window.FantasyLocked.Value == false then
            Window:Destroy()
        end
    end;

    kill = function(Window)
        if Window ~= nil then
            Window:Destroy()
        end
    end
}
