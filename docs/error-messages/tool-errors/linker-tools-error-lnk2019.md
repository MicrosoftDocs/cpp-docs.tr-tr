---
title: Bağlayıcı Araçları Hatası LNK2019
ms.date: 12/15/2017
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
ms.openlocfilehash: 3c4e5578c7b0f496feb4d40933af624f462a31d2
ms.sourcegitcommit: 680a155cc44a38f88bb2b1c5a1ef6dcb7141c011
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/10/2019
ms.locfileid: "72252628"
---
# <a name="linker-tools-error-lnk2019"></a>Bağlayıcı Araçları Hatası LNK2019

çözümlenmemiş dış sembol '*symbol*', '*Function*' işlevinde başvuruluyor

*İşlev* için derlenen kod, bir başvuru veya *simgeye*çağrı yapar, ancak bu sembol bağlayıcı için belirtilen kitaplıkların veya nesne dosyalarının hiçbirinde tanımlı değildir.

Bu hata iletisi, önemli hata [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)tarafından izlenir. Hata LNK1120 'yi onarmak için tüm LNK2001 ve LNK2019 hatalarını çözmeniz gerekir.

## <a name="possible-causes"></a>Olası nedenler

Bu hatayı almanın pek çok yolu vardır, ancak hepsi bağlayıcının *çözememesi*veya bir tanımı bulmak için bir işlev veya değişken başvurusu içerir. Derleyici, bir simgenin ne zaman *bildirilmemiş*olduğunu ancak *tanımlanmadığında*, tanım farklı bir kaynak dosyasında veya kitaplıkta olabileceğinden tanımlayabilir. Bir sembolle bahsedildiğinde ancak hiç tanımlanmamışsa, bağlayıcı çözümlenmemiş bir dış sembol hatası oluşturur.

LNK2019 neden olan bazı yaygın sorunlar şunlardır:

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-is-not-linked"></a>Simgenin tanımını içeren nesne dosyası veya kitaplık bağlı değil

Visual Studio 'da, tanımı içeren kaynak dosyanın projenizin bir parçası olarak oluşturulup bağlandığını doğrulayın. Komut satırında, tanımı içeren kaynak dosyanın derlendiğini ve elde edilen nesne dosyasının bağlanacak dosya listesine eklendiğinden emin olun.

### <a name="the-declaration-of-the-symbol-is-not-spelled-the-same-as-the-definition-of-the-symbol"></a>Simgenin bildirimi, simgenin tanımıyla aynı değil

Doğru Yazımın ve büyük harflerin hem bildirimde hem de tanımda ve simgenin kullanıldığı veya çağrıldığı her yerde kullanıldığını doğrulayın.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-do-not-match-the-function-definition"></a>Bir işlev kullanıldı, ancak parametrelerin türü veya numarası işlev tanımıyla eşleşmiyor

İşlev bildiriminin tanımıyla eşleşmesi gerekir. İşlev çağrısının bildirimle eşleştiğini ve bildirimin tanımıyla eşleştiğini doğrulayın. Şablon işlevlerini çağıran kodun Ayrıca, tanımıyla aynı şablon parametrelerini içeren eşleşen şablon işlev bildirimlerine sahip olması gerekir. Şablon bildirimi uyuşmazlığının bir örneği için örnekler bölümünde örnek LNK2019e. cpp bölümüne bakın.

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Bir işlev veya değişken tanımlanmış ancak tanımlanmamış

