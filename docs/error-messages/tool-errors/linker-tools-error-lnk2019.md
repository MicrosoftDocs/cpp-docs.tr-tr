---
title: "Bağlayıcı araçları hatası LNK2019 | Microsoft Docs"
ms.custom: 
ms.date: 05/17/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2019
dev_langs: C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.assetid: 4392be92-195c-4eb2-bd4d-49cfac3ca291
caps.latest.revision: "39"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ce3fddc9977f0abda1d776fd66172dbb49e86d3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2019"></a>Bağlayıcı Araçları Hatası LNK2019
Çözümlenmemiş dış simgesi '*simgesi*'işlevinde başvurulan'*işlevi*'  
  
Derlenmiş kodunu *işlevi* bir başvuru veya çağrı yapar *simgesi*, ancak bu simge herhangi bir bağlayıcıya belirtilen nesne dosyaları ve kitaplıkları tanımlanmadı.  
  
Bu hata iletisini önemli hatası tarafından izlenir [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). LNK1120 hatayı düzeltmek için tüm LNK2001 ve LNK2019 hataları düzeltmeniz gerekir.  
  
## <a name="possible-causes"></a>Olası nedenler  
  
Bu hatayı almak için birçok yolu vardır, ancak bunların tümünün bir işlevi veya bağlayıcı olamaz değişkeni bir başvuru içeren *gidermek*, veya için bir tanım bulunamıyor. Bir simge olmadığında derleyici tanımlayabilirsiniz *bildirilen*, ancak ne zaman onu değil *tanımlanan*, tanımı farklı bir kaynak dosya ya da kitaplık olabileceğinden. Bir simge başvurulan ancak hiç tanımlanmış, bağlayıcı çözümlenmemiş dış simgesi hata oluşturur.  
  
LNK2019 neden bazı yaygın sorunlar şunlardır:  
  
-   **Nesne dosyası ya da simgenin tanımını içeren kitaplığı bağlı değil.** Visual Studio'da tanımını içeren kaynak dosyasını yerleşik ve projenizin bir parçası olarak bağlı olduğunu doğrulayın. Komut satırında tanımını içeren kaynak dosyası derlenir ve sonuç nesnesi dosyası bağlamak için dosya listesinde bulunduğunu doğrulayın.  
  
-   **Simgenin bildirim simgesinin tanımı aynı yazıldığından değil.** Büyük/küçük harf ve doğru yazım hem bildirim hem de tanımı kullanılır ve simge yerde kullanılan veya adlı doğrulayın.  
  
-   **Bir işlev kullanılır, ancak parametre sayısı ve türü, işlev tanımının eşleşmiyor.** İşlev bildirimi tanımı eşleşmesi gerekir. İşlev çağrısı bildirimi eşleşip eşleşmediğini ve bildirim tanımı eşleştiğini doğrulayın. Şablon işlevleri çağıran kodu, ayrıca tanımı aynı şablon parametreleri dahil şablon işlev bildirimleri eşleşen sahip olmalıdır. Bir şablon bildirimi uyumsuzluğu örneği için örnek LNK2019e.cpp örnekler bölümünde bakın.  
  
-   **Bir işlev veya değişken bildirilen ancak tanımlı değil.** Bu genellikle bir bildirimi üstbilgi dosyasında var, ancak hiçbir eşleşen tanımı uygulanan anlamına gelir. Üye işlevleri veya statik veri üyeleri için uygulama sınıf kapsamı seçici eklemeniz gerekir. Bir örnek için bkz: [eksik işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md).  
  
-   **Çağırma kuralı işlevi bildirimi ve işlev tanımı arasında farklılık gösterir.** Çağırma Kuralları ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), veya [__vectorcall](../../cpp/vectorcall.md)) düzenlenmiş adı bir parçası olarak kodlanır. Çağırma kuralı aynı olduğundan emin olun.  
  
