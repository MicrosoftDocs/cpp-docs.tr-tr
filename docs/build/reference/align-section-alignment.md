---
title: "/ ALIGN (bölüm hizalama) | Microsoft Docs"
ms.custom: 
ms.date: 12/29/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
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
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4ca4572e84c7ad32be2d03a312f7bb7d8a3f3f29
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="align-section-alignment"></a>/ALIGN (Bölüm Hizalama)

## <a name="syntax"></a>Sözdizimi

> **/ ALIGN**[**:**_numarası_]

### <a name="arguments"></a>Arguments

*sayı*  
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
