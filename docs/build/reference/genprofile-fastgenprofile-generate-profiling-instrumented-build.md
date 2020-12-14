---
description: Şu konuda daha fazla bilgi edinin:/GENPROFILE,/FASTGENPROFıLE (Profil Oluşturucu belgelenmiş derleme oluştur)
title: /GENPROFILE,/FASTGENPROFıLE (profil oluşturma belgelenmiş derleme oluştur)
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
ms.openlocfilehash: 7bb0f9b1c7a6036c5e721f79b438bf9dd6504111
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200240"
---
# <a name="genprofile-fastgenprofile-generate-profiling-instrumented-build"></a>/GENPROFILE,/FASTGENPROFıLE (profil oluşturma belgelenmiş derleme oluştur)

Profil temelli iyileştirme (PGO) desteği için bağlayıcı tarafından bir. pgd dosyasının üretilmesini belirtir. **/Genprofile** ve **/fastgenprofile** farklı varsayılan parametreler kullanır. Profil oluşturma sırasında hız ve bellek kullanımının doğruluğunu tercih etmek için **/Genprofile** kullanın. Daha küçük bellek kullanımını ve Duyarlığın hızını artırmak için **/Fastgenprofile** kullanın.

## <a name="syntax"></a>Syntax

> **/Genprofile** \[ **:**{ \[ **COUNTER32** \| **COUNTER64**] \| \[ **tam** \| **yok**] \| **MEMMAX =** _#_ \| **memmin =** _#_ \| \[ **Path** \| **NOPATH**] \| \[ **TRACKEH** \| **NOTRACKEH** ] \| **PGD =**_filename_}] \
> **/Fastgenprofile** \[ **:**{ \[ **COUNTER32** \| **COUNTER64**] \| \[ **tam** \| **yok**] \| **MEMMAX =** _#_ \| **memmin**= _#_ \| [**Path** \| **NOPATH** ] \| \[ **TRACKEH** \| **NOTRACKEH** ] \| **PGD =**_filename_}]

### <a name="arguments"></a>Arguments

Aşağıdaki bağımsız değişkenlerden biri **/Genprofile** veya **/fastgenprofile** olarak belirtilebilir. Burada bir kanal () karakteriyle ayrılmış olarak listelenen bağımsız değişkenler **|** birbirini dışlıyor. Seçenekleri ayırmak için virgül (**,**) karakterini kullanın.

**COUNTER32** &#124; **COUNTER64**<br/>
32 bitlik araştırma sayaçlarının kullanımını belirtmek için **COUNTER32** kullanın ve 64-bit araştırma sayaçlarını belirtmek için **COUNTER64** . **/Genprofile** belirttiğinizde varsayılan değer **COUNTER64**' dir. **/Fastgenprofile** belirttiğinizde varsayılan değer **COUNTER32**' dir.

**Tam** &#124; **NOTAM**<br/>
Yoklamalar için iş parçacığı güvenli karşılıklı kilitli artışlarını belirtmek için **tam** kullanın. **NOTAM** , yoklamalar için korumasız artırma işlemleri belirtir. Varsayılan değer **NOTAM**' dır.

**MEMMAX** = *değer*, **memmin** = *değeri*<br/>
Bellekte eğitim verileri için maksimum ve en düşük ayırma boyutunu belirtmek için **MEMMAX** ve **memmin** kullanın. Değer, ayrılan bellek miktarıdır (bayt cinsinden). Varsayılan olarak, bu değerler dahili bir buluşsal yöntem tarafından belirlenir.

**Yol**  &#124; **NOPATH** <br/>
Bir işleve yönelik her benzersiz yol için ayrı bir PGO sayaç kümesi belirtmek üzere **yolunu**  kullanın. Her bir işlev için yalnızca bir sayaç kümesi belirtmek üzere **NOPATH**  kullanın. **/Genprofile** belirttiğinizde, varsayılan **yoldur** . **/Fastgenprofile** belirttiğinizde, varsayılan olarak **NOPATH** olur.

**Trackingkeh**  &#124; **NOTRACKEH** <br/>
Eğitim sırasında özel durumlar oluştuğunda doğru bir sayı tutmak için ek sayaçların kullanılıp kullanılmayacağını belirtir. Tam sayı için ek sayaçlar belirtmek üzere **TRACKEH**  kullanın. Özel durum işleme kullanmayan veya eğitim senaryolarınızda özel durumlarla karşılaşmayan kod için tek sayaçlar belirtmek üzere **NOTRACKEH**  kullanın.  **/Genprofile** belirttiğinizde, varsayılan olarak **TRACKEH** olur. **/Fastgenprofile** belirttiğinizde, varsayılan olarak **NOTRACKEH** olur.

**PGD** = *dosya adı*<br/>
. Pgd dosyası için bir taban dosya adı belirtir. Varsayılan olarak, bağlayıcı temel yürütülebilir görüntü dosyası adını. pgd uzantısıyla kullanır.

## <a name="remarks"></a>Açıklamalar

**/Genprofile** ve **/fastgenprofile** seçenekleri bağlayıcıya, profil temelli iyileştirme (PGO) için uygulama eğitimini desteklemek üzere gereken profil oluşturma izleme dosyasını oluşturmasını söyler. Bu seçenekler, Visual Studio 2015 ' de yenidir. Bu seçenekleri kullanım dışı **/LTCG: PGıNSTRUMENT**, **/PGD** ve **/POGOSAFEMODE** options ve **POGOSAFEMODE**, **VCPROFILE_ALLOC_SCALE** ve **VCPROFILE_PATH** ortam değişkenlerine tercih edin. Uygulama eğitimi tarafından oluşturulan profil oluşturma bilgileri, derlemeler sırasında hedeflenen tam program iyileştirmeleri gerçekleştirmek için giriş olarak kullanılır. Uygulama eğitimi ve derlemeler sırasında performans için çeşitli profil oluşturma özelliklerini denetlemek üzere ek seçenekler ayarlayabilirsiniz. **/Genprofile** tarafından belirtilen varsayılan seçenekler, özellikle büyük ve karmaşık çok iş parçacıklı uygulamalar için en doğru sonuçları verir. **/Fastgenprofile** seçeneği, düşük bellek kaplama ve eğitim sırasında daha hızlı performans için farklı varsayılanlar kullanır, doğruluk masrafında.

**/Fastgenprofile**' in **/GENPROFILE** kullanılarak oluşturulduktan sonra, bir profil oluşturma bilgileri, Araçlı uygulamayı çalıştırdığınızda yakalanır. Bu bilgiler, profil oluşturma adımını gerçekleştirmek için [/Useprofile](useprofile.md) bağlayıcı seçeneğini belirttiğinizde ve ardından iyileştirilmiş derleme adımına kılavuzluk etmek için kullanılırsa yakalanır. Uygulamanızı ve ayrıntıları toplanan verilerle eğitme hakkında daha fazla bilgi için bkz. [Profil temelli iyileştirmeler](../profile-guided-optimizations.md).

**/Genprofile** veya **/Fastgenprofile** belirttiğinizde, **/LTCG** de belirtmeniz gerekir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler** kutusuna **/Genprofile** veya **/fastgenprofile** seçeneklerini ve bağımsız değişkenlerini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[/LTCG (bağlama zamanı kodu oluşturma)](ltcg-link-time-code-generation.md)<br/>
