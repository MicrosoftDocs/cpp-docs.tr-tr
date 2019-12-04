---
title: Derleyici hatası C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: e6962e5c127a92acc5dfdad580c7bc89fa134751
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753451"
---
# <a name="compiler-error-c3345"></a>Derleyici hatası C3345

' tanımlayıcı ': modül adı için geçersiz tanımlayıcı

Modül için *tanımlayıcı* , kabul edilmeyen bir veya daha fazla karakter içeriyor. Bir tanımlayıcı, ilk karakter alfabetik, alt çizgi veya yüksek bir ANSI (0x80-FF) karakteri ise ve sonraki karakter bir alfasayısal, alt çizgi veya yüksek bir ANSI karakter olduğunda geçerlidir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. *Tanımlayıcının* boşluk veya kabul edilemez başka karakterler içermediğinden emin olun.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği, C3345 özniteliğinin `name` `module` parametresi boş içerdiğinden hata iletisine neden olur.

```cpp
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
