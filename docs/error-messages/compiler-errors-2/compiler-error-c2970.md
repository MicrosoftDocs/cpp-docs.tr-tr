---
title: Derleyici hatası C2970
ms.date: 11/04/2016
f1_keywords:
- C2970
helpviewer_keywords:
- C2970
ms.assetid: 21d90348-20d3-438c-b278-efdbfb93a7d2
ms.openlocfilehash: af30ccc4a71c51d042d6f7807a648a1eef066a70
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74742671"
---
# <a name="compiler-error-c2970"></a>Derleyici hatası C2970

' class ': şablon parametresi ' param ': ' arg ': iç bağlantısı olan nesneleri içeren bir ifade, tür olmayan bir bağımsız değişken olarak kullanılamaz

Statik bir değişkenin adını veya adresini şablon bağımsız değişkeni olarak kullanamazsınız. Şablon sınıfı, derleme zamanında değerlendirilebilen bir const değeri bekler.

Aşağıdaki örnek C2970 oluşturur:

```cpp
// C2970.cpp
// compile with: /c
static int si;
// could declare nonstatic to resolve all errors
// int si;

template <int i>
class X {};

template <int *pi>
class Y {};

X<si> anX;   // C2970 cannot use static variable in templates

// this would also work
const int i = 10;
X<i> anX2;
```
