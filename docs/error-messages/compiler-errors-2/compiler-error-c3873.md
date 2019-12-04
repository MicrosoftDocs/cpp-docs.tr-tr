---
title: Derleyici hatası C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: e63c3870a60194b72f1be8e1b401bbdef8fa47be
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736730"
---
# <a name="compiler-error-c3873"></a>Derleyici hatası C3873

' Char ': bu karaktere bir tanımlayıcının ilk karakteri olarak izin verilmez

C++ Derleyici, bir tanımlayıcıda izin verilen karakterlerle c++ 11 standardını izler. Tanımlayıcıda yalnızca belirli karakter aralıklarına ve evrensel karakter adlarına izin verilir. Ek kısıtlamalar, bir tanımlayıcının ilk karakteri için geçerlidir. Daha fazla bilgi ve izin verilen karakterlerin ve evrensel karakter adı aralıklarının listesi için bkz. [tanımlayıcılar](../../cpp/identifiers-cpp.md).

Bir tanımlayıcıda izin verilen karakter aralığı,/CLI kodu derlenirken C++daha az kısıtlayıcıdır. /Clr kullanılarak derlenen koddaki tanımlayıcılar [standart ECMA-335: ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm)izlemelidir.

Aşağıdaki örnek C3873 oluşturur:

```cpp
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```
