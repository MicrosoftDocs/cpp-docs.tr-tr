---
title: Ad düzenlemesi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8e956d0acf9e6debcb183577775e2215e7eccec7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323306"
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