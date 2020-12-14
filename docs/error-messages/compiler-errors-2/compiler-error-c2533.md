---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2533'
title: Derleyici hatası C2533
ms.date: 11/04/2016
f1_keywords:
- C2533
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
ms.openlocfilehash: 46f9a18d80bcf75d916a6cf5387dc7145f1f1629
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258128"
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
