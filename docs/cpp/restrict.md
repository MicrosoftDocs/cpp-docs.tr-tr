---
title: restrict
ms.date: 02/09/2018
f1_keywords:
- restrict_cpp
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
ms.openlocfilehash: 40c1c05ca72f639829f2d3658497b0e9f3199640
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403379"
---
# <a name="restrict"></a>restrict

**Microsoft'a özgü**

Bir işlev bildiriminin ya da bir işaretçi türü döndüren tanımı uygulandığında **kısıtlama** işlev olmayan bir nesne döndürür derleyiciye *diğer adlı*, diğer bir deyişle, diğer tarafından başvurulan işaretçileri. Bu, derleyicinin ek iyileştirmeler sağlar.

## <a name="syntax"></a>Sözdizimi

> **__declspec(restrict)** *pointer_return_type* *function*();

## <a name="remarks"></a>Açıklamalar

Derleyici yayar **__declspec(restrict)**. Örneğin CRT `malloc` işleve sahip bir **__declspec(restrict)** düzenleme ve bu nedenle, derleyici varsayar işaretçiler tarafından bellek konumları için başlatılan `malloc` ayrıca diğer adlı olarak olmayan daha önce Varolan işaretçilerin.

Derleyici, döndürülen işaretçi gerçekten diğer adlı olmadığını denetlemez. Program yapar olmayan diğer ad ile işaretlenmiş bir işaretçi emin olmak için korumanın geliştiricinin sorumluluğunda olan **__declspec kısıtlama** değiştiricisi.

Değişkenleri, benzer semantiğe için bkz. [__restrict](../cpp/extension-restrict.md).

Diğer ad kullanımı bir işlev içinde geçerlidir başka bir açıklama için bkz. [__declspec(noalias)](../cpp/noalias.md).

Hakkında bilgi için **kısıtlama** C++ AMP parçası olan anahtar sözcüğü bkz [(C++ AMP) kısıtlama](../cpp/restrict-cpp-amp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir **__declspec(restrict)**.

Zaman **__declspec(restrict)** işaretçi döndürür, bu dönüş değeri tarafından işaret edilen bellek diğer adlı değil derleyiciye, bir işlev olarak uygulanır. Bu örnekte, işaretçiler `mempool` ve `memptr` derleyici başvurmak için bellek diğer adı olmadığından emin olamaz için geneldir. İçinde ancak kullanılan `ma` ve arayanına `init` döndürür, aksi takdirde program tarafından bu nedenle başvuru yapılmaz bellek şekilde **__decslpec(restrict)** iyileştirici yardımcı olmak için kullanılır. Bu nasıl CRT üstbilgileri ayırma işlevleri gibi donatmak için benzer `malloc` kullanarak **__declspec(restrict)** bunlar her zaman varolan işaretçilerin tarafından diğer ad verilemez bellek döndüreceğini belirtmek için.

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[__declspec](../cpp/declspec.md)<br/>
[__declspec(noalias)](../cpp/noalias.md)