-   **Bir simge C dosyasında tanımlı, ancak bir C++ dosyasında extern "C" kullanmadan bildirilmedi.** C derlenmiş bir dosyasında tanımlanmış semboller simgeleri kullanmadığınız sürece bir C++ dosyasında bildirilen'den farklı düzenlenmiş adlar sahip bir [extern "C"](../../cpp/using-extern-to-specify-linkage.md) değiştiricisi. Bildirimi her simge derleme bağlantı eşleştiğini doğrulayın. Benzer şekilde, bir C programı tarafından kullanılacak bir C++ dosyasındaki bir simge tanımlarsanız kullanmak `extern "C"` tanımında.  
  
-   **Bir simge statik olarak tanımlanmış ve daha sonra dosyanın dışında başvurulan.** Aksine C c++ [global sabitler](../../error-messages/tool-errors/global-constants-in-cpp.md) sahip `static` bağlantı. Bu sınırlamaya geçici almak için dahil edebileceğiniz `const` başlığındaki başlatmaları dosya ve o üstbilgi .cpp dosyalarınıza eklemek veya değişkeni sabit olmayan hale getirebilir ve sabit başvuru erişmek için kullanabilirsiniz.  
  
-   **Statik bir sınıf üyesi tanımlı değil.** Bir tanım kuralını ihlal veya statik sınıf üyesi benzersiz bir tanım olmalıdır. Satır içi olarak tanımlanan olamaz statik sınıf üyesi tam adını kullanarak bir kaynak dosyasında tanımlanmalıdır. Hiç tanımlanmazsa, bağlayıcı LNK2019 oluşturur.  
  
-   **Derleme bağımlılığına yalnızca çözümdeki bir proje bağımlılık olarak tanımlanır.** Visual Studio'nun önceki sürümleri bu düzeyde bir bağımlılık yeterli. Ancak, Visual Studio 2010 ile başlayarak, Visual Studio gerektirir bir [proje proje başvurusu](/visualstudio/ide/managing-references-in-a-project). Projenizi proje proje başvurusu yoksa, bu bağlayıcı hatası alabilirsiniz. Sorunu gidermek için bir proje proje başvuru ekleyin.  
  
-   **Bir Windows uygulaması için ayarları kullanarak bir konsol uygulaması derleme**. Hata iletisi benzer ise **WinMain başvurulan işlevinde çözümlenmemiş dış simgesi**`function_name`, kullanarak bağlantı **/SUBSYSTEM:CONSOLE** yerine **/SUBSYSTEM:WINDOWS** . Bu ayar hakkında daha fazla bilgi ve Visual Studio'da bu özelliği ayarlamak yönergeler için bkz: [/SUBSYSTEM (alt sistemi belirtin)](../../build/reference/subsystem-specify-subsystem.md).  
  
-   **64-bit kitaplıkları 32 bit kod ya da 32-bit kitaplıkları 64 bit koda bağlantı girişimi.** Kitaplıkları ve kodunuzu bağlantılı nesne dosyaları kodunuzu aynı mimarisine derlenmiş olmalıdır. Doğrulayın, proje başvuruları projenize aynı mimarisine için derlenen kitaplıkları. Emin olun [/Libpath](../../build/reference/libpath-additional-libpath.md) veya **ek kitaplık dizinleri** doğru mimarisi için oluşturulmuş kitaplıklarına bağlayıcı noktaları tarafından kullanılan yolu seçeneği.

-   **Farklı kaynak dosyalarında işlev satır içi kullanım için farklı derleyici seçenekleri kullanın.** Satır içi işlevler kullanılarak .cpp dosyalarında tanımlanan ve işlev satır içi kullanım derleyici seçenekleri farklı kaynak dosyalarında karıştırma LNK2019 neden olabilir. Daha fazla bilgi için bkz: [işlev satır içi kullanım sorunları](../../error-messages/tool-errors/function-inlining-problems.md).  
  
-   **Otomatik değişkenler kendi kapsamı dışında kullanın.** Otomatik (işlev kapsamı) değişkenleri yalnızca o işlevi kapsamında kullanılabilir. Bu değişkenler bildirilemez `extern` ve diğer kaynak dosyalarında kullanılır. Bir örnek için bkz: [otomatik (işlev kapsamı) değişkenleri](../../error-messages/tool-errors/automatic-function-scope-variables.md).  
  
