---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2784'
title: Derleyici hatası C2784
ms.date: 11/04/2016
f1_keywords:
- C2784
helpviewer_keywords:
- C2784
ms.assetid: 3d761fe2-881c-48bd-afae-e2e714e20473
ms.openlocfilehash: dcee0cc2c6c8154bafe4a37fe83c66b1c8d477d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297921"
---
# <a name="compiler-error-c2784"></a>Derleyici hatası C2784

' bildirim ': ' Type ' içindeki ' Type ' için şablon bağımsız değişkeni çıkarılamıyor

Derleyici, sağlanan işlev bağımsız değişkenlerinden bir şablon bağımsız değişkeni belirleyemiyor.

Aşağıdaki örnek C2784 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2784.cpp
template<class T> class X {};
template<class T> void f(X<T>) {}

int main() {
   X<int> x;
   f(1);   // C2784

   // To fix it, try the following line instead
   f(x);
}
```
