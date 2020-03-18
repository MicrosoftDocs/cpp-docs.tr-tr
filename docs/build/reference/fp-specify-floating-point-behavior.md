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
ms.openlocfilehash: 402b59c4aee34a413a08235aab2327ca64e7db39
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439687"
---
# <a name="fp-specify-floating-point-behavior"></a>/fp (Kayan nokta davranışını belirt)

Derleyicinin kayan nokta ifadelerini, iyileştirmeleri ve özel durumları nasıl ele aldığını belirtir. **/FP** seçenekleri, üretilen kodun, kayan nokta ortam değişikliklerine, yuvarlama moduna, özel durum maskelerine ve alt normal davranışa izin verip etmediğini ve kayan nokta durum denetimlerinin geçerli, doğru sonuçları döndürmeyeceğini belirtir. Derleyicinin kaynak işlemini ve ifade sıralamasını tutan ve NaN yayılması için standart olan kodu oluşturup üretmediğini veya bunun yerine, işlemleri yeniden sıralayıp birleştirebilen ve basitleştirecek daha verimli bir kod oluşturuyor olup olmadığını denetler Standart tarafından izin verilmeyen cebirsel dönüşümleri.

## <a name="syntax"></a>Sözdizimi

> **/FP:** [**tam** | **katı** | **hızlı** | [ **-** ]] **dışında**)

### <a name="arguments"></a>Bağımsız Değişkenler

#### <a name="precise"></a>gösterip

Varsayılan olarak, derleyici `/fp:precise` davranışını kullanır.

`/fp:precise`, derleyici, hedef makine için nesne kodu oluştururken ve iyileştirdiği zaman kayan nokta kodunun kaynak ifade sıralamasını ve yuvarlama özelliklerini korur. Derleyici, ifade değerlendirmesi sırasında dört özel noktaya göre kaynak kodu duyarlığına yuvarlar: atama sırasında, bir işlev çağrısına bir kayan nokta bağımsız değişkeni geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Ara hesaplamalar makine duyarlığına göre gerçekleştirilebilir. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir.

Derleyici, bir bit düzeyinde özdeş sonuç üretme garantisi olmadığı sürece yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadelerinde cebirsel dönüştürmeleri gerçekleştirmez.
Özel değerleri (NaN, + Infinity,-Infinity-0,0) içeren ifadeler, IEEE-754 belirtimlerine göre işlenir. Örneğin, x NaN ise, `x != x` **true** olarak değerlendirilir. Kayan *nokta, diğer*bir deyişle kayan nokta işlemlerini birleştiren makine yönergeleri `/fp:precise`altında oluşturulabilir.

