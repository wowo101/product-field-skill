# The Product Field — Geographic Model

The Product Field is a cognitive medium for product innovation. It provides a geographic model — a two-dimensional coordinate system where spatial position encodes meaning — that supports systematic exploration, validation, and evaluation of product innovations.

This file describes the model's structure. For individual aspect definitions, see `aspects.md`. For the relational grammar and validation sentences, see `relations.md`.

## Conceptual Space

The Product Field's conceptual space is defined by two orthogonal dimensions derived from the canonical definition of product innovation: the creation and market introduction of new, redesigned or substantially improved products.

### Axes

**Introduction** (horizontal: Inside → Outside) — A product originates inside an organization and must be introduced to users and customers outside of it. This dimension captures the inside-to-outside trajectory every product follows.

**Realization** (vertical: Purpose → Implementation) — A product exists to achieve a certain purpose for its stakeholders and is implemented to realize that purpose. This dimension captures the purpose-to-implementation trajectory.

Together these axes form a finite Cartesian coordinate system with the product at the origin, midway between inside and outside, purpose and implementation.

### The Canvas

The conceptual space is visually represented as a canvas. The center of the canvas corresponds to the coordinate system's origin. Every fact about a product innovation maps to a position on the canvas based on which aspect it belongs to.

```
                          PURPOSE
                             ^
                             |
           IDEA              |              VALUE
        (inside+purpose)     |        (outside+purpose)
                             |
    GOALS ─── uniqueness ─── problem ─── MOTIVATIONS
      |                      |                      |
   DRIVERS                   |                   USERS
      |                      |                      |
  INSIDE ─────────────── [PRODUCT] ─────────────── OUTSIDE
      |                      |                      |
   ENABLERS                  |                 CUSTOMERS
      |                      |                      |
  PRODUCTION ── solution ─── alternatives ── DISTRIBUTION
                             |
        RESOURCES            |            MARKET
      (inside+impl)          |        (outside+impl)
                             |
                             v
                       IMPLEMENTATION
```

## Three Layers

The model organizes its thirteen aspects into three concentric layers, each representing a different level of abstraction.

### Center

The product itself — a physical or virtual good or service created inside an organization, introduced outside of it, and implemented to achieve a certain purpose. It sits at the origin of the coordinate system. The center is a singleton: one canvas describes one product.

### Core (Value Proposition)

The four aspects that define the product's value proposition — its specific promise of value to users and customers:

- **problem** (top-right of core) — what the product addresses
- **solution** (bottom-left of core) — how the product addresses it
- **uniqueness** (top-left of core) — what makes this product distinct
- **alternatives** (bottom-right of core) — what exists instead

The core zone surrounds the center on the canvas. At its core, every innovation is a promise of value.

### Context

The eight aspects that represent the environment in which the product is created, realized, introduced, and used — the interacting stakeholders, objectives, and means of innovation:

- **GOALS** (inside + purpose) — organizational objectives the product serves
- **DRIVERS** (inside, between purpose and implementation) — people and teams inside the organization who push the product forward
- **ENABLERS** (inside + implementation) — assets, capabilities, and know-how available to the organization
- **PRODUCTION** (inside + implementation) — processes and systems that build the product
- **DISTRIBUTION** (outside + implementation) — channels and mechanisms that deliver the product to customers
- **CUSTOMERS** (outside, between purpose and implementation) — people and organizations who pay for or procure the product
- **USERS** (outside + purpose) — people who directly use and interact with the product
- **MOTIVATIONS** (outside + purpose) — needs, desires, and jobs-to-be-done that drive users and customers

The context zone forms the outermost ring of the canvas. The context of an innovation determines its chances of success.

### Layer Relationships

Center, core, and context are mutually exclusive and complementary. Every fact about a product innovation belongs to exactly one aspect in exactly one layer. The layers interact through the relational grammar described in `relations.md`.

## Four Elements (Corners)

The aspects can be aggregated into four elements, each occupying one quadrant of the canvas. Each element represents a distinct dimension of innovation.

### IDEA (top-left: inside + purpose)

The internal vision and ambition behind the product.

- Context aspects: GOALS, DRIVERS
- Core aspect: uniqueness
- Validation quality: **Viability** — does the product express a practical business idea?

### VALUE (top-right: outside + purpose)

The external demand and user need the product addresses.

- Context aspects: USERS, MOTIVATIONS
- Core aspect: problem
- Validation quality: **Desirability** — does the product create real user value?

