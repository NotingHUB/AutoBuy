                                                                                 if  not game:IsLoaded 
                                                                        () then game.Loaded:Wait();end task.wait(5);    
                                                                    local Players=game:GetService("Players");local                
                                                                ReplicatedStorage=game:GetService("ReplicatedStorage");local            
                                                            UserInputService=game:GetService("UserInputService");local TweenService=game: 
                                                          GetService("TweenService");local RotatingShop=ReplicatedStorage:WaitForChild(     
                                                        "Remotes"):WaitForChild("RotatingShop");local AutoBuyEnabled=false;local AutoInterval 
                                                      =300;local GoldShopItems={{Currency="Raid",Item="TraitRerolls",Amount=3},{Currency="Gold" 
                                                    ,Item="GreenEssence",Amount=15},{Currency="Gold",Item="RedEssence",Amount=3},{Currency="Gold" 
                                                  ,Item="PurpleEssence",Amount=3},{Currency="Gold",Item="BlueEssence",Amount=3},{Currency="Gold",   
                                                  Item="SuperStatChip",Amount=10},{Currency="Gold",Item="PinkEssence",Amount=3},{Currency="Gold",Item 
                                                ="RainbowEssence",Amount=1},{Currency="Gold",Item="TraitRerolls",Amount=3},{Currency="Gold",Item=       
                                                "YellowEssence",Amount=3},{Currency="Gold",Item="StatChip",Amount=10}};local ScreenGui=Instance.new(      
                                              "ScreenGui");ScreenGui.Name="NHUB_Auto_Version";ScreenGui.Parent=game.CoreGui;ScreenGui.ResetOnSpawn=false;   
                                              local MainFrame=Instance.new("Frame",ScreenGui);MainFrame.Size=UDim2.new(0,500,0,380);MainFrame.Position=     
                                            UDim2.new(0.5, -250,0.5, -190);MainFrame.BackgroundColor3=Color3.fromRGB(0,0,0);MainFrame.BackgroundTransparency= 
                                            0.35;MainFrame.BorderSizePixel=0;MainFrame.Active=true;MainFrame.Draggable=true;MainFrame.Visible=true;Instance.new 
                                          ("UICorner",MainFrame).CornerRadius=UDim.new(0,12);local MainStroke=Instance.new("UIStroke",MainFrame);MainStroke.Color 
                                          =Color3.fromRGB(0,255,120);MainStroke.Thickness=1.5;MainStroke.Transparency=0.4;local TopBar=Instance.new("Frame",        
                                          MainFrame);TopBar.Size=UDim2.new(1,0,0,40);TopBar.BackgroundTransparency=1;local Title=Instance.new("TextLabel",TopBar);    
                                          Title.Size=UDim2.new(1, -50,1,0);Title.Position=UDim2.new(0,15,0,0);Title.Text=                                             
                                        "NHUB <font color='#00FF78'>| SHOP MENU</font>";Title.RichText=true;Title.TextColor3=Color3.new(1,1,1);Title.Font=Enum.Font.    
                                        GothamBold;Title.TextSize=16;Title.TextXAlignment=Enum.TextXAlignment --[[==============================]].Left;Title.            
                                        BackgroundTransparency=1;local CloseBtn=Instance.new(       --[[============================================]]"TextButton",TopBar 
                                        );CloseBtn.Size=UDim2.new(0,28,0,28);CloseBtn.Position= --[[======================================================]]UDim2.new(1, -  
                                      35,0,6);CloseBtn.BackgroundColor3=Color3.fromRGB(255, --[[==========================================================]]75,75);CloseBtn.  
                                      Text="×";CloseBtn.TextColor3=Color3.new(1,1,1);     --[[==============================================================]]CloseBtn.       
                                      TextSize=20;Instance.new("UICorner",CloseBtn).      --[[================================================================]]CornerRadius=   
                                      UDim.new(1,0);CloseBtn.MouseButton1Click:Connect(   --[[==================================================================]]function()    
                                      MainFrame.Visible=false;end);local Sidebar=Instance --[[==================================================================]].new("Frame",     
                                    MainFrame);Sidebar.Size=UDim2.new(0,120,1, -50);      --[[====================================================================]]Sidebar.      
                    Position=UDim2.new(0,10,0,45);Sidebar.BackgroundTransparency=0.8;     --[[====================================================================]]Sidebar.        
              BackgroundColor3=Color3.new(0,0,0);Instance.new("UICorner",Sidebar).        --[[======================================================================]]CornerRadius= 
            UDim.new(0,8);local SidebarList=Instance.new("UIListLayout",Sidebar);         --[[======================================================================]]SidebarList.  
          HorizontalAlignment=Enum.HorizontalAlignment.Center;SidebarList.Padding=UDim.   --[[======================================================================]]new(0,5);     
        local ContentFrame=Instance.new("Frame",MainFrame);ContentFrame.Position=UDim2.   --[[======================================================================]]new(0,140,0,  
        45);ContentFrame.Size=UDim2.new(1, -150,1, -60);ContentFrame.                     --[[======================================================================]]              
      BackgroundTransparency=1;ContentFrame.Visible=false;local ContentList=Instance.new( --[[======================================================================]]              
      "UIListLayout",ContentFrame);ContentList.Padding=UDim.new(0,10);ContentList.          --[[==================================================================]]                
      HorizontalAlignment=Enum.HorizontalAlignment.Center;local MiniHolder=Instance.new(    --[[================================================================]]"Frame",ScreenGui 
    );MiniHolder.Size=UDim2.new(0,60,0,60);MiniHolder.Position=UDim2.new(0.05,0,0.2,0);     --[[==============================================================]]MiniHolder.       
    BackgroundTransparency=1;MiniHolder.Active=true;MiniHolder.Draggable=true;local OpenBtn=  --[[==========================================================]]Instance.new(       
    "TextButton",MiniHolder);OpenBtn.Size=UDim2.new(1,0,1,0);OpenBtn.BackgroundColor3=Color3.   --[[====================================================]]fromRGB(25,25,25);      
    OpenBtn.BackgroundTransparency=0.1;OpenBtn.Text="NHUB";OpenBtn.TextColor3=Color3.fromRGB(0,   --[[==============================================]]255,120);OpenBtn.Font=    
    Enum.Font.LuckiestGuy;OpenBtn.TextSize=18;OpenBtn.TextXAlignment=Enum.TextXAlignment.Center;      --[[====================================]]OpenBtn.TextYAlignment=Enum.  
    TextYAlignment.Center;Instance.new("UICorner",OpenBtn).CornerRadius=UDim.new(1,0);local RemoveBtn=    --[[========================]]Instance.new("TextButton",MiniHolder) 
    ;RemoveBtn.Size=UDim2.new(0,22,0,22);RemoveBtn.Position=UDim2.new(1, -18,0, -4);RemoveBtn.BackgroundColor3=Color3.fromRGB(255,75,75);RemoveBtn.Text="×";RemoveBtn.      
  TextColor3=Color3.new(1,1,1);RemoveBtn.TextSize=18;RemoveBtn.Font=Enum.Font.GothamBold;Instance.new("UICorner",RemoveBtn).CornerRadius=UDim.new(1,0);Instance.new(      
  "UIStroke",RemoveBtn).Color=Color3.new(1,1,1);local function CreateBtn(text,color,parent,callback) local b=Instance.new("TextButton",parent);b.Size=UDim2.new(0.95,0, 
  0,40);b.BackgroundColor3=color;b.BackgroundTransparency=0.2;b.Text=text;b.TextColor3=Color3.new(1,1,1);b.Font=Enum.Font.GothamBold;b.TextSize=12;Instance.new(          
  "UICorner",b).CornerRadius=UDim.new(0,6);b.MouseButton1Click:Connect(callback);return b;end local function BuyAllItems() for _,v in ipairs(GoldShopItems) do pcall(     
  function() RotatingShop:FireServer(v.Currency,v.Item,v.Amount);end);task.wait(0.1);end end CreateBtn("Gold Shop",Color3.fromRGB(30,30,30),Sidebar,function()            
  ContentFrame.Visible= not ContentFrame.Visible;end);local BuyOnceBtn=CreateBtn("⚡ BUY ALL ITEMS (ONCE) ⚡",Color3.fromRGB(0,150,80),ContentFrame,function() BuyAllItems( 
  );end);local AutoToggle=CreateBtn("Auto Buy Every 5 Mins: OFF",Color3.fromRGB(45,45,45),ContentFrame,function() end);AutoToggle.MouseButton1Click:Connect(function()    
  AutoBuyEnabled= not AutoBuyEnabled;if AutoBuyEnabled then AutoToggle.Text="Auto Buy Every 5 Mins: ON";AutoToggle.TextColor3=Color3.fromRGB(0,255,120);AutoToggle.       
  BackgroundColor3=Color3.fromRGB(0,60,30);else AutoToggle.Text="Auto Buy Every 5 Mins: OFF";AutoToggle.TextColor3=Color3.new(1,1,1);AutoToggle.BackgroundColor3=Color3.  
  fromRGB(45,45,45);end end);task.spawn(function() while true do if AutoBuyEnabled then BuyAllItems();task.wait(AutoInterval);end task.wait(1);end end);OpenBtn.          
  MouseButton1Click:Connect(function() MainFrame.Visible= not MainFrame.Visible;end);RemoveBtn.MouseButton1Click:Connect(function() ScreenGui:Destroy();end);             
  UserInputService.InputBegan:Connect(function(i,g) if ( not g and (i.KeyCode==Enum.KeyCode.LeftControl)) then MainFrame.Visible= not MainFrame.Visible;end end);print(     
  "✅ NHOP ");
