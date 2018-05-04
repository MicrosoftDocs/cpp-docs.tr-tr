---
title: -ERRORREPORT (dahili bağlayıcı hatalarını raporla) | Microsoft Docs
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /ERRORREPORT
- VC.Project.VCLinkerTool.ErrorReporting
dev_langs:
- C++
helpviewer_keywords:
- /ERRORREPORT linker option
- ERRORREPORT linker option
- -ERRORREPORT linker option
ms.assetid: f5fab595-a2f1-4eb0-ab5c-1c0fbd3d8c28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72e620e5347d422a8de66cba3ea9cfd601bb3f29
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Dahili Bağlayıcı Hatalarını Raporla)

> **/ errorreport:**[ **hiçbiri** | **istemi** | **sıra** | **Gönder** ]

## <a name="arguments"></a>Arguments

**Yok**  
İç derleyici hataları hakkında raporlar değil toplanmayacak veya Microsoft'a gönderilir.

**istemi**  
Derleyici iç hatası aldığınızda, bir raporu göndermek isteyip istemediğinizi sorar. **İstemi** bir uygulama geliştirme ortamında derlendiğinde varsayılandır.

**Sırası**  
Hata raporu sıralar. Yönetici ayrıcalıklarıyla oturum kapatışınızda oturum en son ne zaman bu yana hataları rapor için bir pencere görüntülenir (üç günde birden çok kez hata raporu göndermek için istenir değildir). **sıra** uygulamanın bir komut isteminde derlendiğinde varsayılandır.

**Gönder**  
Otomatik olarak raporlama tarafından Windows Hata Raporlama hizmeti ayarları etkinse, iç derleyici hata raporlarını Microsoft'a gönderir.

## <a name="remarks"></a>Açıklamalar

**/Errorreport** seçeneği iç derleyici hatası (çok) bilgilerini doğrudan Microsoft'a olanak sağlar.

Seçenek **/errorreport:send** Windows Hata Raporlama hizmeti ayarları tarafından etkinleştirilirse hata bilgilerini Microsoft'a otomatik olarak gönderir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş** özellik sayfası.

1. Değiştirme **hata raporlama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/errorReport (Dahili Derleme Hatalarını Raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md)  
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)  
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)  
