---
title: /PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 68d112c0a40289ba62e3fe5c37ae23f8f55f9209
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601298"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)

**/PGD seçeneği kullanım dışı bırakılmıştır.** Visual Studio 2015'ten başlayarak tercih [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) bağlayıcı seçenekleri yerine. Bu seçenek, profil temelli iyileştirme işlemi tarafından kullanılan bir .pgd dosyası adını belirtmek için kullanılır.

## <a name="syntax"></a>Sözdizimi

> **/ PGD:**_dosya adı_

## <a name="argument"></a>Bağımsız Değişken

*Dosya adı*<br/>
Çalışan programa hakkındaki bilgileri tutmak için kullanılan bir .pgd dosyası adını belirtir.

## <a name="remarks"></a>Açıklamalar

Kullanım dışı kullanırken [/LTCG:PGINSTRUMENT](../../build/reference/ltcg-link-time-code-generation.md) seçeneğinde, kullanın **/PGD** varsayılan olmayan ad veya .pgd dosyası için konumu belirtin. Siz belirtmezseniz **/PGD**, .pgd dosyası taban adı çıkış dosyası (.exe veya .dll) taban adı ile aynıdır ve içinden bağlantı çağrıldığı dizininde oluşturulur.

Kullanım dışı kullanırken **/LTCG:PGOPTIMIZE** seçeneğinde, kullanın **/PGD** iyileştirilmiş görüntü oluşturmak için kullanılacak .pgd dosyası adını belirtmek için seçeneği. *Filename* bağımsız değişken eşleşmelidir *filename* belirtilen **/LTCG:PGINSTRUMENT**.

Daha fazla bilgi için [profil temelli iyileştirme](../../build/reference/profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfası.

1. Değiştirme **profil destekli veritabanı** özelliği. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
