# SigScale OCS
This application implements functions used by communications service
providers (CSP) for authorization, rating and charging of prepaid
services. It is built to TM Forum standards with Open APIs for
management of product, service and balance. A web components front
end is also provided for standalone use.

## 3GPP Functions
This application conforms to 3GPP specifications for the interfaces,
protocols and procedures of the OCS, PCRF, HSS and 3GPP AAA Server
functions in the 3GPP reference architecture.

### AAA
Authentication, authorization and accounting (AAA) functions are the
foundation to commercial operations of a CSP. Subscriber credentials
may (optionally) be stored internally or provided by an external
Home Subscriber Server (HSS).  Authentication is performed using
EAP methods (AKA/AKA', PWD, TTLS). Supports 3GPP SWm, STa and SWx
interfaces as well as RADIUS.

### OCS
A Online Charging System (OCS) performs real-time charging for
services. An OCS authorizes subscribers' sessions subject to
available credit on account and decrements account balance as
services are consumed.  When a subscriber's account balance is
depleted authorization may be withdrawn and ongoing session(s)
terminated. Supports 3GPP Gy and Ro interfaces as well as RADIUS.

### PCRF
A Policy Control and Charging Rules Function (PCRF) encompasses
policy control decision and flow based charging control
functionalities. The PCRF provides network control regarding the
service data flow detection, gating, QoS and flow based charging.
Supports the 3GPP Gx interface.

## Graphical User Interface (GUI)
A web front end built with web components for material design
provides simple guided management of Product Offerings & Prices,
Subscribers, Balance Buckets and NAS clients. Provisioning common
authorization attributes as well as viewing usage and access
logs is supported. Uses TM Forum Open APIs exclusively.

## Interfaces

### REST
Most aspects of provisioning and operations may be performed
through integration using an HTTP RESTful interface. Specifically
the TM Forum Open APIs are supported including: Product Catalog,
Product Inventory, Prepay Balance, Service Inventory, Resource
Inventory and Usage Management.

### DIAMETER
SigScale OCS supports the DIAMETER applications for the 3GPP
interfaces of an OCS (Ro/Gy/Wo) (3GPP 32.299), PCRF (Gx),
HSS (S6a) and AAA Server (STa/SWm/SWx,S6b), The OCS function
supports Session Charging with Unit Reservation (SCUR) and
Event Charging with Unit Reservation (ECUR) in CS, PS and IMS
domains with both centralized and distributed unit determination.
Non-3GPP access is supported for ePDG with either internal HSS
or proxy over SWx to external HSS.

### RADIUS
The OCS acts as an authentication, authorization and accounting
(AAA) server for network access servers (NAS) using the RADIUS
protocol such as wireless local area network (WLAN) access points
(AP), broadband remote access server (BRAS) or broadband network
gateway (BNG).

### SNMP
A Simple Network Management Protocol (SNMP) agent is included
which allows a Network Management System (NMS) to interogate the
Management Information Bases (MIB) supported including RADIUS
and DIAMETER MIBs.

### Prometheus
A Prometheus exporter provides signaling traffic statstics.

