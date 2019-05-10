---
title: Bağlayıcı Araçları Hatası LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: 0ef0bfd565b8c76816cc1f8a20b1521da238cdfc
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447714"
---
# <a name="linker-tools-error-lnk2019"></a>Bağlayıcı Araçları Hatası LNK2019

Çözümlenmemiş dış Sembol '*sembol*'işlevinde başvurulan'*işlevi*'

Derlenmiş kodunu *işlevi* bir başvurusu veya çağrı yapar *sembol*, ancak herhangi bir bağlayıcıya belirtilen nesne dosyaları ve kitaplıkları sembol tanımlı değil.

Bu hata iletisini önemli hata tarafından izlenir [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md). Tüm LNK2001 ve LNK2019 LNK1120 hatayı düzeltmek için hataları düzeltmeniz gerekir.

## <a name="possible-causes"></a>Olası nedenler

Bu hatayı almak için birçok yolu vardır, ancak bunların tümünü bir işlev ya da bağlayıcı olamaz değişken başvuru içeren *çözmek*, veya bir tanımı için bulunamadı. Bir sembol olmadığında derleyici tanımlayabilirsiniz *bildirilen*, ancak değil zaman *tanımlanan*, tanımı farklı kaynak dosya veya kitaplık içinde olabilir. Bir sembol başvurulan ancak hiçbir zaman tanımlanmış, bağlayıcı çözümlenmemiş dış sembol hata üretir.

LNK2019 neden bazı yaygın sorunlar aşağıda verilmiştir:

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>Nesne dosyası veya sembolün tanımını içeren kitaplık bağlı değil

Visual Studio'da, tanımını içeren kaynak dosyasını oluşturulan ve projenizin bir parçası olarak bağlı olduğunu doğrulayın. Komut satırında tanımını içeren kaynak dosyayı derlenir ve ortaya çıkan nesne dosyası bağlamak için dosya listesinde bulunduğunu doğrulayın.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>Sembolün bildirimi simgesinin tanımı olarak aynı yazılmış

Yazım ve büyük/küçük harf hem bildirim hem de tanımı kullanılır ve her yerde sembol kullanılan çağrılan veya doğrulayın.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>Bir işlev kullanılır, ancak parametre sayısı ve türü, işlev tanımı eşleşmiyor

İşlev bildiriminin, tanımının eşleşmesi gerekir. İşlev çağrısı bildirimi eşleşip eşleşmediğini ve bildirim tanımı eşleştiğini doğrulayın. Şablon işlevleri çağıran kod, ayrıca tanımı olarak aynı şablon parametreleri şablon işlev bildirimleri eşleşen olması gerekir. Şablon bildirimi uyuşmazlığı örneği için örnek LNK2019e.cpp örnekler bölümünde bakın.

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Bir işlev veya değişken bildirimi yapıldı ancak tanımlanmadı

Bu genellikle bir üstbilgi dosyasında bir bildirimi var, ancak hiçbir eşleşen tanımı uygulanan anlamına gelir. Uygulama, üye işlevleri veya statik veri üyeleri için sınıf kapsamı Seçici içermesi gerekir. Bir örnek için bkz. [eksik işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Çağırma kuralı, işlev bildirimi ile işlev tanımı arasında farklıdır

Çağırma Kuralları ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md), veya [__vectorcall](../../cpp/vectorcall.md)) düzenlenmiş adı bir parçası olarak kodlanır. Çağırma kuralı aynı olduğunu doğrulayın.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>Bir sembol C dosyasında tanımlanan, ancak C++ dosyasında extern "C" kullanılarak olmadan bildirilen

C derlenmiş bir dosyada tanımlanan semboller sembolleri kullanmadığınız sürece bir C++ dosyasında bildirilen değerinden farklı düzenlenmiş adlarına sahip bir [extern "C"](../../cpp/using-extern-to-specify-linkage.md) değiştiricisi. Bildirimi derleme bağlantı için her simge eşleştiğini doğrulayın. Benzer şekilde, bir C programının tarafından kullanılacak olan C++ dosyasındaki bir simge tanımlarsanız, kullanın `extern "C"` tanımında.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>Bir sembol statik olarak tanımlanır ve daha sonra dosyanın dışında başvurulan

C++, C, aksine [global sabitler](../../error-messages/tool-errors/global-constants-in-cpp.md) sahip `static` bağlantı. Bu sınırlamaya geçici almak için dahil edebileceğiniz `const` başlatmalarının üstbilgi dosya ve o üstbilgisini .cpp dosyalarınızdan veya değişken sabit olmayan hale getirebilir ve ona erişmek için sabit bir başvuru kullanın.

