---
title: /EH (Özel durum işleme modeli)
description: Visual Studio 'daki Microsoft C++/EH (özel durum işleme modeli) derleyicisi seçeneklerine yönelik başvuru kılavuzu.
ms.date: 08/25/2020
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
- SEH
- try
- catch
- throw
- extern
- finally
- noexcept
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 0d18d0f1d73b1de46b12262deecb2436c34e6176
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898381"
---
# <a name="eh-exception-handling-model"></a>`/EH` (Özel durum işleme modeli)

Derleyici tarafından oluşturulan özel durum işleme modeli desteğini belirtir. Bağımsız değişkenler `catch(...)` , hem yapılandırılmış hem de standart C++ özel durumlarına sözdiziminin uygulanıp uygulanmayacağını, ** extern "C"** kodunun özel durumlara kabul edilip edilmeyeceğini throw ve belirli denetimleri iyileştirip iyileştirmeyeceğini belirtir **`noexcept`** .

## <a name="syntax"></a>Syntax

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>Arguments

**`a`**\
Standart C++ yığını geriye doğru izlemeyi mümkün. Sözdizimi kullandığınızda hem yapılandırılmış (zaman uyumsuz) hem de standart C++ (zaman uyumlu) özel durumlarını yakalar `catch(...)` . **`/EHa`** hem hem **`/EHs`** de **`/EHc`** bağımsız değişkenlerini geçersiz kılar.

**`s`**\
Standart C++ yığını geriye doğru izlemeyi mümkün. Söz dizimi kullandığınızda yalnızca standart C++ özel durumlarını yakalar `catch(...)` . **`/EHc`** Ayrıca belirtilmediği sürece, derleyici ** extern "C"** olarak belirtilen işlevlerin throw bir C++ özel durumu olabileceğini varsayar.

**`c`**\
İle kullanıldığında **`/EHs`** , derleyici ** extern "C"** olarak belirtilen işlevlerin hiçbir zaman throw C++ özel durumu olarak olduğunu varsayar. İle kullanıldığında **`/EHa`** (yani, **`/EHca`** öğesine eşdeğerdir) hiçbir etkisi yoktur **`/EHa`** . **`/EHc`** belirtilmemişse, yok **`/EHs`** sayılır **`/EHa`** .

**`r`**\
Derleyiciye tüm işlevler için her zaman çalışma zamanı sonlandırma denetimleri oluşturmasını söyler **`noexcept`** . Varsayılan olarak, **`noexcept`** derleyici işlevi yalnızca kullanmayan işlevleri çağırdığında, çalışma zamanı denetimleri en iyi duruma getirilebilir throw . Bu seçenek, bazı ek kodların maliyetiyle katı C++ uygunluğu sağlar. **`/EHr`** belirtilmemişse, yok **`/EHs`** sayılır **`/EHa`** .

**`-`**\
Önceki seçenek bağımsız değişkenini temizler. Örneğin, **`/EHsc-`** olarak yorumlanır ve ile **`/EHs /EHc-`** eşdeğerdir **`/EHs`** .

**`/EH`** bağımsız değişkenler herhangi bir sırada ayrı ayrı veya birleştirilmiş olarak belirtilebilir. Aynı bağımsız değişkenin birden fazla örneği belirtilirse, son bir daha önceki olanları geçersiz kılar.  Örneğin, ile **`/EHr- /EHc /EHs`** aynıdır **`/EHscr-`** ve **`/EHscr- /EHr`** aynı etkiye sahiptir **`/EHscr`** .

## <a name="remarks"></a>Açıklamalar

### <a name="default-exception-handling-behavior"></a>Varsayılan özel durum işleme davranışı