### RESOURCES (bottom-left: inside + implementation)

The internal capabilities and execution capacity.

- Context aspects: ENABLERS, PRODUCTION
- Core aspect: solution
- Validation quality: **Feasibility** — can the product be realized with available resources?

### MARKET (bottom-right: outside + implementation)

The external landscape of distribution and competition.

- Context aspects: DISTRIBUTION, CUSTOMERS
- Core aspect: alternatives
- Validation quality: **Marketability** — is there a sufficiently large and addressable market?

## The Diagonal

The fundamental movement of product innovation runs diagonally from **IDEA** (top-left) to **MARKET** (bottom-right). A product begins as an internal vision driven by purpose and must ultimately reach an external market through implementation.

This diagonal trajectory — from inside+purpose to outside+implementation — is the primary axis of progress. The force field analysis (see below) reveals what pushes a product along this trajectory and what holds it back.

The secondary diagonal runs from **RESOURCES** (bottom-left) to **VALUE** (top-right). Resources enable the creation of value; value justifies the investment of resources.

## Core/Context Fit

A product innovation succeeds when its means and objectives (context) support the realization of its value proposition (core), and the product is successfully introduced to users and customers.

This fit between core and context is validated using the Product Field's grammar — four sentence templates that connect aspects through each element. When these sentences hold empirically, the innovation has core/context fit. See `relations.md` for the full grammar and validation templates.

The four validation qualities — desirability, viability, feasibility, marketability — correspond to the four elements and together describe the overall health of a product innovation.

## Force Field

Once strengths and weaknesses of a product's context are identified through evaluation, their combined effect can be visualized as a force field along the introduction dimension (inside → outside).

Forces can:
- **Push** the product from inside to outside (strengths that propel introduction)
- **Pull** the product from outside (demand or market forces that attract the product)
- **Hold back** (weaknesses, gaps, or counterproductive forces that impede progress)

Patterns of counterproductive forces mark the points with the highest risk of failure. Steering product innovation means alleviating these risks while leveraging existing strengths to amplify positive forces.

An advanced state of innovation with a high probability of success is represented by a steady flow from left to right — from inside to outside.

## Character Types

The character of a product innovation is defined by the relative contribution of each of its four elements. When one element dominates, the innovation exhibits a recognizable type:

- **Idea Push** — strongest in IDEA. Strong drivers with clear goals and distinctive uniqueness push the idea from inside toward users and customers. Needs a driver with power over enablers and a clear purpose.
- **Value Pull** — strongest in VALUE. Deep understanding of users, motivations, and needs pulls toward usage of the product. Purpose is turning satisfied users into paying customers.
- **Resources Push** — strongest in RESOURCES. Strong enablers empower production to build a solution, pushing from resources to users and customers. Implementation capability drives innovation.
- **Market Pull** — strongest in MARKET. Finding and reaching customers, scaling distribution, and outcompeting alternatives pulls toward market adoption. Distribution power drives adoption.

Most real innovations are blends. The character type indicates where the primary energy comes from, and where attention may need to be redirected.

## The Meta-Method Principle

The Product Field does not prescribe how to gather insights. It is a meta-method — a geographic structure that tells you where insights are needed and how they connect.

Established methods each illuminate specific regions of the field:
- JTBD illuminates the VALUE corner (users, motivations, problem)
- Lean Canvas maps across multiple aspects with emphasis on problem and solution
- Design Thinking focuses on desirability (VALUE) and feasibility (RESOURCES)
- Business Model Canvas spans the full field with emphasis on MARKET and RESOURCES

When the Check or Find steps reveal a gap, the position of the gap on the canvas tells you which method to reach for. See `methods.md` for the method library mapped to PF regions.

## Workflow

The Product Field provides a four-step workflow for systematically working with the model:

1. **Frame** — establish shared understanding of the model's structure and vocabulary
2. **Map** — gather and organize facts about the product innovation onto the canvas
3. **Check** — validate consistency and core/context fit using the relational grammar
4. **Find** — evaluate strengths and weaknesses, generate the force field, determine character

These steps are not strictly sequential. You can revisit any step as understanding deepens. The canvas is a living document that evolves through iterative exploration.

---

*The Product Field is by Klaus-Peter Frahm, Michael Schieben, and Wolfgang Wopperer-Beholz. The model structure is licensed CC BY-SA 4.0. This reference file contains original content informed by and building on the Product Field framework.*