### <a name="a-static-member-of-a-class-is-not-defined"></a>Bir sınıfın statik bir üye tanımlanmadı

Tek tanım kuralı ihlal veya bir statik sınıf üyesinin benzersiz bir tanımı olmalıdır. Statik sınıf üyesi tanımlı satır içi olamaz, tam olarak nitelenmiş adını kullanarak bir kaynak dosyasında tanımlanmalıdır. Tüm tanımlı değilse, bağlayıcı LNK2019 oluşturur.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Bir derleme bağımlılığı yalnızca çözümdeki proje bağımlılık olarak tanımlanır

Visual Studio'nun önceki sürümlerinde, bu düzeyde bağımlılık yeterli. Ancak, Visual Studio 2010 ile başlayarak, Visual Studio gerektirir bir [projeden projeye başvuru](/visualstudio/ide/managing-references-in-a-project). Projenize bir projeden projeye başvuru yoksa, bu bağlayıcı hatası alabilirsiniz. Bunu düzeltmek için bir projeden projeye başvuru ekleyin.

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Bir Windows uygulaması için ayarları kullanarak bir konsol uygulaması oluşturma

Hata iletisi benzerse **WinMain işlevi başvurulan çözümlenmemiş dış sembol** *işlev_adı*, bağlantıyı kullanarak **/Subsystem: Console** yerine **/SUBSYSTEM:WINDOWS**. Bu ayar hakkında daha fazla bilgi ve bu özellik, Visual Studio'da ayarlamak konusunda yönergeler için bkz. [/Subsystem (alt sistemi belirtin)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>32 bit kod veya 32-bit kitaplıklarına 64-bit kodu 64-bit kitaplıkları bağlantı girişimi

Kitaplıkları ve kodunuzu bağlı nesne dosyaları kodunuz aynı mimarisine derlenmiş olmalıdır. Doğrulayın projenizin başvurularına projeniz gibi aynı mimarisi için derlenen kitaplıkları. Emin [/Libpath](../../build/reference/libpath-additional-libpath.md) veya **ek kitaplık dizinleri** kitaplıklarına doğru bir mimari için bağlayıcı noktaları tarafından kullanılan yolu seçeneği.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Farklı kaynak dosyalarında işlevi satır içi kullanım için farklı derleyici seçenekleri kullanın

