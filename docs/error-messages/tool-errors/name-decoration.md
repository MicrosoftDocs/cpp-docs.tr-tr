---
title: Düzenlemeyi Adlandır
ms.date: 04/22/2019
helpviewer_keywords:
- name decoration [C++]
- names [C++], decorated
- decorated names, calling conventions
ms.assetid: 8327a27b-bb4f-49f2-8218-b851b9d2a463
ms.openlocfilehash: cc00c971eac2a089ccec5bd9eab594bdf4e8348e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173523"
---
# <a name="name-decoration"></a>Düzenlemeyi Adlandır

Ad dekorasyonu genellikle C++ adlandırma kurallarına başvurur, ancak çeşitli C örneklerine da uygulanabilir. Varsayılan olarak, C++ işlev için bir bağlayıcı adı oluşturmak üzere işlev adını, parametreleri ve dönüş türünü kullanır. Aşağıdaki işlev bildirimini göz önünde bulundurun:

`void CALLTYPE test(void);`

Aşağıdaki tabloda çeşitli çağırma kuralları için bağlayıcı adı gösterilmektedir.

|Çağırma kuralı|`extern "C"` veya `.c` dosyası|`.cpp`, `.cxx` veya `/TP`|
|------------------------|---------------------------|------------------------|
|C adlandırma kuralı (`__cdecl`)|`_test`|`?test@@ZAXXZ`|
|Hızlı çağrı adlandırma kuralı (`__fastcall`)|`@test@0`|`?test@@YIXXZ`|
|Standart çağrı adlandırma kuralı (`__stdcall`)|`_test@0`|`?test@@YGXXZ`|
|Vektör çağrısı adlandırma kuralı (`__vectorcall`)|`test@@0`|`?test@@YQXXZ`|

İçindeki C++bir C işlevini çağırmak için `extern "C"` kullanın. `extern "C"` sınıf C++ olmayan Işlevler için C adlandırma kuralını kullanmaya zorlar. Derleyiciye dosya adı uzantısını yok saymasını ve **/Tp**dosyayı sırasıyla C veya C++olarak derlemeyi söyleyen, **/TC** veya/TP derleyici anahtarlarından haberdar olun. Bu seçenekler, beklemediğinizi bağlayıcı adlarına neden olabilir.

Eşleşmeyen parametrelere sahip işlev prototiptürleri de bu hataya neden olabilir. Ad dekorasyonu, bir işlevin parametrelerini, son düzenlenmiş işlev adına ekler. İşlev bildirimiyle eşleşmeyen parametre türleriyle bir işlevi çağırmak, LNK2001 de neden olabilir.

Şu anda derleyici satıcıları arasında veya C++ bir derleyicinin farklı sürümleri arasında adlandırma standartları yoktur. Diğer derleyiciler tarafından derlenen nesne dosyalarının bağlanması aynı adlandırma şemasını oluşturmayabilir ve çözümlenmemiş dışlar neden olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Araçları Hatası LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md)
