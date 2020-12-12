---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3872'
title: Derleyici hatası C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: 860db2f94fa198246290a0e491b1a647dbc91c20
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222742"
---
# <a name="compiler-error-c3872"></a>Derleyici hatası C3872

' Char ': bir tanımlayıcıda bu karaktere izin verilmiyor

C++ derleyicisi, bir tanımlayıcıda izin verilen karakterlerle C++ 11 standardını izler. Tanımlayıcıda yalnızca belirli karakter aralıklarına ve evrensel karakter adlarına izin verilir. Ek kısıtlamalar, bir tanımlayıcının ilk karakteri için geçerlidir. Daha fazla bilgi ve izin verilen karakterlerin ve evrensel karakter adı aralıklarının listesi için bkz. [tanımlayıcılar](../../cpp/identifiers-cpp.md).

Bir tanımlayıcıda izin verilen karakter aralığı, C++/CLı kodu derlenirken daha az kısıtlayıcıdır. /Clr kullanılarak derlenen koddaki tanımlayıcılar  [standart ECMA-335: ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)izlemelidir.

Aşağıdaki örnek C3872 oluşturur:

```cpp
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```
