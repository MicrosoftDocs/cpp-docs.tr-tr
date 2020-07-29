---
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: a0108cff3d6b98fd929b7888d2ad718e7b6b3a64
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213261"
---
# <a name="restrict"></a>restrict

**Microsoft'a Özgü**

Bir işaretçi türü döndüren bir işlev bildirimine veya tanımına uygulandığında, **`restrict`** derleyiciye işlevin diğer işaretçilerin başvurduğu bir nesne döndürdüğünü söyler. *aliased* Bu, derleyicinin ek iyileştirmeler gerçekleştirmesini sağlar.

## <a name="syntax"></a>Sözdizimi

> **`__declspec(restrict)`***pointer_return_type* *işlevi*();

## <a name="remarks"></a>Açıklamalar

Derleyici yayar **`__declspec(restrict)`** . Örneğin, CRT `malloc` işlevinin bir **`__declspec(restrict)`** dekorasyonu vardır ve bu nedenle derleyici, bellek konumlarına tarafından başlatılan işaretçilerin `malloc` daha önce varolan işaretçilerle de diğer ad olarak yer aldığını varsayar.

Derleyici, döndürülen işaretçinin gerçekte diğer adı olmadığını denetlemez. Bu, programın **restrict __declspec** değiştiricisiyle işaretlenmiş bir işaretçiye diğer ad olmamasını sağlamak için geliştirici sorumluluğundadır.

Değişkenlerle ilgili benzer semantik için bkz. [__restrict](../cpp/extension-restrict.md).

Bir işlev içindeki diğer ad için geçerli olan başka bir ek açıklama için, bkz. [__declspec (noalias)](../cpp/noalias.md).

**`restrict`** C++ amp parçası olan anahtar sözcük hakkında daha fazla bilgi için bkz. [restrict (C++ amp)](../cpp/restrict-cpp-amp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek öğesinin kullanımını gösterir **`__declspec(restrict)`** .

**`__declspec(restrict)`** Bir işaretçi döndüren bir işleve uygulandığında, bu derleyiciye dönüş değeri tarafından işaret edilen belleğin diğer ad olmadığını söyler. Bu örnekte, işaretçiler `mempool` ve `memptr` geneldir, bu nedenle derleyici başvuran belleğin diğer ad olmadığından emin olamaz. Bununla birlikte, bu kişiler içinde `ma` ve çağıranın, `init` program tarafından başka bir şekilde başvurulmayan belleği döndüren bir şekilde kullanıldıklarından, iyileştiriciye yardımcı olması için **__decslpec (restrict)** kullanılır. Bu, CRT üst bilgilerinin,, `malloc` **`__declspec(restrict)`** var olan işaretçilerin izin vermemelidir her zaman bellek getirdiğinden emin olmak için kullanarak gibi ayırma işlevlerini süsleyerek de benzerdir.

```C
// declspec_restrict.c
// Compile with: cl /W4 declspec_restrict.c
#include <stdio.h>
#include <stdlib.h>

#define M 800
#define N 600
#define P 700

float * mempool, * memptr;

__declspec(restrict) float * ma(int size)
{
    float * retval;
    retval = memptr;
    memptr += size;
    return retval;
}

__declspec(restrict) float * init(int m, int n)
{
    float * a;
    int i, j;
    int k=1;

    a = ma(m * n);
    if (!a) exit(1);
    for (i=0; i<m; i++)
        for (j=0; j<n; j++)
            a[i*n+j] = 0.1f/k++;
    return a;
}

void multiply(float * a, float * b, float * c)
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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec (noalias)](../cpp/noalias.md)
