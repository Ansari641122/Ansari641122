- 👋 Hi, I’m @Ansari641122
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Ansari641122/Ansari641122 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
function UNICORN()
end
function SearchWrite(Search, Write, Type) gg.clearResults() gg.setVisible(false) gg.searchNumber(Search[1][1], Type) local count = gg.getResultCount() local result = gg.getResults(count) gg.clearResults() local data = {}  local base = Search[1][2]  if (count > 0) then for i, v in ipairs(result) do v.isUseful = true end for k=2, #Search do local tmp = {} local offset = Search[k][2] - base local num = Search[k][1] for i, v in ipairs(result) do tmp[#tmp+1] = {} tmp[#tmp].address = v.address + offset tmp[#tmp].flags = v.flags end tmp = gg.getValues(tmp) for i, v in ipairs(tmp) do if ( tostring(v.value) ~= tostring(num) ) then result[i].isUseful = false end end end for i, v in ipairs(result) do if (v.isUseful) then data[#data+1] = v.address end end if (#data > 0) then local t = {} local base = Search[1][2] for i=1, #data do for k, w in ipairs(Write) do offset = w[2] - base t[#t+1] = {} t[#t].address = data[i] + offset t[#t].flags = Type t[#t].value = w[1] if (w[3] == true) then local item = {} item[#item+1] = t[#t] item[#item].freeze = true gg.addListItems(item) end end end gg.setValues(t) gg.addListItems(t) else gg.toast("Value Not Found", false) return false end else gg.toast("Value Not Found") return false end end
function setvalue(A0_21, A1_22, A2_23)
local L3_24
L3_24 = {}
L3_24[1] = {}
L3_24[1].address = A0_21
L3_24[1].flags = A1_22
L3_24[1].value = A2_23
gg.setValues(L3_24)
end
function split(szFullString, szSeparator) local nFindStartIndex = 1 local nSplitIndex = 1 local nSplitArray = {} while true do local nFindLastIndex = string.find (szFullString, szSeparator, nFindStartIndex) if not nFindLastIndex then nSplitArray[nSplitIndex] = string.sub(szFullString, nFindStartIndex, string.len (szFullString)) break end nSplitArray[nSplitIndex] = string.sub (szFullString, nFindStartIndex, nFindLastIndex - 1) nFindStartIndex = nFindLastIndex + string.len (szSeparator) nSplitIndex = nSplitIndex + 1 end return nSplitArray end function xgxc(szpy, qmxg) for x = 1, #(qmxg) do xgpy = szpy + qmxg[x]["offset"] xglx = qmxg[x]["type"] xgsz = qmxg[x]["value"] xgdj = qmxg[x]["freeze"] if xgdj == nil or xgdj == "" then gg.setValues({[1] = {address = xgpy, flags = xglx, value = xgsz}}) else gg.addListItems({[1] = {address = xgpy, flags = xglx, freeze = xgdj, value = xgsz}}) end xgsl = xgsl + 1 xgjg = true end end function xqmnb(qmnb) gg.clearResults() gg.setRanges(qmnb[1]["memory"]) gg.searchNumber(qmnb[3]["value"], qmnb[3]["type"]) if gg.getResultCount() == 0 then gg.toast(qmnb[2]["name"] .. "Value Found") else gg.refineNumber(qmnb[3]["value"], qmnb[3]["type"]) gg.refineNumber(qmnb[3]["value"], qmnb[3]["type"]) gg.refineNumber(qmnb[3]["value"], qmnb[3]["type"]) if gg.getResultCount() == 0 then gg.toast(qmnb[2]["name"] .. "Value Found") else sl = gg.getResults(999999) sz = gg.getResultCount() xgsl = 0 if sz > 999999 then sz = 999999 end for i = 1, sz do pdsz = true for v = 4, #(qmnb) do if pdsz == true then pysz = {} pysz[1] = {} pysz[1].address = sl[i].address + qmnb[v]["offset"] pysz[1].flags = qmnb[v]["type"] szpy = gg.getValues(pysz) pdpd = qmnb[v]["lv"] .. ";" .. szpy[1].value szpd = split(pdpd, ";") tzszpd = szpd[1] pyszpd = szpd[2] if tzszpd == pyszpd then pdjg = true pdsz = true else pdjg = false pdsz = false end end end if pdjg == true then szpy = sl[i].address xgxc(szpy, qmxg) end end if xgjg == true then gg.toast(qmnb[2]["name"] .. "Value Found" .. xgsl .. "Value Found") else gg.toast(qmnb[2]["name"] .. "Value Found") end end end end function SearchWrite(Search, Write, Type) gg.clearResults() gg.setVisible(false) gg.searchNumber(Search[1][1], Type) local count = gg.getResultCount() local result = gg.getResults(count) gg.clearResults() local data = {} local base = Search[1][2] if (count > 0) then for i, v in ipairs(result) do v.isUseful = true end for k=2, #Search do local tmp = {} local offset = Search[k][2] - base local num = Search[k][1] for i, v in ipairs(result) do tmp[#tmp+1] = {} tmp[#tmp].address = v.address + offset tmp[#tmp].flags = v.flags end tmp = gg.getValues(tmp) for i, v in ipairs(tmp) do if ( tostring(v.value) ~= tostring(num) ) then result[i].isUseful = false end end end for i, v in ipairs(result) do if (v.isUseful) then data[#data+1] = v.address end end if (#data > 0) then local t = {} local base = Search[1][2] for i=1, #data do for k, w in ipairs(Write) do offset = w[2] - base t[#t+1] = {} t[#t].address = data[i] + offset t[#t].flags = Type t[#t].value = w[1] if (w[3] == true) then local item = {} item[#item+1] = t[#t] item[#item].freeze = true gg.addListItems(item) end end end gg.setValues(t) gg.toast("Value Found"..#t.."") gg.addListItems(t) else gg.toast("Value Found", false) return false end else gg.toast("Value Not Found") return false end end
function setvalue(A0_21, A1_22, A2_23)
local L3_24
L3_24 = {}
L3_24[1] = {}     
L3_24[1].address = A0_21
L3_24[1].flags = A1_22
L3_24[1].value = A2_23
gg.setValues(L3_24)
end
--------------------------------------------------------------------
so = gg.getRangesList("libil2cpp.so")[1].start
setvalue(so + "0x41E66D4", 4, "h 00 00 00 00")
setvalue(so + "0x42AEE18", 4, "h 00 00 00 00")
setvalue(so + "0x42B221C", 4, "h 00 00 00 00")
setvalue(so + "0x42B2504", 4, "h 00 00 00 00")
setvalue(so + "0x42B3A4C", 4, "h 00 00 00 00")
setvalue(so + "0x42B46E4", 4, "h 00 00 00 00")
setvalue(so + "0x590ECB8", 4, "h 00 00 00 00")
setvalue(so + "0x590ECC4", 4, "h 00 00 00 00")
setvalue(so + "0x590ECD0", 4, "h 00 00 00 00")
setvalue(so + "0x590ECDC", 4, "h 00 00 00 00")
setvalue(so + "0x590ECE8", 4, "h 00 00 00 00")
setvalue(so + "0x590ECF4", 4, "h 00 00 00 00")
setvalue(so + "0x590ED00", 4, "h 00 00 00 00")
setvalue(so + "0x590EDC8", 4, "h 00 00 00 00")
setvalue(so + "0x590EDE0", 4, "h 00 00 00 00")
setvalue(so + "0x590EDE4", 4, "h 00 00 00 00")
setvalue(so + "0x590EDEC", 4, "h 00 00 00 00")
setvalue(so + "0x590EDF4", 4, "h 00 00 00 00")
setvalue(so + "0x590EDF8", 4, "h 00 00 00 00")
setvalue(so + "0x590EE0C", 4, "h 00 00 00 00")
setvalue(so + "0x590EE10", 4, "h 00 00 00 00")
setvalue(so + "0x590EE18", 4, "h 00 00 00 00")
setvalue(so + "0x590EE28", 4, "h 00 00 00 00")
setvalue(so + "0x590EE2C", 4, "h 00 00 00 00")
setvalue(so + "0x590EE88", 4, "h 00 00 00 00")
setvalue(so + "0x590EE90", 4, "h 00 00 00 00")
setvalue(so + "0x590EE94", 4, "h 00 00 00 00")
setvalue(so + "0x590EFE4", 4, "h 00 00 00 00")
setvalue(so + "0x590F050", 4, "h 00 00 00 00")
gg.clearResults()
gg.setRanges(gg.REGION_CODE_APP | gg.REGION_C_ALLOC)
gg.searchNumber("h 7F 45 4C 46 01 01 01 00 00 00 00 00 00 00 00 00 03 00 28 00 01 00 00 00", gg.TYPE_BYTE)
gg.getResults(100000)
gg.editAll("h 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00", gg.TYPE_BYTE)
gg.clearResults()
