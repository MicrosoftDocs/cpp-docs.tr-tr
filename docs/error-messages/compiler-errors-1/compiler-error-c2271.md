---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2271'
title: Derleyici hatası C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: 750af0551aadc274ea2c90f265fe9df9e0e9ab6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336282"
---
# <a name="compiler-error-c2271"></a>Derleyici hatası C2271

' operator ': New/Delete biçimsel liste değiştiricilerine sahip olamaz

İşleci ( **`new`** veya **`delete`** ) bir bellek modeli belirticisi ile bildirilmiştir.

Aşağıdaki örnek C2271 oluşturur:

```cpp
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```
