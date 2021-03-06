---
layout: default 
title: Home
---

#### Pawel
* Exponential growth

#### Confusion
* Confusion in petri nets

#### Related Things
[Event Structures - http://www.cl.cam.ac.uk/~gw104/EvStr.pdf](http://www.cl.cam.ac.uk/~gw104/EvStr.pdf)

[Removing Confusion - https://arxiv.org/pdf/1710.04570.pdf](https://arxiv.org/pdf/1710.04570.pdf)

[Pawel Sobocinski - https://www.semanticscholar.org/paper/Representations-of-Petri-Net-Interactions-Sobocinski/5af3fa656639d55afdfde980a74878c1d0a84ba8](https://www.semanticscholar.org/paper/Representations-of-Petri-Net-Interactions-Sobocinski/5af3fa656639d55afdfde980a74878c1d0a84ba8)

----

#### Maintaining

- [edit](https://github.com/PetriNets/petrinets.github.io/edit/master/index.md)
- [markdown guide](https://guides.github.com/features/mastering-markdown/).

<script>
    // pnet1
    var states_pnet1 = [
        {label:'a', y:10, x:20},
        {label:'b', y:30, x:20},
        {label:'c', y:10, x:80},
        {label:'d', y:30, x:80},
        {label:'queue', y:20, x:50},
    ]

    var transitions_pnet1 = [
        {label: 'x', y: 20, x: 30,
            pre: {a: 1},
            post: { queue: 1, b: 1 }
        },
        {label: 'y', y: 20, x: 10,
            pre: {b: 1},
            post: {a: 1}
        },
        {label: 'w', y: 20, x: 70,
            pre: {queue: 1, d: 1},
            post: {c: 1}
        },
        {label: 'z', y: 20, x: 90,
            pre: {c: 1},
            post: {d: 1}}
    ];

    var marking_pnet1 = {a: 1, d: 1};
    // end pnet1    

    // pnet2
    var states_pnet2 = [
        {label:'a', y:60, x:20},
        {label:'b0', y:30, x:100},
        {label:'b1', y:90, x:100},
        {label:'d0', y:30, x:180},
        {label:'d1', y:90, x:180},
        {label:'c', y:60, x:260}
    ]

    var transitions_pnet2 = [
        {label: 'x', y: 60, x: 60,
            pre: {a: 1},
            post: { b0: 1, b1: 1 }
        },
        {label: 'z0', y: 30, x: 140,
            pre: {b0: 1},
            post: {d0: 1}
        },
        {label: 'z1', y: 90, x: 140,
            pre: {b1: 1},
            post: {d1: 1}
        },
        {label: 'y', y: 60, x: 220,
            pre: { d0: 1, d1: 1 },
            post: {c: 1}}
    ];

    var marking_pnet2 = {a: 1};
    // pnet 2

    // pnet 3
    var states_pnet3 = [
        { label: 'a', y: 30, x: 10 },
        { label: 'b', y: 30, x: 30 },
        { label: 'c', y: 30, x: 90 },
        { label: 'd', y: 30, x: 70 },
        { label: 'queue', y: 30, x: 50 },
    ]
    var transitions_pnet3 = [
        {
            label: 'x', y: 20, x: 30,
            pre: { a: 1 },
            post: { queue: 1, b: 1 }
        },
        {
            label: 'y', y: 40, x: 30,
            pre: { b: 1, queue: 1 },
            post: { a: 1 }
        },
        {
            label: 'w', y: 20, x: 70,
            pre: { queue: 1, d: 1 },
            post: { c: 1 }
        },
        {
            label: 'z', y: 40, x: 70,
            pre: { c: 1 },
            post: { d: 1, queue: 1 }
        }
    ];

    var marking_pnet3 = { a: 1, d: 1 };
    //end pnet3

    scaleModel(transitions_pnet1, states_pnet1, 4, 4);
    scaleModel(transitions_pnet3, states_pnet3, 4, 4);

    // drawing stuffs
    drawNet('#pnet1', states_pnet1, transitions_pnet1, marking_pnet1);
    drawNet('#pnet2', states_pnet2, transitions_pnet2, marking_pnet2);
    drawNet('#pnet3', states_pnet3, transitions_pnet3, marking_pnet3);
</script>