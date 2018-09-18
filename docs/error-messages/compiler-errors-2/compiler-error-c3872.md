---
title: Derleyici Hatası C3872 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3872
dev_langs:
- C++
helpviewer_keywords:
- C3872
ms.assetid: 519e95be-5641-40cc-894c-da4819506604
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5ec6450dca0faa86f3cf27452eff6df9851742d4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018840"
---
# <a name="compiler-error-c3872"></a>Derleyici Hatası C3872

'char': Bu karakter bir tanımlayıcıda kullanılamaz

C++ Derleyici C ++ 11 standart bir tanımlayıcıda izin verilen karakterleri izler. Bir tanımlayıcı yalnızca karakterler ve evrensel karakter adları belirli aralıklarına izin verilir. Bir tanımlayıcının ilk karakteri ek kısıtlamalar. Daha fazla bilgi ve izin verilen karakter ve evrensel karakter adı aralıkları listesi için bkz: [tanımlayıcıları](../../cpp/identifiers-cpp.md).

Bir tanımlayıcı izin verilen karakter aralığı daha az kısıtlayıcı olduğunda C + derleniyor +/ CLI kodu. / CLR ile derlenmiş kodda tanımlayıcıları izlemelidir [ECMA-335 standart: ortak dil altyapısı (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).

Aşağıdaki örnek, C3872 oluşturur:

```
// C3872.cpp
int main() {
   int abc_\u0040;   // C3872, U+0040 is in base char set
   int abc_\u3001;   // C3872, U+3001 is not in allowed range
   int \u30A2_abc_\u3042;   // OK, UCNs in allowed range
}
```