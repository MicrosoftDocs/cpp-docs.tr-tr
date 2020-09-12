---
title: /fp (Kayan nokta davranışını belirt)
ms.date: 11/09/2018
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
ms.openlocfilehash: 7a8ae885bbbf00ae916505bf5df646b32268a17a
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040918"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Kayan nokta davranışını belirt)

Derleyicinin kayan nokta ifadelerini, iyileştirmeleri ve özel durumları nasıl ele aldığını belirtir. **/FP** seçenekleri, üretilen kodun, kayan nokta ortam değişikliklerine, yuvarlama moduna, özel durum maskelerine ve alt normal davranışa izin verip etmediğini ve kayan nokta durum denetimlerinin geçerli, doğru sonuçları döndürmeyeceğini belirtir. Derleyicinin kaynak işlemini ve ifade sıralamasını tutan ve Nan yayılması için standart olan kodu oluşturup üretmediğini veya bunun yerine, işlemleri yeniden sıralayıp birleştirebilen ve standart tarafından izin verilmeyen cebirsel dönüştürmelerini destekleyen daha verimli bir kod oluşturuyor olup olmadığını denetler.

## <a name="syntax"></a>Syntax

> **/FP:**[**precise**  |  **strict**  |  **fast**  |  **except**[ **-** ]] haricinde kesin kesin hızlı

### <a name="arguments"></a>Arguments

#### <a name="precise"></a>gösterip

Varsayılan olarak, derleyici davranışı kullanır `/fp:precise` .

Derleyici altında, `/fp:precise` hedef makine için nesne kodu oluştururken ve iyileştirdiği zaman kayan nokta kodunun kaynak ifade sıralamasını ve yuvarlama özelliklerini korur. Derleyici, ifade değerlendirmesi sırasında dört özel noktaya göre kaynak kodu duyarlığına yuvarlar: atama sırasında, bir işlev çağrısına bir kayan nokta bağımsız değişkeni geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Ara hesaplamalar makine duyarlığına göre gerçekleştirilebilir. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir.

Derleyici, bir bit düzeyinde özdeş sonuç üretme garantisi olmadığı sürece yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadelerinde cebirsel dönüştürmeleri gerçekleştirmez.
Özel değerleri (NaN, + Infinity,-Infinity-0,0) içeren ifadeler, IEEE-754 belirtimlerine göre işlenir. Örneğin, `x != x` x NaN ise olarak değerlendirilir **`true`** . Kayan nokta *karşıtı*, diğer bir deyişle, kayan nokta işlemlerini birleştiren makine yönergeleri altında oluşturulabilir `/fp:precise` .

