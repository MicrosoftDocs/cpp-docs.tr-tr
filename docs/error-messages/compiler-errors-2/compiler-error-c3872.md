---
title: Derleyici hatası C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: f4b116729ad3b84014d202deb31ab490435fcef3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761448"
---
# <a name="compiler-error-c3872"></a>Derleyici hatası C3872

' Char ': bir tanımlayıcıda bu karaktere izin verilmiyor

C++ Derleyici, bir tanımlayıcıda izin verilen karakterlerle c++ 11 standardını izler. Tanımlayıcıda yalnızca belirli karakter aralıklarına ve evrensel karakter adlarına izin verilir. Ek kısıtlamalar, bir tanımlayıcının ilk karakteri için geçerlidir. Daha fazla bilgi ve izin verilen karakterlerin ve evrensel karakter adı aralıklarının listesi için bkz. [tanımlayıcılar](../../cpp/identifiers-cpp.md).

Bir tanımlayıcıda izin verilen karakter aralığı,/CLI kodu derlenirken C++daha az kısıtlayıcıdır. /Clr kullanılarak derlenen koddaki tanımlayıcılar [standart ECMA-335: ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)izlemelidir.

Aşağıdaki örnek C3872 oluşturur:

```cpp
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```
