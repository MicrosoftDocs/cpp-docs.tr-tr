---
title: / GENPROFILE, /FASTGENPROFILE (Araçlı derleme Profil Oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- GENPROFILE
- FASTGENPROFILE
- /GENPROFILE
- /FASTGENPROFILE
helpviewer_keywords:
- GENPROFILE
- FASTGENPROFILE
ms.assetid: deff5ce7-46f5-448a-b9cd-a7a83a6864c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 05d7961ff46661b8f6df2768591932699c3965d4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32379308"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/ GENPROFILE, /FASTGENPROFILE (Araçlı derleme Profil Oluştur)

Profil temelli iyileştirme (PGO) desteklemek için bağlayıcı tarafından bir .pgd dosyasının üretilmesi belirtir. **/ GENPROFILE** ve **/FASTGENPROFILE** farklı varsayılan parametrelerini kullanın. Kullanım **/GENPROFILE** profil oluşturma sırasında duyarlık hızı ve bellek kullanımı ayrıcalık tanıma için. Kullanım **/FASTGENPROFILE** küçük bellek kullanımı ve hız duyarlık ayrıcalık tanıma için.

## <a name="syntax"></a>Sözdizimi

> **/ GENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **Tam**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Yolu**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_filename_}]<br/>
> **/ FASTGENPROFILE**[**:**{[**COUNTER32**|**COUNTER64**] | [ **Tam**|**NOEXACT**] | **MEMMAX =**_#_|**MEMMIN =**_#_| [ **Yolu**|**NOPATH** ] | [ **TRACKEH** |**NOTRACKEH** ] | **PGD =**_filename_}]

### <a name="arguments"></a>Arguments

Aşağıdaki bağımsız değişkenlerden biri için belirtilebilir **/GENPROFILE** veya **/FASTGENPROFILE**. Burada listelenen bağımsız değişkenleri dikey çubukla ayrılan (**|**) karakter karşılıklı olarak birbirini dışlar. Bir virgül kullanın (**,**) seçenekleri ayırmak için karakter.

**COUNTER32** &AMP;#124; **COUNTER64**<br/>
Kullanmak **COUNTER32** 32-bit araştırma sayaçları kullanıldığını belirtmek için ve **COUNTER64** 64-bit araştırma sayaçları belirtmek için. Belirttiğinizde **/GENPROFILE**, varsayılan **COUNTER64**. Belirttiğinizde **/FASTGENPROFILE**, varsayılan **COUNTER32**.

**TAM** &AMP;#124; **NOEXACT**<br/>
Kullanım **tam** araştırmalar için iş parçacığı ınterlocked artışlarla belirtmek için. **NOEXACT** araştırmalar korumasız artışı işlemlerinde belirtir. Varsayılan değer **NOEXACT**.

**MEMMAX**=*değeri*, **MEMMIN**=*değeri*<br/>
Kullanım **MEMMAX** ve **MEMMIN** bellekte eğitim verileri için maksimum ve minimum ayırma boyutunu belirlemek için. Bayt cinsinden ayrılan bellek miktarını değerdir. Varsayılan olarak, bu değerleri bir iç buluşsal yöntem tarafından belirlenir.

**YOL** &AMP;#124; **NOPATH** <br/>
Kullanım **yolu** PGO sayaçları her benzersiz yolu bir işlev için ayrı bir dizi belirtmek için. Kullanım **NOPATH** sayaçları her işlevi için yalnızca bir kümesini belirtmek için. Belirttiğinizde **/GENPROFILE**, varsayılan **yolu** . Belirttiğinizde **/FASTGENPROFILE**, varsayılan **NOPATH** .

**TRACKEH** &AMP;#124; **NOTRACKEH** <br/>
Eğitim sırasında özel durumlar sırasında doğru sayısı tutmak için fazladan sayaçlar kullanılıp kullanılmayacağını belirtir. Kullanım **TRACKEH** bir tam sayı için fazladan sayaçlar belirtmek için. Kullanmak **NOTRACKEH** tek özel durum kullanmaz kod sayaçlarını belirtmek için işleme ya da özel durumlar, eğitim senaryolarda karşılaştığınız değil.  Belirttiğinizde **/GENPROFILE**, varsayılan **TRACKEH** . Belirttiğinizde **/FASTGENPROFILE**, varsayılan **NOTRACKEH** .

**PGD**=*dosya adı*<br/>
.Pgd dosyası için bir temel dosya adı belirtir. Varsayılan olarak, bağlayıcı .pgd uzantısı ile temel yürütülebilir görüntü dosya adını kullanır.

## <a name="remarks"></a>Açıklamalar

**/GENPROFILE** ve **/FASTGENPROFILE** seçenekleri uygulama eğitim profil temelli iyileştirme için (PGO) desteklemek için gereken profil oluşturma araçları dosyası oluşturmak için bağlayıcı söyleyin. Bu seçenekler, Visual Studio 2015'te yenidir. Bu seçenekler için kullanım dışı tercih **/LTCG:PGINSTRUMENT**, **/PGD** ve **/POGOSAFEMODE** seçenekleri ve **PogoSafeMode**,  **Vcprofıle_alloc_scale** ve **vcprofıle_path** ortam değişkenleri. Uygulama eğitim tarafından oluşturulan profil bilgilerini gerçekleştirmek için giriş sırasında derlemeleri bütün program iyileştirmeleri hedeflenen olarak kullanılır. Derlemeler ve uygulama eğitim sırasında performansı için çeşitli profil özelliklerini denetlemek için ek seçenekler ayarlayabilirsiniz. Tarafından belirlenen varsayılan seçenekleri **/GENPROFILE** özellikle büyük ve karmaşık çok iş parçacıklı uygulamalar için en doğru sonuçlar verir. **/FASTGENPROFILE** seçenek daha düşük bellek alanını ve doğruluk ödün verme pahasına eğitim sırasında daha hızlı performans farklı Varsayılanları kullanır.

Bilgi profil yakalanır kullanarak yapı sonra Araçlı uygulamayı çalıştırdığınızda **/GENPROFILE** , **/FASTGENPROFILE**. Bu bilgileri belirttiğinizde yakalanan [/USEPROFILE](useprofile.md) profil gerçekleştirmek için bağlayıcı seçeneği adım ve en iyi duruma getirilmiş derleme adımı kılavuzluk etmesi için kullanılır. Uygulamanızı eğitmek hakkında daha fazla bilgi ve toplanan verileri hakkında ayrıntılar için bkz: [profil temelli iyileştirme](profile-guided-optimizations.md).

Ayrıca belirtmelisiniz **/LTCG** belirttiğinizde **/GENPROFILE** veya **/FASTGENPROFILE**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/GENPROFILE** veya **/FASTGENPROFILE** seçenekleri ve bağımsız değişkenleriyle **ek seçenekler** kutusu. Seçin **Tamam** yaptığınız değişiklikleri kaydetmek için.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[/LTCG (Bağlama Zamanı Kodu Oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)<br/>
