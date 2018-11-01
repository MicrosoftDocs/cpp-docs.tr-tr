---
title: /fp (Kayan Nokta Davranışını Belirt)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
ms.openlocfilehash: 8b948edba3244eb22089b2ef5b4c8131736e1fb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452578"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Kayan Nokta Davranışını Belirt)

Bir kaynak kodu dosyasında kayan nokta türü davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/ FP:**[**kesin** | **dışında**[**-**] | **hızlı** | **katı**]

### <a name="arguments"></a>Arguments

#### <a name="precise"></a>kesin

Varsayılan değer olan **/FP** olduğu **/FP: precise**.

**/FP: precise** bayrağı, kayan nokta hesaplamalarının duyarlığını değiştirme imkanınız iyileştirmeleri devre dışı bırakarak eşitlik ve eşitsizlik için kayan nokta testlerinin tutarlılığını artırır. (Katı ANSI uyumluluğu için belirli düzeyde duyarlığın korunması gereklidir.) Varsayılan olarak, kod x86 için kullanım x87 eşişlemcisi yönergeleri, derleyici eşişlemcisi kullanan mimarileri 80 bit kayan nokta hesaplamalarının Ara sonuçlarını tutmak için kaydeder. Bu program hızını artırır ve program boyutunu küçültür. Ancak, hesaplama, bellekte 80 bitten düşük olarak temsil edilen kayan nokta veri türleri içerdiği için, ekstra bit duyarlığını (80 bit eksi daha küçük bir kayan nokta türündeki bit sayısı) uzun bir hesaplama boyunca taşımak tutarsız sonuçlar verebilir.

İle **/FP: precise** x86 işlemcilerde, derleyici gerçekleştirir türündeki değişkenlerde yuvarlama `float` doğru duyarlığa yuvarlar için atamalar ve yayınlar ve ne zaman Parametreler bir işleve geçirilir. Bu yuvarlama, verinin, kendi türünün kapasitesinden büyük bir anlam taşımadığından emin olunmasını sağlar. Bir program ile derlenmiş **/FP: precise** daha yavaş ve olmadan derlenmiş bir büyük olabilir **/FP: precise**. **/ FP: precise** iç devre dışı bırakır; standart çalışma zamanı kitaplık yordamları yerine kullanılır. Daha fazla bilgi için [(iç işlevler Oluştur) /Oi](../../build/reference/oi-generate-intrinsic-functions.md).

Aşağıdaki kayan nokta davranışını etkinleştirilmiş olan **/FP: precise**:

- Kısaltmalar — yani, birden çok işlemin yerini almak üzere, sonda yalnızca bir yuvarlamaya sahip bileşik bir işlem kullanma.

- Özel değerler için geçersiz olan ifade iyileştirmelerine (NaN, + sonsuz, - sonsuz + 0, - 0) izin verilmez. En iyi duruma getirme x-x = > 0 x * 0 = > 0, x-0 = > x, x + 0 = > x ve 0-x = > x - çeşitli nedenlerle geçersizdir. (Bkz. IEEE 754 ve C99 standardı.)

- Derleyici NaN içeren karşılaştırmaları doğru olarak işler. Örneğin, x! = x değerlendirilen **true** varsa `x` NaN ise ve NaN içeren sıralı karşılaştırmalar bir özel durum.

- İfade değerinin hesaplanması, şu özel durumla, C99 FLT_EVAL_METHOD=2'yi izler: x86 işlemciler için programlama yaptığınızda, FPU 53-bit duyarlığa ayarlanmış olduğu için bu uzun çift duyarlık olarak değerlendirilir.

- Tam olarak 1.0 ile çarpım diğer bir faktörün kullanımı olarak dönüştürüldü. x * y\*1.0 x dönüştürülmüş\*y. Benzer şekilde, x\*1.0\*y x dönüştürülmüş\*y.

- Tam olarak 1.0 ile bölme, bölünen sayının kullanımı olarak dönüştürüldü. x * y/1.0 x dönüştürülür\*y. Benzer şekilde, x / 1.0\*y x dönüştürülmüş\*y.

Kullanarak **/FP: precise** olduğunda [fenv_access](../../preprocessor/fenv-access.md) , kayan nokta ifadelerinin derleme zamanı değerlendirmeleri gibi iyileştirmeleri devre dışı bırakır olduğu. Örneğin, kullanırsanız [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) değişiklik yuvarlama modu ve derleyici bir kayan nokta hesaplaması gerçekleştirir, belirttiğiniz yuvarlama modu değil sürece etkilidir `fenv_access`açık'tır.

