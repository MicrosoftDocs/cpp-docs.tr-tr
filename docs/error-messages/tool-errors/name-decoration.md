---
title: "Ad düzenlemesi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f780b91d7d58ecdfc9b2af4295c76253357f8e66
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="name-decoration"></a>Düzenlemeyi Adlandır
Ad düzenlemesi genellikle C++ adlandırma kurallarına başvuruyor, ancak C durumlarda bir dizi için geçerli olabilir. Varsayılan olarak, C++ işlevi için bir bağlayıcı adı oluşturmak için bu işlev adı, parametreler ve dönüş türü kullanır. Aşağıdaki işlevi göz önünde bulundurun:  
  
```  
void CALLTYPE test(void)  
```  
  
 Aşağıdaki tabloda, çeşitli çağırma kurallarını bağlayıcı adını gösterir.  
  
|Çağırma kuralı|extern "C" veya .c dosyası|.cpp, .cxx veya /TP|  
|------------------------|---------------------------|------------------------|  
|C adlandırma kuralı (`__cdecl`)|_test|? @ test@ZAXXZ|  
|Fastcall adlandırma kuralı (`__fastcall`)|@test@0|? @ test@YIXXZ|  
|Standart arama adlandırma kuralı (`__stdcall`)|_test@0|? @ test@YGXXZ|  
|Vectorcall adlandırma kuralı (`__vectorcall`)|Test @@0|? @ test@YQXXZ|  
  
 C++ içinden C işlevi çağırmak için extern "C" kullanın. Extern "C" sınıfı olmayan C++ işlevlerini C adlandırma kuralı kullanılmasını zorlar. Derleyici anahtarları unutmayın **tp** veya **/Tp**, dosya adı uzantısı yoksay ve C veya C++ olarak dosya sırasıyla derlemek için derleyici söyleyin. Bu seçenekler beklemediğiniz adları neden olabilir.  
  
 Eşleşmeyen parametrelerine sahip işlev prototipleri sahip bu hataya neden olabilir. Ad düzenlemesi son düzenlenmiş işlevi adlı bir işlev parametreleri içerir. İşlev bildirimi de eşleşmiyor parametre türleri ile bir işlevi çağırmak LNK2001 neden olabilir.  
  
 Şu anda hiçbir standart c++ derleyici satıcılar veya bir derleyici farklı sürümleri arasında bile adlandırma. Bu nedenle diğer derleyicileri ile derlenen nesne dosyaları bağlama aynı adlandırma şeması vermeyebilir ve böylece çözümlenmemiş externals neden olur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı Araçları Hatası LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)