Derleyici zaman uyumsuz yapılandırılmış özel durum işlemeyi () destekleyen bir kod üretir SEH . Varsayılan olarak (yani,, **`/EHsc`** **`/EHs`** veya **`/EHa`** seçeneği belirtilmişse), derleyici SEH Yerel C++ `catch(...)` yan tümcesindeki işleyicileri destekler. Ancak, C++ özel durumlarını yalnızca kısmen destekleyen kodu da oluşturur. Varsayılan özel durum geriye doğru izleme kodu, [`try`](../../cpp/try-throw-and-catch-statements-cpp.md) özel bir durum nedeniyle kapsam dışına çıkan blokların dışındaki otomatik C++ nesnelerini yok etmez. C++ özel durumu n olduğunda kaynak sızıntıları ve tanımsız davranış ortaya çıkabilir throw .

### <a name="standard-c-exception-handling"></a>Standart C++ özel durum işleme

Standart C++ özel durum işleme modeli için, güvenli bir şekilde yığın nesneleri gerektiren **`/EHsc`** (önerilen), veya için tam derleyici desteği **`/EHs`** **`/EHa`** .

**`/EHs`** Veya kullanıyorsanız **`/EHsc`** , `catch(...)` yan tümcelerinizi catch zaman uyumsuz yapılandırılmış özel durumlar değildir. Tüm erişim ihlalleri ve yönetilen <xref:System.Exception?displayProperty=fullName> özel durumlar yakalanamayan. Ve, zaman uyumsuz özel durum oluştuğunda kapsamdaki nesneler, kod uyumsuz özel durumu işlese bile yok edilmez. Bu davranış, yapılandırılmış özel durumların işlenmemiş bırakılması için bir bağımsız değişkendir. Bunun yerine, bu özel durumları önemli değerlendirin.

**`/EHs`** Veya kullandığınızda **`/EHsc`** , derleyici özel durumların yalnızca bir **`throw`** ifadede veya bir işlev çağrısında gerçekleşebileceğini varsayar. Bu varsayım, derleyicinin, kod boyutunu önemli ölçüde azaltan birçok nesnenin ömrünü izlemeye yönelik kodu ortadan kaldırmasına olanak tanır. Kullanırsanız **`/EHa`** , derleyici blokları kararlılık olarak iyileştirmediği için yürütülebilir görüntünüz daha büyük ve daha yavaş olabilir **`try`** . Derleyici C++ özel durumu ile ilgili herhangi bir kodu görmese de, yerel nesneleri otomatik olarak temizleyen özel durum filtrelerinde de kalır throw .

### <a name="structured-and-standard-c-exception-handling"></a>Yapılandırılmış ve standart C++ özel durum işleme

**`/EHa`** Derleyici seçeneği, hem zaman uyumsuz özel durumlar hem de C++ özel durumları için güvenli yığın geri sarma özelliğini sunar. Yerel C++ yan tümcesini kullanarak hem standart C++ hem de yapılandırılmış özel durumların işlenmesini destekler `catch(...)` . Belirtmeden uygulamak için,, SEH **`/EHa`** **`__try`** **`__except`** ve **`__finally`** sözdizimini kullanabilirsiniz. Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md).

> [!IMPORTANT]
> **`/EHa`** try Kullanarak tüm özel durumları işlemek için belirtme ve kullanma `catch(...)` tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.
>
> Windows ve Visual C++ desteklese de SEH , ISO standardı C++ özel durum işleme (veya) kullanmanızı önemle öneririz **`/EHsc`** **`/EHs`** . Kodunuzu daha taşınabilir ve esnek hale getirir. SEHEski kodda veya belirli türde programlar için kullanmak istediğiniz zamanlar olabilir. Örneğin, ortak dil çalışma zamanını () desteklemek için derlenen kodda gereklidir [`/clr`](clr-common-language-runtime-compilation.md) . Daha fazla bilgi için bkz. [yapılandırılmış özel durum işleme](../../cpp/structured-exception-handling-c-cpp.md).
>
> Kullanılarak derlenen nesne dosyalarını **`/EHa`** , veya kullanılarak derlenenlere **`/EHs`** **`/EHsc`** aynı yürütülebilir modülde bağlamayın. Modülünüzün herhangi bir yerini kullanarak zaman uyumsuz bir özel durumu işlemeniz gerekiyorsa **`/EHa`** , **`/EHa`** modüldeki tüm kodu derlemek için kullanın. Kullanılarak derlenen kodla aynı modülde yapılandırılmış özel durum işleme sözdizimini kullanabilirsiniz **`/EHs`** . Ancak, SEH sözdizimini C++ **`try`** , **`throw`** , ve ile aynı işlevde karıştıramazsınız **`catch`** .

