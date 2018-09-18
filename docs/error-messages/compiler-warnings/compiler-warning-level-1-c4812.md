---
title: Derleyici Uyarısı (düzey 1) C4812 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4812
dev_langs:
- C++
helpviewer_keywords:
- C4812
ms.assetid: a7f5721f-2019-44de-ad62-ed30bac8b1f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ef4136a23cca23e75464de04bf2738ca51e1ee26
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033361"
---
# <a name="compiler-warning-level-1-c4812"></a>Derleyici Uyarısı (düzey 1) C4812

eski bildirim stili: Lütfen bunun yerine 'new_syntax' kullanın

Visual C++'ın geçerli sürümünde açık Oluşturucu özelleştirmesi hala desteklenmektedir, ancak gelecekteki bir sürümde desteklenmeyebilir.

Aşağıdaki örnek, C4812 oluşturur:

```
// C4812.cpp
// compile with: /W1 /c
template <class T>
class MyClass;

template<class T>
class MyClass<T*> {
   MyClass();
};

template<class T>
MyClass<T*>::MyClass<T*>() {}   // C4812
// try the following line instead
// MyClass<T*>::MyClass() {}
```