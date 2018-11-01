---
title: Derleyici Hatası C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: eb2a6935073c3b4a2b9eb3d9b099b372cfa34303
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467372"
---
# <a name="compiler-error-c3873"></a>Derleyici Hatası C3873

'char': Bu karakter bir tanımlayıcının ilk karakteri olarak izin verilmez

C++ Derleyici C ++ 11 standart bir tanımlayıcıda izin verilen karakterleri izler. Bir tanımlayıcı yalnızca karakterler ve evrensel karakter adları belirli aralıklarına izin verilir. Bir tanımlayıcının ilk karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakter ve evrensel karakter adı aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).

Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [ECMA-335 standart: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Aşağıdaki örnek, C3873 oluşturur:

```
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```