' **`/EHa`** catch Den başka bir şey tarafından oluşturulan bir özel durum istiyorsanız kullanın **`throw`** . Bu örnek, catch yapılandırılmış bir özel durum oluşturur ve geliştirir:

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail()
{
    // generates SE and attempts to catch it using catch(...)
    try
    {
        int i = 0, j = 1;
        j /= i;   // This will throw a SE (divide by zero).
        printf("%d", j);
    }
    catch(...)
    {
        // catch block will only be executed under /EHa
        cout << "Caught an exception in catch(...)." << endl;
    }
}

int main()
{
    __try
    {
        fail();
    }

    // __except will only catch an exception here
    __except(EXCEPTION_EXECUTE_HANDLER)
    {
        // if the exception was not caught by the catch(...) inside fail()
        cout << "An exception was caught in __except." << endl;
    }
}
```

### <a name="exception-handling-under-clr"></a>/Clr altında özel durum işleme

**`/clr`** Seçeneği (yani **`/EHa`** , **`/clr /EHa`** gereksizdir) anlamına gelir. Derleyici, **`/EHs`** veya sonrasında kullanıldığında bir hata oluşturur **`/EHsc`** **`/clr`** . İyileştirmeler Bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici özel durumla aynı kapsamda olan herhangi bir nesne için sınıf yıkıcıları çağırır. Bir özel durum yakalanmazsa, bu yok ediciler çalıştırılmaz.

Altında özel durum işleme kısıtlamaları hakkında daha fazla bilgi için **`/clr`** bkz. [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).

### <a name="runtime-exception-checks"></a>Çalışma zamanı özel durum denetimleri

**`/EHr`** Seçeneği özniteliği olan tüm işlevlerde çalışma zamanı sonlandırma denetimlerini zorlar **`noexcept`** . Varsayılan olarak, derleyici arka ucu bir işlevin yalnızca *yapmayan throw * işlevleri çağırdığını belirlerse, çalışma zamanı denetimleri en iyi duruma getirilebilir. Olmayan throw İşlevler, hiçbir özel durum belirten bir özniteliği olan işlevlerdir, throw n olabilir. ,,, Ve belirtildiğinde işlevleri,,, **`noexcept`** `throw()` `__declspec(nothrow)` ve **`/EHc`** **`extern "C"`** işlevleri içerir. Yerleşik olmayan throw İşlevler, derleyicinin İnceleme tarafından belirlenebileceği tüm özellikleri de içerir throw . Kullanarak varsayılan davranışı açık bir şekilde ayarlayabilirsiniz **`/EHr-`** .

Olmayan bir throw öznitelik, özel durumların throw bir işlev tarafından n olamaz. Bir işlevin davranışının aksine, **`noexcept`** MSVC derleyicisi,, throw `throw()` `__declspec(nothrow)` veya tanımsız davranışlar kullanılarak belirtilen bir işlev tarafından n özel durumunu değerlendirir **`extern "C"`** . Bu üç bildirim özniteliğini kullanan işlevler, özel durumlar için çalışma zamanı sonlandırma denetimlerini zorlamaz. **`/EHr`** Bu tanımsız davranışı belirlemenize yardımcı olması için, derleyicinin bir işlev kaçış işlenmemiş özel durumlar için çalışma zamanı denetimleri oluşturmasını zorlayarak Bu tanımsız davranışı tanımlamanızı sağlayabilirsiniz **`noexcept`** .

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
[Hatalar ve özel durum işleme](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[Özel durum belirtimleri ( throw )](../../cpp/exception-specifications-throw-cpp.md)\
[Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
