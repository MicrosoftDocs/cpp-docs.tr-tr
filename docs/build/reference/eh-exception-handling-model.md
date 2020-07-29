---
title: /EH (Özel durum işleme modeli)
description: Visual Studio 'daki Microsoft C++/EH (özel durum işleme modeli) derleyicisi seçeneklerine yönelik başvuru kılavuzu.
ms.date: 04/14/2020
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
no-loc:
- ':::no-loc(SEH):::'
- ':::no-loc(try):::'
- ':::no-loc(catch):::'
- ':::no-loc(throw):::'
- ':::no-loc(extern):::'
- ':::no-loc(finally):::'
- ':::no-loc(noexcept):::'
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: f158e951d595d5934ff513254871710db5920bf1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232722"
---
# <a name="eh-exception-handling-model"></a>/EH (Özel durum işleme modeli)

Derleyici tarafından oluşturulan özel durum işleme modeli desteğini belirtir. Bağımsız değişkenler `:::no-loc(catch):::(...)` , hem yapılandırılmış hem de standart C++ özel durumlarına sözdiziminin uygulanıp uygulanmayacağını, ** :::no-loc(extern)::: "C"** kodunun özel durumlara kabul edilip edilmeyeceğini :::no-loc(throw)::: ve belirli denetimleri iyileştirip iyileştirmeyeceğini belirtir **`:::no-loc(noexcept):::`** .

## <a name="syntax"></a>Sözdizimi

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>Arguments

**`a`**\
Standart C++ yığını geriye doğru izlemeyi mümkün. Sözdizimi kullandığınızda hem yapılandırılmış (zaman uyumsuz) hem de standart C++ (zaman uyumlu) özel durumlarını yakalar `:::no-loc(catch):::(...)` . **`/EHa`** hem hem **`/EHs`** de **`/EHc`** bağımsız değişkenlerini geçersiz kılar.

**`s`**\
Standart C++ yığını geriye doğru izlemeyi mümkün. Söz dizimi kullandığınızda yalnızca standart C++ özel durumlarını yakalar `:::no-loc(catch):::(...)` . **`/EHc`** Ayrıca belirtilmediği sürece, derleyici ** :::no-loc(extern)::: "C"** olarak belirtilen işlevlerin :::no-loc(throw)::: bir C++ özel durumu olabileceğini varsayar.

**`c`**\
İle kullanıldığında **`/EHs`** , derleyici ** :::no-loc(extern)::: "C"** olarak belirtilen işlevlerin hiçbir zaman :::no-loc(throw)::: C++ özel durumu olarak olduğunu varsayar. İle kullanıldığında **`/EHa`** (yani, **`/EHca`** öğesine eşdeğerdir) hiçbir etkisi yoktur **`/EHa`** . **`/EHc`** belirtilmemişse, yok **`/EHs`** sayılır **`/EHa`** .

**`r`**\
Derleyiciye tüm işlevler için her zaman çalışma zamanı sonlandırma denetimleri oluşturmasını söyler **`:::no-loc(noexcept):::`** . Varsayılan olarak, **`:::no-loc(noexcept):::`** derleyici işlevi yalnızca kullanmayan işlevleri çağırdığında, çalışma zamanı denetimleri en iyi duruma getirilebilir :::no-loc(throw)::: . Bu seçenek, bazı ek kodların maliyetiyle katı C++ uygunluğu sağlar. **`/EHr`** belirtilmemişse, yok **`/EHs`** sayılır **`/EHa`** .

**`-`**\
Önceki seçenek bağımsız değişkenini temizler. Örneğin, **`/EHsc-`** olarak yorumlanır ve ile **`/EHs /EHc-`** eşdeğerdir **`/EHs`** .

**`/EH`** bağımsız değişkenler herhangi bir sırada ayrı ayrı veya birleştirilmiş olarak belirtilebilir. Aynı bağımsız değişkenin birden fazla örneği belirtilirse, son bir daha önceki olanları geçersiz kılar.  Örneğin, ile **`/EHr- /EHc /EHs`** aynıdır **`/EHscr-`** ve **`/EHscr- /EHr`** aynı etkiye sahiptir **`/EHscr`** .

## <a name="remarks"></a>Açıklamalar

### <a name="default-exception-handling-behavior"></a>Varsayılan özel durum işleme davranışı

