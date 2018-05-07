---
title: Bağlayıcı araçları hatası LNK2019 | Microsoft Docs
ms.custom: ''
ms.date: 12/15/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2019
dev_langs:
- C++
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4323e5f8357da046db7a9403d7c575dfdde566b6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2019"></a>Bağlayıcı Araçları Hatası LNK2019

Çözümlenmemiş dış simgesi '*simgesi*'işlevinde başvurulan'*işlevi*'

Derlenmiş kodunu *işlevi* bir başvuru veya çağrı yapar *simgesi*, ancak bu simge herhangi bir bağlayıcıya belirtilen nesne dosyaları ve kitaplıkları tanımlanmadı.

Bu hata iletisini önemli hatası tarafından izlenir [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). LNK1120 hatayı düzeltmek için tüm LNK2001 ve LNK2019 hataları düzeltmeniz gerekir.

## <a name="possible-causes"></a>Olası nedenler

Bu hatayı almak için birçok yolu vardır, ancak bunların tümünün bir işlevi veya bağlayıcı olamaz değişkeni bir başvuru içeren *gidermek*, veya için bir tanım bulunamıyor. Bir simge olmadığında derleyici tanımlayabilirsiniz *bildirilen*, ancak ne zaman onu değil *tanımlanan*, tanımı farklı bir kaynak dosya ya da kitaplık olabileceğinden. Bir simge başvurulan ancak hiç tanımlanmış, bağlayıcı çözümlenmemiş dış simgesi hata oluşturur.

LNK2019 neden bazı yaygın sorunlar şunlardır:

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>Nesne dosyası ya da simgenin tanımını içeren kitaplığı bağlı değil

Visual Studio'da tanımını içeren kaynak dosyasını yerleşik ve projenizin bir parçası olarak bağlı olduğunu doğrulayın. Komut satırında tanımını içeren kaynak dosyası derlenir ve sonuç nesnesi dosyası bağlamak için dosya listesinde bulunduğunu doğrulayın.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>Simgenin bildirim simgesinin tanımı aynı yazıldığından değil

Büyük/küçük harf ve doğru yazım hem bildirim hem de tanımı kullanılır ve simge yerde kullanılan veya adlı doğrulayın.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>Bir işlev kullanılır, ancak parametre sayısı ve türü, işlev tanımının eşleşmiyor

İşlev bildirimi tanımı eşleşmesi gerekir. İşlev çağrısı bildirimi eşleşip eşleşmediğini ve bildirim tanımı eşleştiğini doğrulayın. Şablon işlevleri çağıran kodu, ayrıca tanımı aynı şablon parametreleri dahil şablon işlev bildirimleri eşleşen sahip olmalıdır. Bir şablon bildirimi uyumsuzluğu örneği için örnek LNK2019e.cpp örnekler bölümünde bakın.

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Bir işlev veya değişken bildirilen ancak tanımlı değil

Bu genellikle bir bildirimi üstbilgi dosyasında var, ancak hiçbir eşleşen tanımı uygulanan anlamına gelir. Üye işlevleri veya statik veri üyeleri için uygulama sınıf kapsamı seçici eklemeniz gerekir. Bir örnek için bkz: [eksik işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Çağırma kuralı işlevi bildirimi ve işlev tanımı arasında farklı.

Çağırma Kuralları ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), veya [__vectorcall](../../cpp/vectorcall.md)) düzenlenmiş adı bir parçası olarak kodlanır. Çağırma kuralı aynı olduğundan emin olun.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>Bir simge C dosyasında tanımlı, ancak bir C++ dosyasında extern "C" kullanmadan bildirilen

C derlenmiş bir dosyasında tanımlanmış semboller simgeleri kullanmadığınız sürece bir C++ dosyasında bildirilen'den farklı düzenlenmiş adlar sahip bir [extern "C"](../../cpp/using-extern-to-specify-linkage.md) değiştiricisi. Bildirimi her simge derleme bağlantı eşleştiğini doğrulayın. Benzer şekilde, bir C programı tarafından kullanılacak bir C++ dosyasındaki bir simge tanımlarsanız kullanmak `extern "C"` tanımında.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>Bir simge statik olarak tanımlanmış ve daha sonra dosyanın dışında başvurulan

Aksine C c++ [global sabitler](../../error-messages/tool-errors/global-constants-in-cpp.md) sahip `static` bağlantı. Bu sınırlamaya geçici almak için dahil edebileceğiniz `const` başlığındaki başlatmaları dosya ve o üstbilgi .cpp dosyalarınıza eklemek veya değişkeni sabit olmayan hale getirebilir ve sabit başvuru erişmek için kullanabilirsiniz.

### <a name="a-static-member-of-a-class-is-not-defined"></a>Statik bir sınıf üyesi tanımlı değil

Bir tanım kuralını ihlal veya statik sınıf üyesi benzersiz bir tanım olmalıdır. Satır içi olarak tanımlanan olamaz statik sınıf üyesi tam adını kullanarak bir kaynak dosyasında tanımlanmalıdır. Hiç tanımlanmazsa, bağlayıcı LNK2019 oluşturur.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Derleme bağımlılığına yalnızca çözümdeki bir proje bağımlılık olarak tanımlanır

