---
title: -fp (kayan nokta davranışını belirt) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.floatingPointModel
- VC.Project.VCCLWCECompilerTool.FloatingPointExceptions
- /fp
- VC.Project.VCCLWCECompilerTool.floatingPointModel
- VC.Project.VCCLCompilerTool.FloatingPointExceptions
dev_langs:
- C++
helpviewer_keywords:
- -fp compiler option [C++]
- /fp compiler option [C++]
ms.assetid: 10469d6b-e68b-4268-8075-d073f4f5d57e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 520a6e2d675c55e47a0424ab93c6a76d521f2358
ms.sourcegitcommit: 5e932a0e110e80bc241e5f69e3a1a7504bfab1f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/21/2018
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Kayan Nokta Davranışını Belirt)

Bir kaynak kodu dosyasında kayan nokta türü davranışını belirtir.

## <a name="syntax"></a>Sözdizimi

> **/FP:**[**kesin** | **dışında**[**-**] | **hızlı** | **katı**]

### <a name="arguments"></a>Arguments

#### <a name="precise"></a>kesin

Varsayılan değer olan **/fp** olan **/fp: kesin**.

**/Fp: kesin** bayrağı kayan nokta hesaplamaların duyarlığını değişebilir iyileştirmeleri devre dışı bırakarak eşitlik ve eşitsizlik için kayan nokta testleri tutarlılığını artırır. (Katı ANSI uyumluluğu için belirli düzeyde duyarlığın korunması gereklidir.) Varsayılan olarak, kod x86 için kullanım x87 eşişlemcisi yönergeleri, derleyici eşişlemcisi kullanan mimarileri 80 bit kayan nokta hesaplamaları Ara sonuçlarını tutmak için kaydeder. Bu program hızını artırır ve program boyutunu küçültür. Ancak, hesaplama, bellekte 80 bitten düşük olarak temsil edilen kayan nokta veri türleri içerdiği için, ekstra bit duyarlığını (80 bit eksi daha küçük bir kayan nokta türündeki bit sayısı) uzun bir hesaplama boyunca taşımak tutarsız sonuçlar verebilir.

İle **/fp: kesin** x86 üzerinde işlemciler derleyici gerçekleştirir türü değişkenlerde yuvarlama `float` doğru duyarlılığa atamaları ve atamalar ve parametreleri bir işleve zaman geçirilir. Bu yuvarlama, verinin, kendi türünün kapasitesinden büyük bir anlam taşımadığından emin olunmasını sağlar. İle bir program derlenmiş **/fp: kesin** daha yavaş ve daha büyük bir olmadan derlenmiş olabilir **/fp: kesin**. **/FP: kesin** devre dışı bırakır yapı; standart çalışma zamanı kitaplığı yordamları yerine kullanılır. Daha fazla bilgi için bkz: [/Oi (iç işlevler Oluştur)](../../build/reference/oi-generate-intrinsic-functions.md).

Aşağıdaki kayan nokta davranışını etkinleştirilmiş olan **/fp: kesin**:

- Kısaltmalar — yani, birden çok işlemin yerini almak üzere, sonda yalnızca bir yuvarlamaya sahip bileşik bir işlem kullanma.

- Özel değerler için geçersiz olan ifade iyileştirmelerine (NaN, + sonsuz, - sonsuz + 0, - 0) izin verilmez. En iyi duruma getirme x-x > 0 = x * 0 = > 0, x-0 = > x, x + 0 = > x ve 0 x = > - x çeşitli nedenlerle geçersizdir. (Bkz. IEEE 754 ve C99 standardı.)

- Derleyici NaN içeren karşılaştırmaları doğru olarak işler. Örneğin, x! = x hesaplar için **true** varsa `x` NaN olup ve sıralı karşılaştırmaları NaN içeren bir özel durum oluşturun.

- İfade değerinin hesaplanması, şu özel durumla, C99 FLT_EVAL_METHOD=2'yi izler: x86 işlemciler için programlama yaptığınızda, FPU 53-bit duyarlığa ayarlanmış olduğu için bu uzun çift duyarlık olarak değerlendirilir.

- Tam olarak 1.0 ile çarpım diğer bir faktörün kullanımı olarak dönüştürüldü. x * y\*1.0 x dönüştürülmüş\*y. Benzer şekilde, x\*1.0\*y x dönüştürülmüş\*y.

- Tam olarak 1.0 ile bölme, bölünen sayının kullanımı olarak dönüştürüldü. x * y/1.0 x dönüştürülmüş\*y. Benzer şekilde, x / 1.0\*y x dönüştürülmüş\*y.

Kullanarak **/fp: kesin** zaman [fenv_access](../../preprocessor/fenv-access.md) iyileştirmeler kayan nokta ifadelerin derleme zamanı değerlendirmeleri gibi devre dışı bırakır üzerinde olduğu. Örneğin, kullanırsanız [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) yuvarlama modu ve derleyici değiştirmek için bir kayan nokta hesaplama gerçekleştirir, belirttiğiniz yuvarlama modu değil yürürlükte sürece `fenv_access`açık.

