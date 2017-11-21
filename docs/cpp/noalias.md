---
title: noalias | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noalias_cpp
dev_langs: C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b70c5e41b3380de241939249f51449ba65406c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="noalias"></a>noalias

**Microsoft özel**

`noalias`bir işlev çağrısı değiştirmeyin veya başvuru görünür genel durum, anlamına gelir ve yalnızca işaret bellek değiştirir *doğrudan* işaretçi parametreleri (birinci düzey indirections) tarafından.

Bir işlevi olarak ek açıklama eklenmişse `noalias`, iyileştirici parametreleri kendilerini yanı sıra, yalnızca ilk düzeyi indirections işaretçi parametrelerinin başvurulan veya işlevinde değiştiren, kabul edilebilir. Görünür genel durum değil tanımlanan veya derleme kapsamı dışında başvurulan tüm veri kümesidir ve kendi adres alınmaz. Tüm kaynak dosyaları derleme kapsamıdır ([/LTCG (bağlama zamanı kodu oluşturma)](../build/reference/ltcg-link-time-code-generation.md) derlemeler) ya da tek bir kaynak dosyası (olmayan**/LTCG** yapı).

## <a name="example"></a>Örnek

Aşağıdaki örneği kullanarak gösteren `__declspec(restrict)` ve `__declspec(noalias)`. Bellek normalde, döndürülen `malloc` olan `restrict` CRT üstbilgileri uygun şekilde donatılmış olduğundan.

Ancak, bu örnekte, işaretçileri `mempool` ve `memptr` derleyici bellek yumuşatma tabi değil garantisi yoktur nedenle geneldir. İşaretçileri ile döndüren işlevler dekorasyon `__declspec(restrict)` bellek dönüş değeri tarafından işaret derleyici diğer değil söyler.

Bellekle erişen örnek işlevinde dekorasyon `__declspec(noalias)` bu işlev işaretçileri parametre listesinde aracılığıyla dışında genel durum etkilemediğinden derleyici söyler.

```C
// declspec_noalias.c
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

## <a name="see-also"></a>Ayrıca Bkz.

[__declspec](../cpp/declspec.md)  
[Anahtar sözcükler](../cpp/keywords-cpp.md)