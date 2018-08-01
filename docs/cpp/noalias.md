---
title: noalias | Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noalias_cpp
dev_langs:
- C++
helpviewer_keywords:
- noalias __declspec keyword
- __declspec keyword [C++], noalias
ms.assetid: efafa8b0-7f39-4edc-a81e-d287ae882c9b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56ee12f65ff9efe9f3b048d061b80aef691eb0f2
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404401"
---
# <a name="noalias"></a>noalias

**Microsoft'a özgü**

**noalias** bir işlev çağrısı değiştirmeyin veya başvuru görünür genel durumu, anlamına gelir ve yalnızca işaret edilen bellek değiştirir *doğrudan* işaretçi parametrelerini (birinci düzey yöneltmeye) tarafından.

Bir işlev olarak eklenmişse **noalias**, iyileştirici parametrelerinin kendilerini ek olarak, yalnızca ilk düzeyi yöneltmeye işaretçi parametrelerinin başvurulan veya işlev içinde değiştirilen, kabul edilebilir. Görünür genel durum değil tanımlanan veya başvurulan derleme kapsamı dışında tüm veri kümesidir ve kendi adres değil alınır. Tüm kaynak dosyaları derleme kapsamıdır ([/LTCG (bağlama zamanı kodu oluşturma)](../build/reference/ltcg-link-time-code-generation.md) oluşturur) veya tek bir kaynak dosyası (olmayan **/LTCG** oluşturun).

**Noalias** ek açıklama yalnızca açıklamalı işlevinin gövdesi içinde geçerlidir. Bir işlev olarak işaretleme **__declspec(noalias)** işaretçiler işlev tarafından döndürülen yumuşatma etkilemez.

Diğer ad kullanımı etkileyebilir başka bir açıklama için bkz. [__declspec(restrict)](../cpp/restrict.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, kullanımını gösterir **__declspec(noalias)**.

İşlev `multiply` erişimleri bellek açıklanıyor **__declspec(noalias)**, bu işlev işaretçileri, parametre listesindeki aracılığıyla dışında genel durumunu değiştirmez derleyiciye bildirir.

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
 [__declspec](../cpp/declspec.md)  
 [Anahtar Sözcükler](../cpp/keywords-cpp.md)  
 [__declspec(restrict)](../cpp/restrict.md)  
