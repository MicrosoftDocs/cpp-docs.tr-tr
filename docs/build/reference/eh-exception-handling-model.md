---
title: "-EH (özel durum işleme modeli) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ExceptionHandling
- /eh
- VC.Project.VCCLCompilerTool.ExceptionHandling
dev_langs: C++
helpviewer_keywords:
- exception handling, compiler model
- cl.exe compiler, exception handling
- EH compiler option [C++]
- -EH compiler option [C++]
- /EH compiler option [C++]
ms.assetid: 754b916f-d206-4472-b55a-b6f1b0f2cb4d
caps.latest.revision: "29"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c56020d5013e951d9d43ed799d34641d114d612
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="eh-exception-handling-model"></a>/EH (Özel Durum İşleme Modeli)
Özel durum işleme koyma özel durumu iyileştirmek için denetlediğinde derleyici ve mi kapsamının dışında bir özel durum nedeniyle Git C++ nesneleri yok etme tarafından kullanılan türünü belirtir. Varsa **/EH** belirtilmezse, derleyici, yapılandırılmış zaman uyumsuz özel durumları ve C++ özel durumlarını yakalar ancak kapsamının dışında bir zaman uyumsuz özel durum nedeniyle Git C++ nesneleri silmiyor.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
/EH{s|a}[c][r][-]  
```  
  
## <a name="arguments"></a>Arguments  
 **bir**  
 Hem zaman uyumsuz (yapılı) hem de zaman uyumlu (C++) özel durumları yakalayan özel durum işleme modeli.  
  
 **s**  
 Yalnızca C++ özel durumları yakalar ve İşlevler olarak bildirilen varsaymak derleyici söyler özel durum işleme modeli `extern "C"` bir özel durum.  
  
 **c**  
 İle kullandıysanız **s** (**/EHsc**), yalnızca C++ özel durumları yakalar ve İşlevler olarak bildirilen varsaymak derleyici söyler `extern "C"` hiçbir zaman bir C++ özel durum.  
  
 **/ EHca** eşdeğerdir **/EHa**.  
  
 **r**  
 Her zaman tüm çalışma zamanı sonlandırma denetimleri oluşturmak için derleyici söyler `noexcept` işlevleri. Varsayılan olarak, çalışma zamanı denetler `noexcept` derleyici işlevi çağırır yalnızca atma olmayan işlevleri belirlerse hemen için iyileştirilmiş.  
  
## <a name="remarks"></a>Açıklamalar  
 **/EHa** derleyici seçeneği ile yerel C++ zaman uyumsuz yapılandırılmış özel durum işleme (SEH) desteklemek için kullanılan `catch(...)` yan tümcesi. SEH belirtmeden uygulamak için **/EHa**, kullanabilirsiniz `__try`, `__except`, ve `__finally` sözdizimi. Windows ve Visual C++ SEH desteklese de, ISO-standart C++ özel durum işleme kullanmanızı öneririz (**/EHs** veya **/EHsc**) çünkü daha taşınabilir ve esnek kodu sağlar. Bununla birlikte, var olan kodu veya programları belirli türde — Örneğin, ortak dil çalışma zamanı desteklemek için derlenmiş kod ([/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md)) — hala SEH kullanmanız gerekebilir. Daha fazla bilgi için bkz: [yapılandırılmış özel durum işleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md).  
  
 Belirtme **/EHa** ve kullanarak, tüm özel durumları işlemeye çalışırken `catch(...)` tehlikeli olabilir. Çoğu durumda, zaman uyumsuz özel durumlar kurtarılamaz olarak kabul edilir ve önemli olarak düşünülmelidir. Onları yakalamak ve devam etmek, işlemin bozulmasına neden olarak bulunması ve giderilmesi zor olan hatalara yol açabilir.  
  
 Kullanırsanız **/EHs** veya **/EHsc**, sonra `catch(...)` yan tümcesi, zaman uyumsuz yapılandırılmış özel durum catch değil. Erişim ihlalleri ve yönetilen <xref:System.Exception?displayProperty=fullName> özel durum yakalanmadı ve zaman uyumsuz özel durum işlendiği olsa bile, zaman uyumsuz bir özel durum oluşturulduğunda kapsamındaki nesnelerin yok değil.  
  
 Kullanırsanız **/EHa**, görüntüyü daha büyük olabilir ve derleyici değil en iyi duruma getirmek için az gerçekleştirebileceğiniz bir `try` olarak titizlikle engelleyin. Ayrıca, derleyicinin C++ özel durum herhangi bir kod görmez olsa bile, tüm yerel nesneleri Yıkıcılar otomatik olarak çağrı özel durum filtreleri bırakır. Bu, güvenli yığını zaman uyumsuz özel durumlar için de C++ özel durumlarını ettirilmesi geriye doğru izleme sağlar. Kullandığınızda **/EHs**, özel durumlar, yalnızca oluşabilir derleyici varsayar bir `throw` deyimi veya bir işlev çağrısı. Bu, derleyicinin geriye doğru izlenebilir pek çok nesnenin kullanım süresini izlemeye yönelik kodun ortadan kaldırılmasına olanak tanıyarak kod boyutunu azaltabilir.  
  
 Kullanarak derlenmiş nesneleri bağlamayan öneririz **/EHa** kullanarak derlenmiş nesneleri ile birlikte **/EHs** aynı yürütülebilir modülünde. Kullanarak bir zaman uyumsuz özel durum işleme gerekip gerekmediğini **/EHa** herhangi bir yere, modülde kullanmak **/EHa** modülündeki tüm Kodu derlemek için. Yapılandırılmış özel durum işleme sözdizimini kullanarak derlenmiş kod aynı modüldeki kullanabilirsiniz **/EHs**, ancak SEH sözdizimiyle karıştıramazsınız `try`, `throw`, ve `catch` aynı işlevde.  
  
 Kullanım **/EHa** dışında bir şey tarafından tetiklenir bir özel durum catch istiyorsanız bir `throw`. Bu örnekte yapılandırılmış bir özel durum oluşturulup yakalanmaktadır:  
  
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
  
 **/EHc** seçenek gerektirir **/EHs** veya **/EHa** belirtilir. **/CLR** seçeneği gelir **/EHa** (diğer bir deyişle, **/CLR /EHa** gereksizdir). Derleyici bir hata oluşturur **/EHs [c]** sonra kullanılan **/CLR**. İyileştirmeler bu davranışı etkilemez. Bir özel durum yakalandığında, derleyici sınıf yok edicisini veya özel durumla aynı kapsamda olan nesne veya nesneler için yok edicileri çağırır. Bir özel durum yakalanmadığında, bu yok ediciler çalıştırılmaz.  
  
 Özel durum kısıtlamaları altında işleme hakkında bilgi için **/CLR**, bkz: [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md).  
  
 Simgenin kullanarak seçeneği temizlenebilir  **-** . Örneğin, **/EHsc-** olarak yorumlanır **/EHs /EHc-** ve eşdeğerdir **/EHs**.  
  
 **/EHr** derleyici seçeneği zorlar sahip tüm işlevleri çalışma zamanı sonlandırma denetimlerinde bir `noexcept` özniteliği. Bir işlev yalnızca çağırır derleyici arka uç belirlerse, varsayılan olarak, çalışma zamanı denetimleri hemen en iyi duruma *atma olmayan* işlevleri. Olmayan atma işlevleri hiçbir durumlar belirten bir özniteliği olan tüm işlevlerdir. Bu işlevler işaretlenmiş içerir `noexcept`, `throw()`, `__declspec(nothrow)`ve ne zaman **/EHc** belirtilirse, `extern "C"` işlevleri. Olmayan atma işlevleri derleyici olmayan denetleme tarafından atma olan belirledi herhangi içerir. Açıkça varsayılan kullanarak ayarlayabileceğiniz **/EHr-**.  
  
 Ancak, atma öznitelik hiçbir özel durum bir işlev tarafından atılabilen bir garanti değil. Davranışını aksine bir `noexcept` işlevi, Visual C++ derleyicisi kullanılarak bildirilen bir işlev tarafından oluşturulan bir özel göz önünde bulundurur `throw()`, `__declspec(nothrow)`, veya `extern "C"` tanımsız davranış olarak. Bu üç bildirimi öznitelikler kullanan işlevler çalışma zamanı sonlandırma denetimleri özel durumlar için uygulamaz. Kullanabileceğiniz **/EHr** seçeneği kaçış işlenmeyen özel durumlar için çalışma zamanı denetimlerini oluşturmak için derleyici zorlayarak tanımsız Bu davranış tanımlamanıza yardımcı olması için bir `noexcept` işlevi.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Sol bölmede **yapılandırma özellikleri**, **C/C++**, **kod oluşturma**.  
  
3.  Değiştirme **C++ özel durumlarını etkinleştirmek** özelliği.  
  
     İsterseniz, **C++ özel durumlarını etkinleştirmek** için **Hayır**ve ardından **komut satırı** özellik sayfasında **ek seçenekler** kutusunda, eklemek derleyici seçeneği.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ExceptionHandling%2A>.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)   
 [Hatalar ve özel durum işleme](../../cpp/errors-and-exception-handling-modern-cpp.md)   
 [Özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md)   
 [Yapılandırılmış Özel Durum İşleme (C/C++)](../../cpp/structured-exception-handling-c-cpp.md)