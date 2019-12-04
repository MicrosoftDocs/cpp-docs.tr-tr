---
title: Derleyici hatası C2894
ms.date: 11/04/2016
f1_keywords:
- C2894
helpviewer_keywords:
- C2894
ms.assetid: 4e250579-2b59-4993-a6f4-49273e7ecf06
ms.openlocfilehash: ffc87008c1874f8f5c7e275778237f611dcbb5af
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760829"
---
# <a name="compiler-error-c2894"></a>Derleyici hatası C2894

Şablonlar ' C ' bağlantısına sahip olacak şekilde bildirilemez

Bu hata, bir `extern` "C" bloğunun içinde tanımlanan bir şablonla kaynaklanmış olabilir.

Aşağıdaki örnek C2894 oluşturur:

```cpp
// C2894.cpp
extern "C" {
   template<class T> class stack {};   // C2894 fail

   template<class T> void f(const T &aT) {}   // C2894
}
```

Aşağıdaki örnek C2894 oluşturur:

```cpp
// C2894b.cpp
// compile with: /c
extern "C" template<class T> void f(const T &aT) {}   // C2894

template<class T> void f2(const T &aT) {}   // OK
```
