---
title: /PROFILE (Performans Araçları Profil Oluşturucusu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 23cbccba9a8ec839252d553cc5cbafd37e66bbf9
ms.sourcegitcommit: 14b292596bc9b9b883a9c58cd3e366b282a1f7b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60124778"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Performans Araçları Profil Oluşturucusu)

Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.

## <a name="syntax"></a>Sözdizimi

```
/PROFILE
```

## <a name="remarks"></a>Açıklamalar

/ PROFILE bağlayıcı şunlardan anlamına gelir:

- [/ OPT: REF](opt-optimizations.md)

- / OPT: NOICF

- [/ INCREMENTAL: NO](incremental-link-incrementally.md)

- [/FIXED:NO](fixed-fixed-base-address.md)

/ PROFILE bağlayıcı program görüntüyü bir yeniden konumlandırma bölümü oluşturmak neden olur.  Bir yeniden konumlandırma bölümü profil verilerini almak için program görüntüyü dönüştürmek profil oluşturucu sağlar.

**/ PROFİL** yalnızca (takım geliştirme) Enterprise sürümlerinde kullanılabilir.  PREfast hakkında daha fazla bilgi için bkz. [C/C++ genel bakış için Kod Analizi](/visualstudio/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** düğümü.

1. Genişletin **bağlayıcı** düğümü.

1. Seçin **Gelişmiş** özellik sayfası.

1. Değiştirme **profili** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Visual Studio CMake proje içinde bu bağlayıcı seçeneğini ayarlamak için

**CMake** projede yok bir **özellik sayfaları**, bağlayıcı seçenekleri tarafından düzenleniyor CMakeLists.txt ayarlayabilirsiniz.

1. Proje kök dizininde cmakelists.txt dosyasını açın.

1. Aşağıdaki kodu ekleyin. Ayrıntılar için bkz [CMake başvuruları](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. Çözümünüzü yeniden oluşturun.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>Ayrıca Bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)

