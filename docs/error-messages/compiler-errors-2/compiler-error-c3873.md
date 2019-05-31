---
title: Derleyici Hatası C3873
ms.date: 11/04/2016
f1_keywords:
- C3873
helpviewer_keywords:
- C3873
ms.assetid: e68fd3be-2391-492b-ac3f-d2428901b2e9
ms.openlocfilehash: ca70af12ef3223c8c5950f0fa98b1c63a2dd3a4c
ms.sourcegitcommit: 28eae422049ac3381c6b1206664455dbb56cbfb6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66450827"
---
# <a name="compiler-error-c3873"></a>Derleyici Hatası C3873

'char': Bu karakter bir tanımlayıcının ilk karakteri olarak izin verilmez

C++ Derleyici C ++ 11 standart bir tanımlayıcıda izin verilen karakterleri izler. Bir tanımlayıcı yalnızca karakterler ve evrensel karakter adları belirli aralıklarına izin verilir. Bir tanımlayıcının ilk karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakter ve evrensel karakter adı aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).

Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [standart ECMA-335: Ortak dil altyapısı (CLI)](https://www.ecma-international.org/publications/standards/Ecma-335.htm).

Aşağıdaki örnek, C3873 oluşturur:

```
// C3873.cpp
int main() {
   int \u036F_abc;   // C3873, not in allowed range for initial character
   int abc_\u036F;   // OK, in allowed range for non-initial character
}
```