---
description: Daha fazla bilgi edinin:/POGOSAFEMODE (iş parçacığı güvenli modunda PGO Çalıştır)
title: /POGOSAFEMODE (iş parçacığı güvenli modunda PGO Çalıştır)
ms.date: 03/14/2018
f1_keywords:
- POGOSAFEMODE
ms.openlocfilehash: dfe8d46a3008a1d41156d077e5b87e50ac345e18
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225927"
---
# <a name="pogosafemode-run-pgo-in-thread-safe-mode"></a>/POGOSAFEMODE (iş parçacığı güvenli modunda PGO Çalıştır)

**/POGOSAFEMODE seçeneği, Visual Studio 2015 ' den itibaren kullanım dışıdır**. Bunun yerine [/Genprofile: tam](genprofile-fastgenprofile-generate-profiling-instrumented-build.md) ve **/GENPROFILE: NOTAM** seçenekleri kullanın. **/POGOSAFEMODE** bağlayıcı seçeneği, profil temelli iyileştirme (PGO) eğitim çalıştırmaları sırasında profil verileri yakalama için iş parçacığı güvenli modunu kullanmak üzere belgelenmiş derleme oluşturulduğunu belirtir.

## <a name="syntax"></a>Syntax

> **/POGOSAFEMODE**

## <a name="remarks"></a>Açıklamalar

Profil temelli iyileştirme (PGO), profil oluşturma aşamasında iki olası moda sahiptir: *hızlı mod* ve *Güvenli mod*. Profil oluşturma hızlı moddayken, veri sayaçlarını artırmak için bir artış yönergesi kullanır. Artış yönergesi daha hızlıdır, ancak iş parçacığı açısından güvenli değildir. Profil oluşturma güvenli moddayken, veri sayaçlarını artırmak için ınterkilitlenen artırma yönergesini kullanır. Bu yönerge, artırma yönergesi ile aynı işlevselliğe sahiptir ve iş parçacığı açısından güvenlidir, ancak daha yavaştır.

**/POGOSAFEMODE** seçeneği, belgelenmiş derlemeyi güvenli mod kullanacak şekilde ayarlar. Bu seçenek yalnızca kullanım dışı [/LTCG: PGıNSTRUMI](ltcg-link-time-code-generation.md) belirtildiğinde, PGO izleme bağlayıcı aşaması sırasında kullanılabilir.

Varsayılan olarak, PGO profil oluşturma hızlı modda çalışır. **/POGOSAFEMODE** yalnızca güvenli mod kullanmak istiyorsanız gereklidir.

PGO profil oluşturmayı güvenli modda çalıştırmak için **/Genprofile: tam** (tercih edilen) veya [PogoSafeMode](../environment-variables-for-profile-guided-optimizations.md) ortam değişkenini ya da sisteme bağlı olarak **/POGOSAFEMODE** bağlayıcı anahtarını kullanmanız gerekir. Bir x64 bilgisayarda profil oluşturma işlemi yapıyorsanız bağlayıcı anahtarını kullanmanız gerekir. Bir x86 bilgisayarda profil oluşturma işlemi yapıyorsanız, PGO izleme işlemine başlamadan önce, bağlayıcı anahtarını kullanabilir veya ortam değişkenini herhangi bir değere tanımlayabilirsiniz.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **iyileştirme** özellik sayfasını seçin.

1. **Bağlama zamanı kodu üretimi** özelliğinde **Profil temelli iyileştirme-araç (/LTCG: PGINSTRUMENT)** öğesini seçin.

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/POGOSAFEMODE** seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/GENPROFILE ve/FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil temelli Iyileştirmeler](../profile-guided-optimizations.md)<br/>
[Profile-Guided Iyileştirmeleri için ortam değişkenleri](../environment-variables-for-profile-guided-optimizations.md)<br/>
