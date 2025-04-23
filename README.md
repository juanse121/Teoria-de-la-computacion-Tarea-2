# Teoria-de-la-computacion-Tarea-2

## Members
- Juan Sebastián Cortés Montoya  
- Sebastián Zapata Rendón

## Development Environment
- Operating System: Ubuntu 22.04 on WSL (Windows Subsystem for Linux)
- Tools:
  - GHC (Haskell Compiler)
  - Lambda Shell (lambdabot or custom shell)

## How to Run
1. Install Lambda Shell by following the instructions at: https://asr.github.io/courses/programs-installations-tips-and-tricks.pdf  
2. Open the WSL terminal and run `lambdaShell`.  
3. Enter the following definitions and tests into the shell:

```haskell
let true = \x.\y.x
let false = \x.\y.y
let pair = \m.\n.\z.z m n
let fst = \p.p true
let snd = \p.p false
let cero = \x.x
let suc = \n.pair false n
let iszero = \x.x true
let pred = \x.x false
let succ = \x.(\z.z false x)
```

### Test Evaluations
```haskell
true (\x.x) (\y.y)               -- Result: \x. x
false (\a.a) (\b.b)             -- Result: \b. b
fst (pair (\s.s) (\t.t))        -- Result: \s. s
snd (pair (\u.u) (\v.v))        -- Result: \v. v
pair (\m.m) (\n.n) true         -- Result: \m. m
pair (\p.p) (\q.q) false        -- Result: \q. q
suc cero                          -- Result: \z. z (\x y. y) cero
pred cero                         -- Result: false
pred (suc cero)                   -- Result: cero
iszero cero                       -- Result: true
iszero (suc cero)                 -- Result: false
```

## Repository
(A public repository is not required; submission is done via EAFIT Interactiva.)

## Reference Sources
- SI1001 course notes  
- Lambda Shell course on GitHub: https://asr.github.io/lambdashell/  
- ChatGPT for help with writing and organization
