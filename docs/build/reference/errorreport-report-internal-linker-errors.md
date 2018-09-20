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
ms.openlocfilehash: 3b4b19eed4b481ffa44688e15fb1567e73da1a8f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46373472"
---
# <a name="errorreport-report-internal-linker-errors"></a>/ERRORREPORT (Dahili Bağlayıcı Hatalarını Raporla)

> **/ errorreport:**[ **hiçbiri** | **istemi** | **kuyruk** | **Gönder** ]

## <a name="arguments"></a>Arguments

**Yok**<br/>
Derleyici iç hatalarıyla ilgili raporlar toplanmaz ve Microsoft'a gönderilir.

**istemi**<br/>
Derleyici iç hatası aldığınızda rapor göndermek isteyip istemediğinizi sorar. **İstemi** geliştirme ortamında uygulama derlendiğinde varsayılandır.

**Kuyruk**<br/>
Hata raporunu kuyruğa alır. Böylece son kez oturum açtıktan sonra herhangi bir hata rapor, yönetici ayrıcalıklarıyla oturum açtığınızda, bir pencere görüntülenir (, üç günde birden çok kez hata raporu göndermek isteyip istemediğiniz değil). **Kuyruk** bir komut isteminde uygulama derlendiğinde varsayılandır.

**Gönder**<br/>
Otomatik olarak Windows hata bildirimi hizmeti ayarları tarafından raporlama etkinse, derleyici iç hata raporlarını Microsoft'a gönderir.

## <a name="remarks"></a>Açıklamalar

**/Errorreport** seçeneği derleyici iç hatası (ICE) bilgilerini doğrudan Microsoft'a sağlamasına olanak sağlar.

Seçenek **okunmalı** Windows hata bildirimi hizmeti ayarları tarafından etkinleştirilirse hata bilgileri Microsoft'a otomatik olarak gönderir.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Açık **yapılandırma özellikleri** > **bağlayıcı** > **Gelişmiş** özellik sayfası.

1. Değiştirme **hata raporlama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/errorReport (Dahili Derleme Hatalarını Raporla)](../../build/reference/errorreport-report-internal-compiler-errors.md)<br/>
[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
