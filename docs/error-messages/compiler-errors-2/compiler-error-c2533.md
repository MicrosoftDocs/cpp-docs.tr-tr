---
title: Derleyici hatası C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 6c598c2c5b3ac6d88fb843534cae240c65a2d322
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87207920"
---
# <a name="compiler-error-c2533"></a>Derleyici hatası C2533

' tanımlayıcı ': oluşturucuların bir dönüş türü olmasına izin verilmez

Oluşturucunun dönüş türü olamaz ( **`void`** dönüş türü bile olamaz).

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
