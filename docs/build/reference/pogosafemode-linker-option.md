---
title: / POGOSAFEMODE (iş parçacığı güvenli modda PGO çalıştırın) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- POGOSAFEMODE
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 886fbae5fbeb7606ec0321595f061d2262988170
ms.sourcegitcommit: ee7d74683af7631441c8c7f65ef5ceceaee4a5ee
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/22/2018
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (iş parçacığı güvenli modda PGO çalıştırın)

**Visual Studio 2015'ten başlayarak /POGOSAFEMODE seçeneği kullanım dışıdır**. Kullanım [/GENPROFILE: tam](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve **/GENPROFILE:NOEXACT** yerine seçenekleri. **/POGOSAFEMODE** bağlayıcı seçeneği belirtir Araçlı derleme çalıştırır eğitim profil verilerini yakalama için profil temelli iyileştirme (PGO) sırasında iş parçacığı açısından güvenli modunu kullanacak şekilde oluşturulur.

## <a name="syntax"></a>Sözdizimi

> **/POGOSAFEMODE**

## <a name="remarks"></a>Açıklamalar

Profil temelli iyileştirme (PGO) sahip iki olası modları profil oluşturma aşamasında: *hızlı mod* ve *güvenli mod*. Profil oluşturma Hızlı modda olduğunda, bir artış yönerge veri sayaçları artırmak için kullanır. Artışı yönergeyi hızlıdır ancak iş parçacığı açısından güvenli değil. Profil oluşturma güvenli modda olduğunda, interlocked artışı yönergeyi veri sayaçları artırmak için kullanır. Bu yönerge, artışı yönergeyi sahiptir ve iş parçacığı, ancak daha yavaştır, gibi aynı işlevselliği vardır.

**/POGOSAFEMODE** seçeneği Araçlı derleme güvenli modunu kullanacak şekilde ayarlar. Bu seçenek yalnızca kullanılabilir olduğunda kullanılabilir kullanım dışı [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) PGO araçları bağlayıcı aşaması sırasında belirtilir.

Varsayılan olarak, PGO profil hızlı modunda çalışır. **/ POGOSAFEMODE** olduğundan yalnızca güvenli mod kullanmak istiyorsanız gereklidir.

Güvenli modda PGO profil çalıştırmak için ya da kullanmanız gerekir **/GENPROFILE: tam** (önerilen) veya ortam değişkeni [PogoSafeMode](environment-variables-for-profile-guided-optimizations.md) ya da bağlayıcı anahtar **/POGOSAFEMODE**sistemine bağlı olarak. Profil oluşturma x x64 üzerinde gerçekleştirdiğiniz, bilgisayar, bağlayıcı anahtarı kullanmanız gerekir. Profil oluşturma x x86 üzerinde gerçekleştirdiğiniz, bilgisayar, bağlayıcı anahtarını kullanın veya PGO araçları işlemine başlamadan önce herhangi bir değere ortam değişkeni tanımlamak.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **en iyi duruma getirme** özellik sayfası.

1. İçinde **bağlantı zamanı kodu oluşturma** özelliği seçin **profil temelli iyileştirme - Gereci (/ LTCG:PGInstrument)**.

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/POGOSAFEMODE** içine seçeneği **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/ GENPROFILE ve /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)<br/>
[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
