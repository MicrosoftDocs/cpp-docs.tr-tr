---
title: /EH (Özel Durum İşleme Modeli)
ms.date: 08/14/2018
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
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
ms.openlocfilehash: 8546b14995317afb57e4cc23a5d6f81c2172a1a6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328289"
---
# <a name="eh-exception-handling-model"></a>/EH (Özel Durum İşleme Modeli)

Derleyici tarafından kullanılan özel durum işleme türünü, özel durum denetimlerini ne zaman en iyi duruma getireceklerini ve bir özel durum nedeniyle kapsam dışına çıkan C++ nesnelerini yok edip etmeyeceğini belirtir. **/EH** belirtilmemişse, derleyici kodunuzun hem eşzamanlı yapılandırılmış özel durumları hem de C++ özel durumlarını yakalamasını sağlar, ancak eşzamanlı bir özel durum nedeniyle kapsam dışına çıkan C++ nesnelerini yok etmez.

## <a name="syntax"></a>Sözdizimi

> **/EH**{**s**|**a**}[**c**][**r**][**-**]

## <a name="arguments"></a>Bağımsız Değişkenler

**A**<br/>
C++ `catch(...)` sözdizimi kullanarak hem eşzamanlı (yapılandırılmış) hem de senkron (C++) özel durumları yakalayan özel durum işleme modeli.

**S**<br/>
Yalnızca senkron (C++) özel durumları yakalayan ve derleyiciye **extern "C"** olarak bildirilen işlevlerin bir özel durum ortaya çıkarabileceğini varsaymasını söyleyen özel durum işleme modeli.

**C**<br/>
**s** (**/EHsc**) ile kullanılırsa, yalnızca C++ özel durumlarını yakalar ve derleyiciye **extern "C"** olarak bildirilen işlevlerin asla C++ özel durumu atmadığını varsaymasını söyler. **/EHca** **/EHa'ya**eşdeğerdir.

**R**<br/>
Derleyiciye, tüm **noexcept** işlevleri için her zaman çalışma zamanı sonlandırma denetimleri oluşturmasını söyler. Varsayılan olarak, derleyici yalnızca atanmayan işlevleri çağırır işlevi belirlerse, **noexcept** için çalışma zamanı denetimleri en iyi duruma getirilebilir.

## <a name="remarks"></a>Açıklamalar

**/EHa** derleyici seçeneği, ana c++ `catch(...)` yan tümcesi ile eşzamanlı yapılandırılmış özel durum işleme (SEH) desteklemek için kullanılır. **/EHa**belirtmeden SEH uygulamak **için, __try,** **__except**ve **__finally** sözdizimini kullanabilirsiniz. Windows ve Visual C++ SEH'yi desteklemesine rağmen, kodu daha taşınabilir ve esnek hale getirirken ISO standardı C++ özel durum işleme **(/EHs** veya **/EHsc)** kullanmanızı şiddetle öneririz. Bununla birlikte, varolan kodda veya belirli türde programlariçin(örneğin, ortak dil çalışma süresini desteklemek için derlenen kodda ([/clr (Ortak Dil Çalışma Süresi Derlemesi)](clr-common-language-runtime-compilation.md))—yine de SEH kullanmanız gerekebilir. Daha fazla bilgi için bkz: [Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).

**/EHa** belirtme ve kullanarak `catch(...)` tüm özel durumları ele almaya çalışmak tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.

**/EHs** veya **/EHsc**kullanıyorsanız, `catch(...)` yan tümceniz eşzamanlı yapılandırılmış özel durumları yakalamaz. Erişim ihlalleri ve <xref:System.Exception?displayProperty=fullName> yönetilen özel durumlar yakalanmaz ve eşzamanlı özel durum oluşturulduğunda kapsamdaki nesneler, eşzamanlı özel durum işlense bile yok edilmez.

**/EHa**kullanıyorsanız, derleyici bir **try** bloğunu agresif bir şekilde optimize etmediğinden görüntü daha büyük olabilir ve daha az iyi performans gösterebilir. Derleyici C++ özel durumu atabilecek herhangi bir kod görmese bile, tüm yerel nesnelerin yıkıcılarını otomatik olarak arayan özel durum filtrelerinde de bırakır. Bu, c++ özel durumlar için olduğu kadar eşzamanlı özel durumlar için de güvenli yığın gevşemesini sağlar. **/EHs**kullandığınızda, derleyici özel durumların yalnızca **bir atış** deyiminde veya bir işlev çağrısında oluşabileceğini varsayar. Bu, derleyicinin geriye doğru izlenebilir pek çok nesnenin kullanım süresini izlemeye yönelik kodun ortadan kaldırılmasına olanak tanıyarak kod boyutunu azaltabilir.

