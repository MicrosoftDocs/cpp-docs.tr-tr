---
title: / ALIGN (bölüm hizalama) | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.Alignment
- /align
dev_langs:
- C++
helpviewer_keywords:
- sections, specifying alignment
- ALIGN linker option
- /ALIGN linker option
- -ALIGN linker option
- section alignment
- sections
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb92d4b16be7903004831ffb25e2891f498a8989
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45718256"
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

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
