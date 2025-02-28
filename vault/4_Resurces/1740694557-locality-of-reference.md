---
id: 1740694557-locality-of-reference
aliases:
  - Locality Of Reference
tags: []
---

# Locality Of Reference

In computer science, locality of reference, also known as the principle of locality, 
is the tendency of a processor to access the same set of memory locations repetitively 
over a short period of time. There are two basic types of reference locality – temporal 
and spatial locality. Temporal locality refers to the reuse of specific data and/or 
resources within a relatively small time duration. Spatial locality (also termed data locality) 
refers to the use of data elements within relatively close storage locations. 
Sequential locality, a special case of spatial locality, occurs when data elements 
are arranged and accessed linearly, such as traversing the elements in a one-dimensional array. 

Types of locality:
- [[1740694473-temporal-locality|Temporal Locality]]
- [[1740694481-spatial-locality|Spatial Locality]]
- [[1740694493-memory-locality|Memory Locality]]
- [[1740694512-branch-locality|Branch Locality]]
- [[1740694524-equidistant-locality|Equidistant Locality]]

> [!TIP]
> - Predictability
> - Structure of the program
> - Linear Data structures
> - Efficiency of memory hierarchy use

The systems can benefits from locality:
- Increasing the locality of reference => software side 
- Exploiting the locality of reference => hardware side especially temporal and spatial can be used in hierarchical 
storage hardware. 
