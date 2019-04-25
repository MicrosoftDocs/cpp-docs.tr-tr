---
title: Derleyici Hatası C2447
ms.date: 11/04/2016
f1_keywords:
- C2447
helpviewer_keywords:
- C2447
ms.assetid: d1bd6e9a-ee42-4510-ae5e-6b0378f7b931
ms.openlocfilehash: 64dca8313af8b640b7b03c1ab27a1a31fa90de09
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301974"
---
# <a name="compiler-error-c2447"></a>Derleyici Hatası C2447

' {': işlev üstbilgisi eksik (eski stil resmi liste?)

Derleyici, genel kapsamda beklenmedik bir açık ayraç ile karşılaştı. Çoğu durumda, bunun nedeni hatalı biçimlendirilmiş işlev üstbilgisi, yanlış yerleştirilmiş bir bildirim ya da boştaki bir noktalı virgüldür. Bu sorunu gidermek için, açık ayracın düzgün biçimlendirilmiş bir işlev üstbilgisini izlediğini ve kendinden önce bir bildirim veya boşta noktalı virgül gelmediğini doğrulayın.

Bu hata ayrıca eski stil C dili biçimsel bağımsız değişken listesi nedeniyle de meydana gelebilir. Bu sorunu gidermek için, bağımsız değişken listesini modern stili (parantez içine alınmış biçimi) kullanacak şekilde yeniden düzenleyin.

Aşağıdaki örnek, C2447 oluşturur:

```
// C2447.cpp
int c;
{}       // C2447
```