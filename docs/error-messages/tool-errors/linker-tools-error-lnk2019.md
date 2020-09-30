---
title: Bağlayıcı Araçları Hatası LNK2019
description: Microsoft Visual Studio bağlayıcı hatası LNK2019 ve C ve C++ kodunda tanılama ve düzeltme hakkında bilgi.
ms.date: 01/15/2020
f1_keywords:
- LNK2019
helpviewer_keywords:
- nochkclr.obj
- LNK2019
- _check_commonlanguageruntime_version
no-loc:
- main
- WinMain
- wmain
- wWinMain
- __cdecl
- __stdcall
- __fastcall
- __vectorcall
- extern
- static
- const
- ARCH
- AVX2
- wchar_t
- VERBOSE
- EXPORTS
- SYMBOLS
- DUMPBIN
- UNDNAME
ms.openlocfilehash: d09e232b934761d138fee7324c462c915d919959
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509742"
---
# <a name="linker-tools-error-lnk2019"></a>Bağlayıcı Araçları Hatası LNK2019

> çözümlenmemiş extern Al simgesi '*symbol*', '*Function*' işlevinde başvuruluyor

*İşlev* için derlenen kod, bir başvuru veya *simgeye*çağrı yapar, ancak bağlayıcı, bağlantı yapılacak kitaplıkların veya nesne dosyalarının hiçbirinde sembol tanımını bulamaz.

Bu hata iletisi, önemli hata [LNK1120](../../error-messages/tool-errors/linker-tools-error-lnk1120.md)tarafından izlenir. Hata LNK1120 düzeltmesini sağlamak için, önce tüm LNK2001 ve LNK2019 hatalarını çözmeniz gerekir.

## <a name="possible-causes"></a>Olası nedenler

Bu hatayı almanın birçok yolu vardır. Hepsi, bağlayıcının *çözememesi*veya bir tanımı bulmak için bir işlev veya değişken başvurusu içerir. Derleyici bir simgenin ne zaman *bildirilmemiş*olduğunu tanımlayabilir, ancak simgenin ne zaman *tanımlanmadığında*bunu söyleyebilir. Bunun nedeni, tanımın farklı bir kaynak dosyasında veya kitaplıkta olabilir. Bir sembolle bahsedildiğinde ancak hiç tanımlanmamışsa, bağlayıcı çözümlenmemiş bir extern sembol hatası oluşturur.

LNK2019 neden olan bazı yaygın sorunlar şunlardır:

### <a name="the-source-file-that-contains-the-definition-of-the-symbol-isnt-compiled"></a>Simgenin tanımını içeren kaynak dosya derlenmiyor

Visual Studio 'da, sembolü tanımlayan kaynak dosyanın projenizin bir parçası olarak derlendiğinden emin olun. Eşleşen bir. obj dosyası için ara derleme çıkış dizinini denetleyin. Kaynak dosya derlenmemişse, Çözüm Gezgini dosya üzerinde sağ tıklayın ve sonra dosyanın özelliklerini denetlemek için **Özellikler** ' i seçin. **Yapılandırma özellikleri**  >  **genel** sayfası, **C/C++ derleyicisinin**bir **öğe türünü** göstermelidir. Komut satırında, tanımı içeren kaynak dosyanın derlendiğinden emin olun.

### <a name="the-object-file-or-library-that-contains-the-definition-of-the-symbol-isnt-linked"></a>Simgenin tanımını içeren nesne dosyası veya kitaplık bağlı değil

Visual Studio 'da, sembol tanımını içeren nesne dosyasının veya kitaplığın projenizin bir parçası olarak bağlı olduğundan emin olun. Komut satırında, bağlanacak dosya listesinin nesne dosyasını veya kitaplığı içerdiğinden emin olun.

### <a name="the-declaration-of-the-symbol-isnt-spelled-the-same-as-the-definition-of-the-symbol"></a>Simgenin bildirimi, simgenin tanımıyla aynı değil

