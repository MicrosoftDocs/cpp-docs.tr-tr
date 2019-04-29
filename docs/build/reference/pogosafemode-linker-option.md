---
title: / POGOSAFEMODE (iş parçacığı güvenli modda PGO çalıştırın)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: bbb328bf67d7823305a43f1d61252747cf5ea29e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62319726"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/ POGOSAFEMODE (iş parçacığı güvenli modda PGO çalıştırın)

**Visual Studio 2015'ten başlayarak /POGOSAFEMODE seçeneği kullanım dışı**. Kullanım [/genprofıle: tam](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve **/GENPROFILE:NOEXACT** yerine seçenekleri. **/POGOSAFEMODE** bağlayıcı seçeneğini belirtir eğitim çalıştırmaları profil verilerini yakalama için profil temelli iyileştirme (PGO) sırasında iş parçacığı açısından güvenli mod kullanmak üzere işaretlenmiş yapımda oluşturulur.

## <a name="syntax"></a>Sözdizimi

> **/POGOSAFEMODE**

## <a name="remarks"></a>Açıklamalar

Profil temelli iyileştirme (PGO) profil oluşturma aşamasında olası iki modu vardır: *hızlı mod* ve *güvenli mod*. Hızlı modda profil oluşturulduğunda, veri sayısını artırmak için bir artış yönerge kullanır. Artırma yönergesi daha hızlıdır ancak iş parçacığı açısından güvenli değildir. Güvenli modda profil oluşturulduğunda, veri sayısını artırmak için birbirine geçmiş artırma yönerge kullanır. Bu yönerge artırma yönerge sahiptir ve iş parçacığı açısından güvenlidir ancak daha yavaştır gibi aynı işlevlere sahiptir.

**/POGOSAFEMODE** seçeneği güvenli mod kullanmak için işaretlenmiş yapımda ayarlar. Bu seçenek yalnızca kullanılabilir olduğunda kullanılabilir kullanım dışı [/LTCG:PGINSTRUMENT](ltcg-link-time-code-generation.md) PGO izleme bağlayıcı aşaması sırasında belirtilir.

Varsayılan olarak, PGO profil oluşturma Hızlı modda çalışır. **/ POGOSAFEMODE** olduğundan yalnızca güvenli mod kullanmak isterseniz gereklidir.

PGO profil oluşturmayı güvenli modda çalıştırmak için ya da kullanmalısınız **/genprofıle: tam** (tercih edilir), veya ortam değişkenini kullanmak [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) veya bağlayıcı anahtarını **/POGOSAFEMODE**sistem bağlı olarak. X x64 profil oluşturma işlemi yapıyorsanız bilgisayarı bağlayıcı anahtarını kullanmanız gerekir. X x86 profil oluşturma işlemi yapıyorsanız bilgisayar, bağlayıcı anahtarını kullanarak olabilir veya PGO izleme işlemine başlamadan önce herhangi bir değere ortam değişkenini tanımlar.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfası.

1. İçinde **bağlama sırasında kod oluşturmayı** özelliği seçin **profil temelli iyileştirme - İzle (/ LTCG: pginstrument)**.

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/POGOSAFEMODE** içine seçeneği **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/ GENPROFILE ve fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil Temelli İyileştirmeler](../profile-guided-optimizations.md)<br/>
[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../environment-variables-for-profile-guided-optimizations.md)<br/>
