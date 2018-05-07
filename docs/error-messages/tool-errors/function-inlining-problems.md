---
title: İşlev satır içi kullanım sorunları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- /Ob1 C++ compiler option
- inline functions, problems
- -Ob1 C++ compiler option
- /Ob2 C++ compiler option
- -Ob2 C++ compiler option
- function inlining problems
ms.assetid: 65d59943-4b3c-4a43-aeb6-dccbf7686740
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 670136a61d5991655a5d99e8257c6bcc907f2dfb
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="function-inlining-problems"></a>İşlev Satır İçi Kullanım Sorunları
İşlev satır içi kullanım kullanıyorsanız, şunları yapmalısınız:  
  
-   Eklediğiniz üstbilgi dosyasında uygulanan satır içi işlevler vardır.  
  
-   Sahip satır içi kullanım üstbilgi dosyasında açık.  
  
```  
// LNK2019_function_inline.cpp  
// compile with: /c   
// post-build command: lib LNK2019_function_inline.obj  
#include <stdio.h>  
struct _load_config_used {  
   void Test();  
   void Test2() { printf("in Test2\n"); }  
};  
  
void _load_config_used::Test() { printf("in Test\n"); }  
```  
  
 Ardından,  
  
```  
// LNK2019_function_inline_2.cpp  
// compile with: LNK2019_function_inline.lib  
struct _load_config_used {  
   void Test();  
   void Test2();  
};  
  
int main() {  
   _load_config_used x;  
   x.Test();  
   x.Test2();   // LNK2019  
}  
```  
  
 Kullanıyorsanız `#pragma inline_depth` derleyici yönergesi emin 2 veya daha büyük kümesi değerine sahip. Sıfır değeri kapanır satır içi kullanım. Ayrıca kullandığınızdan emin olun **/Ob1** veya **/Ob2** derleyici seçenekleri.  
  
 Satır içi ve dışı satır içi derleme seçenekleri farklı modülleri karıştırma bazen sorunlara neden olabilir. C++ Kitaplığı işlev satır içi kullanım açık ile oluşturulup oluşturulmadığını ([/Ob1](../../build/reference/ob-inline-function-expansion.md) veya [/Ob2](../../build/reference/ob-inline-function-expansion.md)) ancak (seçeneği) açık işlevleri açıklayan ilgili üstbilgi dosyası satır içi kullanım sahiptir, hatası LNK2001 alırsınız. İşlevler üstbilgi dosyasından koda içermesinden almamış ancak kitaplığı dosyasında olmadığından başvuruyu çözümlemek için adres yok.  
  
 Benzer şekilde, yerine üst bilgi dosyası da LNK2019 alırsınız, işlev satır içi kullanım kullanan bir proje henüz işlevleri .cpp dosyasında tanımlar. Her yerde uygun kabul üstbilgi dosyası eklenmiştir, ancak yalnızca işlevlerdir içermesinden .cpp dosyasına derleyicide; geçtiğinde Bu nedenle, bağlayıcı diğer modüllerde kullanıldığında çözümlenmemiş externals olarak işlev görür.  
  
```  
// LNK2019_FIP.h  
struct testclass {  
   void PublicStatMemFunc1(void);  
};  
```  
  
 Ardından,  
  
```  
// LNK2019_FIP.cpp  
// compile with: /c  
#include "LNK2019_FIP.h"  
inline void testclass::PublicStatMemFunc1(void) {}  
```  
  
 Ardından,  
  
```  
// LNK2019_FIP_2.cpp  
// compile with: LNK2019_FIP.cpp  
// LNK2019 expected  
#include "LNK2019_FIP.h"  
int main() {  
   testclass testclsObject;  
  
   // module cannot see the implementation of PublicStatMemFunc1  
   testclsObject.PublicStatMemFunc1();  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Araçları Hatası LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md)