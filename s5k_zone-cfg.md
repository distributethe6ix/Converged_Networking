**S5000 and MXL Zoning**

conf t
\*\*\*\*ENABLE FC SWITCHING\*\*\*\*
feature fc
fc switch-mode fabric-services
\*\*\*\*VERY FLOGIs\*\*\*\*
show fc ns fabric
show fc ns database
\*\*\*\*CREATE ALIASES\*\*\*\*
fc alias [name] \*\*REPEAT FOR MULTIPLE ALIASES\*\*
member [pWWN]
exit
\*\*\*\*CREATE ZONES\*\*\*\*
fc zone [name of zone] \*\*REPEAT FOR MULTIPLE ZONES\*\*
member [alias 1]
member [alias 2]
exit
exit
show fc zone \*\*VERIFY ZONES AND MEMBERS\*\*
\*\*\*\*CREATE ZONESET AND ADD ZONES\*\*\*\*\*
conf t
fc zoneset [name]
member [your zone]
member [your zone 2]
...
member [zone name]
exit
\*\*\*\*ACTIVATE ZONESET\*\*\*\*
fcoe-map default\_full\_fabric
fc-fabric
active-zoneset [name]
exit
exit
exit
\*\*\*\*VERIFY ZONESET is ACTIVE\*\*\*\*
do show fc zoneset active
