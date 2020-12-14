---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3672'
title: Derleyici hatası C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: aea8a03e409e1144985cb7b94dcca94975d58db5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228826"
---
# <a name="compiler-error-c3672"></a>Derleyici hatası C3672

sözde yıkıcısı ifadesi yalnızca bir işlev çağrısının bir parçası olarak kullanılabilir

Yıkıcı yanlış çağrıldı.  Daha fazla bilgi için bkz. [Yıkıcılar](../../cpp/destructors-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3672 oluşturur.

```cpp
// C3672.cpp
template<typename T>
void f(T* pT) {
   &pT->T::~T;   // C3672
   pT->T::~T();   // OK
};

int main() {
   int i;
   f(&i);
}
```
