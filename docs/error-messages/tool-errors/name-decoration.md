---
title: Düzenlemeyi Adlandır
ms.date: 09/05/2018
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: b916a73e0b8f86755384914fa85ef8a901e4a64c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59041529"
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

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı araçları hatası LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)