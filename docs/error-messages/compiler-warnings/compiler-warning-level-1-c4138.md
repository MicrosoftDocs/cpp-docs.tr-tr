---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4138'
title: Derleyici Uyarısı (düzey 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: 68789c7300944c7435431688ff147f40cd4cadb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278031"
---
# <a name="compiler-warning-level-1-c4138"></a>Derleyici Uyarısı (düzey 1) C4138

' */' açıklama dışında bulundu

Kapanış yorumu sınırlayıcısından önce bir açılış yorumu sınırlayıcısı yok. Derleyici, yıldız işareti ( <strong>\*</strong> ) ile eğik çizgi (/) arasında bir boşluk olduğunu varsayar.

## <a name="example"></a>Örnek

```cpp
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

Bu uyarı, yorumları iç içe oluşturmaya çalışırken meydana olabilir.

Bu uyarı, yorum içeren kodun bölümlerini açıklama satırı **#if/#endif** bloğunda içine eklerseniz ve denetim ifadesini sıfır olarak ayarlarsanız çözülebilir:

```cpp
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