**/FP: kesin** değiştirir **/Op** derleyici seçeneği.

#### <a name="fast"></a>Hızlı

**/Fp:fast** seçenek oluşturur hızlı kod çoğu durumda kayan nokta işlemlerini iyileştirme kuralları gevşetme tarafından. Bu, derleyicinin, doğruluk ve kesinlikten ödün vererek kayan nokta kodunun hızını iyileştirmesini sağlar. Zaman **/fp:fast** belirtilirse, derleyici doğru atama deyimlerini yuvarlamak değil, işaretçisine tür olarak atar, veya işlev çağrıları ve Ara ifadelerin yuvarlama çalışmayabilir. Derleyici, sonlu duyarlık sonuçları üzerindeki etkiden bağımsız olarak, işlemlerini yeniden sıralayabilir veya cebirsel dönüşümleri gerçekleştirebilir (ör. ilişkilendirilebilir ve dağıtılabilir kuralları izleyerek). Derleyici; C++ türü promosyon kurallarını izlemek yerine işlemleri ve işleçleri tek duyarlıklı hale getirebilir. Floating point özgü daraltmaya iyileştirmeler her zaman etkin ([fp_contract](../../preprocessor/fp-contract.md) açık). Kayan nokta özel durumlar ve FPU ortam erişim devre dışı bırakıldı (**/fp: dışında-** kapsanır ve [fenv_access](../../preprocessor/fenv-access.md) Kapalı'dır).

**/FP:Fast** kullanılamaz **/fp: katı** veya **/fp: kesin**. Komut satırında belirtilen en son seçenek kullanılır. Her ikisi de belirtme **/fp:fast** ve **/fp: dışında** derleyici hatası oluşturur.

Belirtme [/Za, /Ze (dil uzantılarını devre dışı bırak)](../../build/reference/za-ze-disable-language-extensions.md) (ANSI uyumluluğu) ve **/fp:fast** beklenmeyen davranışlara neden olabilir. Örneğin, tek duyarlıklı kayan nokta işlemleri tek duyarlıklı olarak yuvarlanmayabilir.

#### <a name="except"></a>dışında

**/Fp: dışında** seçeneği güvenilir kayan nokta özel durumu modeli sağlar. Özel durumlar, tetiklendikten hemen sonra oluşur. Varsayılan olarak, bu değer kapalıdır. Seçeneğini eksi işareti ekleme (**/fp: dışında-**) açıkça devre dışı bırakır.

#### <a name="strict"></a>Katı

**/Fp: katı** seçeneği sıkı kayan nokta modeli sağlar. **/FP: katı** neden [fp_contract](../../preprocessor/fp-contract.md) kapalı olması ve [fenv_access](../../preprocessor/fenv-access.md) açık olmalıdır. **/FP: dışında** kapsanır ve açıkça belirterek devre dışı bırakılabilir **/fp: dışında-**. İle kullanıldığında **/fp: dışında-**, **/fp: katı** katı kayan nokta semantiğini uygular, ancak olağanüstü olaylar için saygı olmadan.

## <a name="remarks"></a>Açıklamalar

Birden çok **/fp** seçenekleri aynı derlemede belirtilebilir.

İşlev tarafından kayan nokta davranışını denetlemek için bkz: [float_control](../../preprocessor/float-control.md) pragması. Bu geçersiz kılmaları **/fp** derleyici ayarı. İyi bir mühendislik davranışı olarak, yerel kayan nokta davranışını kaydedip geri yüklemenizi öneririz:

```cpp
#pragma float_control(precise, on, push)
// Code that uses /fp:precise mode
#pragma float_control(pop)
```

Kayan nokta iyileştirmeler çoğunu ilgili **/fp: katı**, **/fp: dışında** (ve karşılık gelen pragmaları) ve `fp_contract` pragma makine bağımlı. **/FP: katı** ve **/fp: dışında** ile uyumlu değil **/CLR**.

**/FP: kesin** çoğu uygulamanın kayan nokta gereksinimleri karşılamanız gerekir. Kullanabileceğiniz **/fp: dışında** ve **/fp: katı**, ancak bazı performans düşüklüğü olabilir. Performansı en önemli ise, kullanıp kullanmayacağınızı düşünün **/fp:fast**.

**/FP: katı**, **/fp:fast**, ve **/fp: kesin** duyarlık (doğruluk) modu. Aynı anda yalnızca biri kullanımda olabilir. Her iki **/fp: katı** ve **/fp: kesin** belirtilirse, derleyici, en son işlediği bir kullanır. Her ikisi de **/fp: katı** ve **/fp:fast** belirtilemez.

Daha fazla bilgi için bkz: [Microsoft Visual C++ Floating-Point iyileştirme](floating-point-optimization.md).

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).

1. Genişletme **yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **kayan nokta modeli** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [Derleyici Seçenekleri](compiler-options.md)
- [Derleyici Seçeneklerini Ayarlama](setting-compiler-options.md)
- [Microsoft Visual C++ kayan nokta en iyi duruma getirme](floating-point-optimization.md)