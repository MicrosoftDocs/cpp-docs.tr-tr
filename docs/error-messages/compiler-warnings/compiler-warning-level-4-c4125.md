---
title: Derleyici Uyarısı (düzey 4) C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 3b82bfd1a1acff07a0fd47bbd2abfb08178a74c6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605367"
---
# <a name="compiler-warning-level-4-c4125"></a>Derleyici Uyarısı (düzey 4) C4125

ondalık basamak sekizlik kaçış sırasını sonlandırıyor

Derleyici, ondalık basamak olmadan sekizlik sayı değerlendirir ve ondalık basamak karakteri olduğunu varsayar.

## <a name="example"></a>Örnek

```
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

9 basamaklı bir karakter olarak amaçlanıyorsa, örnek şu şekilde düzeltin:

```
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```