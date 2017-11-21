---
title: "-Zc: satır içi (başvurulmayan comdat'ı kaldırma) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /Zc:inline
- VC.Project.VCCLCompilerTool.RemoveUnreferencedCodeData
dev_langs: C++
helpviewer_keywords:
- -Zc compiler options (C++)
- /Zc compiler options (C++)
- Zc compiler options (C++)
- /Zc:inline
ms.assetid: a4c94224-1d73-4bea-a9d5-4fa73dc924df
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7031a5f7a92a6775718b77ea20a69623ae3066c9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="zcinline-remove-unreferenced-comdat"></a>/Zc:inline (Başvurulmayan COMDAT'ı kaldırma)
Kaldırır başvurulmayan işlevleri veya COMDATs veya yalnızca iç bağlantı sahip veriler. Zaman **/ZC: inline** belirtilirse, derleyici gerektirir veya satır içi işlevler satır içi verileri kullanmak çeviri birimleri, veri veya işlevler için tanımları de dahil etmelisiniz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/Zc:inline[-]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Zaman **/ZC: inline** belirtilirse, derleyici sembol bilgileri başvurulmayan comdat'ı işlevleri veya veriler veya işlevler veya yalnızca iç bağlantı sahip veriler yayma değil. Varsayılan olarak, bu seçenek kapalıdır (**/Zc:inline-**). Bu iyileştirme yayın derlemelerde bağlayıcı tarafından gerçekleştirilen iş bazıları basitleştirir veya ne zaman bağlayıcı seçeneği [/OPT:REF](../../build/reference/opt-optimizations.md) belirtilir. Bu iyileştirme derleyici gerçekleştirdiğinde, bu önemli ölçüde .obj dosya boyutunu küçültmek ve bağlayıcı hızını artırmak. İyileştirmeleri devre dışı bırakıldığında Bu derleyici seçeneği etkin değil ([/Od](../../build/reference/od-disable-debug.md)) veya ne zaman [/GL (bütün Program iyileştirmesi)](../../build/reference/gl-whole-program-optimization.md) belirtilir.  
  
 Varsa **/ZC: inline** belirtilirse, derleyici zorlar bildirilen tüm işlevler C ++ 11 gereksinim `inline` kullanıldıkları tanımı aynı çeviri biriminde kullanılabilir olması gerekir. Seçenek belirtilmediğinde [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] bildirilen işlevler çağırır uyumlu olmayan kod tanır `inline` tanım görülemiyor olsa bile. Daha fazla bilgi için C ++ 11 standart, 3.2 ve bölümleri 7.1.2 bakın. Bu derleyici seçeneği Visual Studio 2013 güncelleştirme 2'de sunulmuştur.  
  
 Kullanılacak **/ZC: inline** seçeneği, güncelleştirme uyumlu olmayan kod. Bu örnek nasıl uyumlu olmayan bir satır içi işlev bildirimi bir tanımı olmadan kullanımını hala derler ve ne zaman bağlantıları gösterir varsayılan **/Zc:inline-** seçeneği kullanıldığında:  
  
```cpp  
// example.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#pragma once  
  
class Example {  
public:  
   inline void inline_call(); // declared but not defined inline  
   void normal_call();  
   Example() {};  
};  
```  
  
```cpp  
// example.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include <stdio.h>  
#include "example.h"  
  
void Example::inline_call() {  
   printf("inline_call was called.\n");   
}  
  
void Example::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call(); // with /Zc:inline-, inline_call forced into .obj file  
}  
```  
  
```cpp  
// zcinline.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline.cpp example.cpp  
#include "example.h"  
  
void main() {  
   Example example;  
   example.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Zaman **/ZC: inline** etkin, aynı kod neden bir [LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md) hata derleyici içermesinden olmayan kod gövdesi için yayma değil çünkü `Example::inline_call` example.obj içinde. Bu satır içi olmayan çağrısında neden `main` tanımlanmamış bir dış simge başvurmak için.  
  
 Bu hatayı gidermek için kaldırabilirsiniz `inline` bildirimi anahtar sözcüğünün `Example::inline_call`, tanımını taşıma `Example::inline_call` üstbilgisi içine dosya ya da uygulanmasını taşıma `Example` main.cpp içine. Sonraki örnek üstbilgi içeren herhangi bir çağırıcı görünür olduğu üstbilgi dosyası tanımı taşır.  
  
```cpp  
// example2.h  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#pragma once  
#include <stdio.h>  
  
class Example2 {  
public:  
   inline void inline_call() {  
      printf("inline_call was called.\n");   
   }  
   void normal_call();  
   Example2() {};  
};  
```  
  
```cpp  
// example2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void Example2::normal_call() {  
   printf("normal_call was called.\n");   
   inline_call();   
}  
```  
  
```cpp  
// zcinline2.cpp  
// Compile by using: cl /W4 /EHsc /O2 zcinline2.cpp example2.cpp  
#include "example2.h"  
  
void main() {  
   Example2 example2;  
   example2.inline_call(); // normal call when definition unavailable  
}  
```  
  
 Visual c++ uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Seçin **C/C++** klasör.  
  
3.  Seçin **komut satırı** özellik sayfası.  
  
4.  Değiştirme **ek seçenekler** eklenecek özellik `/Zc:inline` ve ardından **Tamam**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ZC (Uyumluluk)](../../build/reference/zc-conformance.md)