**/EHa** kullanarak derlenen nesneleri aynı çalıştırılabilir modülde **/EHs** veya **/EHsc** kullanılarak derlenen nesnelerle birbirine bağlamamanızı öneririz. Modülünüzün herhangi bir yerinde **/EHa** kullanarak bir eşzamanlı özel durum işlemek zorundaysanız, modüldeki tüm kodu derlemek için **/EHa'yı** kullanın. **/EH'ler**kullanılarak derlenen kodla aynı modülde yapılandırılmış özel durum işleme sözdizimini kullanabilirsiniz, ancak SEH sözdizimini aynı işlevi **kullanarak deneyin,** **atve** **yada** karıştıramazsınız.

**Bir atış**dışında bir şey tarafından yükseltilen bir özel durum yakalamak istiyorsanız **/ EHa** kullanın. Bu örnekte yapılandırılmış bir özel durum oluşturulup yakalanmaktadır:

```cpp
// compiler_options_EHA.cpp
// compile with: /EHa
#include <iostream>
#include <excpt.h>
using namespace std;

void fail() {   // generates SE and attempts to catch it using catch(...)
   try {
      int i = 0, j = 1;
      j /= i;   // This will throw a SE (divide by zero).
      printf("%d", j);
   }
   catch(...) {   // catch block will only be executed under /EHa
      cout<<"Caught an exception in catch(...)."<<endl;
   }
}

int main() {
   __try {
      fail();
   }

   // __except will only catch an exception here
   __except(EXCEPTION_EXECUTE_HANDLER) {
      // if the exception was not caught by the catch(...) inside fail()
      cout << "An exception was caught in __except." << endl;
   }
}
```

**/EHc** seçeneği için **/EHs** veya **/EHa** belirtilmesi gerekmektedir. **/clr** seçeneği **/EHa** (yani/ **clr** **/EHa** gereksizdir) anlamına gelir. **/EHs** veya **/EHsc** **/clr'den**sonra kullanılırsa derleyici hata oluşturur. İyileştirmeler bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici sınıf yok edicisini veya özel durumla aynı kapsamda olan nesne veya nesneler için yok edicileri çağırır. Bir özel durum yakalanmadığında, bu yok ediciler çalıştırılmaz.

**/clr**altındaki özel durum işleme kısıtlamaları hakkında bilgi için [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)bkz.

Seçenek, sembolü **-** kullanılarak temizlenebilir. Örneğin, **/EHsc-** **/EHs** **/EHc-** olarak yorumlanır ve **/EHs'e**eşdeğerdir.

**/EHr** derleyici seçeneği, **noexcept** özniteliği olan tüm işlevlerde çalışma zamanı sonlandırma denetimlerini zorlar. Varsayılan olarak, derleyici arka uç bir işlevin yalnızca *atanmayan* işlevleri çağırdığını belirlerse, çalışma zamanı denetimleri en iyi duruma getirilebilir. Atamayan işlevler, özel durum ların atılabileceğine dair bir özniteliğe sahip işlevlerdir. `throw()`Bu, `__declspec(nothrow)` **"C"** işlevlerini **extern** olarak işaretli işlevleri içerir. **/EHc** Fırlatma yapmayan işlevler, derleyicinin denetim le fırlatmamaya karar verdiği işlevleri de içerir. Varsayılan ı **açıkça /EHr-**.

Ancak, atmayan öznitelik, bir işlev tarafından hiçbir özel durum atılanınabileceğinin garantisi değildir. Bir **dış** işlevin davranışından farklı olarak, MSVC derleyicisi , `throw()` `__declspec(nothrow)`"C" kullanarak bildirilen bir işlev tarafından atılan bir özel durum olarak kabul eder veya **"C" adlı işlevi** tanımlanmamış davranış olarak görür. Bu üç bildirim özniteliklerini kullanan işlevler, özel durumlar için çalışma zamanı sonlandırma denetimleri zorlamaz. Derlemeyi, **bir noexcept** işlevinden kaçan işlenmemiş özel durumlar için çalışma zamanı denetimleri oluşturmaya zorlayarak, bu tanımlanmamış davranışı belirlemenize yardımcı olmak için **/EHr** seçeneğini kullanabilirsiniz.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **Yapılandırma Özellikleri** > **C/C++** > **Kod Oluşturma'yı**seçin.

1. **C++ Özel Durumlar Özelliğini Etkinleştir** özelliğini değiştirin.

   Veya **C++ Özel Durumlarını** **Hayır**olarak etkinleştir'i ve ardından **Komut Satırı** özelliği sayfasında **Ek Seçenekler** kutusunda derleyici seçeneğini ekleyin.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Hatalar ve Özel Durum Taşıma](../../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