Bu genellikle bir başlık dosyasında bir bildirimin bulunduğu ancak eşleşen bir tanım uygulandığı anlamına gelir. Üye işlevleri veya statik veri üyeleri için, uygulama sınıf kapsamı seçiciyi içermelidir. Bir örnek için bkz. [eksik Işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Çağırma kuralı, işlev bildirimi ve işlev tanımı arasında farklıdır

Çağırma kuralları ([__cdecl](../../cpp/cdecl.md), [__stdcall](../../cpp/stdcall.md), [__fastcall](../../cpp/fastcall.md)veya [__vectorcall](../../cpp/vectorcall.md)), düzenlenmiş adın bir parçası olarak kodlanır. Çağırma kuralının aynı olduğunu doğrulayın.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-extern-c-in-a-c-file"></a>Bir sembol C dosyasında tanımlanır, ancak bir C++ dosyada extern "C" kullanılmadan bildirilmiştir

C olarak derlenen bir dosyada tanımlanan semboller, [extern bir "C"](../../cpp/using-extern-to-specify-linkage.md) değiştiricisi kullanmadığınız sürece C++ dosyada belirtilen sembollere göre farklı düzenlenmiş adlara sahiptir. Bildirimin her bir simgenin derleme bağlantısıyla eşleştiğini doğrulayın. Benzer şekilde, bir C++ dosyada C programı tarafından kullanılacak bir sembol tanımlarsanız, tanımda `extern "C"` ' i kullanın.

### <a name="a-symbol-is-defined-as-static-and-then-later-referenced-outside-the-file"></a>Bir sembol statik olarak tanımlanır ve daha sonra dosyanın dışında başvurulur

' C++De, C 'nin aksine, [Global sabitlerin](../../error-messages/tool-errors/global-constants-in-cpp.md) `static` bağlantısı vardır. Bu kısıtlamayı aşmak için, `const` başlatmaları bir üst bilgi dosyasına dahil edebilir ve bu üstbilgiyi. cpp dosyalarınıza ekleyebilir ya da değişkeni sabit olmayan hale getirebilirsiniz ve buna erişmek için sabit bir başvuru kullanabilirsiniz.

### <a name="a-static-member-of-a-class-is-not-defined"></a>Bir sınıfın statik üyesi tanımlı değil

Statik sınıf üyesinin benzersiz bir tanımı olmalıdır veya tek tanım kuralını ihlal eder. Satır içi tanımlanmayan bir statik sınıf üyesi, tam nitelikli adı kullanılarak bir kaynak dosyasında tanımlanmalıdır. Hiç tanımlanmamışsa, bağlayıcı LNK2019 oluşturur.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Derleme bağımlılığı yalnızca çözümde bir proje bağımlılığı olarak tanımlanır

Visual Studio 'nun önceki sürümlerinde bu bağımlılık düzeyi yeterlidir. Ancak Visual Studio 2010 ' den itibaren, Visual Studio bir [projeden projeye başvuru](/visualstudio/ide/managing-references-in-a-project)gerektirir. Projenizde proje başvurusu yoksa, bu bağlayıcı hatasını alabilirsiniz. Bir projeden projeye başvuru ekleyerek bunu düzeltir.

### <a name="an-entry-point-is-not-defined"></a>Bir giriş noktası tanımlı değil

Uygulama kodu uygun bir giriş noktası tanımlamalıdır: konsol uygulamaları için `main` veya `wmain`, Windows uygulamaları için `WinMain` veya `wWinMain`. Daha fazla bilgi için bkz. [Main: program başlatması](../../cpp/main-program-startup.md) veya [WinMain işlevi](/windows/win32/api/winbase/nf-winbase-winmain). Özel bir giriş noktası kullanmak için [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini belirtin. 

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Bir Windows uygulaması için ayarları kullanarak bir konsol uygulaması oluşturursunuz

Hata iletisi **çözümlenmemiş dış sembol function_name ' de başvuruluyorsa**,/Subsystem: **WINDOWS**yerine **/Subsystem: Console** komutunu kullanarak bağlayın. Bu ayar hakkında daha fazla bilgi ve Visual Studio 'da bu özelliğin nasıl ayarlanacağı hakkında yönergeler için bkz. [/Subsystem (alt sistemi belirt)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>64 bitlik kitaplıkları 32 bit koda veya 32-bit kitaplıklarına 64-bit koda bağlamayı denediğinizde

Kodunuza bağlı kitaplıklar ve nesne dosyaları, kodunuzla aynı mimari için derlenmelidir. Projenizin başvurduğu kitaplıkların, projenizle aynı mimari için derlendiğini doğrulayın. Bağlayıcı tarafından kullanılan [/LIBPATH](../../build/reference/libpath-additional-libpath.md) veya **Ek kitaplık dizinleri** yol seçeneğinin doğru mimari için oluşturulan kitaplıklara işaret ettiğini doğrulayın.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Farklı kaynak dosyalarında işlev girişi için farklı derleyici seçenekleri kullanın

. Cpp dosyalarında tanımlanmış satır içine alınmış işlevleri kullanma ve farklı kaynak dosyalarındaki işlev satır içi derleyici seçeneklerini karıştırma LNK2019 neden olabilir. Daha fazla bilgi için bkz. [Işlev satır Içi sorunlar](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Otomatik değişkenleri kapsam dışında kullanırsınız

Otomatik (işlev kapsamı) değişkenleri yalnızca söz konusu işlevin kapsamında kullanılabilir. Bu değişkenler, `extern` olarak bildirilemez ve diğer kaynak dosyalarında kullanılabilir. Bir örnek için bkz. [Otomatik (Işlev kapsamı) değişkenleri](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-instrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-are-not-supported-on-your-target-architecture"></a>Instrinsic işlevlerini çağırır veya bağımsız değişken türlerini hedef mimariniz üzerinde desteklenmeyen iç işlevlere geçirin

Örneğin, bir AVX2 iç kullanır, ancak [/Arch: AVX2](../../build/reference/arch-x86.md) derleyici seçeneğini belirtmezseniz, derleyici, iç öğenin bir dış işlev olduğunu varsayar. Bir satır içi yönerge oluşturmak yerine, derleyici, iç ile aynı ada sahip bir dış simgeye çağrı oluşturur. Bağlayıcı bu eksik işlevin tanımını bulmaya çalıştığında, LNK2019 oluşturur. Yalnızca hedef mimariniz tarafından desteklenen iç bilgileri ve türleri kullandığınızı doğrulayın.

### <a name="you-mix-code-that-uses-native-wchar_t-with-code-that-doesnt"></a>Yerel wchar @ no__t-0T kullanan kodu,

C++Visual Studio 2005 ' de yapılan, varsayılan olarak yerel bir tür olan `wchar_t` ' de gerçekleştirilen dil uyumluluğu işleri. Visual Studio 'nun önceki sürümleri kullanılarak derlenen kitaplık ve nesne dosyalarıyla uyumlu kod oluşturmak için [/Zc: wchar_t-](../../build/reference/zc-wchar-t-wchar-t-is-native-type.md) derleyici seçeneğini kullanmanız gerekir. Tüm dosyalar aynı **/Zc: wchar @ no__t-1T** ayarları kullanılarak derlenmezse, tür başvuruları uyumlu türlere çözümlenmeyebilir. Tüm kitaplık ve nesne dosyalarındaki `wchar_t` türlerinin uyumlu olduğunu, kullanılan türleri güncelleştirerek veya derlerken tutarlı **/Zc: wchar_t** ayarlarını kullanarak doğrulayın.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve Vcpkg

Derlemeniz kapsamında bir üçüncü taraf kitaplığı yapılandırmaya çalışırken bu hatayı görürseniz, kitaplığı yüklemek ve oluşturmak için [Vcpkg](../../vcpkg.md), Visual C++ Package Manager 'ı kullanmayı düşünün. Vcpkg, [üçüncü taraf kitaplıkların](https://github.com/Microsoft/vcpkg/tree/master/ports)büyük ve artan bir listesini destekler ve projenizin bir parçası olarak başarılı derlemeler için gereken tüm yapılandırma özelliklerini ve bağımlılıklarını ayarlar. Daha fazla bilgi için ilgili [görsel C++ blog](https://blogs.msdn.microsoft.com/vcblog/2016/09/19/vcpkg-a-tool-to-acquire-and-build-c-open-source-libraries-on-windows/) gönderisine bakın.

## <a name="diagnosis-tools"></a>Tanılama araçları

Bağlayıcının belirli bir sembol tanımını neden bulamadığına söylemek zor olabilir. Genellikle sorunu, derlemenize tanımı içeren kodu dahil etmeniz veya yapı seçeneklerinde dış semboller için farklı düzenlenmiş adlar oluşturulmamasından kaynaklanır. Bir LNK2019 hatasını tanılamanıza yardımcı olabilecek çeşitli araçlar ve seçenekler vardır.

- [/Verbose](../../build/reference/verbose-print-progress-messages.md) bağlayıcı seçeneği, bağlayıcının başvurduğu dosyaları belirlemenize yardımcı olabilir. Bu, simgenin tanımını içeren dosyanın derlemenize dahil olup olmadığını doğrulamanıza yardımcı olabilir.

- **Dumpbin** yardımcı programının [/dışarı aktarmalar](../../build/reference/dash-exports.md) ve [/Symbols](../../build/reference/symbols.md) seçenekleri,. dll ve nesne veya kitaplık dosyalarınızda hangi simgelerin tanımlandığını keşfetmenize yardımcı olabilir. Verdiğiniz düzenlenmiş adların, bağlayıcının aradığı düzenlenmiş adlarla eşleştiğinden emin olun.

- **Undname** yardımcı programı, düzenlenmiş bir ad için, fark edilmemiş dış sembolü gösterebilir.

## <a name="examples"></a>Örnekler

Hatanın nasıl düzeltileceğiyle ilgili bilgilerle birlikte LNK2019 hatasına neden olan kodun birkaç örneği aşağıda verilmiştir.

### <a name="a-symbol-is-declared-but-not-defined"></a>Bir sembol tanımlanmış ancak tanımlanmamış

Bu örnekte, bir dış değişken bildirildiği halde tanımlı değil:

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B is not available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

Bir değişken ve işlevin `extern` olarak bildirildiği, ancak hiçbir tanım sağlanmadığından başka bir örnek aşağıda verilmiştir:

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

@No__t-0 ve `g`, derlemede bulunan dosyalardan birinde tanımlanmamışsa, bağlayıcı LNK2019 oluşturur. Derlemenin bir parçası olarak tanımları içeren kaynak kodu dosyasını ekleyerek hataları giderebilirsiniz. Alternatif olarak, bağlayıcıya tanımları içeren. obj dosyalarını veya. lib dosyalarını geçirebilirsiniz.

### <a name="a-static-data-member-is-declared-but-not-defined"></a>Statik bir veri üyesi tanımlanmış ancak tanımlanmamış

LNK2019, statik bir veri üyesi bildirildiğinde ancak tanımlanmadığında da gerçekleşebilir. Aşağıdaki örnek LNK2019 oluşturur ve nasıl düzeltileceğini gösterir.

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

### <a name="declaration-parameters-do-not-match-definition"></a>Bildirim parametreleri tanımıyla eşleşmiyor

Şablon işlevlerini çağıran kodun eşleşen şablon işlevi bildirimleri olmalıdır. Bildirimlerin tanımıyla aynı şablon parametrelerini içermesi gerekir. Aşağıdaki örnek, Kullanıcı tanımlı bir operatör üzerinde LNK2019 oluşturur ve nasıl düzeltileceğini gösterir.

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

### <a name="inconsistent-wchar_t-type-definitions"></a>Tutarsız wchar_t tür tanımları

Bu örnek, `wchar_t` ' i çözümleyen `WCHAR` kullanan dışarı aktarma içeren bir DLL oluşturur.

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

Sonraki örnek, önceki örnekteki DLL 'yi kullanır ve imzasız Short * ve WCHAR @ no__t-0 türleri aynı olmadığından LNK2019 oluşturur.

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

Bu hatayı onarmak için `unsigned short` ' ı `wchar_t` veya `WCHAR` olarak değiştirin ya da **/Zc: wchar_t-** kullanarak LNK2019g. cpp öğesini derleyin.

## <a name="additional-resources"></a>Ek kaynaklar

LNK2001 için olası nedenler ve çözümler hakkında daha fazla bilgi için, [tanımsız bir başvuru/çözümlenmemiş dış sembol hatası nedir ve nasıl giderebilirim?](https://stackoverflow.com/q/12573816/2002113)sorusuna Stack Overflow bakın.

