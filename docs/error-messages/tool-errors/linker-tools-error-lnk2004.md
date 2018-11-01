---
title: Bağlayıcı Araçları Hatası LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 37eb01b5dd8266bce34e1a932271d5d9a9d15c52
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529330"
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