# Crayon

Crayon is a stack-based programming language based on a 2-dimensional output canvas. More spec will come soon, then an interpreter sometime later.

## Spec

#### Output manipulation

| Char | Action
| --- | ---
| `N` | point cursor N
| `S` | point cursor S
| `E` | point cursor E
| `W` | point cursor W
| `n` | move cursor N by 1
| `s` | move cursor S by 1
| `e` | move cursor E by 1
| `w` | move cursor W by 1
| `L` | turn cursor 90° counter|clockwise
| `R` | turn cursor 90° clockwise
| `U` | turn cursor 180°
| `l` | turn cursor 45° counter|clockwise
| `r` | turn cursor 45° counter|clockwise
| `u` | start next line
| `f` | move cursor forward by 1
| `F` | pop `X`, move cursor forward by `X`
| `m` | pop `X`, pop `Y`, move cursor by (x: `X`, y: `Y`)
| `M` | pop `X`, pop `Y`, move cursor to (x: `X`, y: `Y`)
| `x` | pop `X`, move cursor by (x: `X`)
| `y` | pop `Y`, move cursor by (y: `Y`)
| `X` | pop `X`, set cursor X to `X`
| `Y` | pop `Y`, set cursor Y to `Y`
| `q` | pop `X`, draw pattern `X` at cursor, push `X`
| `Q` | pop `X`, fill canvas with pattern `X`, push `X`
| `k` | push canvas as pattern
| `K` | pop `X`, set canvas to pattern `X`
| `P` | pop `X`, pretend `X` is the canvas, push `X`
| `p` | quit pretending

More spec to come...