---
title: Derleyici Hatası C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: 5cadb8165b5b63b2f7ac2d4cc31e2623b0f6bce9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243017"
---
# <a name="compiler-error-c3872"></a>Derleyici Hatası C3872

'char': Bu karakter bir tanımlayıcıda kullanılamaz

C++ Derleyici C ++ 11 standart bir tanımlayıcıda izin verilen karakterleri izler. Bir tanımlayıcı yalnızca karakterler ve evrensel karakter adları belirli aralıklarına izin verilir. Bir tanımlayıcının ilk karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakter ve evrensel karakter adı aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).

Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [standart ECMA-335: Ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Aşağıdaki örnek, C3872 oluşturur:

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```