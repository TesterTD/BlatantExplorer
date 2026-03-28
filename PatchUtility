local genv = getgenv()

if genv.BlatantBlatantBlatantieeeeeee then return end
genv.BlatantBlatantBlatantieeeeeee = true

local getgc = getgc
local rawget = rawget
local rawset = rawset
local type = type
local getmetatable = debug.getmetatable
local find = string.find
local gsub = string.gsub

task.spawn(function()
	local patched = {}

	while true do
		for _, v in getgc(true) do
			if type(v) ~= "table" then continue end

			local mt = getmetatable(v)
			if not mt or patched[mt] then continue end

			local mode = rawget(mt, "__mode")
			if type(mode) ~= "string" or not find(mode, "v", 1, true) then continue end

			rawset(mt, "__mode", gsub(mode, "v", ""))
			patched[mt] = true
		end

		task.wait(1)
	end
end)
