
SELECT 
	string_to_array(r.campaign,',','')::int[] AS "campaign", 
	c.dpid,rlm.dpid
FROM 
	ecrm_test.roles r,
	ecrm_test.role_location_maps rlm,
	ecrm_test.campaigns c
WHERE
	assigned_to = 1274
	AND
	assigned_role = r.id
	AND
	6 = ANY(string_to_array(r.campaign,',','')::int[])
	AND 
	c.dpid <@ rlm.dpid