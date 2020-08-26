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
ms.openlocfilehash: 9af502d65dd81efdedc6b80951f11d68f766cb31
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88842630"
---
# <a name="dynamicbase-use-address-space-layout-randomization"></a>/DYNAMICBASE (Adres boşluğu düzeni rastgele seçimini kullan)

Windows Vista 'da ilk olarak bulunan Windows 'un adres alanı düzeni rastgele seçme (ASLR) özelliğini kullanarak yükleme zamanında rastgele bir şekilde yeniden temellenebilir bir yürütülebilir görüntü oluşturulup oluşturulmayacağını belirtir.

## <a name="syntax"></a>Syntax

> **/DynamicBase**[**: No**]

## <a name="remarks"></a>Açıklamalar

**/DynamicBase** seçeneği bir *yürütülebilir görüntünün*, bir. dll veya. exe dosyasının üst bilgisini değiştirerek uygulamanın yükleme zamanında rastgele bir şekilde yeniden yapılıp yapılmayacağını ve sanal adres ayırma rastgele olmasını, bu da Heap 'ler, yığınların ve diğer işletim sistemi ayırmalarının sanal bellek konumunu etkiler. **/DynamicBase** seçeneği, hem 32-bit hem de 64 bit görüntüler için geçerlidir. ASLR, Windows Vista ve sonraki işletim sistemlerinde desteklenir. Bu seçenek önceki işletim sistemleri tarafından yok sayılır.

Varsayılan olarak, **/DynamicBase** etkindir. Bu seçeneği devre dışı bırakmak için **/DynamicBase: No**kullanın. [/Highentropyva](highentropyva-support-64-bit-aslr.md) seçeneğinin bir etkisi olması için **/DynamicBase** seçeneği gereklidir.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **Bağlayıcısı**  >  **Gelişmiş** özellik sayfasını seçin.

1. **Rastgele temel adres** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.RandomizedBaseAddress%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
- [/HıGHENTROPYVA](highentropyva-support-64-bit-aslr.md)
- [Windows ISV yazılım güvenliği savunmaları](/previous-versions/bb430720(v=msdn.10))
