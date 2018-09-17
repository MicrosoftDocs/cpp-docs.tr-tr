---
title: -GUARD (koruyucu denetimlerini etkinleştirme) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d775e9c42ceb8a564e2cc7992cb95ac9717a966d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707687"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (Koruyucu Denetimlerini Etkinleştirme)

Denetim akışı koruyucusu denetimleri için destek yürütülebilir bir görüntüde belirtir.

## <a name="syntax"></a>Sözdizimi

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>Açıklamalar

/ Guard: cf belirtildiğinde, bağlayıcı üst bilgisine bir .dll veya .exe denetim akışı koruyucusu (CFG) çalışma zamanı denetimleri için destek belirtmek için değiştirir. Bağlayıcı, gerekli denetimi akış hedef adresi veri başlığına da ekler. Varsayılan olarak, / Guard: cf devre dışıdır. Bu açıkça /GUARD:NO kullanarak devre dışı bırakılabilir. Gerektirir ayrıca/Guard: cf etkili olması için [dynamıcbase (adres boşluğu düzeni rastgele'seçimini kullan)](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) bağlayıcı seçeneği varsayılan olarak açıktır.

Zaman kaynak kodu derlendiğinde kullanarak [/Guard: cf](../../build/reference/guard-enable-control-flow-guard.md) seçeneği, derleyicinin çözümler denetim akışı olası hedef adresi için tüm dolaylı aramalar inceleyerek. Derleme zamanında bilinen hedef adresi listesinden bir dolaylı çağrı talimatı hedef adresi olduğu doğrulamak için kod ekler. CFG durdurma CFG çalışma zamanı başarısız bir program destekleyen işletim sistemleri denetleyin. Çağrı hedefi değiştirmek için veri bozulması kullanarak kötü amaçlı kod yürütmek bir saldırgan daha zor yapar.

/ Guard: cf seçeneği, derleyici ve bağlayıcı CFG özellikli yürütülebilir görüntüler oluşturmak için için belirtilmelidir. Kod derlenir, ancak/Guard: cf kullanarak bağlantılı olmayan çalışma zamanı denetimleri maliyeti doğurur, ancak CFG koruma sağlamaz. İçin/Guard: cf seçeneği belirtildiğinde `cl` derlemek ve bir adımda, derleyici bağlamak için komut bayrağı bağlayıcıya geçirir. Zaman **denetim akışı koruyucusu** özelliği, Visual Studio'da ayarlanır, derleyici ve bağlayıcı için/Guard: cf seçeneği geçirilir. Nesne dosyalarında veya kitaplıklarındaki ayrı olarak derlenen, seçeneğini açıkça belirtilmesi gerekir `link` komutu.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri**, **bağlayıcı**, **komut satırı**.

1. İçinde **ek seçenekler**, girin `/GUARD:CF`.

## <a name="see-also"></a>Ayrıca Bkz.

[Guard (Denetim etkinleştirme akışı)](../../build/reference/guard-enable-control-flow-guard.md)
[bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)