Derleyici, [varsayılan kayan nokta ortamında](#the-default-floating-point-environment) çalışması amaçlanan kodu oluşturur ve kayan nokta ortamının çalışma zamanında erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.

Kayan nokta kodunuz, kayan nokta deyimlerindeki işlemler ve ifadeler sırasına bağlı değilse (örneğin, `a * b + a * c` veya olarak hesaplanmadığına bakılmaksızın `(b + c) * a` `2 * a` `a + a` ), [/FP: Fast](#fast) seçeneğini göz önünde bulundurun. Bu, daha hızlı ve daha verimli kod üretebilirler. Kodunuzun her ikisi de işlem ve deyimlerin sırasına bağlıdır ve kayan nokta ortamına erişir veya onu değiştirir (örneğin, yuvarlama modlarını değiştirmek veya kayan nokta özel durumlarını yakalamak için), [/FP: Strict](#strict)kullanın.

#### <a name="strict"></a>sert

`/fp:strict` Şuna benzer bir davranış içerir `/fp:precise` , yani derleyici, hedef makine için nesne kodu oluştururken ve iyileştirdiği sırada kayan nokta kodunun kaynak sıralamasını ve yuvarlama özelliklerini korur ve özel değerleri işlerken standart hale getirir. Ayrıca, program, çalışma zamanında kayan nokta ortamına güvenle erişebilir veya değiştirebilir.

`/fp:strict`Derleyici, programın kayan nokta özel durumlarının maskesini güvenli bir şekilde kaldırmak, kayan nokta durum yazmaçlarını okumak veya yazmak ya da yuvarlama modlarını değiştirmek için kod üretir. İfade değerlendirmesi sırasında dört özel noktaya göre kaynak kodu duyarlığına yuvarlar: atama sırasında, bir işlev çağrısına bir kayan nokta bağımsız değişkeni geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Ara hesaplamalar makine duyarlığına göre gerçekleştirilebilir. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir. Derleyici, bir bit düzeyinde özdeş sonuç üretme garantisi olmadığı sürece yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadelerinde cebirsel dönüştürmeleri gerçekleştirmez. Özel değerleri (NaN, + Infinity,-Infinity-0,0) içeren ifadeler, IEEE-754 belirtimlerine göre işlenir. Örneğin, `x != x` x NaN ise olarak değerlendirilir **`true`** . Kayan nokta aykırlıkları altında oluşturulmaz `/fp:strict` .

`/fp:strict` , `/fp:precise` derleyicinin özel durumları yakalamak ve programların çalışma zamanında kayan nokta ortamına erişmesine veya değiştirmesine izin vermek için ek yönergeler eklemesi gerektiğinden, hesaplama daha yüksektir. Kodunuz bu yeteneği kullanmıyorsa, ancak kaynak kodu sıralama ve yuvarlama gerektirir ya da özel değerleri kullanır, kullanın `/fp:precise` . Aksi takdirde, `/fp:fast` daha hızlı ve daha küçük kod üretebilen kullanmayı düşünün.

#### <a name="fast"></a>Hızlı

Seçeneği, derleyicinin kayan nokta `/fp:fast` işlemlerini hız ve boşluk için iyileştirmek üzere kayan nokta işlemlerini yeniden sıralayıp basitleştirmesini sağlar. Derleyici atama deyimlerine, tür yayınlarına veya işlev çağrılarına yuvarlama alabilir. Bu, benzer dönüşümler observably farklı yuvarlama davranışına neden olsa da, işlemleri yeniden sıralayabilir veya örneğin, ilişkilendirilebilir ve dağıtılabilir yasaları kullanılarak cebirsel dönüştürmeleri gerçekleştirebilir. Bu gelişmiş iyileştirmede, bazı kayan nokta hesaplamaların sonucu diğer seçeneklerle oluşturulan verilerden farklı olabilir `/fp` . Özel değerler (NaN, + Infinity,-Infinity,-0,0), IEEE-754 standardına göre tamamen yayılmayabilir veya çalışmayabilir. Kayan nokta karşıtı, altında oluşturulabilir `/fp:fast` . Derleyici, altındaki temel mimari tarafından hala bağlanmıştır `/fp:fast` ve [/Arch](arch-minimum-cpu-architecture.md) seçeneğinin kullanımıyla birlikte ek iyileştirmeler kullanılabilir.

`/fp:fast`, Derleyici, varsayılan kayan nokta ortamında çalışacak şekilde tasarlanan kodu oluşturur ve kayan nokta ortamının çalışma zamanında erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.

`/fp:fast` , katı kaynak kodu sıralaması gerektirmeyen ve kayan nokta ifadelerinin yuvarlanması gerektirmeyen ve NaN gibi özel değerleri işlemek için Standart kurallara dayanmayan programlar için tasarlanmıştır. Kayan nokta kodunuz kaynak kodu sıralama ve yuvarlama için koruma gerektiriyorsa veya özel değerlerin standart davranışına dayanıyorsa, [/FP: net](#precise)kullanın. Kodunuz, yuvarlama modlarını değiştirmek, kayan nokta özel durumlarının maskesini kaldırmak veya kayan nokta durumunu denetlemek için kayan nokta ortamına eriştiğinde veya değişiklik yaparsa, [/FP: Strict](#strict)kullanın.

#### <a name="except"></a>kullanıldıkları

`/fp:except`Seçeneği, maskelenmemiş kayan nokta özel durumlarının gerçekleştikleri kesin bir noktada oluşmasını ve başka hiçbir kayan nokta özel durumu oluşmamasını sağlamak için kod üretir. Varsayılan olarak, `/fp:strict` seçeneği etkinleştirilir `/fp:except` ve yapmaz `/fp:precise` . `/fp:except`Seçeneği ile uyumlu değildir `/fp:fast` . Seçeneği, bizden açıkça devre dışı bırakılabilir `/fp:except-` .

`/fp:except`Herhangi bir kayan nokta özel durumu kendiliğinden etkinleştiremediğini unutmayın, ancak programlar kayan nokta özel durumlarını etkinleştirmek için gereklidir. Kayan nokta özel durumlarını etkinleştirme hakkında bilgi için bkz. [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) .

## <a name="remarks"></a>Açıklamalar

`/fp`Aynı derleyici komut satırında birden çok seçenek belirtilebilir. Tek seferde `/fp:strict` ,, `/fp:fast` ve seçeneklerinden yalnızca biri `/fp:precise` geçerli olabilir. Komut satırında bu seçeneklerden birden fazlası belirtilirse, sonraki seçenek önceliklidir ve derleyici bir uyarı oluşturur. `/fp:strict`Ve `/fp:except` seçenekleri ile uyumlu değildir `/clr` .

[/Za](za-ze-disable-language-extensions.md) (ANSI uyumluluğu) seçeneği ile uyumlu değildir `/fp` .

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>Kayan nokta davranışını denetlemek için derleyici yönergelerini kullanma

Derleyici, komut satırında belirtilen kayan nokta davranışını geçersiz kılmak için üç pragma yönergesi sağlar: [float_control](../../preprocessor/float-control.md), [fenv_access](../../preprocessor/fenv-access.md)ve [fp_contract](../../preprocessor/fp-contract.md). Bu yönergeleri, bir işlev içinde değil, işlev düzeyinde kayan nokta davranışını denetlemek için kullanabilirsiniz. Bu yönergelerin doğrudan seçeneklere karşılık gelmediğini unutmayın `/fp` . Bu tabloda, `/fp` seçeneklerin ve pragma yönergelerinin birbirleriyle nasıl eşlenme gösterilmektedir. Daha fazla bilgi için, tek tek seçenekler ve pragma yönergeleri için belgelere bakın.

| Seçenek | float_control (kesin) | float_control (hariç) | fenv_access | fp_contract |
|-|-|-|-|-|
|`/fp:fast`|Kapalı|Kapalı|Kapalı|on|
|`/fp:precise`|on|Kapalı|Kapalı|on|
|`/fp:strict`|on|on|on|Kapalı|

### <a name="the-default-floating-point-environment"></a>Varsayılan kayan nokta ortamı

Bir işlem başlatıldığında, *varsayılan kayan nokta ortamı* ayarlanır. Bu ortam tüm kayan nokta özel durumlarını arar, yuvarlama modunu en yakın () olarak ayarlar, `FE_TONEAREST` alt normal (denormal) değerlerini korur,,, ve değerleri için mantisinin (Mantis) varsayılan hassasiyetini kullanır **`float`** **`double`** **`long double`** ve desteklenir, sonsuz denetimini varsayılan Afine moduna ayarlar.

### <a name="floating-point-environment-access-and-modification"></a>Kayan nokta ortam erişimi ve değiştirme

Microsoft Visual C++ çalışma zamanı, kayan nokta ortamına erişmek ve bunları değiştirmek için çeşitli işlevler sağlar. Bunlar [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)ve [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) ve türevlerini içerir. Kodunuz kayan nokta ortamına eriştiğinde veya değişiklik yaptığında doğru program davranışına olanak sağlamak için, `fenv_access` `/fp:strict` `fenv_access` Bu işlevlerin herhangi bir etkiye sahip olması için ya da pragma kullanılarak etkinleştirilmiş olmalıdır. `fenv_access`Etkin olmadığında, kayan nokta ortamının erişimi veya değiştirilmesi beklenmeyen program davranışına neden olabilir: kod, kayan nokta ortamında istenen değişiklikleri kabul etmez; kayan nokta durum Yazmaçları beklenen veya geçerli sonuçları bildiremeyebilir; beklenmedik kayan nokta özel durumları oluşabilir veya beklenen kayan nokta özel durumları gerçekleşmeyebilir.

Kodunuz, kayan nokta ortamına eriştiğinde veya değişiklik yaptığında, `fenv_access` etkin olmayan kod ile etkinleştirilmiş kodu birleştirdiğinizde dikkatli olmanız gerekir `fenv_access` . `fenv_access`Etkin olmayan kodda, derleyici platform varsayılan kayan nokta ortamının geçerli olduğunu ve kayan nokta durumunun erişilmeyeceğini veya değiştirilmediğini varsayar. Denetim, etkinleştirilmemiş bir işleve aktarılmadan önce yerel kayan nokta ortamını, varsayılan durumuna kaydetmenizi ve geri yüklemenizi öneririz `fenv_access` . Bu örnekte, `float_control` pragma 'ın nasıl ayarlanacağı ve geri yüklenebildiğinden gösterilmektedir:

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>Kayan nokta yuvarlama modları

Her ikisi `/fp:precise` de `/fp:fast` derleyici, varsayılan kayan nokta ortamında çalışması amaçlanan kodu oluşturur ve çalışma zamanında ortama erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.  Ancak bazı programların kayan nokta ortamını değiştirihtiyacı vardır. Örneğin, bu örnek kayan nokta yuvarlama modlarını değiştirerek kayan nokta çarpma 'nın hata sınırlarını hesaplar:

```cpp
// fp_error_bounds.cpp
#include <iostream>
#include <limits>
using namespace std;

int main(void)
{
    float a = std::<float>::max();
    float b = -1.1;
    float cLower = 0.0;
    float cUpper = 0.0;
    unsigned int control_word = 0;
    int err = 0;

    // compute lower error bound.
    // set rounding mode to -infinity.
    err = _controlfp_s(&control_word, _RC_DOWN, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_DOWN, _MCW_RC) failed with error:" << err << endl;
    }  
    cLower = a * b;

    // compute upper error bound.
    // set rounding mode to +infinity.
    err = _controlfp_s(&control_word, _RC_UP, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _RC_UP, _MCW_RC) failed with error:" << err << endl;
    }
    cUpper = a * b;

    // restore default rounding mode.
    err = _controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC);
    if (err)
    {
        cout << "_controlfp_s(&control_word, _CW_DEFAULT, _MCW_RC) failed with error:" << err << endl;
    }
    // display error bounds.
    cout << "cLower = " << cLower << endl;
    cout << "cUpper = " << cUpper << endl;
    return 0;
}
```

Derleyici varsayılan kayan nokta ortamını altında varsaydığından `/fp:fast` ve `/fp:precise` çağrıları yok saymaya ücretsizdir `_controlfp_s` . Örneğin, ve x86 mimarisi için, her ikisi de kullanılarak derlendiğinde, `/O2` `/fp:precise` sınırlar hesaplanmaz ve örnek program tarafından çıkış yapılır:

```Output
cLower = -inf
cUpper = -inf
```

, `/O2` Ve `/fp:strict` x86 mimarisi için derlendiğinde, örnek program şunu verir:

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>Kayan nokta özel değerleri

`/fp:precise`Ve ' nin altında `/fp:strict` özel değerleri (NaN, + Infinity,-Infinity,-0,0) IÇEREN ifadeler ıeee-754 belirtimlerine göre davranır. Altında `/fp:fast` , bu özel değerlerin DAVRANıŞı IEEE-754 ile tutarsız olabilir.

Bu örnek, ve altındaki özel değerlerin farklı davranışlarını gösterir `/fp:precise` `/fp:strict` `/fp:fast` :

```cpp
// fp_special_values.cpp
#include <stdio.h>
#include <cmath>

float gf0 = -0.0;

int main()
{
    float f1 = INFINITY;
    float f2 = NAN;
    float f3 = -INFINITY;
    bool a, b;
    float c, d, e;
    a = (f1 == f1);
    b = (f2 == f2);
    c = (f1 - f1);
    d = (f2 - f2);
    printf("INFINITY == INFINITY : %d\n", a);
    printf("NAN == NAN           : %d\n", b);
    printf("INFINITY - INFINITY  : %f\n", c);
    printf("NAN - NAN            : %f\n", d);

    e = gf0 / abs(f3);
    printf("std::signbit(-0.0/-INFINITY): %d\n", std::signbit(c));
    return 0;
}
```

`/O2` `/fp:precise` Veya `/O2` `/fp:strict` x86 mimarisi Ile derlendiğinde, çıktılar IEEE-754 belirtimiyle tutarlıdır:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

`/O2` `/fp:fast` , X86 mimarisi için derlendiğinde, çıktılar ıeee-754 ile tutarlı değildir:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>Kayan nokta cebirsel dönüşümleri

`/fp:precise`Ve ' ın altında `/fp:strict` , bir bit düzeyinde özdeş sonuç üretmek için dönüşüm garanti edilmediği takdirde derleyici matematik dönüştürmeleri gerçekleştirmez. Derleyici, altında bu dönüşümleri gerçekleştirebilir `/fp:fast` . Örneğin, `a * b + a * c` Sample işlevindeki ifade `algebraic_transformation` altında derlenmiş olabilir `a * (b + c)` `/fp:fast` . Bu tür dönüştürmeler veya altında gerçekleştirilmemektedir `/fp:precise` `/fp:strict` ve derleyici tarafından oluşturulur `a * b + a * c` .

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>Kayan nokta açık atama noktaları

Ve ' nin altında, `/fp:precise` `/fp:strict` derleyici ifade değerlendirmesi sırasında dört özel noktaya göre kaynak kodu duyarlığına yuvarlar: atama sırasında, bir işlev çağrısına bir kayan nokta bağımsız değişkeni geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir. `/fp:fast`Bu noktada, derleyici kaynak kodu hassasiyetini sağlamak için bu noktalarda açık yayınlar oluşturmaz. Bu örnek, farklı seçenekler altındaki davranışı gösterir `/fp` :

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

Veya kullanılarak derlendiğinde `/O2` `/fp:precise` `/O2` `/fp:strict` , açık tür öğelerinin hem typecast hem de x64 mimarisi için üretilen koddaki işlev dönüş noktasında eklendiğini görebilirsiniz:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

`/O2` `/fp:fast` Oluşturulan kodun altında basitleştirilmiştir, çünkü tüm tür atamaları en iyi duruma getirilmiştir:

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod oluşturma** özellik sayfasını seçin.

1. **Kayan nokta modeli** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
