---
title: /PROFILE (Performans Araçları Profil Oluşturucusu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 26f4ba4efc20f5fee70b2937cdb943689c948888
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519928"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Performans Araçları Profil Oluşturucusu)

Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.

## <a name="syntax"></a>Sözdizimi

```
/PROFILE
```

## <a name="remarks"></a>Açıklamalar

/ PROFILE bağlayıcı şunlardan anlamına gelir:

- [/ OPT: REF](../../build/reference/opt-optimizations.md)

- / OPT: NOICF

- [/ INCREMENTAL: NO](../../build/reference/incremental-link-incrementally.md)

- [/ FIXED: NO](../../build/reference/fixed-fixed-base-address.md)

/ PROFILE bağlayıcı program görüntüyü bir yeniden konumlandırma bölümü oluşturmak neden olur.  Bir yeniden konumlandırma bölümü profil verilerini almak için program görüntüyü dönüştürmek profil oluşturucu sağlar.

**/ PROFİL** yalnızca (takım geliştirme) Enterprise sürümlerinde kullanılabilir.  PREfast hakkında daha fazla bilgi için bkz. [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **profili** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)