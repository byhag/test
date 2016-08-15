# JBKLabs intern coding challenge

## Description

Using `blackbox` (a SAT technology planning system), write a PDDL program to solve the classic Tower of Hanoi problem.  This exercise should take about an hour.  Please provide a Git repo with commits for each step of development, showing your thought process.  This challenge is in the category of artificial intelligence.

## Resources

### Blackbox binaries: 
[https://www.cs.rochester.edu/u/kautz/satplan/blackbox/](https://www.cs.rochester.edu/u/kautz/satplan/blackbox/
)

### Problem source (`hanoi-problem.pddl`):
```pddl
(define (problem hanoi-problem)
  (:domain hanoi)
  (:objects peg1 peg2 peg3 disk1 disk2 disk3)
  (:init
    (smaller peg1 disk1) (smaller peg1 disk2) (smaller peg1 disk3)
    (smaller peg2 disk1) (smaller peg2 disk2) (smaller peg2 disk3)
    (smaller peg3 disk1) (smaller peg3 disk2) (smaller peg3 disk3)
    (smaller disk2 disk1) (smaller disk3 disk2) (smaller disk3 disk1)
    (topmost peg2) (topmost peg3) (topmost disk1)
    (on disk3 peg1) (on disk2 disk3) (on disk1 disk2)
  )
  (:goal (and (on disk3 peg3) (on disk2 disk3) (on disk1 disk2)))
)
```

### Problem solver (`hanoi.pddl`):
```pddl
(define (domain hanoi)
  (:requirements :strips)
  ;; TODO
)
```

### Running (`*nix`):
```bash
./ blackbox -o hanoi.pddl -f hanoi-problem.pddl
```
