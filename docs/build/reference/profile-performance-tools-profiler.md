---
title: /PROFILE (Performans Araçları Profil Oluşturucusu)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: 678816ce455d2a982ff8218becd805a0b2cdd896
ms.sourcegitcommit: 7bea0420d0e476287641edeb33a9d5689a98cb98
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/17/2020
ms.locfileid: "77416041"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE (Performans Araçları Profil Oluşturucusu)

Performans araçları Profilcisi ile kullanılabilecek bir çıkış dosyası üretir.

## <a name="syntax"></a>Sözdizimi

```
/PROFILE
```

## <a name="remarks"></a>Açıklamalar

/PROFILE aşağıdaki bağlayıcı seçeneklerini belirtir:

- [/OPT: REF](opt-optimizations.md)

- /OPT: NOıCF

- [/ARTıMLı: HAYıR](incremental-link-incrementally.md)

- [/FIXED: HAYıR](fixed-fixed-base-address.md)

/PROFILE, bağlayıcının program görüntüsünde bir konum değiştirme bölümü oluşturmasına neden olur.  Bir konum değiştirme bölümü, profil oluşturucunun profil verilerini almak için program görüntüsünü dönüştürmesini sağlar.

**/Profile** yalnızca Enterprise (Team Development) sürümlerinde kullanılabilir.  PREfast hakkında daha fazla bilgi için bkz. [C/C++ Overview için kod analizi](/cpp/code-quality/code-analysis-for-c-cpp-overview).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** düğümünü genişletin.

1. **Bağlayıcı** düğümünü genişletin.

1. **Gelişmiş** özellik sayfasını seçin.

1. **Profil** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>.

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>Visual Studio CMake projesi içinde bu bağlayıcı seçeneğini ayarlamak için

**CMake** projesinde bir **özellik sayfası**yok, bağlayıcı seçenekleri cmakelists. txt ' nin değiştirilmesine göre ayarlanabilir.

1. Proje kök dizininde CMakeLists. txt dosyasını açın.

1. Aşağıdaki kodu ekleyin. Ayrıntılar için bkz. [CMake başvuruları](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. Çözümünüzü yeniden oluşturun.

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>Ayrıca Bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)

