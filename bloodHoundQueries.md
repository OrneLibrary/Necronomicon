# BloodHound Queries
Below are queries that can used to show specific items inside of BlooHound.

## Map DAs that contain strings.
Change `SVC` or `SERVICE` to the strings you are looking for.

`MATCH (n:Group) WHERE n.objectid =~ "(?i)S-1-5-21-.*-512" WITH n MATCH p=(n)<-[r:MemberOf*1..]-(m) WHERE m.name CONTAINS "SVC" OR m.name CONTAINS "SERVICE"  RETURN n,r,m`