Satır içine alınmış işlevleri kullanarak .cpp dosyalarında tanımlanan ve işlev satır içi derleyici seçenekleri farklı kaynak dosyalarında karıştırma LNK2019 neden olabilir. Daha fazla bilgi için [işlevi satır içi kullanım sorunları](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Otomatik değişkenler kendi kapsamı dışında kullanın

Otomatik (işlev kapsamı) değişkenleri yalnızca bu işlevin kapsamında kullanılabilir. Bu değişkenler bildirilemez `extern` ve diğer kaynak dosyalarında kullanılır. Bir örnek için bkz. [otomatik (işlev kapsamı) değişkenleri](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>İnstrinsic işlevlerini çağıran ya da hedef Mimarinizi desteklenmeyen iç işlevler için bağımsız değişken türleri geçirin

Örneğin, bir iç AVX2 kullanıyorsanız, ancak belirtmeyin [/ARCH:AVX2](../../build/reference/arch-x86.md) derleyici seçeneği, derleyici iç bir dış işlev olduğunu varsayar. Derleyici, bir satır içi yönerge üretmek yerine iç olarak aynı ada sahip bir dış sembol için bir çağrı oluşturur. Bağlayıcı, bu eksik işlev tanımı bulmayı dener LNK2019 oluşturur. Yalnızca yapı içi değerler ve hedef Mimarinizi tarafından desteklenen tür kullandığını doğrulayın.

### <a name="you-mix-code-that-uses-native-wchart-with-code-that-doesnt"></a>Yerel wchar kullanan kodu karıştırmak\_olmayan kod ile t

C++Visual Studio 2005 yapılan yapıldığı dil uyumluluğu iş `wchar_t` varsayılan olarak yerel bir tür. Kullanmalısınız [/Zc:wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) Visual Studio'nun önceki sürümleri kullanılarak derlenmiş kitaplığı ve nesne dosyaları ile uyumlu bir kod oluşturmak için derleyici seçeneği. Tüm dosyalar aynı kullanarak derlenen varsa **/Zc:wchar\_t** ayarları, türü başvuruları uyumlu türlerine değil çözebilir. Doğrulayın `wchar_t` tarafından kullanılan türleri güncelleştiriliyor veya tutarlı kullanarak tüm kitaplığı ve nesne dosyalarında türleri uyumlu **/ZC: wchar_t** derlediğinizde ayarları.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Bu hatayı görürseniz, bir üçüncü taraf kitaplığı yapınızın bir parçası olarak yapılandırılmaya çalışılırken kullanmayı [Vcpkg](../../vcpkg.md), Visual C++ paketi yükleyip kitaplığı derleme Yöneticisi. Vcpkg destekleyen çok ve artan [üçüncü taraf kitaplıkların listesini](https://github.com/Microsoft/vcpkg/tree/master/ports)ve tüm başarılı derleme için projenizin bir parçası olarak gerekli bağımlılıkları ve yapılandırma özelliklerini ayarlar. Daha fazla bilgi için bkz. ilgili [Visual C++ blogu](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderin.

## <a name="diagnosis-tools"></a>Tanılama araçları

Bağlayıcının belirli sembol tanımı neden bulunamıyor ayırt etmek zor olabilir. Çoğunlukla sorun, derleme tanımını içeren kod eklemediniz veya düzenlenmiş adları dış sembolleri için seçenekler farklı oluşturmuş olduğunuz derleme olmasıdır. Çeşitli araçları ve yardımcı olabilecek seçenekleri LNK2019 hata tanılayın.

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md) bağlayıcı seçeneği hangi dosyaların bağlayıcı başvuruları belirlemenize yardımcı olabilir. Bu, simgesinin tanımı içeren dosyanın yapınızda içerilip içerilmeyeceğini doğrulamanıza yardımcı olabilir.

- [/EXPORTS](../../build/reference/dash-exports.md) ve [/SEMBOLLER](../../build/reference/symbols.md) seçenekleri **DUMPBIN** yardımcı programı simgelerin, .dll ve nesne veya kitaplık dosyalarında tanımlanan keşfetmenize yardımcı olabilir. Dışarı aktarılan adları eşleşen bağlayıcı arar düzenlenmiş adları düzenlenmiş olduğunu doğrulayın.

- **UNDNAME** yardımcı programı, eşdeğer ve dış sembol düzenlenmiş adını gösterebilir.

## <a name="examples"></a>Örnekler

Birkaç hatayı düzeltme hakkında bilgi ile birlikte bir LNK2019 hatasına neden olur, kod örnekleri aşağıda verilmiştir.

### <a name="a-symbol-is-declared-but-not-defined"></a>Bir sembol bildirimi yapıldı ancak tanımlanmadı

Bu örnekte, bir dış değişken bildirimi yapıldı ancak tanımlanmadı:

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B is not available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

Burada bir değişken ve işlev bildirilir olarak başka bir örnek `extern` ancak hiçbir tanım sağlanır:

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

Sürece `i` ve `g` tanımlanır yapıya dahil dosyaları her birinde LNK2019 bağlayıcı oluşturur. Derlemenin bir parçası tanımları içeren kaynak kodu dosyası dahil ederek hataları düzeltebilirsiniz. Alternatif olarak, .obj dosyaları veya bağlayıcı için tanımları içeren .lib dosyaları geçirebilirsiniz.

### <a name="a-static-data-member-is-declared-but-not-defined"></a>Statik veri üyesi bildirimi yapıldı ancak tanımlanmadı

Statik veri üyesine bildirimli ancak tanımlanmamış olduğunda LNK2019 da meydana gelebilir. Aşağıdaki örnek, LNK2019 oluşturur ve bu sorunun nasıl gösterir.

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

Şablon işlevleri çağıran kod, şablonu işlev bildirimleri eşleşen olması gerekir. Bildirimleri tanımı olarak aynı şablon parametrelerine içermelidir. Aşağıdaki örnek bir kullanıcı tanımlı işlecinin LNK2019 oluşturur ve bu sorunun nasıl gösterir.

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

### <a name="inconsistent-wchart-type-definitions"></a>Tutarsız wchar_t türü tanımları

Bu örnek kullanan bir dışarı aktarma sahip bir DLL oluşturur `WCHAR`, çözümler için `wchar_t`.

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

Sonraki örnek önceki örnekte DLL kullanır ve türleri kısa * ve WCHAR işaretsiz olduğundan LNK2019 oluşturur\* aynı değildir.

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

Bu hatayı düzeltmek için değiştirme `unsigned short` için `wchar_t` veya `WCHAR`, veya LNK2019g.cpp kullanarak derleme **/Zc:wchar_t-**.

## <a name="additional-resources"></a>Ek kaynaklar

Stack Overflow soru LNK2001 olası nedenleri ve çözümleri hakkında daha fazla bilgi için bkz. [tanımlanmamış başvuru/çözümlenmemiş dış sembol hata nedir ve nasıl düzeltirim bunu?](http://stackoverflow.com/q/12573816/2002113).

