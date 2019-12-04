---
title: Derleyici hatası C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: b111448e7e9d8260a5101d05996a670013936894
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74746415"
---
# <a name="compiler-error-c2533"></a>Derleyici hatası C2533

' tanımlayıcı ': oluşturucuların bir dönüş türü olmasına izin verilmez

Oluşturucu bir dönüş türüne sahip olamaz (`void` bir dönüş türüne eşit değildir).

Bu hatanın ortak bir kaynağı, bir sınıf tanımının sonu ile ilk Oluşturucu uygulamasının arasına eksik bir noktalı virgüldür. Derleyici, Oluşturucu işlevi için dönüş türünün tanımı olarak sınıfını görür ve C2533 oluşturur.

Aşağıdaki örnek C2533 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```
