# Blockscope
    
    // var, let, const
    // global

    var vOuter = 'var-outer';
    let lOuter = 'let-outer';
    const cOuter = 'const-outer';

    if (true) {
        // block
        console.log('var innerhalb vom block -', vOuter);
        console.log('let innerhalb vom block -', lOuter);
        console.log('const innerhalb vom block -', cOuter);

        var vInner = 'var-inner';
        let lInner = 'let-inner';
        const cInner = 'const-inner';

        console.log('var i innerhal vom block -', vInner);
        console.log('let i innerhalb vom block -', lInner);
        console.log('const i innerhalb vom block -', cInner);
        // child nicht erreichbar - weil parent block

    if (true) {
        // block in block == child block
        console.log('let i innerhalb vom child block -', lInner);
        console.log('let o innerhalb vom child block -', lOuter);

        let child = 'let-child-block';

        {
            var test;
            // child ist erreichbar - weil child block
        }
    }

    // console.log('let child innerhalb vom block -', child);

    }

    if (true) {
            let lInner = 'another block';
    }

    let lInner = 'let global';
    const cInner = 'const global';

    console.log('var i ausserhalb vom block -', vInner);
    console.log('let i ausserhalb vom block -', lInner);
    console.log('const i ausserhalb vom block -', cInner);


    console.log('var ausserhalb vom block -', vOuter);
    console.log('let ausserhalb vom block -', lOuter);
    console.log('const ausserhalb vom block -', cOuter);


