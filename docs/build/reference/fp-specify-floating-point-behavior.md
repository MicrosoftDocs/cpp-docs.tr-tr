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
ms.openlocfilehash: 616efc0980c6ddadfee078dbe7a382372c5636ec
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57818173"
---
# <a name="fp-specify-floating-point-behavior"></a>/FP (kayan nokta davranışını belirt)

Derleyicinin kayan nokta ifadeleri, iyileştirmeler ve özel durumları nasıl işler belirtir. **/FP** oluşturulan kodun ortam kayan nokta yuvarlama modu, özel durum maskeleri ve subnormal davranışını değiştirir izin verip ve kayan nokta durum denetimleri olup iade geçerli, doğru seçeneklerini belirtin Sonuç. Olup derleyici kaynak işlemi ve ifade sıralamasını korur ve NaN yayma işlemi standardına uygun kodu oluşturur ya da, bunun yerine yeniden sıralamak veya işlemleri birleştirin ve basitleştirme kullanmak daha verimli kod oluşturursa denetler Standart tarafından izin verilmeyen cebirsel dönüşümleri.

## <a name="syntax"></a>Sözdizimi

> **/ FP:**[**kesin** | **katı** | **hızlı** | **dışında**[ **-**]]

### <a name="arguments"></a>Arguments

#### <a name="precise"></a>kesin

Varsayılan olarak, derleyicinin kullandığı **/FP: precise** davranışı.

Altında **/FP: precise** derleyici kaynak ifade sıralama ve kayan nokta kodu özelliklerini oluşturur ve nesne kodu hedef makine için en iyi duruma getirir, yuvarlama korur. Derleyici için kaynak kodu duyarlık dört belirli noktalarda ifadesi değerlendirmesi sırasında yuvarlar: adresindeki atamaları olarak yuvarlamasını, bir kayan noktalı bağımsız değişken işlev çağrısına geçirilen zaman ve kayan nokta değeri zaman bir işlev çağrısında döndürülür. Ara hesaplamalar makine duyarlık gerçekleştirilebilir. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir.