Hem bildirimde hem de tanımda doğru yazımı ve büyük harfleri kullandığınızı, simgenin nerede kullanıldığını veya çağrıldığını doğrulayın.

### <a name="a-function-is-used-but-the-type-or-number-of-the-parameters-dont-match-the-function-definition"></a>Bir işlev kullanıldı, ancak parametrelerin türü veya numarası işlev tanımıyla eşleşmiyor

İşlev bildiriminin tanımıyla eşleşmesi gerekir. İşlev çağrısının bildirimle eşleştiğinden ve bildirimin tanımıyla eşleştiğinden emin olun. Şablon işlevlerini çağıran kodun Ayrıca, tanımıyla aynı şablon parametrelerini içeren eşleşen şablon işlev bildirimlerine sahip olması gerekir. Şablon bildirimi uyuşmazlığının bir örneği için örnekler bölümünde örnek LNK2019e. cpp bölümüne bakın.

### <a name="a-function-or-variable-is-declared-but-not-defined"></a>Bir işlev veya değişken tanımlanmış ancak tanımlanmamış

Başlık dosyasında bir bildirim varsa ancak eşleşen bir tanım uygulanmadığında LNK2019 oluşabilir. Üye işlevleri veya static veri üyeleri için, uygulama sınıf kapsamı seçiciyi içermelidir. Bir örnek için bkz. [eksik Işlev gövdesi veya değişken](../../error-messages/tool-errors/missing-function-body-or-variable.md).

### <a name="the-calling-convention-is-different-between-the-function-declaration-and-the-function-definition"></a>Çağırma kuralı, işlev bildirimi ve işlev tanımı arasında farklıdır

Çağırma kuralları ( [__cdecl](../../cpp/cdecl.md) , [__stdcall](../../cpp/stdcall.md) , [__fastcall](../../cpp/fastcall.md) veya [__vectorcall](../../cpp/vectorcall.md) ), düzenlenmiş adın bir parçası olarak kodlanır. Çağırma kuralının aynı olduğundan emin olun.

### <a name="a-symbol-is-defined-in-a-c-file-but-declared-without-using-no-locextern-c-in-a-c-file"></a>Bir sembol C dosyasında tanımlanır, ancak extern C++ dosyasında "c" kullanılmadan bildirilmiştir

C olarak derlenen bir dosyada tanımlanan semboller, bir [ extern "c"](../../cpp/extern-cpp.md) değiştiricisi kullanmadığınız sürece C++ dosyasında belirtilen sembollere göre farklı düzenlenmiş adlara sahiptir. Bildirimin her bir simgenin derleme bağlantısıyla eşleştiğinden emin olun. Benzer şekilde, bir C programı tarafından kullanılacak C++ dosyasında bir sembol tanımlarsanız, `extern "C"` tanımında kullanın.

### <a name="a-symbol-is-defined-as-no-locstatic-and-then-later-referenced-outside-the-file"></a>Bir sembol olarak tanımlanır static ve daha sonra dosyanın dışında başvurulur

C++ ' da, C 'nin aksine, [genel const ](../../error-messages/tool-errors/global-constants-in-cpp.md) olarak **`static`** bağlantısı vardır. Bu kısıtlamayı aşmak için, **`const`** başlatmalar bir başlık dosyasına dahil edebilir ve bu üstbilgiyi. cpp dosyalarınıza ekleyebilir ya da değişkeni, const const ona erişmek için bir ant başvurusu kullanabilirsiniz.

### <a name="a-no-locstatic-member-of-a-class-isnt-defined"></a>staticBir sınıfın üyesi tanımlı değil

Bir static sınıf üyesinin benzersiz bir tanımı olmalıdır veya tek tanım kuralını ihlal eder. staticSatır içi tanımlanmayan bir sınıf üyesinin, tam adı kullanılarak bir kaynak dosyasında tanımlanması gerekir. Hiç tanımlanmamışsa, bağlayıcı LNK2019 oluşturur.

