---
title: / PGD (Profil temelli iyileştirmeler için veritabanını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
dev_langs:
- C++
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9947e95e3d6c96d07eb12eb2f2a579e0ea1b3a6a
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)

**/PGD seçeneği kullanım dışıdır.** Visual Studio 2015'ten başlayarak tercih [/GENPROFILE veya /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) bağlayıcı seçenekleri yerine. Bu seçenek, profil temelli iyileştirme işlemi tarafından kullanılan .pgd dosyasının adını belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **/ PGD:**_dosya adı_

## <a name="argument"></a>Bağımsız Değişken

*Dosya adı*<br/>
Çalışan programla ilgili bilgileri saklamak için kullanılan .pgd dosya adını belirtir.

## <a name="remarks"></a>Açıklamalar

Kullanım dışı kullanırken [/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) seçeneği, kullanın **/PGD** varsayılan olmayan ad veya .pgd dosyası için konumu belirtin. Belirtmezseniz, **/PGD**, .pgd dosya temel adı çıktı dosyası (.exe veya .dll) temel adı ile aynıdır ve kendisinden bağlantıyı çağrıldığı aynı dizinde oluşturulur.

Kullanım dışı kullanırken **/LTCG:PGOPTIMIZE** seçeneği, kullanın **/PGD** seçeneği en iyi duruma getirilmiş görüntü oluşturmak için kullanılacak .pgd dosyasının adını belirtin. *Filename* bağımsız değişkeni eşleşmelidir *filename* belirtilen **/LTCG:PGINSTRUMENT**.

Daha fazla bilgi için bkz: [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **en iyi duruma getirme** özellik sayfası.

1. Değiştirme **profil destekli veritabanını** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
