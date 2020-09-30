---
title: Derleyici hatası C3345
ms.date: 11/04/2016
f1_keywords:
- C3345
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
ms.openlocfilehash: 8682069fdf719f4e85d1d6f5107de1903e3ae071
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504839"
---
# <a name="compiler-error-c3345"></a>Derleyici hatası C3345

' tanımlayıcı ': modül adı için geçersiz tanımlayıcı

Modül için *tanımlayıcı* , kabul edilmeyen bir veya daha fazla karakter içeriyor. Bir tanımlayıcı, ilk karakter alfabetik, alt çizgi veya yüksek bir ANSI (0x80-FF) karakteri ise ve sonraki karakter bir alfasayısal, alt çizgi veya yüksek bir ANSI karakter olduğunda geçerlidir.

### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için

1. *Tanımlayıcının* boşluk veya kabul edilemez başka karakterler içermediğinden emin olun.

## <a name="example"></a>Örnek

Aşağıdaki kod örneği C3345 hata iletisine neden olur çünkü `name` `module` özniteliğin parametresi boş bir içerir.

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
[Karakter sınıflandırması](../../c-runtime-library/character-classification.md)<br/>
[birimi](../../windows/attributes/module-cpp.md)
