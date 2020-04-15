---
title: /EH (Özel durum işleme modeli)
description: Visual Studio'da Microsoft C++ /EH (Özel Durum işleme modeli) derleyici seçeneklerine başvuru kılavuzu.
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
- SEH
- try
- catch
- throw
- extern
- finally
- noexcept
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 68d6af657e7c20c0f5e84674dd91803beb35fba0
ms.sourcegitcommit: 0e4feb35b47c507947262d00349d4a893863a6d3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81396296"
---
# <a name="eh-exception-handling-model"></a>/EH (Özel durum işleme modeli)

Derleyici tarafından oluşturulan özel durum işleme modeli desteğini belirtir. Bağımsız değişkenler, `catch(...)` sözdizimini hem yapılandırılmış hem de standart C++ özel throw durumlarına uygulayıp uygulamayacağını, **noexcept** ** extern "C"** kodunun özel durumlara kabul edilip edilemeyeceğini ve belirli denetimleri optimize edip etmeyeceğini belirtir.

## <a name="syntax"></a>Sözdizimi

> **`/EHa`**[**`-`**]\
> **`/EHs`**[**`-`**]\
> **`/EHc`**[**`-`**]\
> **`/EHr`**[**`-`**]

## <a name="arguments"></a>Bağımsız Değişkenler

**`a`**\
Standart C++ yığınının gevşemesini sağlar. Sözdizimini kullandığınızda `catch(...)` hem yapılandırılmış (asynchronous) hem de standart C++ (senkron) özel durumları yakalar. **`/EHa`** hem de **`/EHs`** **`/EHc`** bağımsız değişkenleri geçersiz kılar.

**`s`**\
Standart C++ yığınının gevşemesini sağlar. Sözdizimini kullandığınızda `catch(...)` yalnızca standart C++ özel durumlarını yakalar. Ayrıca **`/EHc`** belirtilmediği sürece, derleyici ** extern "C"** olarak throw bildirilen işlevlerin C++ özel durumu olabileceğini varsayar.

**`c`**\
**`/EHs`**'ile kullanıldığında derleyici, ** extern "C"** olarak bildirilen işlevlerin hiçbir zaman throw C++ özel durumu olmadığını varsayar. Bu ile **`/EHa`** kullanıldığında hiçbir etkisi yoktur **`/EHca`** (yani, **`/EHa`** eşdeğerdir). **`/EHc`****`/EHs`** belirtilmemişse **`/EHa`** veya belirtilmemişse yoksayılır.

**`r`**\
Derleyiciye tüm **noexcept** işlevler için her zaman çalışma zamanı sonlandırma denetimleri oluşturmasını söyler. Varsayılan olarak, derleyici **noexcept** yalnızca atanmayan işlevleri çağıran işlevi belirlerse, çalışma zamanı denetimleri en iyi duruma getirilebilir. Bu seçenek, bazı ekstra kod pahasına sıkı C++ uygunluğu sağlar. **`/EHr`****`/EHs`** belirtilmemişse **`/EHa`** veya belirtilmemişse yoksayılır.

**`-`**\
Önceki seçenek bağımsız değişkenini temizler. Örneğin, **`/EHsc-`** olarak **`/EHs /EHc-`** yorumlanır ve **`/EHs`** eşdeğerdir .

**`/EH`** bağımsız değişkenler herhangi bir sırada ayrı ayrı veya birleştirilebilir. Aynı bağımsız değişkenin birden fazla örneği belirtilirse, sonuncusu öncekileri geçersiz kılar.  Örneğin, **`/EHr- /EHc /EHs`** **`/EHscr-`** aynı ' ve **`/EHscr- /EHr`** **`/EHscr`** aynı etkiye sahiptir .

## <a name="remarks"></a>Açıklamalar

### <a name="default-exception-handling-behavior"></a>Varsayılan özel durum işleme davranışı

