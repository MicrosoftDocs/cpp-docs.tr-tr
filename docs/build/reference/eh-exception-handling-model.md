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
ms.openlocfilehash: 9f5eed60ecb51abc1d8fbd3c38773bbf782b23a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271807"
---
# <a name="eh-exception-handling-model"></a>/EH (Özel Durum İşleme Modeli)

Dışarıda özel durumu iyileştirmek için denetlediğinde derleyici ve bir özel durum nedeniyle kapsam dışına çıkmadan C++ nesnelerini yok mi tarafından kullanılan özel durum işleme türünü belirtir. Varsa **/EH** belirtilmezse, derleyici hem zaman uyumsuz yapılandırılmış özel durumları hem de C++ özel durumları yakalamak kodunuzu sağlar, ancak bir zaman uyumsuz özel durum nedeniyle kapsam dışına çıkmadan C++ nesnelerini yok eder.

## <a name="syntax"></a>Sözdizimi

> **/EH**{**s**|**a**}[**c**][**r**][**-**]

## <a name="arguments"></a>Arguments

**a**<br/>
Her ikisi de zaman uyumsuz yakalayan özel durum işleme modeli (yapılandırılmış) ve zaman uyumlu (C++) özel durumları kullanılarak c++ `catch(...)` söz dizimi.

**s**<br/>
Zaman uyumlu () yalnızca C++ özel durumlarını yakalayan ve derleyiciye olarak bildirilen işlevlerin bir özel durum işleme modeli **extern "C"** bir özel durum oluşturabilir.

**c**<br/>
Birlikte kullanılırsa **s** (**/ehsc**), yalnızca C++ özel durumlarını yakalayan ve derleyiciye olarak bildirilen işlevlerin **extern "C"** hiçbir zaman C++ özel durumu oluşturur. **/ EHca** eşdeğerdir **/eha**.

**r**<br/>
Her zaman tüm çalışma zamanı sonlandırma denetimleri oluştur derleyiciye **noexcept** işlevleri. Varsayılan olarak, çalışma zamanı denetler **noexcept** derleyici bir işlevi çağırır işlevler yalnızca oluşturmayan belirlerse iyileştirmede.

## <a name="remarks"></a>Açıklamalar

