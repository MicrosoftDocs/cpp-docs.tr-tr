---
title: / USEPROFILE (LTCG verilerle kullanım PGO) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- USEPROFILE
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156a571eaa3db31b8c5345f1550346503651665d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377999"
---
# <a name="useprofile-run-pgo-in-thread-safe-mode"></a>/ USEPROFILE (iş parçacığı güvenli modda PGO çalıştırın)

Bu bağlayıcı seçeneği ile birlikte [/LTCG (bağlama zamanı kodu oluşturma](ltcg-link-time-code-generation.md) profil temelli iyileştirme (PGO) eğitim verileri kullanarak derleme için bağlayıcı söyler.

## <a name="syntax"></a>Sözdizimi

> **/ USEPROFILE**[**:**{**etkin**|**PGD =**_filename_}]

### <a name="arguments"></a>Arguments

**AGRESİF**<br/>
Bu isteğe bağlı bağımsız değişkeni agresif hızı en iyi duruma getirme en iyi duruma getirilmiş kod oluşturma sırasında kullanılması gerektiğini belirtir.

**PGD**=*dosya adı*<br/>
.Pgd dosyası için bir temel dosya adı belirtir. Varsayılan olarak, bağlayıcı .pgd uzantısı ile temel yürütülebilir dosyanın adını kullanır.

## <a name="remarks"></a>Açıklamalar

**/USEPROFILE** bağlayıcı seçeneği ile birlikte kullanıldığında **/LTCG** PGO eğitim verilerine dayalı en iyi duruma getirilmiş bir sürüme güncelleştirmek veya oluşturmak için. Kullanım dışı denk olan **/LTCG:PGUPDATE** ve **/LTCG:PGOPTIMIZE** seçenekleri.

İsteğe bağlı **etkin** bağımsız değişkeni, hızı en iyi duruma getirme girişiminde boyutu ilgili buluşsal yöntemler devre dışı bırakır. Bu, önemli ölçüde yürütülebilir dosyanın boyutunu artırın ve sonuçta elde edilen hızını artırabilir değil iyileştirmeleri neden olabilir. Profil ve sonuçları kullanarak ve kullanmıyorsa, karşılaştırma **etkin**. Bu bağımsız değişken açıkça belirtilmesi gerekir; Varsayılan olarak etkin değildir.

**PGD** bağımsız değişkeni kullanmak de aynı eğitim veri .pgd dosyası için isteğe bağlı bir ad belirtir [/GENPROFILE veya /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md). Kullanım dışı denk olan **/PGD** geçin. Varsayılan olarak, veya yoksa *filename* belirtilen yürütülebilir dosya kullanılan aynı taban adına sahip bir .pgd dosya.

**/USEPROFILE** bağlayıcı seçeneği Visual Studio 2015'te yenidir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **en iyi duruma getirme** özellik sayfası.

1. İçinde **bağlantı zamanı kodu oluşturma** özelliği seçin **kullanım bağlantı zamanı kodu oluşturma (/ LTCG)**.

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/USEPROFILE** seçeneği ve isteğe bağlı bağımsız değişkenler **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[/ GENPROFILE ve /FASTGENPROFILE](genprofile-fastgenprofile-generate-profiling-instrumented-build.md)<br/>
[/LTCG](ltcg-link-time-code-generation.md)<br/>
[Profil Temelli İyileştirmeler](../../build/reference/profile-guided-optimizations.md)<br/>
[Profil Temelli İyileştirmeler için Ortam Değişkenleri](../../build/reference/environment-variables-for-profile-guided-optimizations.md)<br/>
