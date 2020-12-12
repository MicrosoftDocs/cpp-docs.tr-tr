---
description: Daha fazla bilgi edinin:/GUARD (koruma denetimlerini etkinleştir)
title: /GUARD (Koruyucu Denetimlerini Etkinleştirme)
ms.date: 11/04/2016
ms.assetid: 72758e23-70ac-4616-94d7-d767477406d1
ms.openlocfilehash: 4f76de815bc10f8e1203510b25b237fe8db93444
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191725"
---
# <a name="guard-enable-guard-checks"></a>/GUARD (Koruyucu Denetimlerini Etkinleştirme)

Yürütülebilir görüntüde denetim akışı koruyucu denetimleri için desteği belirtir.

## <a name="syntax"></a>Syntax

```
/GUARD:{CF|NO}
```

## <a name="remarks"></a>Açıklamalar

/GUARD: CF belirtildiğinde, bağlayıcı denetim akışı koruyucusu (CFG) çalışma zamanı denetimleri için desteği göstermek üzere bir. dll veya. exe üst bilgisini değiştirir. Bağlayıcı, gerekli denetim akış hedefi adres verilerini üstbilgiye de ekler. Varsayılan olarak,/GUARD: CF devre dışıdır. /GUARD: NO kullanılarak açık olarak devre dışı bırakılabilir. Etkin olması için/GUARD: CF, varsayılan olarak açık olan [/DynamicBase (adres alanı düzeni rastgele seçme)](dynamicbase-use-address-space-layout-randomization.md) bağlayıcı seçeneğini de gerektirir.

Kaynak kodu [/Guard: CF](guard-enable-control-flow-guard.md) seçeneği kullanılarak derlendiğinde, derleyici olası hedef adreslere yönelik tüm dolaylı çağrıları inceleyerek denetim akışını analiz eder. Derleyici, bir dolaylı çağrı yönergesinin hedef adresini doğrulamak için kod ekler ve çalışma zamanında bilinen hedef adresleri listesinde bulunur. CFG çalışma zamanı denetiminde başarısız olan bir programı CFG 'yi destekleyen işletim sistemleri. Bu, bir saldırganın bir çağrı hedefini değiştirmek için veri bozulması kullanarak kötü amaçlı kod yürütmesini zorlaştırır.

CFG özellikli çalıştırılabilir görüntüleri oluşturmak için hem derleyici hem de bağlayıcı için/GUARD: CF seçeneğinin belirtilmesi gerekir. Kod derlendi, ancak/GUARD: CF kullanılarak bağlanmadı. çalışma zamanı denetimlerinin maliyeti, ancak CFG korumasını etkinleştirmez. `cl`Bir adımda derlemek ve bağlamak için komutuna/GUARD: CF seçeneği belirtildiğinde, derleyici bayrağı bağlayıcıya geçirir. **Control Flow Guard** özelliği Visual Studio 'da ayarlandığında,/Guard: CF seçeneği hem derleyiciye hem de bağlayıcıya geçirilir. Nesne dosyaları veya kitaplıklar ayrı olarak derlenmişse, seçeneği komutta açıkça belirtilmelidir `link` .

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**, **bağlayıcı**, **komut satırı**' nı genişletin.

1. **Ek seçenekler**' de girin `/GUARD:CF` .

## <a name="see-also"></a>Ayrıca bkz.

[/guard (Denetim Akışı Korumasını Etkinleştirme)](guard-enable-control-flow-guard.md)<br/>
[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
