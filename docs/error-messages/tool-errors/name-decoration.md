---
title: Ad düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 09/05/2018
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
ms.openlocfilehash: 063464fe58417cfce58160ccba12fbcd514c7320
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43894479"
---
# <a name="name-decoration"></a>Düzenlemeyi Adlandır

Düzenlemeyi Adlandır genellikle C++ adlandırma kurallarına başvuruyor, ancak C çalışmalarını bir dizi için geçerli olabilir. Varsayılan olarak, C++ işlevi için bir bağlayıcı adı oluşturmak için bu işlev adı, parametreleri ve dönüş türü kullanır. Aşağıdaki işlev göz önünde bulundurun:

```
void CALLTYPE test(void)  
```

Aşağıdaki tabloda, çeşitli çağırma kuralları bağlayıcı adını gösterir.

|Çağırma kuralı|extern "C" ya da .c dosyası|.cpp veya .cxx /TP|
|------------------------|---------------------------|------------------------|
|C adlandırma kuralı (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Fastcall adlandırma kuralı (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|Standart çağrı adlandırma kuralı (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vectorcall adlandırma kuralı (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

Extern "C" C++'tan bir C işlevini çağırmak için kullanın. Extern "C" sınıf olmayan C++ işlevlerini C adlandırma kuralı kullanılmasını zorlar. Derleyici anahtarları unutmayın **/Tc** veya **/Tp**, dosya adı uzantısı yoksaymak ve sırasıyla C veya C++ olarak dosyasını derlemek için derleyicinin söyleyin. Bu seçenekler beklemediğiniz adları neden olabilir.

Eşleşmeyen parametrelerine sahip işlev prototipleri sahip bu hataya neden olabilir. Düzenlemeyi Adlandır son düzenlenmiş işlevi adı bir işlev parametrelerini içerir. Bu işlev bildiriminde eşleşmeyen parametre türleri ile bir işlev çağırmanın LNK2001 neden olabilir.

Şu anda hiçbir C++ Derleyici satıcılar veya bir derleyicinin farklı sürümleri arasında bile adlandırma standardı. Bu nedenle diğer derleyicilerle derlenmiş nesne dosyaları bağlama aynı adlandırma şeması vermeyebilir ve bu nedenle çözümlenmemiş dışlar neden olur.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Araçları Hatası LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)