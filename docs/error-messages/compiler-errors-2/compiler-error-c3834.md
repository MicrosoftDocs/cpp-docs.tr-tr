---
title: Derleyici Hatası C3834
ms.date: 11/04/2016
f1_keywords:
- C3834
helpviewer_keywords:
- C3834
ms.assetid: 059e0dc4-300b-4e74-b6c2-41a57831fe2a
ms.openlocfilehash: 9f2bb96beaac8ede75863084c8ebf8345c940f53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62327515"
---
# <a name="compiler-error-c3834"></a>Derleyici Hatası C3834

Geçersiz açık bir sabitleme işaretçisine dönüştürme; Bunun yerine sabitlenmiş bir yerel değişken kullanın

Açık yayınları sabitlenmiş bir işaretçiye izin verilmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3834 oluşturur.

```
// C3834.cpp
// compile with: /clr
int main() {
   int x = 33;

   pin_ptr<int> p = safe_cast<pin_ptr<int> >(&x);   // C3834
   pin_ptr<int> p2 = &x;   // OK
}
```
