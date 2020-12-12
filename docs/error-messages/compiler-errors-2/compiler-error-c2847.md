---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2847'
title: Derleyici hatası C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: fc9b7a75d662778bc532bb35e4520fb5627c9f2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97260221"
---
# <a name="compiler-error-c2847"></a>Derleyici hatası C2847

Managed veya WinRT türü ' class ' öğesine sizeof uygulanamıyor

[Sizeof](../../cpp/sizeof-operator.md) işleci, derleme zamanında bir nesnenin değerini alır. Yönetilen veya WinRT sınıfının, arabiriminin veya değer türünün boyutu dinamiktir, bu nedenle derleme zamanında tanınamaz.

Örneğin, aşağıdaki örnek C2847 oluşturur:

```cpp
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
