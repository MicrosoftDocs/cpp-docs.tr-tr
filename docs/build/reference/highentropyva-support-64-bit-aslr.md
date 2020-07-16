---
title: /HIGHENTROPYVA (64 Bit ASLR Destekle)
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: 929d6aa71010c1f303bf7a1ce64109a01b8792e4
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404131"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (64 Bit ASLR Destekle)

Yürütülebilir resmin yüksek entrolebilir 64 bit adres alanı düzeni rastgele seçimini (ASLR) destekleyip desteklemediğini belirtir.

## <a name="syntax"></a>Syntax

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>Açıklamalar

**`/HIGHENTROPYVA`***executable image* *`.dll`* *`.exe`* ASLR 'in tüm 64-bit adres alanını kullanıp kullanamayacağını göstermek için yürütülebilir bir görüntü dosyasının üst bilgisini (örneğin, bir veya dosya) değiştirir.  Bir etkiye sahip olmak için, hem çalıştırılabilir hem de bağımlı olduğu tüm modüller üzerinde seçeneğini ayarlayın. Ardından 64-bit ASLR destekleyen bir işletim sistemi, 64 bit rastgele sanal adresler kullanarak yürütülebilir görüntünün segmentlerini yükleme zamanında yeniden temellendirebilirler. Bu büyük adres alanı, bir saldırganın belirli bir bellek bölgesinin konumunu tahmin etmesini zorlaştırır.

Varsayılan olarak, **`/HIGHENTROPYVA`** 64 bitlik yürütülebilir görüntüler için etkinleştirilmiştir. Bu seçenek [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md) , 64-bit görüntüler için varsayılan olarak da etkinleştirilen bir gerektirir. **`/HIGHENTROPYVA`**, bağlayıcının seçeneği yoksaydığı 32 bitlik yürütülebilir görüntüler için geçerli değildir. Bu seçeneği açıkça devre dışı bırakmak için kullanın **`/HIGHENTROPYVA:NO`** .

**`/HIGHENTROPYVA`** Yükleme zamanında bir etkiye sahip olmak için, ' nin [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md) de etkinleştirilmesi gerekir. **`/DYNAMICBASE`** Varsayılan olarak etkindir ve Windows Vista ve sonraki işletim sistemlerinde ASLR etkinleştirmesi için gereklidir. Windows 'un önceki sürümleri bu bayrağı yoksayar.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de, `/HIGHENTROPYVA` veya girin `/HIGHENTROPYVA:NO` .

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
- [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md)
- [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md)
- [Windows ISV yazılım güvenliği savunmaları](https://docs.microsoft.com/previous-versions/bb430720(v=msdn.10))
