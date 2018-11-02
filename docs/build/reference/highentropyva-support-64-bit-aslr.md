---
title: /HIGHENTROPYVA (64 Bit ASLR Destekle)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: a8bd1b2231530c0f1632b244edaf36ee14ed65b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534803"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 Bit ASLR Destekle)

Yürütülebilir resmin yüksek entropili 64-bit rastgele adres alanı düzenini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ HIGHENTROPYVA**[**: NO**]

## <a name="remarks"></a>Açıklamalar

**/ HIGHENTROPYVA** üstbilgisi değiştiren bir *yürütülebilir görüntü*, bir .dll dosyasının veya .exe dosyası, tüm 64 bit adres ASLR kullanıp kullanamayacağını göstermek için. Bu seçenek yürütülebilir olarak ve tüm bağımlı modüllerini ayarlandığında, 64 bit ASLR destekleyen bir işletim sistemi yürütülebilir resmin parçalarını yükleme zamanında bir 64 bit sanal adres alanında rastgele adresler kullanarak ReBase işlemi yapabilirsiniz. Bu geniş adres alanı bir saldırganın belirli bir bellek bölgesinin konumunu tahmin edilmesi daha zor hale getirir.

Varsayılan olarak, **/highentropyva** 64-bit yürütülebilir resimler için etkinleştirilir. Bu seçenek gerektirir [/largeaddressaware](largeaddressaware-handle-large-addresses.md), ayrıca etkin olan 64-bit görüntüleri için varsayılan olarak. **/ HIGHENTROPYVA** nerede bağlayıcı seçeneğini yoksayar 32-bit yürütülebilir resimler için geçerli değildir. Açıkça bu seçeneği devre dışı bırakma, **/HIGHENTROPYVA:NO**.

İçin **/highentropyva** yükleme zamanında bir etkiye sahip olma [dynamıcbase](dynamicbase-use-address-space-layout-randomization.md) etkinleştirilmiş olması da gerekir. **/ DYNAMICBASE** varsayılan olarak etkindir ve Windows Vista ve sonraki işletim sistemlerinde ASLR etkinleştirmek için gereklidir. Önceki Windows sürümlerinde bu bayrağı yoksayın.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. İçinde **ek seçenekler**, girin `/HIGHENTROPYVA` veya `/HIGHENTROPYVA:NO`.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [ISV yazılım güvenlik Savunmaları Windows](https://msdn.microsoft.com/library/bb430720.aspx)
