---
title: Derleyici Hatası C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: eb1d15a12bfebbf44f7335a848d68c367c285586
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59027572"
---
# <a name="compiler-error-c3345"></a>Derleyici Hatası C3345

'identifier': Modül adı için geçersiz tanımlayıcı

*Tanımlayıcı* bir modül bir veya daha fazla Kabul edilemeyen karakterler içeriyor. Bir tanımlayıcının ilk karakteri alfabetik, alt çizgi veya yüksek ANSI (0x80-FF) karakterini ve herhangi bir sonraki karakteri bir alfasayısal karakterler, geçerli ise alt çizgi veya yüksek ANSI karakter.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. Emin *tanımlayıcı* boşluk veya diğer Kabul edilemeyen karakterler içermiyor.

## <a name="example"></a>Örnek

Çünkü aşağıdaki kod örneğinde hata iletisi C3345 neden `name` parametresinin `module` boş bir öznitelik içeriyor.

```
// cpp_attr_name_module.cpp
// compile with: /LD /link /OPT:NOREF
#include <atlbase.h>
#include <atlcom.h>
#include <atlwin.h>
#include <atltypes.h>
#include <atlctl.h>
#include <atlhost.h>
#include <atlplus.h>

// C3345 expected
[module(dll, name="My Library", version="1.2", helpfile="MyHelpFile")]
// Try the following line instead
//[module(dll, name="MyLibrary", version="1.2", helpfile="MyHelpFile")]
// Module attribute now applies to this class
class CMyClass {
public:
BOOL WINAPI DllMain(DWORD dwReason, LPVOID lpReserved) {
   // add your own code here
   return __super::DllMain(dwReason, lpReserved);
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[__iscsym](../../c-runtime-library/reference/iscsym-functions.md)<br/>
[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[module](../../windows/module-cpp.md)