Visual Studio'nun önceki sürümleri bu düzeyde bir bağımlılık yeterli. Ancak, Visual Studio 2010 ile başlayarak, Visual Studio gerektirir bir [proje proje başvurusu](/visualstudio/ide/managing-references-in-a-project). Projenizi proje proje başvurusu yoksa, bu bağlayıcı hatası alabilirsiniz. Sorunu gidermek için bir proje proje başvuru ekleyin.

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Bir Windows uygulaması için ayarları kullanarak bir konsol uygulaması oluşturma

Hata iletisi benzer ise **WinMain başvurulan işlevinde çözümlenmemiş dış simgesi** *işlev_adı*, kullanarak bağlantı **/SUBSYSTEM:CONSOLE** yerine **/SUBSYSTEM:WINDOWS**. Bu ayar hakkında daha fazla bilgi ve Visual Studio'da bu özelliği ayarlamak yönergeler için bkz: [/SUBSYSTEM (alt sistemi belirtin)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>64-bit kitaplıkları 32 bit kod ya da 32-bit kitaplıkları 64 bit koda bağlantı girişimi

Kitaplıkları ve kodunuzu bağlantılı nesne dosyaları kodunuzu aynı mimarisine derlenmiş olmalıdır. Doğrulayın, proje başvuruları projenize aynı mimarisine için derlenen kitaplıkları. Emin olun [/Libpath](../../build/reference/libpath-additional-libpath.md) veya **ek kitaplık dizinleri** doğru mimarisi için oluşturulmuş kitaplıklarına bağlayıcı noktaları tarafından kullanılan yolu seçeneği.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Farklı kaynak dosyalarında işlev satır içi kullanım için farklı derleyici seçenekleri kullanın

Satır içi işlevler kullanılarak .cpp dosyalarında tanımlanan ve işlev satır içi kullanım derleyici seçenekleri farklı kaynak dosyalarında karıştırma LNK2019 neden olabilir. Daha fazla bilgi için bkz: [işlev satır içi kullanım sorunları](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Otomatik değişkenler kendi kapsamı dışında kullanın

Otomatik (işlev kapsamı) değişkenleri yalnızca o işlevi kapsamında kullanılabilir. Bu değişkenler bildirilemez `extern` ve diğer kaynak dosyalarında kullanılır. Bir örnek için bkz: [otomatik (işlev kapsamı) değişkenleri](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>İnstrinsic işlevleri çağırmak ya da hedef Mimarinizi desteklenmeyen iç işlevler için bağımsız değişken türleri geçirin

Örneğin, bir iç AVX2 kullanır, ancak belirtmeyin [/ARCH:AVX2](../../build/reference/arch-x86.md) derleyici seçeneği derleyici varsayar iç bir dış işlev olduğunu. Satır içi yönerge üretmek yerine derleyici iç aynı ada sahip bir dış sembol yapılan bir çağrı oluşturur. Bağlayıcı, bu eksik işlev tanımı bulmaya çalıştığında LNK2019 oluşturur. Yalnızca iç bilgileri ve hedef Mimarinizi tarafından desteklenen türleri kullanma doğrulayın.

### <a name="you-mix-code-that-uses-native-wchart-with-code-that-doesnt"></a>Yerel wchar kullanan kodu karışık\_değil koduyla t

Yapılan Visual C++ 2005'te yapıldığı C++ dili uyumluluğu iş `wchar_t` varsayılan olarak yerel bir tür. Kullanmalısınız [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Visual C++'ın önceki sürümlerini kullanarak derlenmiş kitaplığı ve nesne dosyalarını uyumlu kodu oluşturmak için derleyici seçeneği. Tüm dosyalar aynı kullanılarak derlenmiştir varsa **/Zc:wchar\_t** ayarları, başvuruları uyumlu türlerine değil çözebilir türü. Doğrulayın `wchar_t` kullanılan türleri güncelleştirerek ya da tutarlı kullanarak tüm dosyalardaki kitaplığı ve nesne türleri uyumlu **/ZC: wchar_t** derlediğinizde ayarlar.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bir üçüncü taraf kitaplık yapınızın bir parçası yapılandırmak çalışırken bu hatayı görürseniz, kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paket yüklemek ve kitaplık yapı yöneticisi,. Büyük ve artan Vcpkg desteklemektedir [üçüncü taraf kitaplıkların bir listesi](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derlemeler için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için ilgili bkz [Visual C++ Blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="diagnosis-tools"></a>Tanılama araçları

Bağlayıcı belirli sembol tanımı neden bulunamıyor söylemek zor olabilir. Genellikle, yapı tanımında içeren kodu dahil edilmeyen veya adlar dış sembolleri için derleme seçenekleri farklı oluşturdunuz sorunudur. Yardımcı olabilecek seçenekleri LNK2019 hatasını tanılayın ve çeşitli araçlar vardır.

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) bağlayıcı seçeneği hangi bağlayıcı başvuruları dosyalara belirlemenize yardımcı olabilir. Bu, simgesinin tanımı içeren dosyayı derlemenizde dahil edilip edilmediğini doğrulamanıza yardımcı olabilir.

- [/EXPORTS](../../build/reference/dash-exports.md) ve [/SYMBOLS](../../build/reference/symbols.md) seçeneklerini **DUMPBIN** yardımcı programı hangi simgeleri .dll ve nesne veya kitaplık dosyalarınızda tanımlanan keşfetmenize yardımcı olabilir. Dışa aktarılan düzenlenmiş bağlayıcı arar adları adları eşleşme donatılmış olduğunu doğrulayın.

- **UNDNAME** yardımcı programı, eşdeğer ve dış simgesi düzenlenmiş adı gösterebilir.

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