### <a name="a-build-dependency-is-only-defined-as-a-project-dependency-in-the-solution"></a>Derleme bağımlılığı yalnızca çözümde bir proje bağımlılığı olarak tanımlanır

Visual Studio 'nun önceki sürümlerinde bu bağımlılık düzeyi yeterlidir. Ancak Visual Studio 2010 ' den itibaren, Visual Studio bir [projeden projeye başvuru](/visualstudio/ide/managing-references-in-a-project)gerektirir. Projenizde proje başvurusu yoksa, bu bağlayıcı hatasını alabilirsiniz. Bir projeden projeye başvuru ekleyerek bunu düzeltir.

### <a name="an-entry-point-isnt-defined"></a>Bir giriş noktası tanımlı değil

Uygulama kodu, uygun bir giriş noktası tanımlamalıdır: `main` ya da `wmain` konsol uygulamaları için ve `WinMain` veya `wWinMain` Windows uygulamaları için. Daha fazla bilgi için bkz. [ main işlev ve komut satırı bağımsız değişkenleri](../../cpp/main-function-command-line-args.md) veya [ WinMain işlevi](/windows/win32/api/winbase/nf-winbase-winmain). Özel bir giriş noktası kullanmak için [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneğini belirtin.

### <a name="you-build-a-console-application-by-using-settings-for-a-windows-application"></a>Bir Windows uygulaması için ayarları kullanarak bir konsol uygulaması oluşturursunuz

Hata iletisi, işlev *function_name* ** extern WinMain başvurulan çözümlenmemiş al simgesine** benziyorsa,/Subsystem: **WINDOWS**yerine **/Subsystem: Console** kullanarak bağlayın. Bu ayar hakkında daha fazla bilgi ve Visual Studio 'da bu özelliğin nasıl ayarlanacağı hakkında yönergeler için bkz. [/Subsystem (alt sistemi belirt)](../../build/reference/subsystem-specify-subsystem.md).

### <a name="you-attempt-to-link-64-bit-libraries-to-32-bit-code-or-32-bit-libraries-to-64-bit-code"></a>64 bitlik kitaplıkları 32 bit koda veya 32-bit kitaplıklarına 64-bit koda bağlamayı denediğinizde

Kodunuza bağlı kitaplıklar ve nesne dosyaları, kodunuzla aynı mimari için derlenmelidir. Projenizin başvurduğu kitaplıkların, projenizle aynı mimari için derlendiğinden emin olun. [/Libpath](../../build/reference/libpath-additional-libpath.md) veya **Ek kitaplık dizinleri** özelliğinin doğru mimari için oluşturulmuş kitaplıklara işaret ettiğini doğrulayın.

### <a name="you-use-different-compiler-options-for-function-inlining-in-different-source-files"></a>Farklı kaynak dosyalarında işlev girişi için farklı derleyici seçenekleri kullanın

. Cpp dosyalarında tanımlanmış satır içine alınmış işlevleri kullanma ve farklı kaynak dosyalarındaki işlev satır içi derleyici seçeneklerini karıştırma LNK2019 neden olabilir. Daha fazla bilgi için bkz. [Işlev satır Içi sorunlar](../../error-messages/tool-errors/function-inlining-problems.md).

### <a name="you-use-automatic-variables-outside-their-scope"></a>Otomatik değişkenleri kapsam dışında kullanırsınız

Otomatik (işlev kapsamı) değişkenleri yalnızca söz konusu işlevin kapsamında kullanılabilir. Bu değişkenler **`extern`** diğer kaynak dosyalarında bildirilemez ve kullanılamaz. Bir örnek için bkz. [Otomatik (Işlev kapsamı) değişkenleri](../../error-messages/tool-errors/automatic-function-scope-variables.md).

### <a name="you-call-intrinsic-functions-or-pass-argument-types-to-intrinsic-functions-that-arent-supported-on-your-target-architecture"></a>Hedef mimariniz üzerinde desteklenmeyen iç işlevlere iç işlevleri çağırır veya bağımsız değişken türleri geçirmiş olursunuz

Örneğin, bir AVX2 iç kullanır, ancak [ / ARCH AVX2 :](../../build/reference/arch-x86.md) derleyici seçeneğini belirtmezseniz, derleyici, iç öğenin bir extern Al işlevi olduğunu varsayar. Derleyici, bir satır içi yönerge oluşturmak yerine, extern iç öğe ile aynı ada sahip bir al simgesine çağrı oluşturur. Bağlayıcı bu eksik işlevin tanımını bulmaya çalıştığında, LNK2019 oluşturur. Yalnızca hedef mimariniz tarafından desteklenen iç bilgileri ve türleri kullandığınızdan emin olun.

### <a name="you-mix-code-that-uses-native-no-locwchar_t-with-code-that-doesnt"></a>wchar_tYerel kullanan kodu,

Visual Studio 2005 ' de yapılan C++ dil uyumluluğu çalışması, **`wchar_t`** Varsayılan olarak yerel bir tür yaptı. Tüm dosyalar aynı **/Zc: wchar_t ** ayarları kullanılarak derlenmezse, tür başvuruları uyumlu türlere çözümlenmeyebilir. **`wchar_t`** Tüm kitaplık ve nesne dosyalarındaki türlerin uyumlu olduğundan emin olun. Bir typedef 'ten güncelleştirin **`wchar_t`** ya da derlerken tutarlı **/Zc: wchar_t ** ayarlarını kullanın.

## <a name="third-party-library-issues-and-vcpkg"></a>Üçüncü taraf kitaplığı sorunları ve vcpkg

Derlemeniz kapsamında bir üçüncü taraf kitaplığı yapılandırmaya çalışırken bu hatayı görürseniz, kitaplığı yüklemek ve derlemek için [vcpkg](../../build/vcpkg.md)'Yi bir C++ paket yöneticisi olarak kullanmayı düşünün. vcpkg [, üçüncü taraf kitaplıkların](https://github.com/Microsoft/vcpkg/tree/master/ports)büyük ve büyüyen bir listesini destekler. Projenin bir parçası olarak başarılı derlemeler için gereken tüm yapılandırma özelliklerini ve bağımlılıklarını ayarlar.

## <a name="diagnosis-tools"></a>Tanılama araçları

Bazen bağlayıcının belirli bir sembol tanımını bulamamasını söylemek zordur. Genellikle bu sorun, derlemenize tanımı içeren kodu eklemediniz. Ya da, yapı seçenekleri al sembolleri için farklı düzenlenmiş adlar oluşturmuş extern . LNK2019 hatalarını tanılamanıza yardımcı olabilecek çeşitli araçlar ve seçenekler vardır.

- [/VERBOSE](../../build/reference/verbose-print-progress-messages.md)Bağlayıcı seçeneği, bağlayıcının başvurduğu dosyaları belirlemenize yardımcı olabilir. Bu seçenek, simgenin tanımını içeren dosyanın derlemenize dahil olup olmadığını doğrulamanıza yardımcı olabilir.

- [/EXPORTS](../../build/reference/dash-exports.md) [/SYMBOLS](../../build/reference/symbols.md) Yardımcı programın ve seçenekleri, **DUMPBIN** . dll 'niz ve nesne veya kitaplık dosyalarınızda hangi simgelerin tanımlandığını keşfetmenize yardımcı olabilir. Verdiğiniz düzenlenmiş adların bağlayıcının aradığı düzenlenmiş adlarla eşleştiğinden emin olun.

- **UNDNAME** Yardımcı program, extern düzenlenmiş bir ad için eşdeğer, yaygın olmayan al sembolünü gösterebilir.

## <a name="examples"></a>Örnekler

Hatanın nasıl düzeltileceğiyle ilgili bilgilerle birlikte LNK2019 hatasına neden olan kodun birkaç örneği aşağıda verilmiştir.

### <a name="a-symbol-is-declared-but-not-defined"></a>Bir sembol tanımlanmış ancak tanımlanmamış

Bu örnekte, bir extern Al değişkeni tanımlanmış ancak tanımlanmamış:

```cpp
// LNK2019.cpp
// Compile by using: cl /EHsc /W4 LNK2019.cpp
// LNK2019 expected
extern char B[100];   // B isn't available to the linker
int main() {
   B[0] = ' ';   // LNK2019
}
```

Bir değişken ve işlevin olarak bildirildiği ancak tanım sağlanmadığından başka bir örnek aşağıda verilmiştir **`extern`** :

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

`i`Ve `g` yapı içinde yer alan dosyalardan birinde tanımlanmadıysa, bağlayıcı LNK2019 oluşturur. Derlemenin bir parçası olarak tanımları içeren kaynak kodu dosyasını ekleyerek hataları giderebilirsiniz. Alternatif olarak, bağlayıcıya tanımları içeren. obj dosyalarını veya. lib dosyalarını geçirebilirsiniz.

### <a name="a-no-locstatic-data-member-is-declared-but-not-defined"></a>Bir static veri üyesi tanımlanmış ancak tanımlanmamış

LNK2019, bir static veri üyesi bildirildiğinde ancak tanımlanmadığında da oluşabilir. Aşağıdaki örnek LNK2019 oluşturur ve nasıl düzeltileceğini gösterir.

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

### <a name="declaration-parameters-dont-match-the-definition"></a>Bildirim parametreleri tanımıyla eşleşmiyor

Şablon işlevlerini çağıran kodun eşleşen şablon işlevi bildirimleri olmalıdır. Bildirimlerin tanımıyla aynı şablon parametrelerini içermesi gerekir. Aşağıdaki örnek, Kullanıcı tanımlı bir operatör üzerinde LNK2019 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
// LNK2019e.cpp
// compile by using: cl /EHsc LNK2019e.cpp
// LNK2019 expected
#include <iostream>
using namespace std;

template<class T> class
Test {
   // The operator<< declaration doesn't match the definition below:
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

### <a name="inconsistent-no-locwchar_t-type-definitions"></a>Tutarsız wchar_t tür tanımları

Bu örnek `WCHAR` , tarafından ' ı ' a çözümlenen bir dışarı aktarma içeren BIR DLL oluşturur **`wchar_t`** .

```cpp
// LNK2019g.cpp
// compile with: cl /EHsc /LD LNK2019g.cpp
#include "windows.h"
// WCHAR resolves to wchar_t
__declspec(dllexport) void func(WCHAR*) {}
```

Sonraki örnek, önceki örnekteki DLL 'yi kullanır ve türler için LNK2019 oluşturur `unsigned short*` `WCHAR*` .

```cpp
// LNK2019h.cpp
// compile by using: cl /EHsc LNK2019h LNK2019g.lib
// LNK2019 expected
__declspec(dllimport) void func(unsigned short*);

int main() {
   func(0);
}
```

Bu hatayı onarmak için **`unsigned short`** **`wchar_t`** `WCHAR` **/Zc: wchar_t - **kullanarak LNK2019g. cpp olarak değiştirin veya derleyin.

## <a name="additional-resources"></a>Ek kaynaklar

LNK2001 için olası nedenler ve çözümler hakkında daha fazla bilgi için, [tanımsız bir başvuru/çözümlenmemiş extern Al sembol hatası nedir ve nasıl düzeltirım](https://stackoverflow.com/q/12573816/2002113)Stack Overflow sorusuna bakın.
