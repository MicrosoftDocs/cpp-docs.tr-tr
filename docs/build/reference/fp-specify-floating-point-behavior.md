---
title: /FP (kayan nokta davranışını belirt)
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
ms.openlocfilehash: 25b228c16f534ca227d50bfdf632fdacb5703cd9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62292361"
---
# <a name="fp-specify-floating-point-behavior"></a>/FP (kayan nokta davranışını belirt)

Derleyicinin kayan nokta ifadeleri, iyileştirmeler ve özel durumları nasıl işler belirtir. **/FP** oluşturulan kodun ortam kayan nokta yuvarlama modu, özel durum maskeleri ve subnormal davranışını değiştirir izin verip ve kayan nokta durum denetimleri olup iade geçerli, doğru seçeneklerini belirtin Sonuç. Olup derleyici kaynak işlemi ve ifade sıralamasını korur ve NaN yayma işlemi standardına uygun kodu oluşturur ya da, bunun yerine yeniden sıralamak veya işlemleri birleştirin ve basitleştirme kullanmak daha verimli kod oluşturursa denetler Standart tarafından izin verilmeyen cebirsel dönüşümleri.

## <a name="syntax"></a>Sözdizimi

> **/ FP:**[**kesin** | **katı** | **hızlı** | **dışında**[ **-**]]

### <a name="arguments"></a>Arguments

#### <a name="precise"></a>kesin

Varsayılan olarak, derleyicinin kullandığı `/fp:precise` davranışı.

Altında `/fp:precise` derleyici kaynak ifade sıralama ve kayan nokta kodu özelliklerini oluşturur ve nesne kodu hedef makine için en iyi duruma getirir, yuvarlama korur. Derleyici için kaynak kodu duyarlık dört belirli noktalarda ifadesi değerlendirmesi sırasında yuvarlar: adresindeki atamaları olarak yuvarlamasını, bir kayan noktalı bağımsız değişken işlev çağrısına geçirilen zaman ve kayan nokta değeri zaman bir işlev çağrısında döndürülür. Ara hesaplamalar makine duyarlık gerçekleştirilebilir. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir.