**/ FP: precise** değiştirir **; /OP &** derleyici seçeneği.

#### <a name="fast"></a>Hızlı

**Fast** seçeneği oluşturur en hızlı kodu çoğu durumda kayan nokta işlemlerini iyileştirmek için kuralları esneterek. Bu, derleyicinin, doğruluk ve kesinlikten ödün vererek kayan nokta kodunun hızını iyileştirmesini sağlar. Zaman **Fast** belirtilirse, derleyici doğru atama deyimleri yuvarlak değil, yuvarlamasını veya işlev çağrıları ve Ara ifadelerin yuvarlama çalışmayabilir. Derleyici, sonlu duyarlık sonuçları üzerindeki etkiden bağımsız olarak, işlemlerini yeniden sıralayabilir veya cebirsel dönüşümleri gerçekleştirebilir (ör. ilişkilendirilebilir ve dağıtılabilir kuralları izleyerek). Derleyici; C++ türü promosyon kurallarını izlemek yerine işlemleri ve işleçleri tek duyarlıklı hale getirebilir. Kayan noktaya özgü kısaltma iyileştirmeleri her zaman etkindir ([fp_contract](../../preprocessor/fp-contract.md) açık). Kayan nokta özel durumları ve FPU ortam erişimi devre dışı bırakıldı (**/FP: except-** kastedilir ve [fenv_access](../../preprocessor/fenv-access.md) Kapalı'dır).

**Fast** kullanılamaz **/FP: strict** veya **/FP: precise**. Komut satırında belirtilen en son seçenek kullanılır. Her ikisi de belirtme **Fast** ve **/FP: except** bir derleyici hatasına neden olur.

Belirtme [/Za, /Ze (dil uzantılarını devre dışı bırak)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI uyumluluğu) ve **Fast** beklenmeyen davranışlara neden olabilir. Örneğin, tek duyarlıklı kayan nokta işlemleri tek duyarlıklı olarak yuvarlanmayabilir.

#### <a name="except"></a>Dışında

**/FP: except** seçeneği güvenilir kayan nokta özel durum modeli sağlar. Özel durumlar, tetiklendikten hemen sonra oluşur. Varsayılan olarak, bu değer kapalıdır. Bir eksi işareti seçeneği ekleme (**/FP: except-**) açıkça devre dışı bırakır.

#### <a name="strict"></a>Katı

**/FP: strict** seçeneği, en katı kayan nokta modeli sağlar. **/ FP: strict** neden [fp_contract](../../preprocessor/fp-contract.md) kapalı ve [fenv_access](../../preprocessor/fenv-access.md) açık olması. **/ FP: except** kastedilir ve açıkça belirterek devre dışı bırakılabilir **/FP: except-**. İle kullanıldığında **/FP: except-**, **/FP: katı** katı kayan nokta semantiklerini zorlar özel durum olaylarını yoksayarak.

## <a name="remarks"></a>Açıklamalar

Birden çok **/FP** aynı derlemede seçeneği belirtilebilir.

Kayan nokta davranışını işleve göre kontrol için bkz: [float_control](../../preprocessor/float-control.md) pragması. Bu geçersiz kılmaları **/FP** derleyici ayarını. İyi bir mühendislik davranışı olarak, yerel kayan nokta davranışını kaydedip geri yüklemenizi öneririz:

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

Kayan nokta iyileştirmelerinin çoğu ilgili **/FP: katı**, **/FP: except** (ve ona karşılık gelen pragmalar) ve `fp_contract` pragma makineye bağlıdır. **/ FP: strict** ve **/FP: except** ile uyumlu **/CLR**.

**/ FP: precise** bir uygulamanın kayan nokta gereksinimlerinden çoğunu gidermelidir. Kullanabilirsiniz **/FP: except** ve **/FP: strict**, ancak bazı performans düşüklüğü olabilir. Performans en önemli ise, kullanamayacağınızı düşünmenizi **Fast**.

**/ FP: strict**, **Fast**, ve **/FP: precise** duyarlık (doğruluk) modlarıdır. Aynı anda yalnızca biri kullanımda olabilir. Her iki **/FP: strict** ve **/FP: precise** belirtilirse, derleyici en son işlediğini olanı kullanır. Her ikisi de **/FP: strict** ve **Fast** belirtilemez.

Daha fazla bilgi için [Microsoft Visual C++ Floating-Point iyileştirme](floating-point-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Genişletin **yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **kayan nokta modeli** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](setting-compiler-options.md)
- [Microsoft Visual C++ kayan nokta iyileştirme](floating-point-optimization.md)