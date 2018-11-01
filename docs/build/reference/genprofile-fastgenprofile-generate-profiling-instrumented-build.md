---
title: / GENPROFILE, fastgenprofıle (profil oluşturma üret)
ms.date: 03/14/2018
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
ms.openlocfilehash: e703c94d4a8b7cf7c70e68071959b775987f1710
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496453"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/ GENPROFILE, fastgenprofıle (profil oluşturma üret)

Profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyası oluşturulmasını belirtir. **/ GENPROFILE** ve **fastgenprofıle** farklı varsayılan parametreleri kullanın. Kullanım **/genprofıle** duyarlık hızı ve bellek kullanımı profil oluşturma sırasında yerine boyuta ayrıcalık. Kullanım **fastgenprofıle** duyarlılık üzerinde daha küçük bellek kullanımı ve hız yerine boyuta ayrıcalık.

## <a name="syntax"></a>Sözdizimi

> **/ GENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **EXACT**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Yolu**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_filename_}]<br/>
> **/ FASTGENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **EXACT**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Yolu**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_filename_}]

### <a name="arguments"></a>Arguments

Aşağıdaki bağımsız değişken için belirtilebilir **/genprofıle** veya **fastgenprofıle**. Burada listelenen bağımsız değişkenleri bir çubukla ayrılan (**|**) karakter karşılıklı olarak birbirini dışlar. Virgül kullanın (**,**) seçenekleri ayırmak için karakter.

**COUNTER32** &AMP;#124; **COUNTER64**<br/>
Kullanma **COUNTER32** 32-bit araştırma sayaçları kullanımını belirlemek için ve **COUNTER64** 64-bit araştırma sayaçları belirtmek için. Belirttiğinizde **/genprofıle**, varsayılan **COUNTER64**. Belirttiğinizde **fastgenprofıle**, varsayılan **COUNTER32**.

**TAM** &AMP;#124; **NOEXACT**<br/>
Kullanım **EXACT** araştırmaları için iş parçacığı açısından güvenli birbirine kenetlenmiş artışlarla belirtmek için. **NOEXACT** araştırmaları için korumasız artırma işlemleri belirtir. Varsayılan değer **NOEXACT**.

**MEMMAX**=*değer*, **MEMMIN**=*değeri*<br/>
Kullanım **MEMMAX** ve **MEMMIN** bellekte eğitim verileri maksimum ve minimum rezervasyon boyutunu belirtmek için. Bayt cinsinden ayrılacak bellek miktarını değerdir. Varsayılan olarak, bu değerleri, iç bir buluşsal yöntem tarafından belirlenir.

**YOL** &AMP;#124; **NOPATH**  <br/>
Kullanım **yolu** PGO sayaçları her benzersiz yolu bir işlev için ayrı bir kümesini belirtmek için. Kullanım **NOPATH** sayaçları her işlev için yalnızca bir kümesini belirtmek için. Belirttiğinizde **/genprofıle**, varsayılan **yolu** . Belirttiğinizde **fastgenprofıle**, varsayılan **NOPATH** .

**TRACKEH** &AMP;#124; **NOTRACKEH**  <br/>
Eğitim sırasında özel durumlar oluşturulduğunda bir doğru sayısı korumak için ek sayaçları kullanılıp kullanılmayacağını belirtir. Kullanım **TRACKEH** ek sayaçları için bir tam sayı belirtmek için. Kullanma **NOTRACKEH** tek özel durum kullanmayan kod sayaçları belirtmek için işleme ya da özel durumlarını araştırma, eğitim senaryolarını karşılaşılmadı.  Belirttiğinizde **/genprofıle**, varsayılan **TRACKEH** . Belirttiğinizde **fastgenprofıle**, varsayılan **NOTRACKEH** .

**PGD**=*dosya adı*<br/>
.Pgd dosyası için bir temel dosya adı belirtir. Varsayılan olarak bağlayıcı bir .pgd uzantısı ile temel bir yürütülebilir görüntü dosya adı kullanır.

## <a name="remarks"></a>Açıklamalar

**/Genprofıle** ve **fastgenprofıle** profil temelli iyileştirme (PGO) için uygulama eğitim desteklemek için gereken profil oluşturma araçları dosyasını oluşturmak için bağlayıcı seçenekleri söyleyin. Bu seçenekler, Visual Studio 2015'te yenidir. Kullanım dışı olan bu seçenekleri tercih **/LTCG:PGINSTRUMENT**, **/PGD** ve **/POGOSAFEMODE** seçenekleri ve **PogoSafeMode**,  **Vcprofıle_alloc_scale** ve **vcprofıle_path** ortam değişkenleri. Uygulama eğitim tarafından oluşturulan profil bilgilerini gerçekleştirmek için giriş bütün program iyileştirmeleri derleme sırasında hedef olarak kullanılır. Derlemeler ve uygulama eğitim sırasında performansı için çeşitli profil oluşturma özellikleri denetlemek için ek seçenekler ayarlayabilirsiniz. Tarafından belirtilen varsayılan Seçenekler **/genprofıle** özellikle büyük, karmaşık çok iş parçacıklı uygulamalar için en doğru sonuçlar verir. **Fastgenprofıle** seçeneği, daha küçük bellek Ayak izi ve eğitim, doğruluktan sırasında daha hızlı performans için varsayılan değerleri farklı kullanır.

Profil oluşturma bilgileri yakalanmıyor kullanarak derledikten sonra izleme eklenmiş uygulama çalıştırdığınızda **/genprofıle** , **fastgenprofıle**. Bu bilgiler, belirttiğiniz zaman yakalanır [/USEPROFILE](useprofile.md) bağlayıcı seçeneği, profil oluşturma gerçekleştirmek için adım ve en iyi duruma getirilmiş yapı adımının yol göstermesi için kullanılır. Uygulamanızı geliştirmek nasıl daha fazla bilgi ve toplanan verileri hakkında ayrıntılı bilgi için bkz: [profil temelli iyileştirme](profile-guided-optimizations.md).

De belirtmeniz gerekir **/LTCG** belirttiğinizde **/genprofıle** veya **fastgenprofıle**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/genprofıle** veya **fastgenprofıle** seçenekleri ve bağımsız değişkenleriyle **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/LTCG (Bağlama Zamanı Kodu Oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)<br/>
