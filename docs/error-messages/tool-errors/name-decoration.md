---
title: Düzenlemeyi Adlandır
ms.date: 04/22/2019
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: d1557f53a07a544ff4f9e5a63f905e6854fb74ce
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64857164"
---
# <a name="name-decoration"></a>Düzenlemeyi Adlandır

Düzenlemeyi Adlandır genellikle C++ adlandırma kurallarına başvuruyor, ancak C çalışmalarını bir dizi için geçerli olabilir. Varsayılan olarak, C++ işlevi için bir bağlayıcı adı oluşturmak için bu işlev adı, parametreleri ve dönüş türü kullanır. Aşağıdaki işlev bildirimi göz önünde bulundurun:

`void CALLTYPE test(void);`

Aşağıdaki tabloda, çeşitli çağırma kuralları bağlayıcı adını gösterir.

|Çağırma kuralı|`extern "C"` veya `.c` dosyası|`.cpp`, `.cxx` veya `/TP`|
|------------------------|---------------------------|------------------------|
|C adlandırma kuralı (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Hızlı arama adlandırma kuralı (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|Standart çağırma adlandırma kuralı (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vektör çağrı adlandırma kuralı (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

Kullanım `extern "C"` bir C işlevini çağırmak için C++. `extern "C"` sınıf olmayan C adlandırma kuralı kullanılmasını zorlar C++ işlevleri. Derleyici anahtarları unutmayın **/Tc** veya **/Tp**, dosya adı uzantısı yoksaymak ve sırasıyla C veya C++ olarak dosyasını derlemek için derleyicinin söyleyin. Bu seçenekler, beklemiyoruz bağlayıcı adları neden olabilir.

Eşleşmeyen parametrelerine sahip işlev prototipleri sahip bu hataya neden olabilir. Düzenlemeyi Adlandır son düzenlenmiş işlevi adı bir işlev parametrelerini içerir. Bu işlev bildiriminde eşleşmeyen parametre türleri ile bir işlev çağırmanın LNK2001 neden olabilir.

Şu anda hiçbir standartları vardır C++ adlandırma derleyici satıcıları arasında veya hatta bir derleyicinin farklı sürümleri arasında. Diğer derleyiciler tarafından derlenmiş nesne dosyaları bağlantılandırma aynı adlandırma şeması vermeyebilir ve Çözülmemiş dış öğeleri neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hatası LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)