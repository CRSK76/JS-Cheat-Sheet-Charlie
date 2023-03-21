# Objekte

-> Math.max();
-> Math.min();

    const youngest = Math.min(
        // Maxim
        40,
        // Wojtek
        40,
        // Ronny
        26,
        // Andre
        36,
        // Charlie
        40,
        // Pemo
        35,
        // Jörg
        47,
        // Radwan
        31,
      // Nicole
         52,
         // Nawras
        33,
        // Stefanie
        34,
        // Arasch
        33,
        // Susann
        44,
        // Imad
        36,
        // Jan
        31,
        // Andreas
        32,
        // Simin
        48,
        // Stephie
        36,
        // Lilia
        54
    )

    console.log(`Die jüngste Person ist ${youngest} Jahre alt.`)

    // Älteste Person
    const oldest = Math.max(
        // Maxim
        40,
        // Wojtek
        40,
        // Ronny
        26,
        // Andre
        36,
        // Charlie
        40,
        // Pemo
        35,
        // Jörg
        47,
        // Radwan
        31,
        // Nicole
        52,
        // Nawras
        33,
        // Stefanie
        34,
        // Arasch
        33,
        // Susann
        44,
        // Imad
        36,
        // Jan
        31,
        // Andreas
        32,
        // Simin
        48,
        // Stephie
        36,
        // Lilia
        54
    )

    console.log(`Die älteste Person ist ${oldest} Jahre alt.`)


    // Durchschnittsalter
    const average = (40 + 40 + 26 + 36 + 40 + 35 + 47 + 31 + 52 + 33 + 34 + 33 + 44 + 36 + 31 + 32 + 48 + 36 + 54) / 19

    //console.log(`Das Durchschnittsalter beträgt ${average} Jahre.`)


    // Kasse
    //          Käse   Brot  2 x Batterien
    const sum = 3.33 + 1.99 + (2.27 * 2) + (2.25 * 0.5)
    //                 aufrunden auf den nächst höheren Cent
    const roundedSum = Math.round(sum * 100) / 100

    console.log(`Die Summe beträgt ${roundedSum} Euro.`)

    // Zufallszahl
    //                  0 - 0.9999999999999999
    const random = Math.random()
    const to49 = Math.floor(random * 49)
    const lotto1 = to49 + 1

    console.log(`Die erste Zufallszahl ist ${lotto1}`)