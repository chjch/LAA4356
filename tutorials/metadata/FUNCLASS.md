# Functional Class

## Definition

Functional Class defines a hierarchical network used to determine a logical and
efficient route for a traveler.

## Value

| Code  | Description    |
|-------|----------------|
| space | Not Applicable |
| 1     | Level 1        |
| 2     | Level 2        |
| 3     | Level 3        |
| 4     | Level 4        |
| 5     | Level 5        |

## Length

1

## Type

Text

## Usage

Functional Class can be used to determine sets of links that form connected
graphs.

## Specification

- The arterial network is connected. Each link has at least one connection in
  the network to every other link with the same **Functional Class** via a link
  with the same or higher functionality.
- `Functional Class = 1` roads allow for high volume, maximum speed traffic
  movement between and through major metropolitan areas.
  - `Functional Class = 1` is applied to roads with very few, if any, speed
    changes.
    Access to the road is usually controlled.
- `Functional Class = 2` roads are used to channel traffic to
  `Functional Class = 1` roads for travel between and through cities in the
  shortest amount of time.
  - `Functional Class = 2` is applied to roads with very few, if any speed
    changes that allow for high volume, high speed traffic movement.
- Functional Class = 3 is applied to roads which interconnect
  `Functional Class = 2` roads and provide a high volume of traffic movement at
  a lower level of mobility than `Functional Class = 2` roads.
- `Functional Class = 4` is applied to roads which provide for a high volume of
  traffic movement at moderate speeds between neighborhoods.
  These roads connect with higher functional class roads to collect and
  distribute traffic between neighborhoods.
- `Functional Class = 5` is applied to roads whose volume and traffic movement
  are below the level of any functional class. In addition, walkways, truck
  only roads, bus only roads, and emergency vehicle only roads receive
  `Functional Class = 5`.
  The following also receive Functional Class = 5:
  - Access roads, parking lanes, and connections internal to select POIs in
    North America.
  - Roads in marginal and illegal settlements in developing countries.
- Functional Class = Not Applicable is applied to non-navigable links.
- As a general rule, Functional Class assignments have no direct correlation
  with other road attributes like speed, controlled access, route type, etc.
  While in general `Functional Class = 1` roads are controlled access this is
  not always the case, and it is also not the case that all controlled access
  roads are `Functional Class = 1`
- The Functional Class network is a hierarchical classification of roads based
  on reality. Density and pattern of each Functional Class level is influenced
  by the physical road network that exists in reality.
  Physical road network density variations between countries and between
  regions within a country are reflected in the Functional Class network.
  For example, the density of the road network differs between North American
  and European countries.
  Even within the U.S., for instance, density will vary from the East Coast to
  the West Coast.
- `Functional Class = 1, 2, 3, and 4` roads are connected to form a
  comprehensive road network for navigation of long distance, mid-range and
  short routes in any given coverage area.
