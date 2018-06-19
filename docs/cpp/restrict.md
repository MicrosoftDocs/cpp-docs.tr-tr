---
title: kısıtlama | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], restrict
- restrict __declspec keyword
ms.assetid: f39cf632-68d8-4362-a497-2d4c15693689
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed5f91288671eaa3dcf4700ec35dae63ffaef172
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32422894"
---
# <a name="restrict"></a>restrict

**Microsoft özel**

Bir işlev bildirimi veya bir işaretçi türü döndürür tanımı uygulandığında `restrict` işlevi değil bir nesne döndürür derleyici söyler *diğer*, diğer bir deyişle, diğer bir işaretçiler tarafından başvurulan. Bu ek iyileştirmeler gerçekleştirmek derleyici sağlar.

## <a name="syntax"></a>Sözdizimi

> **__declspec(restrict)** *pointer_return_type* *işlevi*();  
  
## <a name="remarks"></a>Açıklamalar

Derleyici yayar `__declspec(restrict)`. Örneğin, CRT `malloc` işlevine sahip bir `__declspec(restrict)` decoration ve bu nedenle, derleyici varsayar işaretçiler tarafından bellek konumlara başlatılmış `malloc` ayrıca diğer önceden varolan tarafından olmayan işaretçileri.

Derleyici döndürülen işaretçi aslında diğer olmadığını denetler. Bu program yapar olmayan diğer ad ile işaretli bir işaretçi emin olmak için geliştiricinin sorumluluğundadır `restrict __declspec` değiştiricisi.  
  
Değişkenleri için benzer semantiği almak için bkz: [__restrict](../cpp/extension-restrict.md).
 
Bir işlevin içindeki yumuşatma uygulandığı başka bir açıklama için bkz: [__declspec(noalias)](../cpp/noalias.md).
  
Hakkında bilgi için **kısıtlamak** C++ AMP parçası olan anahtar sözcük bkz [(C++ AMP) kısıtlamak](../cpp/restrict-cpp-amp.md).  
 
## <a name="example"></a>Örnek  

Aşağıdaki örnek kullanımını gösteren `__declspec(restrict)`.

Zaman `__declspec(restrict)` işaretçi döndürür, bu derleyici dönüş değeri tarafından işaret bellek diğer değil bildirir, bir işlev uygulanır. Bu örnekte, işaretçileri `mempool` ve `memptr` derleyici başvurmak için bellek diğer adı olmadığından emin olamaz için geneldir. İçinde ancak kullanılan `ma` ve kendi arayan `init` , aksi takdirde program tarafından bu nedenle başvurulan değil bellek döndürür şekilde `__decslpec(restrict)` iyileştirici yardımcı olmak için kullanılır. Bu nasıl CRT üstbilgileri ayırma işlevleri gibi tasarlamanız için benzer `malloc` kullanarak `__declspec(restrict)` her zaman varolan işaretçiler tarafından diğer adı olamaz bellek döndürmeleri belirtmek için.

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

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
[__declspec](../cpp/declspec.md)  
[__declspec(noalias)](../cpp/noalias.md)  