Bit düzeyinde aynı sonucu verecek dönüşümü garanti sürece derleyici cebirsel dönüşümleri yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadesine gerçekleştirmez.
IEEE-754 spesifikasyonlarına uygun (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler işlenir. Örneğin, `x != x` değerlendiren **true** x NaN ise. Kayan nokta *kısaltmalar*, diğer bir deyişle, kayan nokta işlemleri birleştiren makine yönergelerine oluşturulabilir altında `/fp:precise`.

Derleyici kod çalıştırmak için hedeflenen oluşturur [varsayılan kayan nokta ortam](#the-default-floating-point-environment) ve kayan nokta ortamı değil erişilen veya çalışma zamanında değiştirilmiş olduğunu varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.

Kayan nokta kodunuzun işlemler ve ifadeler, kayan nokta deyimlerinde bazında bağlı değilse (örneğin, İlgilenmiyor, olmadığını `a * b + a * c` olarak hesaplanan `(b + c) * a` veya `2 * a` olarak `a + a`), gözönündebulundurun[Fast](#fast) seçeneği, daha hızlı, daha verimli kod üretebilirsiniz. Kodunuzu hem işlemleri ve ifadeler, bazında bağlıdır ve erişir veya kayan nokta ortam (örneğin, yuvarlama modunu değiştirmek veya kayan nokta özel durumları yakalamak için) değiştirir, kullanın [/FP: strict](#strict).

#### <a name="strict"></a>Katı

`/fp:strict` benzer şekilde davranışı `/fp:precise`, diğer bir deyişle, derleyici kaynak sıralamasını korur ve kayan nokta kodu özelliklerini oluşturur ve en iyi duruma getirir, yuvarlama nesne için hedef makine kodu ve standart özel değerleri işlerken gözlemler. Ayrıca, programın güvenli bir şekilde erişebilir veya çalışma zamanında kayan nokta ortamı değiştirin.

Altında `/fp:strict`, derleyici veren programın güvenli bir şekilde kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirmek kod oluşturur. İfade değerlendirme sırasında kaynak kod duyarlık dört belirli noktalarda için yuvarlar: adresindeki atamaları olarak yuvarlamasını, bir kayan noktalı bağımsız değişken işlev çağrısına geçirilen zaman ve kayan nokta değeri zaman bir işlev çağrısında döndürülür. Ara hesaplamalar makine duyarlık gerçekleştirilebilir. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir. Bit düzeyinde aynı sonucu verecek dönüşümü garanti sürece derleyici cebirsel dönüşümleri yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadesine gerçekleştirmez. IEEE-754 spesifikasyonlarına uygun (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler işlenir. Örneğin, `x != x` değerlendiren **true** x NaN ise. Kayan nokta kısaltmalar altında oluşturulmaz `/fp:strict`.

`/fp:strict` Daha fazla yoğun olan `/fp:precise` olduğundan derleyici özel durumları yakalamak ve programlar erişmek veya çalışma zamanında kayan nokta ortamı değiştirmek izin vermek için ek yönergeler eklemeniz gerekir. Kodunuzu bu özellik kullanmaz ancak kaynak kod sıralama ve yuvarlama gerektiriyorsa veya özel değerleri kullanır, kullanın `/fp:precise`. Aksi takdirde kullanmayı `/fp:fast`, daha hızlı ve daha küçük kod üretebilirsiniz.

#### <a name="fast"></a>Hızlı

`/fp:fast` Yeniden sıralama, birleştirme veya kayan nokta kodunun hızını ve alanı iyileştirmek için kayan nokta işlemleri basitleştirmek derleyici seçeneği sağlar. Derleyici, atama deyimleri yuvarlama atlasa, yuvarlamasını veya işlev çağrıları. İşlemlerini yeniden sıralayabilir veya cebirsel dönüşümleri tür dönüştürmeleri garantileyebilirsiniz farklı yuvarlama davranışlara neden olsa bile, örneğin, ilişkilendirilebilir ve dağıtılabilir yasaları kullanarak gerçekleştirin olabilir. Bu gelişmiş iyileştirmesi nedeniyle, kayan nokta bazı hesaplamalar sonucunu diğer tarafından üretilen farklı `/fp` seçenekleri. Özel değerler (NaN, + sonsuz, - sonsuz,-0.0) yayılmayacak ya da kesinlikle IEEE 754 standardına göre davranır. Kayan nokta kısaltmalar altında oluşturulabilir `/fp:fast`. Temel alınan mimarisinde altında tarafından derleyici hala bağlı `/fp:fast`, ve ek iyileştirmeler aracılığıyla kullanılabilir [/arch](arch-minimum-cpu-architecture.md) seçeneği.

Altında `/fp:fast`, derleyici varsayılan kayan nokta ortamda çalıştırmak istediğiniz kodu oluşturur ve kayan nokta ortam erişilebilir değil veya çalışma zamanında değiştirilmiş varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.

`/fp:fast` Sıralama ve kayan nokta ifadeleri yuvarlama katı kaynak kod gerektirmez ve NaN gibi özel değerleri işleme standart kurallarını güvenmeyin programlar için tasarlanmıştır. Kayan nokta kodunuzun sıralama ve yuvarlama kaynak kodunun korunması gerektiriyorsa veya özel değerlerinin kullanımı standart davranışı kullanır [/FP: precise](#precise). Kodunuzu erişen veya yuvarlama modunu değiştirmek için kayan nokta ortamı değiştiriyorsa kayan nokta özel durumlarını LUN'nin maskesini kaldırın veya kayan nokta durumu denetleme, kullanın [/FP: strict](#strict).

#### <a name="except"></a>Dışında

`/fp:except` Seçeneği maskelenmemiş bir kayan nokta özel durumlarını tam noktada ortaya çıktığı üretilir ve hiçbir ek kayan nokta özel durum ortaya çıkar sağlar için kod oluşturur. Varsayılan olarak, `/fp:strict` seçeneğini etkinleştirir `/fp:except`, ve `/fp:precise` desteklemez. `/fp:except` Seçeneği ile uyumlu değil `/fp:fast`. Seçeneğini açıkça bizim tarafımızdan devre dışı bırakılabilir `/fp:except-`.

Unutmayın `/fp:except` kayan nokta özel durumların kendisi tarafından izin vermez ancak için programların kayan nokta özel durumlarını etkinleştir gereklidir. Bkz: [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) kayan nokta özel durumlarını etkinleştirme hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Birden çok `/fp` seçenekleri aynı derleyici komut satırında belirtilebilir. Yalnızca biri `/fp:strict`, `/fp:fast`, ve `/fp:precise` seçenekleri aynı anda etkin olabilir. Komut satırında birden çok seçenek belirtilirse, sonraki seçeneğini önceliklidir ve derleyici bir uyarı oluşturur. `/fp:strict` Ve `/fp:except` seçenekleri ile uyumlu olmayan `/clr`.

[/Za](za-ze-disable-language-extensions.md) (ANSI uyumluluğu) seçeneği ile uyumlu değil `/fp`.

### <a name="using-compiler-directives-to-control-floating-point-behavior"></a>Kayan nokta davranışını denetlemek için derleyici yönergeleri kullanma

Derleyici komut satırında belirtilen kayan nokta davranışı geçersiz kılmak için üç pragma yönergeleri sağlar: [float_control](../../preprocessor/float-control.md), [fenv_access](../../preprocessor/fenv-access.md), ve [fp_contract](../../preprocessor/fp-contract.md). İşlev düzeyi, bir işlev içinde değil, kayan nokta davranışını denetlemek için bu yönergeleri kullanabilirsiniz. Bu yönergeler doğrudan benzemez Not `/fp` seçenekleri. Bu tabloda gösterilir nasıl `/fp` seçenekleri ve pragma yönergeleri harita arasındaki ilişki. Daha fazla bilgi için pragma yönergeleri ve ayrı ayrı seçenekler için belgelere bakın.

||float_control(Precise)|float_control(except)|fenv_access|fp_contract|
|-|-|-|-|-|
|`/fp:fast`|kapalı|kapalı|kapalı|on|
|`/fp:precise`|on|kapalı|kapalı|on|
|`/fp:strict`|on|on|on|kapalı|

### <a name="the-default-floating-point-environment"></a>Kayan nokta varsayılan ortam

Bir işlem başlatıldığında *kayan nokta ortam varsayılan* ayarlanır. Bu ortam tüm kayan nokta özel durumlarını maskeler, yuvarlanacak yuvarlama modu yakın ayarlar (`FE_TONEAREST`), subnormal korur (denormal) değerlerini, anlam (Mantis) varsayılan duyarlığını kullanımları **float**, **çift**, ve **uzun çift** değerleri ve desteklenen durumlarda sonsuzluk denetimi varsayılan afin modunu ayarlar.

### <a name="floating-point-environment-access-and-modification"></a>Kayan nokta ortam erişim ve değişiklik

Microsoft Visual C++ çalışma zamanı erişmek ve kayan nokta ortamı değiştirmek için çeşitli işlevler sağlar. Bunlar [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md), ve [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) ve bunların türevleri. Kodunuzu erişen veya kayan nokta ortamı değiştirir doğru programı davranış sağlamak için `fenv_access` , ya da etkinleştirilmelidir tarafından `/fp:strict` seçeneğini veya göre kullanım `fenv_access` pragması, bu işlevlerin hiçbir etkisi. Zaman `fenv_access` olan etkin değilse, erişim veya kayan nokta ortamın değiştirilmesi beklenmeyen program davranışa neden olabilir: kod kayan nokta ortamındaki istenen değişiklikleri değil dikkate; kayan nokta durumu kayıtları değil bildirebilir Beklenen veya geçerli sonuçlar; Beklenmeyen kayan nokta özel durumları oluşabilir ve beklenen kayan nokta özel durumlarını algılanamayabilir.

Kodunuzu erişen veya kayan nokta ortam değiştirir, kod birleştirdiğinizde, dikkatli olmalıdır nerede `fenv_access` olmayan koduyla etkinleştirildi `fenv_access` etkin. Kod burada `fenv_access` , derleyici varsayar etkin değil, platform varsayılan kayan nokta ortamı geçerli ve kayan nokta durumu erişilen veya değiştirilen değil. Kaydet ve denetim sahip olmayan bir işlev aktarılır önce yerel kayan nokta ortam varsayılan durumuna geri öneririz `fenv_access` etkin. Bu örnek gösterir nasıl `float_control` pragma ayarlayın ve geri:

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>Kayan nokta yuvarlama modları

Her ikisi de altında `/fp:precise` ve `/fp:fast` derleyici varsayılan kayan nokta ortamda çalıştırmak istediğiniz kodu oluşturur ve ortam erişilebilir değil veya çalışma zamanında değiştirilmiş varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.  Ancak, bazı programlar kayan nokta ortam değiştirmeniz gerekir. Örneğin, bu örnek, kayan nokta yuvarlama modu değiştirerek hata sınırlarını bir kayan nokta Çarpmanın hesaplar:

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

Derleyicinin kayan nokta ortamı altında varsayılan varsaydığından `/fp:fast` ve `/fp:precise` çağrıları yok saymak ücretsiz olarak `_controlfp_s`. Örneğin, her ikisi de kullanılarak derlendiğinde `/O2` ve `/fp:precise` x86 için Mimari, sınırları hesaplanmayan ve örnek programın çıktısı şudur:

```Output
cLower = -inf
cUpper = -inf
```

Her ikisi de derlendiğinde `/O2` ve `/fp:strict` x86 için Mimari, örnek programın çıktısı şudur:

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>Kayan nokta özel değerler

Altında `/fp:precise` ve `/fp:strict`, (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler IEEE 754 spesifikasyonlarına uygun davranır. Altında `/fp:fast`, bu özel değerler davranışını IEEE-754 ile tutarsız olabilir.

Bu örnek altındaki özel değerleri olan farklı davranışlarını gösterir `/fp:precise`, `/fp:strict` ve `/fp:fast`:

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

İle derlendiğinde `/O2` `/fp:precise` veya `/O2` `/fp:strict` x86 için yapı çıkışları IEEE 754 belirtimi ile tutarlı:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

İle derlendiğinde `/O2` `/fp:fast` x86 için yapı çıkışları tutarlı değil IEEE-754 ile:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>Kayan nokta cebirsel dönüşümleri

Altında `/fp:precise` ve `/fp:strict`, bit düzeyinde aynı sonucu verecek dönüşümü garanti sürece derleyici matematik dönüşümleri gerçekleştirmez. Derleyici bu tür dönüştürmeleri altında gerçekleştirebilir `/fp:fast`. Örneğin, ifade `a * b + a * c` örnek işlevde `algebraic_transformation` içine derlenmiş `a * (b + c)` altında `/fp:fast`. Tür dönüştürmeleri altında gerçekleştirilen olmayan `/fp:precise` veya `/fp:strict`, ve derleyici oluşturur `a * b + a * c`.

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>Kayan nokta açık atama noktaları

Altında `/fp:precise` ve `/fp:strict`, derleyici için kaynak kodu duyarlık dört belirli noktalarda ifadesi değerlendirmesi sırasında yuvarlar: atamaları olarak sırasında bir kayan noktalı bağımsız değişken işlev çağrısına geçirilen zaman ve bir kayan nokta zaman yuvarlamasını değer, bir işlev çağrısında döndürülür. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir. Altında `/fp:fast`, derleyicinin açık yayınları kaynak kod duyarlık güvence altına almak için bu noktalarda oluşturmaz. Bu örnek altında farklı bir davranış gösterir `/fp` seçenekleri:

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

Kullanılarak derlendiğinde `/O2` `/fp:precise` veya `/O2` `/fp:strict`, açık tür atamaları, her iki türü atayarak ve x64 için oluşturulan kodda işlevin dönüş noktasında eklenmiş olduğunu gördüğünüz mimarisi:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

Altında `/O2` `/fp:fast` tüm tür atamaları attığından oluşturulan kodun Basitleştirilmiş:

```asm
        addss    xmm0, xmm1
        mulss    xmm0, DWORD PTR __real@40a00000
        ret      0
```

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **kod oluşturma** özellik sayfası.

1. Değiştirme **kayan nokta modeli** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.floatingPointModel%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