Derleyici zaman uyumsuz yapılandırılmış özel durum işlemeyi () destekleyen bir kod üretir :::no-loc(SEH)::: . Varsayılan olarak (yani,, **`/EHsc`** **`/EHs`** veya **`/EHa`** seçeneği belirtilmişse), derleyici :::no-loc(SEH)::: Yerel C++ `:::no-loc(catch):::(...)` yan tümcesindeki işleyicileri destekler. Ancak, C++ özel durumlarını yalnızca kısmen destekleyen kodu da oluşturur. Varsayılan özel durum geriye doğru izleme kodu, [:::no-loc(try):::](../../cpp/:::no-loc(try):::-:::no-loc(throw):::-and-:::no-loc(catch):::-statements-cpp.md) özel bir durum nedeniyle kapsam dışına çıkan blokların dışındaki otomatik C++ nesnelerini yok etmez. C++ özel durumu n olduğunda kaynak sızıntıları ve tanımsız davranış ortaya çıkabilir :::no-loc(throw)::: .

### <a name="standard-c-exception-handling"></a>Standart C++ özel durum işleme

Standart C++ özel durum işleme modeli için, güvenli bir şekilde yığın nesneleri gerektiren **`/EHsc`** (önerilen), veya için tam derleyici desteği **`/EHs`** **`/EHa`** .

**`/EHs`** Veya kullanıyorsanız **`/EHsc`** , `:::no-loc(catch):::(...)` yan tümcelerinizi :::no-loc(catch)::: zaman uyumsuz yapılandırılmış özel durumlar değildir. Tüm erişim ihlalleri ve yönetilen <xref:System.Exception?displayProperty=fullName> özel durumlar yakalanamayan. Ve, zaman uyumsuz özel durum oluştuğunda kapsamdaki nesneler, kod uyumsuz özel durumu işlese bile yok edilmez. Bu davranış, yapılandırılmış özel durumların işlenmemiş bırakılması için bir bağımsız değişkendir. Bunun yerine, bu özel durumları önemli değerlendirin.

**`/EHs`** Veya kullandığınızda **`/EHsc`** , derleyici özel durumların yalnızca bir **`:::no-loc(throw):::`** ifadede veya bir işlev çağrısında gerçekleşebileceğini varsayar. Bu varsayım, derleyicinin, kod boyutunu önemli ölçüde azaltan birçok nesnenin ömrünü izlemeye yönelik kodu ortadan kaldırmasına olanak tanır. Kullanırsanız **`/EHa`** , derleyici blokları kararlılık olarak iyileştirmediği için yürütülebilir görüntünüz daha büyük ve daha yavaş olabilir **`:::no-loc(try):::`** . Derleyici C++ özel durumu ile ilgili herhangi bir kodu görmese de, yerel nesneleri otomatik olarak temizleyen özel durum filtrelerinde de kalır :::no-loc(throw)::: .

### <a name="structured-and-standard-c-exception-handling"></a>Yapılandırılmış ve standart C++ özel durum işleme

**`/EHa`** Derleyici seçeneği, hem zaman uyumsuz özel durumlar hem de C++ özel durumları için güvenli yığın geri sarma özelliğini sunar. Yerel C++ yan tümcesini kullanarak hem standart C++ hem de yapılandırılmış özel durumların işlenmesini destekler `:::no-loc(catch):::(...)` . Belirtmeden uygulamak için :::no-loc(SEH)::: **`/EHa`** ** :::no-loc(try)::: __**, **`__except`** ve sözdizimini kullanabilirsiniz **`__:::no-loc(finally):::`** . Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md).

> [!IMPORTANT]
> **`/EHa`** :::no-loc(try)::: Kullanarak tüm özel durumları işlemek için belirtme ve kullanma `:::no-loc(catch):::(...)` tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.
>
> Windows ve Visual C++ desteklese de :::no-loc(SEH)::: , ISO standardı C++ özel durum işleme (veya) kullanmanızı önemle öneririz **`/EHsc`** **`/EHs`** . Kodunuzu daha taşınabilir ve esnek hale getirir. :::no-loc(SEH):::Eski kodda veya belirli türde programlar için kullanmak istediğiniz zamanlar olabilir. Örneğin, ortak dil çalışma zamanını ([/clr](clr-common-language-runtime-compilation.md)) desteklemek için derlenen kodda gereklidir. Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md).
>
> Kullanılarak derlenen nesne dosyalarını **`/EHa`** , veya kullanılarak derlenenlere **`/EHs`** **`/EHsc`** aynı yürütülebilir modülde bağlamayın. Modülünüzün herhangi bir yerini kullanarak zaman uyumsuz bir özel durumu işlemeniz gerekiyorsa **`/EHa`** , **`/EHa`** modüldeki tüm kodu derlemek için kullanın. Kullanılarak derlenen kodla aynı modülde yapılandırılmış özel durum işleme sözdizimini kullanabilirsiniz **`/EHs`** . Ancak, :::no-loc(SEH)::: sözdizimini C++ **`:::no-loc(try):::`** , **`:::no-loc(throw):::`** , ve ile aynı işlevde karıştıramazsınız **`:::no-loc(catch):::`** .