Derleyici her zaman eşzamanlı yapılandırılmış özel durum işlemeyiSEHdestekleyen kod lar üretir ( ). Varsayılan olarak (yani, **`/EHsc`** hiçbir **`/EHs`**, **`/EHa`** , veya seçenek belirtilmemişse), derleyici `catch(...)` yerel C++ yan tümcesi'ndeki işleyicileri destekler. SEH Ancak, c++ özel durumlarını kısmen destekleyen kod da oluşturur. Varsayılan özel durum çözme kodu, özel durum nedeniyle kapsam [try](../../cpp/try-throw-and-catch-statements-cpp.md) dışına çıkan blokların dışındaki otomatik C++ nesnelerini yok etmez. C++ özel durumu atıldığında kaynak sızıntıları ve tanımlanmamış davranışlar oluşabilir.

### <a name="standard-c-exception-handling"></a>Standart C++ özel durum işleme

Yığın nesnelerini güvenli bir şekilde söken Standart C++ özel **`/EHsc`** durum **`/EHs`** işleme **`/EHa`** modeli için tam derleyici desteği gerektirir (önerilir), veya .

Eğer **`/EHs`** kullanırsanız **`/EHsc`** veya, `catch(...)` o zaman catch yan tümceleri asynchronous yapılandırılmış özel durumlar yok. Erişim ihlalleri ve <xref:System.Exception?displayProperty=fullName> yönetilen özel durumlar yakalanmadan gider. Ayrıca, eşiş bir özel durum oluştuğunda kapsamdaki nesneler, kod asynchronous özel durumu işlese bile yok olmaz. Bu davranış, yapılandırılmış özel durumları işlenmemiş bırakmak için bir bağımsız değişkendir. Bunun yerine, bu özel durumları ölümcül olarak düşünün.

Kullandığınızda **`/EHs`** veya **`/EHsc`** derleyici özel durumların yalnızca bir **throw** deyimde veya bir işlev çağrısında oluşabileceğini varsayar. Bu varsayım, derleyicinin, kod boyutunu önemli ölçüde azaltabilen birçok durdurulabilir nesnenin yaşam süresini izlemek için kodu ortadan kaldırmasını sağlar. **`/EHa`** İsterseniz, çalıştırılabilir görüntünüz daha büyük ve daha yavaş olabilir, **try** çünkü derleyici blokları agresif bir şekilde optimize etmez. Derleyici C++ özel durumu olabilecek throw herhangi bir kod görmese bile, yerel nesneleri otomatik olarak temizleyen özel durum filtrelerinde de kalır.

### <a name="structured-and-standard-c-exception-handling"></a>Yapılandırılmış ve standart C++ özel durum işleme

Derleyici seçeneği, **`/EHa`** hem eşzamanlı özel durumlar hem de C++ özel durumlar için güvenli yığın gevşemesini sağlar. Yerel C++ `catch(...)` yan tümcesini kullanarak hem standart C++ hem de yapılandırılmış özel durumların işlenmesini destekler. Belirtmeden SEH uygulamak **`/EHa`** için, **sözdizimini**__try, **__except**ve **__finally** kullanabilirsiniz. Daha fazla bilgi için [bkz.](../../cpp/structured-exception-handling-c-cpp.md)

> [!IMPORTANT]
> Kullanarak **`/EHa`** tüm özel durumları belirtme ve `catch(...)` işlemeye çalışmak tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.
>
> Windows ve Visual C++ SEHdesteği ne kadar destekleolsa da, ISO**`/EHsc`** standardı **`/EHs`** C++ özel durum işleme (veya) kullanmanızı şiddetle öneririz. Kodunuzu daha taşınabilir ve esnek hale getirir. Eski kodda veya belirli SEH türde programlarda kullanmanız gereken zamanlar olabilir. Örneğin, ortak dil çalışma süresini[(/clr)](clr-common-language-runtime-compilation.md)desteklemek için derlenen kodda gereklidir. Daha fazla bilgi için [bkz.](../../cpp/structured-exception-handling-c-cpp.md)
>
> Kullanılarak **`/EHa`** derlenen nesne dosyalarını asla aynı çalıştırılabilir **`/EHs`** **`/EHsc`** modülde derlenen dosyalara bağlamamamanızı öneririz. Modülünüzün herhangi bir yerini kullanarak **`/EHa`** bir eşzamanlı özel durum **`/EHa`** işlemek zorundaysanız, modüldeki tüm kodu derlemek için kullanın. Yapılandırılmış özel durum işleme sözdizimini, '' **`/EHs`** kullanılarak derlenen kodla aynı modülde kullanabilirsiniz. Ancak, SEH sözdizimini C++ **try** ile **throw** ve **catch** aynı işlevle karıştıramazsınız.

