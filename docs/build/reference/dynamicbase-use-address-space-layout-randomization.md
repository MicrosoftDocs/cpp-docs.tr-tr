---
title: /DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)
ms.date: 06/12/2018
f1_keywords:
- VC.Project.VCLinkerTool.RandomizedBaseAddress
helpviewer_keywords:
- -DYNAMICBASE linker option
- /DYNAMICBASE linker option
- DYNAMICBASE linker option
ms.assetid: 6c0ced8e-fe9c-4b63-b956-eb8a55fbceb2
ms.openlocfilehash: 47d23ac6f9234e095a1733a8d4078840318cce4b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512404"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)

Rastgele yükleme zamanında adres alanı düzeni rastgele (ASLR) özelliği, öncelikle Windows Vista'da kullanılabilir Windows temellendirilebilen yürütülebilir bir imaj oluşturulup oluşturulmayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ DYNAMICBASE**[**: NO**]

## <a name="remarks"></a>Açıklamalar

**Dynamıcbase** seçenek değiştirir üst bilgisine bir *yürütülebilir görüntü*, uygulama rastgele yükleme zamanında ReBase işlemi gerçekleştirildi ve sayesinde sanal adresi olup olmadığını belirtmek için .dll veya .exe dosyası Yığınlar sanal bellek konumunu etkileyen, ayırma rastgele yığınları ve diğer işletim sistemi ayırma. **Dynamıcbase** seçenek, hem 32-bit hem de 64-bit görüntüleri için geçerlidir. ASLR, Windows Vista ve sonraki işletim sistemlerinde desteklenir. Seçenek, eski işletim sistemleri tarafından göz ardı edilir.

Varsayılan olarak, **dynamıcbase** etkinleştirilir. Bu seçenek devre dışı bırakmak için **taban**. **Dynamıcbase** için seçeneği gereklidir [/highentropyva](highentropyva-support-64-bit-aslr.md) efekt için seçeneği.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş** özellik sayfası.

1. Değiştirme **rastgele taban adresi** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)
- [Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [ISV yazılım güvenlik Savunmaları Windows](https://msdn.microsoft.com/library/bb430720.aspx)