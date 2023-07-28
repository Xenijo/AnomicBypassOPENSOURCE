for i, v in pairs(getgc()) do
    if type(v) == "function" and not iselectronfunction(v) and not iscclosure(v) then
        local info = debug.getinfo(v)
        local constants = debug.getconstants(v)
        if table.find(constants, "FindPartOnRayWithWhitelist") and table.find(constants,"WalkSpeed") then
        if type(v) == "function" then 
hookfunction(v,function(...)
print(...)
return wait(9e9)
        end)
        end
        end
    end
end
local Speed
Speed =  hookmetamethod(game, "__index", function(t, k, v)
    if (not checkcaller() and t:IsA("Humanoid") and (k == "WalkSpeed" or k == "JumpPower")) then
        return 16
    end
    return Speed(t, k, v)
end)

local Speed
Speed =  hookmetamethod(game, "__newindex", function(t, k, v)
    if (not checkcaller() and t:IsA("Humanoid") and (k == "WalkSpeed" or k == "JumpPower")) then
        return
    end
    return Speed(t, k, v)
end)
print("Passed")
