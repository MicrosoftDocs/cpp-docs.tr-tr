---
description: Daha fazla bilgi edinin:/ALIGN (Bölüm hizalama)
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
ms.openlocfilehash: d8a9af473252a2eff8957c5d2b4c54c7f7c862aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187266"
---
# <a name="align-section-alignment"></a>/ALIGN (Bölüm Hizalama)

## <a name="syntax"></a>Syntax

> **/ALIGN**[**:**_sayı_]

### <a name="arguments"></a>Arguments

*sayısından*<br/>
Bayt cinsinden hizalama değeri.

## <a name="remarks"></a>Açıklamalar

**/ALIGN** seçeneği, programın doğrusal adres alanındaki her bölümün hizalamasını belirtir. *Sayı* bağımsız değişkeni bayt cinsinden ve ikinin üssü olmalıdır. Varsayılan değer 4K 'dir (4096). Hizalama geçersiz bir görüntü üretirse bağlayıcı bir uyarı verir.

Bir cihaz sürücüsü gibi bir uygulama yazmadığınız sürece, hizalamayı değiştirmenize gerek kalmaz.

Belirli bir bölümün hizalamasını, [/section](section-specify-section-attributes.md) seçeneğine hizalayın parametresiyle değiştirmek mümkündür.

Belirttiğiniz hizalama değeri en büyük bölüm hizalamadan küçük olamaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna seçeneği girin. Değişikliği uygulamak için **Tamam ' ı** veya **Uygula** ' yı seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
