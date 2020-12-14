---
description: Daha fazla bilgi edinin:/PGD (Profile-Guided Iyileştirmeler için veritabanını belirt)
title: /PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)
ms.date: 03/14/2018
f1_keywords:
- VC.Project.VCLinkerTool.ProfileGuidedDatabase
helpviewer_keywords:
- -PGD linker option
- /PGD linker option
ms.assetid: 9f312498-493b-461f-886f-92652257e443
ms.openlocfilehash: 7030ddaef33c6ee794c470df2c42c72d78555369
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225992"
---
# <a name="pgd-specify-database-for-profile-guided-optimizations"></a>/PGD (Profil Temelli İyileştirmeler için Veritabanını Belirt)

**/PGD seçeneği kullanım dışıdır.** Visual Studio 2015 ' den başlayarak, bunun yerine [/genprofile veya/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) bağlayıcı seçeneklerini tercih edin. Bu seçenek, profil temelli iyileştirme işlemi tarafından kullanılan. pgd dosyasının adını belirtmek için kullanılır.

## <a name="syntax"></a>Syntax

> **/PGD:**_filename_

## <a name="argument"></a>Bağımsız Değişken

*filename*<br/>
Çalışan programla ilgili bilgileri tutmak için kullanılan. pgd dosyasının adını belirtir.

## <a name="remarks"></a>Açıklamalar

Kullanım dışı [/LTCG: PGıNSTRUMENT](ltcg-link-time-code-generation.md) seçeneğini kullanırken,. pgd dosyası için varsayılan adı veya konumu belirtmek için **/PGD** kullanın. **/PGD** belirtmezseniz,. pgd dosya taban adı çıkış dosyası (. exe veya. dll) temel adıyla aynıdır ve bağlantının çağrıldığı dizinde oluşturulur.

Kullanım dışı **/LTCG: PGOPTIMIZE** seçeneği kullanılırken, en iyileştirilmiş görüntüyü oluşturmak için kullanılacak. pgd dosyasının adını belirtmek için **/PGD** seçeneğini kullanın. *Filename* bağımsız değişkeni **/LTCG: PGINSTRUMENT** olarak belirtilen *dosya adıyla* eşleşmelidir.

Daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **iyileştirme** özellik sayfasını seçin.

1. **Profil temelli veritabanı** özelliğini değiştirin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ProfileGuidedDatabase%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
