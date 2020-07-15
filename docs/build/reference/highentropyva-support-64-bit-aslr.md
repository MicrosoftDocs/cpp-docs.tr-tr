---
title: /HIGHENTROPYVA (64 Bit ASLR Destekle)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 8f8601d89e8456461aac3d91f9fd2cfda216d7f5
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373846"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 Bit ASLR Destekle)

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **/highentropyva**[**: No**]

## <a name="remarks"></a>Açıklamalar

**/Highentropyva** , ASLR 'in tüm 64-bit adres alanını kullanıp kullanamayacağını göstermek için *yürütülebilir bir görüntünün*, bir. dll dosyasının veya. exe dosyasının üst bilgisini değiştirir. Bu seçenek, bir yürütülebilir dosya ve bağımlı olduğu tüm modüller üzerinde ayarlandığında, 64 bitlik ASLR destekleyen bir işletim sistemi, bir 64 bit sanal adres alanında rastgele adresler kullanarak, yükleme zamanında yürütülebilir görüntünün segmentlerini yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, **/highentropyva** , 64 bitlik yürütülebilir görüntüler için etkinleştirilmiştir. Bu seçenek, 64 bit görüntüler için varsayılan olarak da etkinleştirilen [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)gerektirir. **/Highentropyva** , bağlayıcının seçeneği yoksaydığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için **/highentropyva: No**komutunu kullanın.

**/Highentropyva** 'nın yükleme zamanında bir etkisi olması için [/DynamicBase](dynamicbase-use-address-space-layout-randomization.md) de etkinleştirilmelidir. **/DynamicBase** varsayılan olarak etkindir ve Windows Vista ve sonraki IŞLETIM sistemlerinde ASLR etkinleştirmesi için gereklidir. Windows 'un önceki sürümleri bu bayrağı yoksayar.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de, `/HIGHENTROPYVA` veya girin `/HIGHENTROPYVA:NO` .

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
- [/DYNAMICBASE](dynamicbase-use-address-space-layout-randomization.md)
- [/LARGEADDRESSAWARE](largeaddressaware-handle-large-addresses.md)
- [Windows ISV yazılım güvenliği savunmaları](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
