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
ms.openlocfilehash: 543ea30b06f62939f378167d8598c73f66061f46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370312"
---
# <a name="align-section-alignment"></a>/ALIGN (Bölüm Hizalama)

## <a name="syntax"></a>Sözdizimi

> **/ ALIGN**[**:**_numarası_]

### <a name="arguments"></a>Arguments

*Sayı*  
Bayt cinsinden hizalama değeri.

## <a name="remarks"></a>Açıklamalar

**/HİZALA** seçeneği programının doğrusal adres alanı içinde her bölüm hizalamasını belirtir. *Numarası* bağımsız değişkeni bayt ve iki gücünü olması gerekir. 4 K (4096) varsayılandır. Hizalama geçersiz bir görüntü üretiyor, bağlayıcı bir uyarı verir.

Bir aygıt sürücüsü gibi bir uygulama yazıyorsanız sürece hizalamasını değiştirme gerekmez.

Belirli bir bölümü için Hizala parametresiyle hizalamasını değiştirmek mümkündür [/SECTION](../../build/reference/section-specify-section-attributes.md) seçeneği.

Belirttiğiniz hizalama değeri en büyük bölüm hizalama küçük olamaz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Seçenek girin **ek seçenekler** kutusu. Seçin **Tamam** veya **Uygula** değişikliği uygulamak için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
