---
title: Bağlayıcı Araçları Hatası LNK2004
ms.date: 11/04/2016
f1_keywords:
- LNK2004
helpviewer_keywords:
- LNK2004
ms.assetid: 07645371-e67b-4a2c-b0e0-dde24c94ef7e
ms.openlocfilehash: 0d26ab12c5b82d52b7dcbb176d9bfa033d7ddfee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80194843"
---
# <a name="linker-tools-error-lnk2004"></a>Bağlayıcı Araçları Hatası LNK2004

' Target ' için GP göreli düzeltme taşması; ' section ' kısa bölümü çok büyük veya aralığın dışında.

Bölüm çok büyüktü.

Bu hatayı çözmek için, kısa bölümün boyutunu küçültün; bu durumda, verileri uzun bölümlere (". sectionname", okuma, yazma, uzun) #pragma yoluyla açık bir şekilde yerleştirerek veri tanımlarında ve bildirimlerinde `__declspec(allocate(".sectionname"))` kullanın.  Örneğin,

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

Ayrıca, derleyicinin uzun bir veri bölümünde ayıracağı 8 bayttan büyük bir veri koleksiyonu olacak şekilde mantıksal olarak gruplanmış verileri kendi yapısına taşıyabilirsiniz.  Örneğin,

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

Bu hatanın ardından önemli hata `LNK1165`.
