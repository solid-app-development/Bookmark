# Annotating URIs in the Decentralized World

## Introduction

As we build a decentralized web, one recurring pattern emerges: **the need to annotate URIs**. Whether it’s adding metadata to a webpage, describing a resource, or linking additional context to an entity, annotating existing URIs is a fundamental capability. This approach simplifies design patterns and improves interoperability—making it easier for different systems to understand and work with shared data.

## The Two Approaches

When dealing with bookmarks (or any referenced resources in RDF), there are two common ways to structure the data:

1. **Direct Annotation (Simple Approach)** – The bookmark **is** the URI, and additional metadata is attached directly to it.
2. **Minted Identifiers (Complex Approach)** – A new URI is created to represent the bookmark, which then references the original URI.

While both are valid approaches, the direct annotation model (1) has strong advantages in a decentralized world, where simplicity and interoperability matter most.

## Why Direct Annotation Works Best

### 1. **Simplicity Leads to Adoption**
The simplest solutions tend to see the widest adoption. If every system needs to create a new URI just to add metadata to an existing one, it increases complexity without clear benefits. Direct annotation allows agents to attach data without unnecessary indirection.

### 2. **URIs Are First-Class Citizens**
In RDF and the Semantic Web, a URI is already an entity that can be described. There’s no inherent need to wrap it in another identifier just to annotate it. For example, if we want to mark a webpage as a bookmark with a timestamp, we can directly reference it:

```turtle
<https://example.com/article> a bookm:Bookmark ;
    dcterms:created "2025-03-15T12:00:00Z"^^xsd:dateTime ;
    dcterms:title "A Great Article" .
```

This keeps things straightforward and avoids creating an unnecessary layer of abstraction.

### 3. **Scalability in the Decentralized Web**
A decentralized web consists of many independent agents interacting with shared resources. If each agent mints a new identifier for every annotation, discoverability and interoperability suffer. By keeping annotations directly attached to existing URIs, different agents can contribute to a shared knowledge graph without needing reconciliation processes.

### 4. **Alignment with Other Decentralized Patterns**
Many decentralized web technologies—such as linked data notifications (LDN), WebMention, and ActivityPub—rely on referencing external URIs directly rather than wrapping them in new identifiers. The direct annotation model aligns well with these existing approaches, reinforcing a unified design philosophy.

## When Minted URIs Make Sense

There are cases where minting a new URI is useful, such as:

- **Versioning & Historical Records** – If you need to track different states of a bookmark over time, using a new URI for each instance can be beneficial.
- **User-Specific Context** – If a bookmark is personal and independent of the original resource (e.g., private notes), a minted identifier can prevent collision with others' annotations.
- **Aggregation & Provenance** – When multiple sources contribute metadata to the same URI, wrapping it in a new entity can help track provenance.

However, these cases are exceptions rather than the norm. Defaulting to direct annotation ensures we maintain simplicity where it’s most effective.

## Conclusion

The decentralized web thrives on **interoperability, simplicity, and shared understanding**. By annotating URIs directly instead of minting new identifiers unnecessarily, we create a more connected and accessible ecosystem. While there are scenarios where minted URIs are valuable, they should be used judiciously. The default should be **to treat URIs as first-class entities that can be annotated directly**.
