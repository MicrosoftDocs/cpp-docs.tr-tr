---
title: /ALIGN (Bölüm Hizalama)
ms.date: 12/29/2017
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
ms.openlocfilehash: b68ec42db9c927fe8f56dad8f5670059359a1843
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665796"
---
# <a name="align-section-alignment"></a>/ALIGN (Bölüm Hizalama)

## <a name="syntax"></a>Sözdizimi

> **/ ALIGN**[**:**_numarası_]

### <a name="arguments"></a>Arguments

*Sayı*<br/>
Bayt hizalama değeri.

## <a name="remarks"></a>Açıklamalar

**/Hizalama** seçeneği, programın doğrusal adres alanındaki her bölümün hizalamasını belirtir. *Numarası* bağımsız değişkeni bayt ve ikinin üssü olmalıdır. 4 K (4096) varsayılandır. Hizalama, geçersiz bir görüntü oluşturursa, bağlayıcı bir uyarı verir.

Bir uygulama bir aygıt sürücüsü gibi yazmakta olduğunuz sürece, hizalama değişiklik gerekmez.

Hizalama parametresi ile belirli bir bölümün hizalamasını değiştirmek mümkündür [/SECTION](../../build/reference/section-specify-section-attributes.md) seçeneği.

Belirttiğiniz hizalama değeri en büyük bölümü hizalama küçük olamaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. De seçeneği girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
