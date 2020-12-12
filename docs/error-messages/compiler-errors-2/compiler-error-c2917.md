---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2917'
title: Derleyici hatası C2917
ms.date: 11/04/2016
f1_keywords:
- C2917
helpviewer_keywords:
- C2917
ms.assetid: ec9da9ee-0f37-47b3-87dd-19ef5a14dc4c
ms.openlocfilehash: c860ee47ae46db5667f39014b2f504f8f6d08e51
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97270439"
---
# <a name="compiler-error-c2917"></a>Derleyici hatası C2917

' name ': geçersiz şablon parametresi

Şablon parametre listesi, bir şablon parametresi olmayan bir tanımlayıcı içeriyor.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2917 oluşturur.

```cpp
// C2917.cpp
// compile with: /c
template<class T> class Vector {
   void sort();
};

template<class T*> void Vector<T>::sort() {}   // C2917
// try the following line instead
// template<class T> void Vector<T>::sort() {}
```
