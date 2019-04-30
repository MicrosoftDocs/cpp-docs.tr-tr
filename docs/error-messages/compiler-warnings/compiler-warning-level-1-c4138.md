---
title: Derleyici Uyarısı (düzey 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: 96f8915b9bec166496ca4305d796ce8ef514ca15
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402534"
---
# <a name="compiler-warning-level-1-c4138"></a>Derleyici Uyarısı (düzey 1) C4138

' * /' açıklama dışında bulundu

Kapanış açıklama sınırlayıcısı bir açılış bir açıklama sınırlayıcısı gelmelidir değil. Yıldız arasında bir boşluk derleyici varsayar (<strong>\**</strong>) ve eğik çizgi (/).

## <a name="example"></a>Örnek

```
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

Bu uyarı açıklamalar iç içe deneyerek neden olabilir.

Bu uyarı açıklama içeren, kod içine kod bölümlerini çıkarırsanız çözümlenebilir bir **#if / #endif** blok ve denetleme ifadesiyle sıfır olarak ayarlayın:

```
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```