---
title: / USEPROFILE (LTCG ile kullanım PGO veriler)
ms.date: 03/14/2018
f1_keywords:
- USEPROFILE
ms.openlocfilehash: 4b780bed3b92b874f2bf18fb0235e8e2baf95ae9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50550637"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/ USEPROFILE (iş parçacığı güvenli modda PGO çalıştırın)

Bu bağlayıcı seçeneği ile birlikte [/LTCG (bağlama zamanı kod oluşturmayı](ltcg-link-time-code-generation.md) profil temelli iyileştirme (PGO) eğitim verilerini kullanarak yapı söyler.

## <a name="syntax"></a>Sözdizimi

> **/ USEPROFILE**[**:**{**AGRESİF**|**PGD =**_filename_}]

### <a name="arguments"></a>Arguments

**AGRESİF**<br/>
Bu isteğe bağlı bağımsız değişken agresif hız iyileştirmelerini en iyi duruma getirilmiş kod oluşturma sırasında kullanılması gerektiğini belirtir.

**PGD**=*dosya adı*<br/>
.Pgd dosyası için bir temel dosya adı belirtir. Varsayılan olarak bağlayıcı bir .pgd uzantısıyla temel yürütülebilir dosya adını kullanır.

## <a name="remarks"></a>Açıklamalar

**/USEPROFILE** bağlayıcı seçeneği ile birlikte kullanıldığında **/LTCG** PGO eğitim verilerini temel alarak en iyi duruma getirilmiş bir sürüme güncelleştirmek veya oluşturmak için. Kullanım dışı denk olan **/LTCG:PGUPDATE** ve **/LTCG:PGOPTIMIZE** seçenekleri.

İsteğe bağlı **AGRESİF** bağımsız değişkeni, hız için İyileştir denemek için buluşsal yöntemler boyutu ile ilgili devre dışı bırakır. Bu, önemli ölçüde yürütülebilir dosyanızın boyutunu artırın ve sonuçta elde edilen hızını artırabilir değil iyileştirmeler neden olabilir. Profil ve ve değil kullanarak sonuçlarını karşılaştırın **AGRESİF**. Bu bağımsız değişken açıkça belirtilmesi gerekir; Varsayılan olarak etkin değildir.

**PGD** bağımsız değişkeni belirtir isteğe bağlı bir ad kullanmak de aynı eğitim veri .pgd dosyası için [/genprofıle veya fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Kullanım dışı denk olan **/PGD** geçin. Varsayılan olarak, ya da hiçbir *filename* belirtilen yürütülebilir kullanıldıkça, aynı temel ada sahip bir .pgd dosyası.

**/USEPROFILE** bağlayıcı seçeneğini Visual Studio 2015'te yenidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **iyileştirme** özellik sayfası.

1. İçinde **bağlama sırasında kod oluşturmayı** özelliği seçin **kullanım bağlama sırasında kod oluşturma (/ LTCG)**.

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/USEPROFILE** seçeneği ve isteğe bağlı bağımsız değişkenler **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/ GENPROFILE ve fastgenprofıle](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)<br/>
[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
