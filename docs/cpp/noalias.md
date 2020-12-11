---
description: 'Hakkında daha fazla bilgi edinin: `noalias`'
title: noalias
ms.date: 07/07/2020
f1_keywords:
- noalias_cpp
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
ms.openlocfilehash: 56306404fc79ea851835ae5913bbdb0b297ba880
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97161657"
---
# `noalias`

**Microsoft'a özgü**

**`noalias`** bir işlev çağrısının görünür genel durumu değiştirmediği veya başvurmayacağı ve yalnızca işaretçi *parametrelerine göre işaret* edilen belleği değiştirmeyeceği anlamına gelir (ilk düzey inyönler).

Bir işleve olarak ek açıklama eklendiğinde **`noalias`** , iyileştirici yalnızca parametrelerin kendileri ve işaretçi parametrelerinin yalnızca birinci düzeyindeki yönlere başvurulduğunu veya işlevin içinde değiştirildiğini varsayabilir.

**`noalias`** Ek açıklama yalnızca açıklamalı işlevin gövdesinde geçerlidir. İşlevin olarak işaretlenmesi **`__declspec(noalias)`** , işlev tarafından döndürülen işaretçilerin diğer adını etkilemez.

Diğer ad ve diğer açıklamaları etkileyebilecek diğer bir açıklama için bkz [`__declspec(restrict)`](../cpp/restrict.md) ..

## <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir **`__declspec(noalias)`** .

`multiply`Belleğe erişen işleve ek açıklama eklendiğinde **`__declspec(noalias)`** , derleyiciye bu işlevin parametre listesindeki işaretçiler dışında genel durumu değiştirmediğini söyler.

```C
// declspec_noalias.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1/k++;
    return a;
}

__declspec(noalias) void multiply(float * a, float * b, float * c)
{
    int i, j, k;

    for (j=0; j<P; j++)
        for (i=0; i<M; i++)
            for (k=0; k<N; k++)
                c[i * P + j] =
                          a[i * N + k] *
                          b[k * P + j];
}

int main()
{
    float * a, * b, * c;

    mempool = (float *) malloc(sizeof(float) * (M*N + N*P + M*P));

    if (!mempool)
    {
        puts("ERROR: Malloc returned null");
        exit(1);
    }

    memptr = mempool;
    a = init(M, N);
    b = init(N, P);
    c = init(M, P);

    multiply(a, b, c);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[`__declspec`](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[`__declspec(restrict)`](../cpp/restrict.md)
