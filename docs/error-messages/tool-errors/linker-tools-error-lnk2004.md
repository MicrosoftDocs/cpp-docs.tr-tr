---
title: Bağlayıcı Araçları Hatası LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 8088494106aa702fda0497fa431e48267167a185
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517560"
---
# <a name="linker-tools-error-lnk2004"></a>Bağlayıcı Araçları Hatası LNK2004

gp göreli düzeltme taşması 'hedeflemek için '; kısa bölüm 'bölümü' çok büyük veya aralığın dışında.

Bölümde çok büyük.

Bu hatayı gidermek için ya da açıkça uzun bölümlerde #pragma bölümü (".sectionname", okuma, yazma, uzun) aracılığıyla veri yerleştirme ve kullanarak kısa bölüm boyutunu `__declspec(allocate(".sectionname"))` veri tanımları ve bildirimleri.  Örneğin,

```
#pragma section(".data$mylong", read, write, long)
__declspec(allocate(".data$mylong"))
char    rg0[1] = { 1 };
char    rg1[2] = { 1 };
char    rg2[4] = { 1 };
char    rg3[8] = { 1 };
char    rg4[16] = { 1 };
char    rg5[32] = { 1 };
```

Ayrıca, derleyici bir uzun veri bölümünde tahsis 8 bayt daha büyük veri koleksiyonu olacak kendi yapısında verileri mantıksal olarak gruplanmış taşıyabilirsiniz.  Örneğin,

```
// from this...
int     w1  = 23;
int     w2 = 46;
int     w3 = 23*3;
int     w4 = 23*4;

// to this...
struct X {
    int     w1;
    int     w2;
    int     w3;
    int     w4;
} x  = { 23, 23*2, 23*3, 23*4 };
```

Bu hata, önemli hata tarafından izlenir `LNK1165`.