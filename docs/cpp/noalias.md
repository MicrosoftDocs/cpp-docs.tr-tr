---
title: noalias | Microsoft Docs
ms.custom: 
ms.date: 02/09/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fd57b10aba4298ff7facd725ab3ce1934ccf1ab
ms.sourcegitcommit: f3c398b1c7dbf36ab71b5ca89d365b1913afa307
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2018
---
# <a name="noalias"></a>noalias

**Microsoft Specific**

`noalias`bir işlev çağrısı değiştirmeyin veya başvuru görünür genel durum, anlamına gelir ve yalnızca işaret bellek değiştirir *doğrudan* işaretçi parametreleri (birinci düzey indirections) tarafından.

Bir işlevi olarak ek açıklama eklenmişse `noalias`, iyileştirici parametreleri kendilerini yanı sıra, yalnızca ilk düzeyi indirections işaretçi parametrelerinin başvurulan veya işlevinde değiştiren, kabul edilebilir. Görünür genel durum değil tanımlanan veya derleme kapsamı dışında başvurulan tüm veri kümesidir ve kendi adres alınmaz. Tüm kaynak dosyaları derleme kapsamıdır ([/LTCG (bağlama zamanı kodu oluşturma)](../build/reference/ltcg-link-time-code-generation.md) derlemeler) ya da tek bir kaynak dosyası (olmayan**/LTCG** yapı).

`noalias` Ek açıklama yalnızca açıklamalı işlev gövdesi içinde geçerlidir. Bir işlevi olarak işaretleme `__declspec(noalias)` işlev tarafından döndürülen işaretçileri yumuşatma etkilemez.

Yumuşatma etkileyebilir başka bir açıklama için bkz: [__declspec(restrict)](../cpp/restrict.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek kullanımını gösteren `__declspec(noalias)`.

Zaman işlevi `multiply` erişir bellek açıklama `__declspec(noalias)`, bu işlev parametre listesinde işaretçileri aracılığıyla dışında genel durumunu değiştirmez derleyici söyler.

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

## <a name="see-also"></a>Ayrıca Bkz.

[__declspec](../cpp/declspec.md)  
[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
[__declspec(restrict)](../cpp/restrict.md)  