Derleyici, [varsayılan kayan nokta ortamında](#the-default-floating-point-environment) çalışması amaçlanan kodu oluşturur ve kayan nokta ortamının çalışma zamanında erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.

Kayan nokta kodunuz, kayan nokta deyimlerinizin işlem ve ifadelerin sırasına bağlı değilse (örneğin, `a * b + a * c` `(b + c) * a` veya `a + a``2 * a` olarak hesaplanmadığını önemsemezseniz), daha hızlı ve daha verimli kod üretebilen [/FP: Fast](#fast) seçeneğini göz önünde bulundurun. Kodunuzun her ikisi de işlem ve deyimlerin sırasına bağlıdır ve kayan nokta ortamına erişir veya onu değiştirir (örneğin, yuvarlama modlarını değiştirmek veya kayan nokta özel durumlarını yakalamak için), [/FP: Strict](#strict)kullanın.

#### <a name="strict"></a>sert

`/fp:strict`, `/fp:precise`benzer bir davranış içerir. derleyici, hedef makine için nesne kodu oluştururken ve iyileştirdiği sırada kayan nokta kodunun kaynak sıralamasını ve yuvarlama özelliklerini korur ve özel değerleri işlerken standart hale getirir. Ayrıca, program, çalışma zamanında kayan nokta ortamına güvenle erişebilir veya değiştirebilir.

`/fp:strict`altında derleyici, programın kayan nokta özel durumlarını güvenli bir şekilde maskesini, kayan nokta durum yazmaçlarını okumasını veya yazabilmesini veya yuvarlama modlarını değiştirmesini sağlayan bir kod oluşturur. İfade değerlendirmesi sırasında dört özel noktaya göre kaynak kodu duyarlığına yuvarlar: atama sırasında, bir işlev çağrısına bir kayan nokta bağımsız değişkeni geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Ara hesaplamalar makine duyarlığına göre gerçekleştirilebilir. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir. Derleyici, bir bit düzeyinde özdeş sonuç üretme garantisi olmadığı sürece yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadelerinde cebirsel dönüştürmeleri gerçekleştirmez. Özel değerleri (NaN, + Infinity,-Infinity-0,0) içeren ifadeler, IEEE-754 belirtimlerine göre işlenir. Örneğin, x NaN ise, `x != x` **true** olarak değerlendirilir. Kayan nokta aykırlıkları `/fp:strict`altında oluşturulmaz.

`/fp:strict`, derleyicinin özel durumlara yönelik ek yönergeler eklemesi ve programların çalışma zamanında kayan nokta ortamına erişmesine veya değiştirmesine izin vermek için `/fp:precise` daha pahalı bir işlemdir. Kodunuz bu yeteneği kullanmıyorsa, ancak kaynak kodu sıralama ve yuvarlama gerektirir ya da özel değerleri kullanır, `/fp:precise`kullanın. Aksi takdirde, daha hızlı ve daha küçük kod üretebilen `/fp:fast`kullanmayı düşünün.

#### <a name="fast"></a>hızlı

`/fp:fast` seçeneği, derleyicinin kayan nokta işlemlerini hız ve boşluk için optimize etmek üzere kayan nokta işlemlerini yeniden sıralayıp basitleştirmesini sağlar. Derleyici atama deyimlerine, tür yayınlarına veya işlev çağrılarına yuvarlama alabilir. Bu, benzer dönüşümler observably farklı yuvarlama davranışına neden olsa da, işlemleri yeniden sıralayabilir veya örneğin, ilişkilendirilebilir ve dağıtılabilir yasaları kullanılarak cebirsel dönüştürmeleri gerçekleştirebilir. Bu gelişmiş iyileştirmede, bazı kayan nokta hesaplamaların sonucu diğer `/fp` seçenekleri tarafından oluşturulan verilerden farklı olabilir. Özel değerler (NaN, + Infinity,-Infinity,-0,0), IEEE-754 standardına göre tamamen yayılmayabilir veya çalışmayabilir. Kayan nokta aykırlıkları `/fp:fast`altında oluşturulabilir. Derleyici, `/fp:fast`altındaki temel mimari tarafından hala bağlanmıştır ve [/Arch](arch-minimum-cpu-architecture.md) seçeneğinin kullanımıyla birlikte ek iyileştirmeler kullanılabilir.

`/fp:fast`altında, derleyici varsayılan kayan nokta ortamında çalışmak üzere tasarlanan kodu oluşturur ve kayan nokta ortamının çalışma zamanında erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.

`/fp:fast`, katı kaynak kodu sıralaması gerektirmeyen ve kayan nokta ifadelerinin yuvarlanması gerektirmeyen ve NaN gibi özel değerleri işlemek için Standart kurallara dayanmayan programlar için tasarlanmıştır. Kayan nokta kodunuz kaynak kodu sıralama ve yuvarlama için koruma gerektiriyorsa veya özel değerlerin standart davranışına dayanıyorsa, [/FP: net](#precise)kullanın. Kodunuz, yuvarlama modlarını değiştirmek, kayan nokta özel durumlarının maskesini kaldırmak veya kayan nokta durumunu denetlemek için kayan nokta ortamına eriştiğinde veya değişiklik yaparsa, [/FP: Strict](#strict)kullanın.

#### <a name="except"></a>kullanıldıkları

`/fp:except` seçeneği, maskelenmemiş kayan nokta özel durumlarının gerçekleştikleri kesin bir noktada oluşmasını ve başka hiçbir kayan nokta özel durumu oluşmamasını sağlamak için kod üretir. Varsayılan olarak, `/fp:strict` seçeneği `/fp:except`etkinleştirilir ve `/fp:precise` desteklemez. `/fp:except` seçeneği `/fp:fast`uyumlu değildir. Bu seçenek, `/fp:except-`bizimle açık olarak devre dışı bırakılabilir.

`/fp:except`, kayan nokta özel durumlarını kendisi tarafından etkinleştirmediğini unutmayın, ancak programlar kayan nokta özel durumlarını etkinleştirmek için gereklidir. Kayan nokta özel durumlarını etkinleştirme hakkında bilgi için bkz. [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) .

## <a name="remarks"></a>Açıklamalar

Aynı derleyici komut satırında birden çok `/fp` seçeneği belirtilebilir. Tek seferde `/fp:strict`, `/fp:fast`ve `/fp:precise` seçeneklerinden yalnızca biri geçerli olabilir. Komut satırında bu seçeneklerden birden fazlası belirtilirse, sonraki seçenek önceliklidir ve derleyici bir uyarı oluşturur. `/fp:strict` ve `/fp:except` seçenekleri `/clr`ile uyumlu değildir.

[/Za](za-ze-disable-language-extensions.md) (ANSI uyumluluğu) seçeneği `/fp`uyumlu değildir.

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>Kayan nokta davranışını denetlemek için derleyici yönergelerini kullanma

Derleyici, komut satırında belirtilen kayan nokta davranışını geçersiz kılmak için üç pragma yönergesi sağlar: [float_control](../../preprocessor/float-control.md), [fenv_access](../../preprocessor/fenv-access.md)ve [fp_contract](../../preprocessor/fp-contract.md). Bu yönergeleri, bir işlev içinde değil, işlev düzeyinde kayan nokta davranışını denetlemek için kullanabilirsiniz. Bu yönergelerin `/fp` seçeneklere doğrudan karşılık gelmediğini unutmayın. Bu tablo `/fp` seçeneklerinin ve pragma yönergelerinin birbirlerine nasıl eşlendiğini gösterir. Daha fazla bilgi için, tek tek seçenekler ve pragma yönergeleri için belgelere bakın.

||float_control (kesin)|float_control (hariç)|fenv_access|fp_contract|
|-|-|-|-|-|
|`/fp:fast`|kapalı|kapalı|kapalı|on|
|`/fp:precise`|on|kapalı|kapalı|on|
|`/fp:strict`|on|on|on|kapalı|

### <a name="the-default-floating-point-environment"></a>Varsayılan kayan nokta ortamı

Bir işlem başlatıldığında, *varsayılan kayan nokta ortamı* ayarlanır. Bu ortam tüm kayan nokta özel durumlarını maskeler, yuvarlama modunu en yakın (`FE_TONEAREST`) olarak ayarlar, alt normal (denormal) değerlerini korur, **float**, **Double**ve **Long Double** değerleri için mantisinin (Mantis) varsayılan hassasiyetini kullanır ve desteklenir, sonsuzluk denetimini varsayılan Afine moduna ayarlar.

### <a name="floating-point-environment-access-and-modification"></a>Kayan nokta ortam erişimi ve değiştirme

Microsoft Visual C++ Runtime, kayan nokta ortamına erişmek ve bunları değiştirmek için çeşitli işlevler sağlar. Bunlar [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md)ve [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) ve türevlerini içerir. Kodunuz, kayan nokta ortamına eriştiğinde veya değişiklik yaptığında doğru program davranışının doğru olmasını sağlamak için, bu işlevlerin herhangi bir etkiye sahip olması için `/fp:strict` seçeneği veya `fenv_access` pragma kullanılarak `fenv_access` etkinleştirilmelidir. `fenv_access` etkinleştirilmediği zaman, kayan nokta ortamının erişimi veya değiştirilmesi beklenmeyen program davranışına neden olabilir: kod, kayan nokta ortamında istenen değişiklikleri kabul edebilir. kayan nokta durum Yazmaçları beklenen veya geçerli sonuçları bildiremeyebilir; ve beklenmeyen kayan nokta özel durumları oluşabilir veya beklenen kayan nokta özel durumları gerçekleşmeyebilir.

Kodunuz kayan nokta ortamına eriştiğinde veya değişiklik yaptığında, `fenv_access` etkin olmayan kodla `fenv_access` etkinleştirildiği zaman kodu birleştirdiğinizde dikkatli olmanız gerekir. `fenv_access` etkinleştirildiği kodda, derleyici platform varsayılan kayan nokta ortamının geçerli olduğunu ve kayan nokta durumunun erişilmeyeceğini veya değiştirilmediğini varsayar. Denetim, `fenv_access` etkin olmayan bir işleve aktarılmadan önce yerel kayan nokta ortamını, varsayılan durumuna kaydetmenizi ve geri yüklemenizi öneririz. Bu örnekte `float_control` pragma 'ın nasıl ayarlanacağı ve geri yüklenebildiğinden gösterilmektedir:

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>Kayan nokta yuvarlama modları

Her iki `/fp:precise` ve `/fp:fast` derleyici, varsayılan kayan nokta ortamında çalışmak üzere tasarlanan kodu oluşturur ve ortamın çalışma zamanında erişilmediğini veya değiştirilmediğini varsayar. Yani, kodun kayan nokta özel durumlarının maskesini kaldırma, kayan nokta durum yazmaçlarını okuma veya yazma ya da yuvarlama modlarını değiştirme olduğunu varsayar.  Ancak bazı programların kayan nokta ortamını değiştirihtiyacı vardır. Örneğin, bu örnek kayan nokta yuvarlama modlarını değiştirerek kayan nokta çarpma 'nın hata sınırlarını hesaplar:

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

Derleyici varsayılan kayan nokta ortamını `/fp:fast` altında varsaydığından `/fp:precise` `_controlfp_s`çağrılarını yok saymaya ücretsizdir. Örneğin, hem `/O2` hem de x86 mimarisi için `/fp:precise` kullanılarak derlendiğinde, sınırlar hesaplanmaz ve örnek program tarafından çıkış yapılır:

```Output
cLower = -inf
cUpper = -inf
```

X86 mimarisi için hem `/O2` hem de `/fp:strict` ile derlendiğinde, örnek program şunu verir:

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>Kayan nokta özel değerleri

`/fp:precise` ve `/fp:strict`altında, özel değerler (NaN, + Infinity,-Infinity-0,0) içeren ifadeler IEEE-754 belirtimlerine göre davranır. `/fp:fast`altında, bu özel değerlerin davranışı IEEE-754 ile tutarsız olabilir.

Bu örnek, `/fp:precise`, `/fp:strict` ve `/fp:fast`altındaki özel değerlerin farklı davranışlarını gösterir:

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

X86 mimarisi için `/O2` `/fp:precise` veya `/O2` `/fp:strict` ile derlendiğinde, çıktılar IEEE-754 belirtimiyle tutarlıdır:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

X86 mimarisi için `/O2` `/fp:fast` ile derlendiğinde, çıktılar IEEE-754 ile tutarlı değildir:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>Kayan nokta cebirsel dönüşümleri

`/fp:precise` ve `/fp:strict`' nin altında, bir bit düzeyinde özdeş sonuç oluşturmak için dönüştürme garantisi yoksa derleyici matematik dönüştürmeleri gerçekleştirmez. Derleyici `/fp:fast`altında bu dönüşümleri gerçekleştirebilir. Örneğin, örnek işlev `algebraic_transformation` `a * b + a * c` ifade `/fp:fast`altında `a * (b + c)` olarak derlenmiş olabilir. Bu tür dönüştürmeler `/fp:precise` veya `/fp:strict`altında gerçekleştirilmemektedir ve derleyici `a * b + a * c`üretir.

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>Kayan nokta açık atama noktaları

`/fp:precise` ve `/fp:strict`' nin altında, derleyici ifade değerlendirmesi sırasında dört özel noktada kaynak kodu duyarlığına yuvarlar: tür atamaları, bir kayan nokta bağımsız değişkeni bir işlev çağrısına geçirildiğinde ve bir işlev çağrısından bir kayan nokta değeri döndürüldüğünde. Tür atamaları, ara hesaplamaları açıkça yuvarlamak için kullanılabilir. `/fp:fast`altında, derleyici kaynak kodu hassasiyetini sağlamak için bu noktalarda açık yayınlar oluşturmaz. Bu örnek, farklı `/fp` seçeneklerinin altındaki davranışı gösterir:

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

`/O2` `/fp:precise` veya `/O2` `/fp:strict`kullanılarak derlendiğinde, açık tür öğelerinin hem typecast hem de x64 mimarisi için üretilen koddaki işlev dönüş noktasında eklendiğini görebilirsiniz:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

`/fp:fast` `/O2` altında, oluşturulan kod basitleştirilmiştir, çünkü tüm tür atamaları en iyi duruma getirilmiştir:

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **CC++ /**  > **kod oluşturma** Özellik sayfası ' nı seçin.

1. **Kayan nokta modeli** özelliğini değiştirin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
 