-   **Hedef Mimarinizi desteklenmeyen iç işlevler için bağımsız değişken türleri geçirin veya instrinsic işlevleri çağırın.** Örneğin, bir iç AVX2 kullanır, ancak belirtmeyin [/ARCH:AVX2](../../build/reference/arch-x86.md) derleyici seçeneği derleyici varsayar iç bir dış işlev olduğunu. Satır içi yönerge üretmek yerine derleyici iç aynı ada sahip bir dış sembol yapılan bir çağrı oluşturur. Bağlayıcı, bu eksik işlev tanımı bulmaya çalıştığında LNK2019 oluşturur. Yalnızca iç bilgileri ve hedef Mimarinizi tarafından desteklenen türleri kullanma doğrulayın.  
  
-   **Yerel wchar kullanan kodu karışık\_t değil koduna sahip.** Yapılan Visual C++ 2005'te yapıldığı C++ dili uyumluluğu iş `wchar_t` varsayılan olarak yerel bir tür. Kullanmalısınız [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Visual C++'ın önceki sürümlerini kullanarak derlenmiş kitaplığı ve nesne dosyalarını uyumlu kodu oluşturmak için derleyici seçeneği. Tüm dosyalar aynı kullanılarak derlenmiştir varsa **/Zc:wchar\_t** ayarları, başvuruları uyumlu türlerine değil çözebilir türü. Doğrulayın `wchar_t` kullanılan türleri güncelleştirerek ya da tutarlı kullanarak tüm dosyalardaki kitaplığı ve nesne türleri uyumlu **/ZC: wchar_t** derlediğinizde ayarlar.  
  
## <a name="diagnosis-tools"></a>Tanılama araçları    
  
Bağlayıcı belirli sembol tanımı neden bulunamıyor söylemek zor olabilir. Genellikle, yapı tanımında içeren kodu dahil edilmeyen veya adlar dış sembolleri için derleme seçenekleri farklı oluşturdunuz sorunudur. Yardımcı olabilecek seçenekleri LNK2019 hatasını tanılayın ve çeşitli araçlar vardır.  
  
-   [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) bağlayıcı seçeneği hangi bağlayıcı başvuruları dosyalara belirlemenize yardımcı olabilir. Bu, simgesinin tanımı içeren dosyayı derlemenizde dahil edilip edilmediğini doğrulamanıza yardımcı olabilir.  
  
-   [/EXPORTS](../../build/reference/dash-exports.md) ve [/SYMBOLS](../../build/reference/symbols.md) DUMPBIN yardımcı programını seçenekleri hangi simgeleri .dll ve nesne veya kitaplık dosyalarınızda tanımlanan keşfetmenize yardımcı olabilir. Dışa aktarılan düzenlenmiş bağlayıcı arar adları adları eşleşme donatılmış olduğunu doğrulayın.  
  
-   UNDNAME yardımcı programı eşdeğer ve dış simgesi düzenlenmiş adı gösterebilir.  
## <a name="examples"></a>Örnekler  
  
Burada, hata düzeltme hakkında bilgi ile birlikte bir LNK2019 hatasına neden oluyor kod çeşitli örnekler verilmiştir.  
  
### <a name="a-symbol-is-declared-but-not-defined"></a>Bir simge bildirilmiş ancak tanımlı değil  
  
Bu örnekte, bir dış değişken bildirilen ancak tanımlı değil:  
  
```cpp  
// LNK2019.cpp  
// Compile by using: cl /EHsc /W4 LNK2019.cpp  
// LNK2019 expected  
extern char B[100];   // B is not available to the linker  
int main() {  
   B[0] = ' ';   // LNK2019  
}  
```  
  
Burada bir değişken ve işlev bildirildiğinde olarak başka bir örnek `extern` ancak tanım sağlanır:  
  
