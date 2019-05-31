---
title: Derleyici Hatası C3872
ms.date: 11/04/2016
f1_keywords:
- C3872
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
ms.openlocfilehash: bd056a63ab60cd5a2504c6a0bc19e388f71b068b
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450058"
---
# <a name="compiler-error-c3872"></a>Derleyici Hatası C3872

'char': Bu karakter bir tanımlayıcıda kullanılamaz

C++ Derleyici C ++ 11 standart bir tanımlayıcıda izin verilen karakterleri izler. Bir tanımlayıcı yalnızca karakterler ve evrensel karakter adları belirli aralıklarına izin verilir. Bir tanımlayıcının ilk karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakter ve evrensel karakter adı aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).

Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [standart ECMA-335: Ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Aşağıdaki örnek, C3872 oluşturur:

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```