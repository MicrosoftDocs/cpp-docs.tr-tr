---
title: Derleyici Hatası C3345 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3345
dev_langs:
- C++
helpviewer_keywords:
- C3345
ms.assetid: 1dda4c79-73bb-441b-b939-746154c3afba
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e6b3a021d9c747e4ec30278d8a22bde899cb39a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3345"></a>Derleyici Hatası C3345
'tanımlayıcısı': Modül adı için geçersiz tanımlayıcı  
  
 *Tanımlayıcısı* bir modül bir veya daha fazla Kabul edilemeyen karakterler içeriyor. Tanımlayıcı ilk karakter alfabetik, alt çizgi ya da yüksek ANSI (0x80-FF) karakterini ve herhangi bir sonraki karakteri bir alfasayısal, geçerli ise alt çizgi veya yüksek ANSI karakter.  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  Emin *tanımlayıcısı* boşlukları veya diğer Kabul edilemeyen karakterler içermiyor.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod örneğinde hata iletisi C3345 neden olur `name` parametresinin `module` boş bir öznitelik içeriyor.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__iscsym](../../c-runtime-library/reference/iscsym-functions.md)   
 [Karakter Sınıflaması](../../c-runtime-library/character-classification.md)   
 [Modülü](../../windows/module-cpp.md)