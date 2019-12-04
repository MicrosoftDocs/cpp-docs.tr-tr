---
title: Derleyici hatası C3247
ms.date: 11/04/2016
f1_keywords:
- C3247
helpviewer_keywords:
- C3247
ms.assetid: f9a2bbb5-3fce-40bf-9fd3-835a5f164dbb
ms.openlocfilehash: 81dc5d5e54551aff49adad2ada2eb25f57a37ec2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754387"
---
# <a name="compiler-error-c3247"></a>Derleyici hatası C3247

' Class1 ': bir coclass başka bir ' Class2 ' coclass 'ından devralınabilir

[Coclass](../../windows/coclass.md) özniteliğiyle işaretlenmiş bir sınıf, `coclass` özniteliğiyle işaretlenmiş başka bir sınıftan devralınabilir.

Aşağıdaki örnek C3247 oluşturur:

```cpp
// C3247.cpp
[module(name="MyLib")];
[coclass]
class a {
};

[coclass]
class b : public a {   // C3247
};
int main() {
}
```
