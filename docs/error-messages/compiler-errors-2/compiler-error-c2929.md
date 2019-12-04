---
title: Derleyici hatası C2929
ms.date: 11/04/2016
f1_keywords:
- C2929
helpviewer_keywords:
- C2929
ms.assetid: 11134027-6adc-4733-b6bd-b94486bd1933
ms.openlocfilehash: d420e3f6470a94874549fadc8cd90e4dac20fe6e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760999"
---
# <a name="compiler-error-c2929"></a>Derleyici hatası C2929

' tanımlayıcı ': açık örnek oluşturma; Şablon sınıfı üyenin örnek oluşturma, açıkça zorlanamıyor ve bastırılamıyor

Bir tanımlayıcıyı örneklendirmesini engellerken açık bir şekilde örnekleyemezsiniz.

Aşağıdaki örnek C2929 oluşturur:

```cpp
// C2929.cpp
// compile with: /c
template<typename T>
class A {
public:
   A() {}
};

template A<int>::A();

extern template A<int>::A();   // C2929
```
