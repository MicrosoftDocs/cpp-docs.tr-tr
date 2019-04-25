---
title: Derleyici Hatası C3672
ms.date: 11/04/2016
f1_keywords:
- C3672
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
ms.openlocfilehash: 36048f3e4b8cc1be3e766f11b5c131513a3365da
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62215010"
---
# <a name="compiler-error-c3672"></a>Derleyici Hatası C3672

Sözde yok edici ifadesi yalnızca bir işlev çağrısının bir parçası olarak kullanılabilir

Bir yok edici hatalı çağrıldı.  Daha fazla bilgi için [yok ediciler](../../cpp/destructors-cpp.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3672 oluşturur.

```
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