**/Eha** derleyici seçeneği ile yerel C++ zaman uyumsuz yapılandırılmış özel durum işleme (SEH) desteklemek için kullanılan `catch(...)` yan tümcesi. Belirtmeden SEH uygulamak için **/eha**, kullanmanızı **__try**, **__except**, ve **__finally** söz dizimi. Windows ve Visual C++ SEH uygulamasını desteklese de, ISO standardı C++ özel durum işleme kullanmanızı öneririz (**EHS** veya **/ehsc**), kod daha taşınabilir ve esnek yapan. Bununla birlikte, varolan kodda ya da belirli program türleri için — örneğin, ortak dil çalışma zamanı desteği için derlenmiş kodda ([/CLR (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md)) — SEH kullanmaya devam olabilir. Daha fazla bilgi için [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).

Belirtme **/eha** ve kullanarak, tüm özel durumları işlemeye çalışırken `catch(...)` tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.

Kullanırsanız **EHS** veya **/ehsc**, ardından, `catch(...)` yan tümcesi zaman uyumsuz yapılandırılmış özel durumları yakalamaz. Erişim ihlalleri ve yönetilen <xref:System.Exception?displayProperty=fullName> özel durumları yakalanmaz ve zaman uyumsuz bir özel durum oluşturulduğunda kapsamdaki nesneler zaman uyumsuz özel durum işlense dahi yok edilmez.

Kullanırsanız **/eha**, görüntüyü daha büyük olabilir ve derleyicinin çünkü az gerçekleştirebileceğiniz bir **deneyin** görmediğinde engelleyin. Ayrıca, derleyici C++ özel durumu oluşturabilecek herhangi bir kod görmez olsa bile, otomatik olarak tüm yerel nesnelerin yok ediciler çağrı özel durum filtrelerinde bırakmasıdır. Bu, güvenli yığın geriye doğru izleme zaman uyumsuz özel durumlar için de C++ özel durumlarını olduğu gibi sağlar. Kullanırken **EHS**, özel durumlar, yalnızca oluşabilir derleyici varsayar bir **throw** deyimi veya bir işlev çağrısı. Bu, derleyicinin geriye doğru izlenebilir pek çok nesnenin kullanım süresini izlemeye yönelik kodun ortadan kaldırılmasına olanak tanıyarak kod boyutunu azaltabilir.

Kullanılarak derlenmiş nesneleri bağlamamanızı öneririz **/eha** kullanılarak derlenmiş nesnelerle birlikte **EHS** veya **/ehsc** aynı yürütülebilir modülde. Kullanarak zaman uyumsuz bir özel durum işleme sahip **/eha** modülünüzde, her yerde kullanma **/eha** modüldeki tüm Kodu derlemek için. Yapılandırılmış özel durum işleme sözdizimini aynı modülde kullanarak derlenmiş kod olarak kullanabileceğiniz **EHS**, fakat SEH sözdizimini ile karıştıramazsınız **deneyin**, **throw**ve **catch** aynı işlevde.

Kullanım **/eha** dışında bir şey tarafından tetiklenir bir özel durum yakalamak istiyorsanız bir **throw**. Bu örnekte yapılandırılmış bir özel durum oluşturulup yakalanmaktadır:

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

**/Ehc** seçeneği gerektirir **EHS** veya **/eha** belirtilir. **/CLR** seçeneği gelir **/eha** (diğer bir deyişle, **/CLR** **/eha** gereksizdir). Derleyici bir hata oluşturur **EHS** veya **/ehsc** sonra kullanılan **/CLR**. İyileştirmeler bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici sınıf yok edicisini veya özel durumla aynı kapsamda olan nesne veya nesneler için yok edicileri çağırır. Bir özel durum yakalanmadığında, bu yok ediciler çalıştırılmaz.

Özel durum işleme kısıtlamaları altında hakkında bilgi için **/CLR**, bkz: [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).

Seçeneği, sembolü kullanılarak silinebilir **-**. Örneğin, **/EHsc-** olarak yorumlanır **EHS** **/EHc-** ve eşdeğerdir **EHS**.

**/EHr** derleyici seçeneği, çalışma zamanı sonlandırma denetimleri sahip tüm işlevlerde zorlar bir **noexcept** özniteliği. Bir işlev yalnızca çağırır derleyici arka uç belirlerse, varsayılan olarak, çalışma zamanı denetimleri iyileştirmede *oluşturmayan* işlevleri. Olmayan atma işlevleri hiçbir özel durum oluşturulabilir belirten bir özniteliği olan tüm işlevlerdir. Bu olarak işaretlenmiş işlevler içerir **noexcept**, `throw()`, `__declspec(nothrow)`ve ne zaman **/ehc** belirtilen **extern "C"** işlevleri. Tüm derleyici tarafından İnceleme oluşturmayan olduğunu belirledi de olmayan atma işlevleri içerir. Varsayılan kullanarak açıkça ayarlayabilirsiniz **/EHr-**.

Ancak, oluşturmayan özniteliği işlev tarafından oluşturulan özel durum garantisi değil. Farklı bir **noexcept** işlevi MSVC derleyicisi kullanılarak bildirilen bir işlevi tarafından oluşturulan bir özel göz önünde bulundurur `throw()`, `__declspec(nothrow)`, veya **extern "C"** tanımsız davranış olarak. Bu üç bildirimi öznitelikleri işlevleri, özel durumlar için çalışma zamanı sonlandırma denetimleri uygulamaz. Kullanabileceğiniz **/EHr** bu tanımlamanıza yardımcı olması için seçeneği tanımsız davranış, çalışma zamanı denetimleri kaçış işlenmeyen özel durumlar için derleyicinin zorlayarak bir **noexcept** işlevi.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **C/C++** > **kod oluşturma**.

1. Değiştirme **C++ özel durumlarını etkinleştir** özelliği.

   Veya ayarlayın **C++ özel durumlarını etkinleştir** için **Hayır**ve ardından **komut satırı** özellik sayfasında **ek seçenekler** kutusunda, ekleyin derleyici seçeneği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)<br/>
[Hatalar ve özel durum işleme](../../cpp/errors-and-exception-handling-modern-cpp.md)<br/>
[Özel Durum Belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)
