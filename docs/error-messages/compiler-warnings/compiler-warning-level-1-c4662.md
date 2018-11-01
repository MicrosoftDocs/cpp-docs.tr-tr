---
title: Derleyici Uyarısı (düzey 1) C4662
ms.date: 11/04/2016
f1_keywords:
- C4662
helpviewer_keywords:
- C4662
ms.assetid: 7efda273-d04a-47b7-ad65-ff1ff94b5ffc
ms.openlocfilehash: ecd8e757e1724fcd4c08540559eab75f1e4bed46
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599859"
---
# <a name="compiler-warning-level-1-c4662"></a>Derleyici Uyarısı (düzey 1) C4662

Açık örnek oluşturma; Şablon sınıfı 'ıdentifier1', 'identifier2' değerini özelleştirecek tanım yok sahiptir.

Belirtilen Şablon sınıfı bildirildi ancak tanımlı değil.

## <a name="example"></a>Örnek

```
// C4662.cpp
// compile with: /W1 /LD
template<class T, int i> class MyClass; // no definition
template MyClass< int, 1>;              // C4662
```