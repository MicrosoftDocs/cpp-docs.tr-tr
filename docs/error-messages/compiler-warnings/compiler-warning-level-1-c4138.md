---
title: Derleyici Uyarısı (düzey 1) C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: e6e368f27371b744efa4006630938f68f51a2ca0
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73627102"
---
# <a name="compiler-warning-level-1-c4138"></a>Derleyici Uyarısı (düzey 1) C4138

' */' açıklama dışında bulundu

Kapanış yorumu sınırlayıcısından önce bir açılış yorumu sınırlayıcısı yok. Derleyici, yıldız işareti (<strong>\*</strong>) ile eğik çizgi (/) arasında bir boşluk olduğunu varsayar.

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