' **`/EHa`** :::no-loc(catch)::: Den başka bir şey tarafından oluşturulan bir özel durum istiyorsanız kullanın **`:::no-loc(throw):::`** . Bu örnek, :::no-loc(catch)::: yapılandırılmış bir özel durum oluşturur ve geliştirir:

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail()
{
    // generates SE and attempts to :::no-loc(catch)::: it using :::no-loc(catch):::(...)
    :::no-loc(try):::
    {
        int i = 0, j = 1;
        j /= i;   // This will :::no-loc(throw)::: a SE (divide by zero).
        printf("%d", j);
    }
    :::no-loc(catch):::(...)
    {
        // :::no-loc(catch)::: block will only be executed under /EHa
        cout << "Caught an exception in :::no-loc(catch):::(...)." << endl;
    }
}

int main()
{
    __:::no-loc(try):::
    {
        fail();
    }

    // __except will only :::no-loc(catch)::: an exception here
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        // if the exception was not caught by the :::no-loc(catch):::(...) inside fail()
        cout << "An exception was caught in __except." << endl;
    }
}
```

### <a name="exception-handling-under-clr"></a>/Clr altında özel durum işleme

**`/clr`** Seçeneği (yani **`/EHa`** , **`/clr /EHa`** gereksizdir) anlamına gelir. Derleyici, **`/EHs`** veya sonrasında kullanıldığında bir hata oluşturur **`/EHsc`** **`/clr`** . İyileştirmeler Bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici özel durumla aynı kapsamda olan herhangi bir nesne için sınıf yıkıcıları çağırır. Bir özel durum yakalanmazsa, bu yok ediciler çalıştırılmaz.

Altında özel durum işleme kısıtlamaları hakkında daha fazla bilgi için **`/clr`** bkz. [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).

### <a name="runtime-exception-checks"></a>Çalışma zamanı özel durum denetimleri

**`/EHr`** Seçeneği özniteliği olan tüm işlevlerde çalışma zamanı sonlandırma denetimlerini zorlar **`:::no-loc(noexcept):::`** . Varsayılan olarak, derleyici arka ucu bir işlevin yalnızca *yapmayan :::no-loc(throw)::: * işlevleri çağırdığını belirlerse, çalışma zamanı denetimleri en iyi duruma getirilebilir. Olmayan :::no-loc(throw)::: İşlevler, hiçbir özel durum belirten bir özniteliği olan işlevlerdir, :::no-loc(throw)::: n olabilir. ,,, **`:::no-loc(noexcept):::`** Ve belirtildiğinde `:::no-loc(throw):::()` , `__declspec(no:::no-loc(throw):::)` **`/EHc`** ** :::no-loc(extern)::: "C"** işlevleri olarak işaretlenen işlevleri içerirler. Yerleşik olmayan :::no-loc(throw)::: İşlevler, derleyicinin İnceleme tarafından belirlenebileceği tüm özellikleri de içerir :::no-loc(throw)::: . Kullanarak varsayılan davranışı açık bir şekilde ayarlayabilirsiniz **`/EHr-`** .

Olmayan bir :::no-loc(throw)::: öznitelik, özel durumların :::no-loc(throw)::: bir işlev tarafından n olamaz. Bir işlevin davranışının aksine, **`:::no-loc(noexcept):::`** MSVC derleyicisi :::no-loc(throw)::: `:::no-loc(throw):::()` ,, `__declspec(no:::no-loc(throw):::)` veya ** :::no-loc(extern)::: "C"** kullanılarak veya tanımsız davranış olarak belirtilen bir işlev tarafından bir özel durum alır. Bu üç bildirim özniteliğini kullanan işlevler, özel durumlar için çalışma zamanı sonlandırma denetimlerini zorlamaz. **`/EHr`** Bu tanımsız davranışı belirlemenize yardımcı olması için, derleyicinin bir işlev kaçış işlenmemiş özel durumlar için çalışma zamanı denetimleri oluşturmasını zorlayarak Bu tanımsız davranışı tanımlamanızı sağlayabilirsiniz **`:::no-loc(noexcept):::`** .

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Visual Studio veya program aracılığıyla seçeneği ayarlama

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **kod üretimi**' ni seçin.

1. **C++ özel durumlarını etkinleştir** özelliğini değiştirin.

   İsterseniz, **C++ özel durumlarını etkinleştir** ' **i Hayır**olarak ayarlayın ve ardından **komut satırı** özellik sayfasındaki **ek seçenekler** kutusunda derleyici seçeneğini ekleyin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)\
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)\
[Hatalar ve özel durum Işleme](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[Özel durum belirtimleri ( :::no-loc(throw)::: )](../../cpp/exception-specifications-:::no-loc(throw):::-cpp.md)\
[Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