Başka **`/EHa`** bir şey catch tarafından yükseltilen bir özel **throw** durum istiyorsanız kullanın . Bu örnekte yapılandırılmış bir özel durum oluşturulup yakalanmaktadır:

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

### <a name="exception-handling-under-clr"></a>/clr altında özel durum işleme

Seçenek **`/clr`** ima **`/EHa`** eder (diğer bir şey, **`/clr /EHa`** gereksizdir). Derleyici, 'den sonra **`/EHs`** **`/clr`** **`/EHsc`** kullanılırsa veya sonra kullanılırsa bir hata oluşturur. Optimizasyonlar bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici özel durumla aynı kapsamda olan nesneler için sınıf yıkıcılarını çağırır. Bir istisna yakalanmazsa, bu yıkıcılar çalıştırılmaz.

Altındaki özel durum işleme **`/clr`** kısıtlamaları hakkında bilgi için [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)bkz.

### <a name="runtime-exception-checks"></a>Çalışma zamanı özel durum denetimleri

Seçenek, **`/EHr`** özniteliği olan **noexcept** tüm işlevlerde çalışma zamanı sonlandırma denetimlerini zorlar. Varsayılan olarak, derleyici arka uç bir işlevin yalnızca *atanmayan* işlevleri çağırdığını belirlerse, çalışma zamanı denetimleri en iyi duruma getirilebilir. Atamayan işlevler, özel durum ların atılabileceğine dair bir özniteliğe sahip işlevlerdir. Bunlar işaretli **noexcept** `throw()`işlevleri `__declspec(nothrow)`içerir , **`/EHc`** , , ve, belirtildiği zaman, ** extern "C"** işlevleri. Fırlatma yapmayan işlevler, derleyicinin denetim le fırlatmamaya karar verdiği işlevleri de içerir. Varsayılan davranışı kullanarak açıkça **`/EHr-`** ayarlayabilirsiniz.

Atamayan bir öznitelik, özel durumların bir işlev tarafından atılamayacağıgarantisi değildir. Bir **noexcept** işlevin davranışından farklı olarak, MSVC derleyicisi, `throw()` `__declspec(nothrow)` ** extern "C"** kullanılarak bildirilen bir işlev tarafından atılan bir özel durumu tanımlanmamış davranış olarak kabul eder. Bu üç bildirim özniteliklerini kullanan işlevler, özel durumlar için çalışma zamanı sonlandırma denetimlerini zorlamaz. Derleyiciyi, **`/EHr`** bir **noexcept** işlevden kaçan işlenmemiş özel durumlar için çalışma zamanı denetimleri oluşturmaya zorlayarak bu tanımlanmamış davranışı belirlemenize yardımcı olmak için bu seçeneği kullanabilirsiniz.

## <a name="set-the-option-in-visual-studio-or-programmatically"></a>Seçeneği Visual Studio'da veya programlı olarak ayarlama

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **Yapılandırma Özellikleri** > **C/C++** > **Kod Oluşturma'yı**seçin.

1. **C++ Özel Durumlar Özelliğini Etkinleştir** özelliğini değiştirin.

   Veya **C++ Özel Durumlarını** **Hayır**olarak etkinleştir'i ve ardından **Komut Satırı** özelliği sayfasında **Ek Seçenekler** kutusunda derleyici seçeneğini ekleyin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyici Seçenekleri](compiler-options.md)\
[MSVC Derleyici Komut Satırı Sözdizimi](compiler-command-line-syntax.md)\
[Hatalar ve Özel Durum Taşıma](../../cpp/errors-and-exception-handling-modern-cpp.md)\
[Özel DurumthrowÖzellikleri ( )](../../cpp/exception-specifications-throw-cpp.md)\
[Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