```cpp  
// LNK2019c.cpp  
// Compile by using: cl /EHsc LNK2019c.cpp  
// LNK2019 expected  
extern int i;  
extern void g();  
void f() {  
   i++;  
   g();  
}  
int main() {}  
```  
  
Sürece `i` ve `g` tanımlanmış bir yapı içinde bulunan dosyalar LNK2019 bağlayıcı oluşturur. Derleme bir parçası olarak tanımlarını içeren kaynak kodu dosyasının dahil ederek hataları düzeltebilir. Alternatif olarak, .obj dosyaları veya bağlayıcı için tanımları içeren .lib dosyaları geçirebilirsiniz.  
  
### <a name="a-static-data-member-is-declared-but-not-defined"></a>Statik veri üyesi bildirilmiş ancak tanımlı değil  
  
Statik veri üyesi bildirilen ancak tanımlanmamış LNK2019 da oluşabilir. Aşağıdaki örnek LNK2019 oluşturur ve nasıl düzeltileceği gösterir.  
  
```cpp  
// LNK2019b.cpp  
// Compile by using: cl /EHsc LNK2019b.cpp  
// LNK2019 expected  
struct C {  
   static int s;  
};  
  
// Uncomment the following line to fix the error.  
// int C::s;  
  
int main() {  
   C c;  
   C::s = 1;  
}  
```  
  
### <a name="declaration-parameters-do-not-match-definition"></a>Bildirimi parametreleri tanımıyla eşleşmiyor  
  
Şablon işlevleri çağıran kodu şablon işlev bildirimleri eşleşen olması gerekir. Bildirimleri tanımı aynı şablon parametreleri eklemeniz gerekir. Aşağıdaki örnek, bir kullanıcı tarafından tanımlanan işlecinin LNK2019 oluşturur ve nasıl düzeltileceği gösterir.  
  
```cpp  
// LNK2019e.cpp  
// compile by using: cl /EHsc LNK2019e.cpp  
// LNK2019 expected  
#include <iostream>  
using namespace std;  
  
template<class T> class   
Test {  
   // The operator<< declaration does not match the definition below:  
   friend ostream& operator<<(ostream&, Test&);  
   // To fix, replace the line above with the following:  
   // template<typename T> friend ostream& operator<<(ostream&, Test<T>&);  
};  
  
template<typename T>  
ostream& operator<<(ostream& os, Test<T>& tt) {  
   return os;  
}  
  
int main() {  
   Test<int> t;  
   cout << "Test: " << t << endl;   // LNK2019 unresolved external  
}  
```  
  
### <a name="inconsistent-wchart-type-definitions"></a>Tutarsız wchar_t tür tanımları  
  
Bu bir örnek kullanan bir verme sahip DLL oluşturur `WCHAR`, çözümler için `wchar_t`.  
  
```cpp  
// LNK2019g.cpp  
// compile with: cl /EHsc /LD LNK2019g.cpp  
#include "windows.h"  
// WCHAR resolves to wchar_t  
__declspec(dllexport) void func(WCHAR*) {}  
```  
  
Sonraki örnek önceki örnekte DLL kullanır ve kısa * ve WCHAR türleri imzalanmamış olduğundan LNK2019 oluşturur\* aynı değildir.  
  
```cpp  
// LNK2019h.cpp  
// compile by using: cl /EHsc LNK2019h LNK2019g.lib  
// LNK2019 expected  
__declspec(dllimport) void func(unsigned short*);  
  
int main() {  
   func(0);  
}  
```  
  
 Bu hatayı düzeltmek için değiştirme `unsigned short` için `wchar_t` veya `WCHAR`, veya kullanarak LNK2019g.cpp derleme **/Zc:wchar_t-**.  
  
## <a name="additional-resources"></a>Ek kaynaklar  
  
Yığın taşması soru LNK2001 için olası nedenler ve çözümler hakkında daha fazla bilgi için bkz: [tanımsız başvuru/çözümlenmemiş dış simgesi hata nedir ve nasıl ı düzelt?](http://stackoverflow.com/q/12573816/2002113).  

