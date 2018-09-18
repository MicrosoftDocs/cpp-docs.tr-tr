---
title: Derleyici Hatası C3672 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3672
dev_langs:
- C++
helpviewer_keywords:
- C3672
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0002b6fdf25374ec0d977c5fa4f450e41d29335f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090652"
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