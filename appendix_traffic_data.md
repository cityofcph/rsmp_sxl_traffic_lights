Appendix - traffic data
=======================

Traffic data (S0201-S0204) needs additional requirements in order to work
correctly.

# Traffic counting must be made at even time intervals.
  For instance; if **updateRate=300** (every 5 minutes) is set at the
  status subscription, the traffic counter must start at 15:00:00,
  15:05:00, 15:10:00 and so on.

# No initial status update should be sent directly after receiving status
  subscription. Status updates should only be sent at even time intervals
  and not contain partial counting, e.g. 15:01-15:03 if updateRate=300

# The traffic counter must not reset its traffic counter after receiving
  a new subscription request. The traffic counter may only reset its
  traffic counter at even time intervals.
 
# Buffering of traffic data during connection interruptions should be
  possible to enable/disable in the equipment. If buffering is enabled it
  means that active subscriptions of traffic data (S0201-S0204) should remain
  active and not be canceled at connection interruption or at reestablishment.

# The traffic data must be buffered according to the time interval as
  determined by the status subscription if buffering is enabled.
