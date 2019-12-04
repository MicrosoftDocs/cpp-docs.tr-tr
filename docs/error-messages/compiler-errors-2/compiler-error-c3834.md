---
title: Derleyici hatası C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 1dac75ca5bea868823eba8e344fb4ec043fae1ad
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74741540"
---
# <a name="compiler-error-c3834"></a>Derleyici hatası C3834

sabitleme işaretçisine geçersiz açık tür dönüştürme; Bunun yerine sabitlenmiş bir yerel değişken kullanın

Sabitlenmiş bir işaretçiye yönelik açık bir işaretçiye izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3834 oluşturur.

```cpp
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
