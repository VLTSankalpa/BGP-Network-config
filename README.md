# Influencing BGP Route Selection Using AS-path Preprend

access-list 2 permit 2.2.2.0 0.0.0.255
!
route-map BGP-path-AS-path-2 permit 10
 match ip address 2
 set as-path prepend 600 600 600 600
!
router bgp 600
 neighbor 4.4.4.1 route-map BGP-path-AS-path-2 out

## advertise 2.2.2.2 & 2.2.2.3 networks with prepend AS path. due to implicit deny at the end of act 2 other any of routes will not advertise over R3.
