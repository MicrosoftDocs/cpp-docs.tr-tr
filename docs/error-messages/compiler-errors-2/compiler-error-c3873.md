---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3873'
title: Derleyici hatası C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: 7ca1346d2a1f22e1aa8bd2a7197daa41d8b416aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222729"
---
# <a name="compiler-error-c3873"></a>Derleyici hatası C3873

' Char ': bu karaktere bir tanımlayıcının ilk karakteri olarak izin verilmez

C++ derleyicisi, bir tanımlayıcıda izin verilen karakterlerle C++ 11 standardını izler. Tanımlayıcıda yalnızca belirli karakter aralıklarına ve evrensel karakter adlarına izin verilir. Ek kısıtlamalar, bir tanımlayıcının ilk karakteri için geçerlidir. Daha fazla bilgi ve izin verilen karakterlerin ve evrensel karakter adı aralıklarının listesi için bkz. [tanımlayıcılar](../../cpp/identifiers-cpp.md).

Bir tanımlayıcıda izin verilen karakter aralığı, C++/CLı kodu derlenirken daha az kısıtlayıcıdır. /Clr kullanılarak derlenen koddaki tanımlayıcılar  [standart ECMA-335: ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)izlemelidir.

Aşağıdaki örnek C3873 oluşturur:

```cpp
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```
