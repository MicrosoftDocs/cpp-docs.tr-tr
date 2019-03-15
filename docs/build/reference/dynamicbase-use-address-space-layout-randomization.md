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
ms.openlocfilehash: a3495de3ec72bcac78cdee2f5f3265864e7a2932
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57807760"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)

Rastgele yükleme zamanında adres alanı düzeni rastgele (ASLR) özelliği, öncelikle Windows Vista'da kullanılabilir Windows temellendirilebilen yürütülebilir bir imaj oluşturulup oluşturulmayacağını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ DYNAMICBASE**[**: NO**]

## <a name="remarks"></a>Açıklamalar

**Dynamıcbase** seçenek değiştirir üst bilgisine bir *yürütülebilir görüntü*, uygulama rastgele yükleme zamanında ReBase işlemi gerçekleştirildi ve sayesinde sanal adresi olup olmadığını belirtmek için .dll veya .exe dosyası Yığınlar sanal bellek konumunu etkileyen, ayırma rastgele yığınları ve diğer işletim sistemi ayırma. **Dynamıcbase** seçenek, hem 32-bit hem de 64-bit görüntüleri için geçerlidir. ASLR, Windows Vista ve sonraki işletim sistemlerinde desteklenir. Seçenek, eski işletim sistemleri tarafından göz ardı edilir.

Varsayılan olarak, **dynamıcbase** etkinleştirilir. Bu seçenek devre dışı bırakmak için **taban**. **Dynamıcbase** için seçeneği gereklidir [/highentropyva](highentropyva-support-64-bit-aslr.md) efekt için seçeneği.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş** özellik sayfası.

1. Değiştirme **rastgele taban adresi** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
- [/HIGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [ISV yazılım güvenlik Savunmaları Windows](https://msdn.microsoft.com/library/bb430720.aspx)