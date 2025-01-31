# Outlines

# Outlines

> Lots of outlines examples are already available in [official reference](https://typst.app/docs/reference/meta/outline/)

## Table of contents

```
#outline()

= Introduction
#lorem(5)

= Prior work
#lorem(10)
```

## Outline of figures

```
#outline(
  title: [List of Figures],
  target: figure.where(kind: table),
)

#figure(
  table(
    columns: 4,
    [t], [1], [2], [3],
    [y], [0.3], [0.7], [0.5],
  ),
  caption: [Experiment results],
)
```

You can use arbitrary selector there, so you can do any crazy things.

<!--TODO: crazy example with labels and selector combinations-->

## Ignore low-level headings

```
#set heading(numbering: "1.")
#outline(depth: 2)

= Yes
Top-level section.

== Still
Subsection.

=== Nope
Not included.
```

## Set indentation

```
#set heading(numbering: "1.a.")

#outline(
  title: [Contents (Automatic)],
  indent: auto,
)

#outline(
  title: [Contents (Length)],
  indent: 2em,
)

#outline(
  title: [Contents (Function)],
  indent: n => [→ ] * n,
)

= About ACME Corp.
== History
=== Origins
#lorem(10)

== Products
#lorem(10)
```

## Replace default dots

```
#outline(fill: line(length: 100%), indent: 2em)

= First level
== Second level
```

## Make different outline levels look different

```
#set heading(numbering: "1.")

#show outline.entry.where(
  level: 1
): it => {
  v(12pt, weak: true)
  strong(it)
}

#outline(indent: auto)

= Introduction
= Background
== History
== State of the Art
= Analysis
== Setup
```