Bit düzeyinde aynı sonucu verecek dönüşümü garanti sürece derleyici cebirsel dönüşümleri yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadesine gerçekleştirmez.
IEEE-754 spesifikasyonlarına uygun (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler işlenir. Örneğin, `x != x` değerlendiren **true** x NaN ise. Kayan nokta *kısaltmalar*, diğer bir deyişle, kayan nokta işlemleri birleştiren makine yönergelerine oluşturulabilir altında **/FP: precise**.

Derleyici kod çalıştırmak için hedeflenen oluşturur [varsayılan kayan nokta ortam](#the-default-floating-point-environment) ve kayan nokta ortamı değil erişilen veya çalışma zamanında değiştirilmiş olduğunu varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.

Kayan nokta kodunuzun işlemler ve ifadeler, kayan nokta deyimlerinde bazında bağlı değilse (örneğin, İlgilenmiyor, olmadığını `a * b + a * c` olarak hesaplanan `(b + c) * a` veya `2 * a` olarak `a + a`), gözönündebulundurun[Fast](#fast) seçeneği, daha hızlı, daha verimli kod üretebilirsiniz. Kodunuzu hem işlemleri ve ifadeler, bazında bağlıdır ve erişir veya kayan nokta ortam (örneğin, yuvarlama modunu değiştirmek veya kayan nokta özel durumları yakalamak için) değiştirir, kullanın [/FP: strict](#strict).

#### <a name="strict"></a>Katı

**/ FP: katı** davranışı benzer **/FP: precise**, diğer bir deyişle, derleyici kaynak sıralamasını korur ve yuvarlama özelliklerini oluşturur ve en iyi duruma getirir, kayan nokta kodu nesne için hedef makine kodu ve özel değerler işlerken standart gözlemler. Ayrıca, programın güvenli bir şekilde erişebilir veya çalışma zamanında kayan nokta ortamı değiştirin.

Altında **/FP: strict**, derleyici veren programın güvenli bir şekilde kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirmek kod oluşturur. İfade değerlendirme sırasında kaynak kod duyarlık dört belirli noktalarda için yuvarlar: adresindeki atamaları olarak yuvarlamasını, bir kayan noktalı bağımsız değişken işlev çağrısına geçirilen zaman ve kayan nokta değeri zaman bir işlev çağrısında döndürülür. Ara hesaplamalar makine duyarlık gerçekleştirilebilir. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir. Bit düzeyinde aynı sonucu verecek dönüşümü garanti sürece derleyici cebirsel dönüşümleri yeniden ilişkilendirme veya dağıtım gibi kayan nokta ifadesine gerçekleştirmez. IEEE-754 spesifikasyonlarına uygun (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler işlenir. Örneğin, `x != x` değerlendiren **true** x NaN ise. Kayan nokta kısaltmalar altında oluşturulmaz **/FP: strict**.

**/ FP: strict** değerinden daha yoğun olan **/FP: precise** derleyici özel durumları yakalamak ve programlar erişmek veya kayan nokta ortam değiştirmek izin vermek için ek yönergeler eklemeniz gerekir çünkü çalışma zamanı. Kodunuzu bu özellik kullanmaz ancak kaynak kod sıralama ve yuvarlama gerektiriyorsa veya özel değerleri kullanır, kullanın **/FP: precise**. Aksi takdirde kullanmayı **Fast**, daha hızlı ve daha küçük kod üretebilirsiniz.

#### <a name="fast"></a>Hızlı

**Fast** yeniden sıralama, birleştirme veya kayan nokta kodunun hızını ve alanı iyileştirmek için kayan nokta işlemleri basitleştirmek derleyici seçeneği sağlar. Derleyici, atama deyimleri yuvarlama atlasa, yuvarlamasını veya işlev çağrıları. İşlemlerini yeniden sıralayabilir veya cebirsel dönüşümleri tür dönüştürmeleri garantileyebilirsiniz farklı yuvarlama davranışlara neden olsa bile, örneğin, ilişkilendirilebilir ve dağıtılabilir yasaları kullanarak gerçekleştirin olabilir. Bu gelişmiş iyileştirmesi nedeniyle, kayan nokta bazı hesaplamalar sonucunu diğer tarafından üretilen farklı **/FP** seçenekleri. Özel değerler (NaN, + sonsuz, - sonsuz,-0.0) yayılmayacak ya da kesinlikle IEEE 754 standardına göre davranır. Kayan nokta kısaltmalar altında oluşturulabilir **Fast**. Temel alınan mimarisinde altında tarafından derleyici hala bağlı **Fast**, ve ek iyileştirmeler aracılığıyla kullanılabilir [/arch](arch-minimum-cpu-architecture.md) seçeneği.

Altında **Fast**, derleyici varsayılan kayan nokta ortamda çalıştırmak istediğiniz kodu oluşturur ve kayan nokta ortam erişilebilir değil veya çalışma zamanında değiştirilmiş varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.

**Fast** katı kaynak kod sıralama ve kayan nokta ifadeleri yuvarlama gerektirmez ve NaN gibi özel değerleri işleme standart kurallarını güvenmeyin programları içindir. Kayan nokta kodunuzun sıralama ve yuvarlama kaynak kodunun korunması gerektiriyorsa veya özel değerlerinin kullanımı standart davranışı kullanır [/FP: precise](#precise). Kodunuzu erişen veya yuvarlama modunu değiştirmek için kayan nokta ortamı değiştiriyorsa kayan nokta özel durumlarını LUN'nin maskesini kaldırın veya kayan nokta durumu denetleme, kullanın [/FP: strict](#strict).

#### <a name="except"></a>Dışında

**/FP: except** seçeneği maskelenmemiş bir kayan nokta özel durumlarını tam noktada ortaya çıktığı üretilir ve hiçbir ek kayan nokta özel durum ortaya çıkar sağlar için kod oluşturur. Varsayılan olarak, **/FP: katı** seçeneğini etkinleştirir **/FP: dışında**, ve **/FP: precise** desteklemez. **/FP: except** seçeneği ile uyumlu değil **Fast**. Seçeneğini açıkça bizim tarafımızdan devre dışı bırakılabilir **/FP: except-**.

Unutmayın **/FP: dışında** kayan nokta özel durumların kendisi tarafından izin vermez ancak için programların kayan nokta özel durumlarını etkinleştir gereklidir. Bkz: [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md) kayan nokta özel durumlarını etkinleştirme hakkında daha fazla bilgi için.

## <a name="remarks"></a>Açıklamalar

Birden çok **/FP** seçenekleri aynı derleyici komut satırında belirtilebilir. Yalnızca biri **/FP: strict**, **Fast**, ve **/FP: precise** seçenekleri aynı anda etkin olabilir. Komut satırında birden çok seçenek belirtilirse, sonraki seçeneğini önceliklidir ve derleyici bir uyarı oluşturur. **/FP: strict** ve **/FP: except** seçenekleri ile uyumlu değildir **/CLR**.

[/Za](za-ze-disable-language-extensions.md) (ANSI uyumluluğu) seçeneği ile uyumlu değil **/FP**.

### <a name="using-pragmas-to-control-floating-point-behavior"></a>Pragmalar denetimi kayan nokta davranışı için kullanma

Derleyici komut satırında belirtilen kayan nokta davranışı geçersiz kılmak için üç pragma yönergeleri sağlar: [float_control](../../preprocessor/float-control.md), [fenv_access](../../preprocessor/fenv-access.md), ve [fp_contract](../../preprocessor/fp-contract.md). İşlev düzeyi, bir işlev içinde değil, kayan nokta davranışını denetlemek için bu pragmaları kullanabilirsiniz. Bu pragmaları doğrudan benzemez Not **/FP** seçenekleri. Bu tabloda gösterilir nasıl **/FP** seçenekleri ve pragmalar harita arasındaki ilişki. Daha fazla bilgi için pragmalar ve ayrı ayrı seçenekler için belgelere bakın.

||float_control(Precise)|float_control(except)|fenv_access|fp_contract|
|-|-|-|-|-|
|**/fp:fast**|kapalı|kapalı|kapalı|on|
|**/fp:precise**|on|kapalı|kapalı|on|
|**/fp:strict**|on|on|on|kapalı|

### <a name="the-default-floating-point-environment"></a>Kayan nokta varsayılan ortam

Bir işlem başlatıldığında *kayan nokta ortam varsayılan* ayarlanır. Bu ortam tüm kayan nokta özel durumlarını maskeler, yuvarlanacak yuvarlama modu yakın ayarlar (`FE_TONEAREST`), subnormal korur (denormal) değerlerini, anlam (Mantis) varsayılan duyarlığını kullanımları **float**, **çift**, ve **uzun çift** değerleri ve desteklenen durumlarda sonsuzluk denetimi varsayılan afin modunu ayarlar.

### <a name="floating-point-environment-access-and-modification"></a>Kayan nokta ortam erişim ve değişiklik

Microsoft Visual C++ çalışma zamanı erişmek ve kayan nokta ortamı değiştirmek için çeşitli işlevler sağlar. Bunlar [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md), [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md), ve [_statusfp](../../c-runtime-library/reference/status87-statusfp-statusfp2.md) ve bunların türevleri. Kodunuzu erişen veya kayan nokta ortamı değiştirir doğru programı davranış sağlamak için `fenv_access` , ya da etkinleştirilmesi gerekir tarafından **/FP: strict** seçeneğini veya göre kullanım `fenv_access` pragması, bu işlevler için herhangi bir etkisi yoktur. Zaman `fenv_access` olan etkin değilse, erişim veya kayan nokta ortamın değiştirilmesi beklenmeyen program davranışa neden olabilir: kod kayan nokta ortamındaki istenen değişiklikleri değil dikkate; kayan nokta durumu kayıtları değil bildirebilir Beklenen veya geçerli sonuçlar; Beklenmeyen kayan nokta özel durumları oluşabilir ve beklenen kayan nokta özel durumlarını algılanamayabilir.

Kodunuzu erişen veya kayan nokta ortam değiştirir, kod birleştirdiğinizde, dikkatli olmalıdır nerede `fenv_access` olmayan koduyla etkinleştirildi `fenv_access` etkin. Kod burada `fenv_access` , derleyici varsayar etkin değil, platform varsayılan kayan nokta ortamı geçerli ve kayan nokta durumu erişilen veya değiştirilen değil. Kaydet ve denetim sahip olmayan bir işlev aktarılır önce yerel kayan nokta ortam varsayılan durumuna geri öneririz `fenv_access` etkin. Bu örnek gösterir nasıl `float_control` pragma ayarlayın ve geri:

```cpp
#pragma float_control(strict, on, push)
// Code that uses /fp:strict mode
#pragma float_control(pop)
```

### <a name="floating-point-rounding-modes"></a>Kayan nokta yuvarlama modları

Her ikisi de altında **/FP: precise** ve **Fast** derleyici varsayılan kayan nokta ortamda çalıştırmak istediğiniz kodu oluşturur ve ortam erişilebilir değil veya çalışma zamanında değiştirilmiş varsayar. Diğer bir deyişle, kodu değil kayan nokta özel durum maskesini kaldırmak, okuma veya kayan nokta durumu kayıtları yazmak veya yuvarlama modu değiştirme olduğunu varsayar.  Ancak, bazı programlar kayan nokta ortam değiştirmeniz gerekir. Örneğin, bu örnek, kayan nokta yuvarlama modu değiştirerek hata sınırlarını bir kayan nokta Çarpmanın hesaplar:

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

Derleyicinin kayan nokta ortamı altında varsayılan varsaydığından **Fast** ve **/FP: precise** çağrıları yok saymak ücretsiz olarak `_controlfp_s`. Örneğin, her ikisi de kullanılarak derlendiğinde **/O2** ve **/FP: precise** x86 için Mimari, sınırları hesaplanmayan ve örnek programın çıktısı şudur:

```Output
cLower = -inf
cUpper = -inf
```

İle derlendiğinde **/O2** ve **/FP: strict** x86 için Mimari, örnek program çıkışı:

```Output
cLower = -inf
cUpper = -3.40282e+38
```

### <a name="floating-point-special-values"></a>Kayan nokta özel değerler

Altında **/FP: precise** ve **/FP: strict**, (NaN, + sonsuz, - sonsuz,-0.0) özel değerler içeren ifadeler IEEE 754 spesifikasyonlarına uygun davranır. Altında **Fast**, bu özel değerler davranışını IEEE-754 ile tutarsız olabilir.

Bu örnek altındaki özel değerleri olan farklı davranışlarını gösterir **/FP: precise**, **/FP: strict** ve **Fast**:

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

İle derlendiğinde **/O2** **/FP: precise** veya **/O2** **/FP: strict** x86 için yapı çıkışları IEEE-754 ile tutarlı belirtimi:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 0
INFINITY - INFINITY  : -nan(ind)
NAN - NAN            : -nan(ind)
std::signbit(-0.0/-INFINITY): 1
```

İle derlendiğinde **/O2** **Fast** x86 için yapı çıkışları tutarlı değil IEEE-754 ile:

```Output
INFINITY == INFINITY : 1
NAN == NAN           : 1
INFINITY - INFINITY  : 0.000000
NAN - NAN            : 0.000000
std::signbit(-0.0/-INFINITY): 0
```

### <a name="floating-point-algebraic-transformations"></a>Kayan nokta cebirsel dönüşümleri

Altında **/FP: precise** ve **/FP: strict**, dönüşümü bir bit düzeyinde aynı sonucu verecek garanti sürece derleyici matematik dönüşümleri gerçekleştirmez. Derleyici bu tür dönüştürmeleri altında gerçekleştirebilir **Fast**. Örneğin, ifade `a * b + a * c` örnek işlevde `algebraic_transformation` içine derlenmiş `a * (b + c)` altında **Fast**. Tür dönüştürmeleri altında gerçekleştirilen olmayan **/FP: precise** veya **/FP: strict**, ve derleyici oluşturur `a * b + a * c`.

```cpp
float algebraic_transformation (float a, float b, float c)
{
    return a * b + a * c;
}
```

### <a name="floating-point-explicit-casting-points"></a>Kayan nokta açık atama noktaları

Altında **/FP: precise** ve **/FP: katı**, derleyici için kaynak kodu duyarlık dört belirli noktalarda ifadesi değerlendirmesi sırasında yuvarlar: atamaları olarak sırasında bir kayan noktalı bağımsız değişken olduğunda yuvarlamasını bir işlev çağrısı için ve bir işlev çağrısında bir kayan nokta değeri döndürüldüğünde geçirilir. Yuvarlamasını açıkça Ara hesaplamalar yuvarlamak için kullanılabilir. Altında **Fast**, derleyicinin açık yayınları kaynak kod duyarlık güvence altına almak için bu noktalarda oluşturmaz. Bu örnek altında farklı bir davranış gösterir **/FP** seçenekleri:

```cpp
float casting(float a, float b)
{
    return 5.0*((double)(a+b));
}
```

Kullanılarak derlendiğinde **/O2** **/FP: precise** veya **/O2** **/FP: strict**, açık tür atamaları her ikisi de eklenmiş olduğunu görebilirsiniz. türü atayarak ve işlevin x64 için üretilen kod noktası döndürmek mimarisi:

```asm
        addss    xmm0, xmm1
        cvtss2sd xmm0, xmm0
        mulsd    xmm0, QWORD PTR __real@4014000000000000
        cvtsd2ss xmm0, xmm0
        ret      0
```

Altında **/O2** **Fast** tüm tür atamaları attığından oluşturulan kodun Basitleştirilmiş:

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

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[MSVC kayan nokta iyileştirme](floating-point-optimization.md)<br/>
