---
title: Derleyici Uyarısı (Düzey 3) C4996 | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d618ace9d922daabecf908c76a319e89a9fdedcc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46094188"
---
# <a name="compiler-warning-level-3-c4996"></a>Derleyici Uyarısı (Düzey 3) C4996

Derleyici, kullanım dışı bir bildirimi ile karşılaşıldı. **Bu her zaman kasıtlı bir ileti yazar kitaplığı veya dahil edilen üst bilgi dosyası, kullanım dışı sembol sonuçları anlama olmadan kullanmamanız gerekir, uyarıdır.** Gerçek bir uyarı iletisi kullanımdan kaldırma değiştiricisi veya öznitelik bildiriminin sitede tarafından belirtilir.

C çalışma zamanı kitaplığı ve standart kitaplık, ancak kapsamlı bir liste tarafından oluşturulan bazı yaygın C4996 iletileri şunlardır. Bağlantıları izleyin veya bu sorunu düzeltmek için veya uyarıyı devre dışı bırakmak için için okumaya devam edin.

- [Bu öğe için POSIX ad kullanım dışı bırakılmıştır. Bunun yerine ISO C ve C++ uyumluluğunu adını kullanın: *new_name*. Ayrıntılar için çevrimiçi yardıma bakın.](#posix-function-names)

- [Bu işlev veya değişken güvenli olmayabilir. Kullanmayı *safe_version* yerine. Kullanımdan kaldırma devre dışı bırakmak için \_CRT\_güvenli\_Hayır\_uyarıları.  Ayrıntılar için çevrimiçi yardıma bakın.](#unsafe-crt-library-functions)

- [' std::*işlev_adı*::\_işaretlenmemiş\_yineleyiciler::\_Deprecate' çağrısı için std::*işlev_adı*bu çağrı olmayabilecek parametrelerle kullanır geçirilen değerlerin doğru olduğunu kontrol etmek için çağırıcı. Bu uyarıyı devre dışı bırakmak için -D_SCL_SECURE_NO_WARNINGS kullanın. Visual C++ 'Denetlenen Yineleyicilerin' kullanmak belgelere bakın.](#unsafe-standard-library-functions)

- [Bu işlev veya değişkeni kitaplığı veya işletim sisteminin daha yeni işlevler tarafından geçersiz kılınan. Kullanmayı *NEW_ITEM* yerine. Ayrıntılar için çevrimiçi yardıma bakın.](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>Sebep

C4996, derleyici bir işlevi veya olarak işaretlenmiş değişken karşılaştığında gerçekleşir [kullanım dışı](../../cpp/deprecated-cpp.md) kullanarak bir `__declspec(deprecated)` değiştiricisi, veya bir işlev, sınıf üyesi veya C ++ 14 sahip typedef erişmeye çalıştığınızda [ \[ \[kullanım dışı\] \] ](../../cpp/attributes.md) özniteliği. Kullanabileceğiniz `__declspec(deprecated)` değiştiricisi veya `[[deprecated]]` kendiniz kitaplıkları veya üst bilgi dosyaları, istemcilerinize kullanım dışı bırakılan İşlevler, değişkenler, üye veya tür tanımları hakkında uyarmak için özniteliği.

## <a name="remarks"></a>Açıklamalar

Birçok işlevleri, üye işlevleri, şablon işlevleri ve Visual Studio'da kitaplıklarındaki genel değişkenleri olarak işaretlenen *kullanım dışı*. Bunlar farklı tercih edilen bir ada sahip, güvenli olmayan sahip olabilir veya daha güvenli bir değişken, çünkü bu işlevler kullanım dışı veya artık kullanılmıyor olabilir. Önerilen kullanım dışı işlev ya da genel değişken yerine birçok kullanımdan kaldırma iletileri içerir.

Bu sorunu gidermek için genellikle bunun yerine önerilen güvenli veya güncelleştirilmiş işlevler ve genel değişkenler kullanmak için kodunu değiştirmeniz tavsiye ederiz. Var olan işlevler veya değişkenleri taşınabilirlik nedenlerle kullanmanız gerekiyorsa, uyarı kapatılabilir.

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>Sorunu düzeltme olmadan uyarıyı kapatmak için

Uyarı için belirli bir kod satırı kullanarak devre dışı bırakabilirsiniz [uyarı](../../preprocessor/warning.md) pragması `#pragma warning(suppress : 4996)`. Ayrıca uyarı bir dosya içinde warning pragması kullanılarak kapatabilirsiniz `#pragma warning(disable : 4996)`.

Uyarı genel komut satırı derlemelerinde kullanarak kapatabilirsiniz **/wd4996** komut satırı seçeneği.

Visual Studio IDE'deki tüm proje için bir uyarı kapatmak için:

- Açık **özellik sayfaları** projeniz için iletişim. Özellik sayfaları iletişim kutusu kullanma hakkında daha fazla bilgi için bkz: [özellik sayfaları](../../ide/property-pages-visual-cpp.md).
- Seçin **yapılandırma özellikleri**, **C/C++**, **Gelişmiş** sayfası.
- Düzen **belirli uyarıları devre dışı** eklemek üzere özellik `4996`. Seçin **Tamam** yaptığınız değişiklikleri uygulamak için.

Önişlemci makroları, bazı sınıflar kitaplıklarında kullanılır kullanımdan kaldırma uyarıları kapatmak için de kullanabilirsiniz. Bu makrolar, aşağıda açıklanmıştır.

Visual Studio'da önişlemci makrosu tanımlamak için:

- Açık **özellik sayfaları** projeniz için iletişim. Özellik sayfaları iletişim kutusu kullanma hakkında daha fazla bilgi için bkz: [özellik sayfaları](../../ide/property-pages-visual-cpp.md).
- Genişletin **yapılandırma özellikleri > C/C++ > önişlemci**.
- İçinde **önişlemci tanımları** özelliği, makro adını ekleyin. Seçin **Tamam** kaydedin ve projenizi yeniden derleyin.

Ekleme gibi bir satır yalnızca belirli kaynak dosyalarında bir makro tanımlamak için `#define EXAMPLE_MACRO_NAME` önce bir üstbilgi dosyası içeren herhangi bir satır.

## <a name="specific-c4996-messages"></a>Belirli C4996 iletileri

Bazı ortak kaynakları C4996 uyarıları ve hataları aşağıda verilmiştir.

### <a name="posix-function-names"></a>POSIX işlev adları

**Bu öğe için POSIX ad kullanım dışı bırakılmıştır. Bunun yerine ISO C ve C++ uyumluluğunu adını kullanın:** *new_name*. **Ayrıntılar için çevrimiçi yardıma bakın.**

Microsoft, bazı POSIX işlevler C99 ve C ++ 03 kuralları uygulama tanımlı genel işlev adları için uygun olması için CRT olarak yeniden adlandırıldı. Yalnızca özgün POSIX adları kullanım dışı bırakılmıştır, İşlevler kendilerini. Çoğu durumda, bir standart uyumluluğunu adı oluşturmak için POSIX işlevi adı bir alt çizgi eklendi. Derleyici, kullanımdan kaldırılma uyarısı orijinal işlev adı için sorunları ve tercih edilen adından da anlaşılacağı.

Bu sorunu gidermek için genellikle önerilen işlev adlarını kullanmanız için kodunu değiştirmeniz tavsiye ederiz. Ancak, güncelleştirilmiş Microsoft'a özgü adlarıdır. Taşınabilirlik nedeniyle var olan işlev adlarını kullanmanız gerekiyorsa, bu uyarılar kapatabilirsiniz. POSIX işlevleri altında özgün adlarını Kitaplığı'nda yine kullanılabilir durumdadır.

Bu işlevler için kullanımdan kaldırılma uyarıları kapatmak için önişlemci makrosu tanımlama  **\_CRT\_NONSTDC\_Hayır\_uyarıları**. Bu makro komut satırında seçeneğini ekleyerek tanımlayabilirsiniz `/D_CRT_NONSTDC_NO_WARNINGS`.


### <a name="unsafe-crt-library-functions"></a>Güvenli olmayan CRT kitaplık işlevleri

**Bu işlev veya değişken güvenli olmayabilir. Kullanmayı** *safe_version* **yerine. Kullanımdan kaldırma devre dışı bırakmak için \_CRT\_güvenli\_Hayır\_uyarıları.  Ayrıntılar için çevrimiçi yardıma bakın.**

Bazı CRT ve standart C++ Kitaplığı işlevleri ve genel öğeleri daha güvenli sürümleri yerine Microsoft kullanım dışı. Çoğu durumda, denetlenmemiş okuma veya yazma erişimi ciddi güvenlik sorunlarına yol açabilir arabellekleri, kullanım dışı bırakılan işlevler sağlar. Derleyici, bu işlevler için kullanımdan kaldırılma uyarı verir ve tercih edilen işlevini önerir.

Bu sorunu gidermek için işlev veya değişkeni kullanmanızı öneririz *safe_version* yerine. Bir arabellek üzerine yazma için mümkün değildir veya kodunuzu ve, oluşmasına overread taşınabilirlik nedeniyle kod değiştiremezsiniz doğruladıysanız, uyarıyı devre dışı kapatabilirsiniz.

CRT'deki bu işlevler için kullanımdan kaldırılma uyarıları kapatmak için tanımladığınız  **\_CRT\_güvenli\_Hayır\_uyarıları**. Kullanım dışı genel değişkenler ilgili uyarıları kapatmak için tanımladığınız  **\_CRT\_güvenli\_Hayır\_uyarıları\_GLOBALS**. Bu kullanım dışı bırakılan işlevler ve genel öğeleri hakkında daha fazla bilgi için bkz. [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md) ve [güvenli kitaplıklar: C++ Standart Kitaplığı](../../standard-library/safe-libraries-cpp-standard-library.md).

### <a name="unsafe-standard-library-functions"></a>Güvenli standart kitaplık işlevleri

__' std::__*işlev_adı*__::\_işaretlenmemiş\_yineleyiciler::\_Deprecate' çağrısı için std::__*işlev_adı* **olmayabilecek parametrelerle geçirilen değerlerin doğru olduğunu kontrol etmek için arayan bu çağrı kullanır. Bu uyarıyı devre dışı bırakmak için -D kullanın.\_SCL\_güvenli\_Hayır\_uyarıları. Visual C++ 'Denetlenen Yineleyicilerin' kullanmak belgelere bakın.**

Belirli C++ Standart kitaplığı şablonu işlev parametreleri doğruluk denetlemez, çünkü hata ayıklama yapılarında bu uyarı görüntülenir. Çoğu durumda, yeterli bilgi işleve kapsayıcı sınırlarının denetlemek için kullanılabilir olmadığından veya yineleyiciler yanlış işleviyle kullanılan çünkü budur. Programlarınızda önemli güvenlik açıkları, kaynak olabileceğinden bu uyarı bu işlev kullanım belirlemenize yardımcı olur. Daha fazla bilgi için [Checked Iterators](../../standard-library/checked-iterators.md).

Örneğin, bu uyarıyı hata ayıklama modunda görünür bir öğe işaretçisi için geçirirseniz `std::copy` düz dizi yerine. Bu sorunu gidermek için uygun şekilde bildirilen bir dizi kitaplığı dizi alanları kontrol edin ve sınır denetimi yapmak için kullanın.

```cpp
// C4996_copyarray.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_copyarray.cpp
#include <algorithm>

void example(char const * const src) {
    char dest[1234];
    char * pdest3 = dest + 3;
    std::copy(src, src + 42, pdest3); // C4996
    std::copy(src, src + 42, dest);   // OK, copy can tell that dest is 1234 elements
}
```

Birçok standart kitaplığı algoritmaları, C ++ 14'te "ikili" aralık"sürümleri için güncelleştirildi. İkili aralığı sürümlerini kullanıyorsanız, ikinci aralığın gerekli sınırların sağlar:

```cpp
// C4996_containers.cpp
// compile with: cl /c /W4 /D_DEBUG C4996_containers.cpp
#include <algorithm>

bool example(
    char const * const left,
    const size_t leftSize,
    char const * const right,
    const size_t rightSize)
{
    bool result = false;
    result = std::equal(left, left + leftSize, right); // C4996
    // To fix, try this form instead:
    // result = std::equal(left, left + leftSize, right, right + rightSize); // OK
    return result;
}
```

Bu örnek, standart kitaplık, yineleyici kullanımı denetlemek için kullanılabilir çeşitli yöntemlerle gösterir ve ne zaman denetlenmeyen kullanım tehlikeli olabilir:

```cpp
// C4996_standard.cpp
// compile with: cl /EHsc /W4 /MDd C4996_standard.cpp
#include <algorithm>
#include <array>
#include <iostream>
#include <iterator>
#include <numeric>
#include <string>
#include <vector>

using namespace std;

template <typename C> void print(const string& s, const C& c) {
    cout << s;

    for (const auto& e : c) {
        cout << e << " ";
    }

    cout << endl;
}

int main()
{
    vector<int> v(16);
    iota(v.begin(), v.end(), 0);
    print("v: ", v);

    // OK: vector::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    vector<int> v2(16);
    transform(v.begin(), v.end(), v2.begin(), [](int n) { return n * 2; });
    print("v2: ", v2);

    // OK: back_insert_iterator is marked as checked in debug mode
    // (i.e. an overrun is impossible)
    vector<int> v3;
    transform(v.begin(), v.end(), back_inserter(v3), [](int n) { return n * 3; });
    print("v3: ", v3);

    // OK: array::iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    array<int, 16> a4;
    transform(v.begin(), v.end(), a4.begin(), [](int n) { return n * 4; });
    print("a4: ", a4);

    // OK: Raw arrays are checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    // NOTE: This applies only when raw arrays are
    // given to C++ Standard Library algorithms!
    int a5[16];
    transform(v.begin(), v.end(), a5, [](int n) { return n * 5; });
    print("a5: ", a5);

    // WARNING C4996: Pointers cannot be checked in debug mode
    // (i.e. an overrun triggers undefined behavior)
    int a6[16];
    int * p6 = a6;
    transform(v.begin(), v.end(), p6, [](int n) { return n * 6; });
    print("a6: ", a6);

    // OK: stdext::checked_array_iterator is checked in debug mode
    // (i.e. an overrun triggers a debug assertion)
    int a7[16];
    int * p7 = a7;
    transform(v.begin(), v.end(),
        stdext::make_checked_array_iterator(p7, 16),
        [](int n) { return n * 7; });
    print("a7: ", a7);

    // WARNING SILENCED: stdext::unchecked_array_iterator
    // is marked as checked in debug mode, but it performs no checking,
    // so an overrun triggers undefined behavior
    int a8[16];
    int * p8 = a8;
    transform( v.begin(), v.end(),
        stdext::make_unchecked_array_iterator(p8),
        [](int n) { return n * 8; });
    print("a8: ", a8);
}
```

Kod bu uyarıyı tetikleyen standart kitaplığı işlevlerinde hata taşması olamaz doğruladıysanız bu uyarıyı devre dışı bırakmak isteyebilirsiniz. Bu işlevler için uyarıları kapatmak için tanımladığınız  **\_SCL\_güvenli\_Hayır\_uyarıları**.

### <a name="checked-iterators-enabled"></a>İşaretli yineleyiciler etkin

C4996 ile derleme yaparken denetlenen bir yineleyiciye kullanmadığınız takdirde da gerçekleşebilir `_ITERATOR_DEBUG_LEVEL` 1 veya 2 tanımlanmış. Hata ayıklama modu yapıları için varsayılan olarak 2 ve perakende derlemeleri için 0 için ayarlanır. Bkz: [Checked Iterators](../../standard-library/checked-iterators.md) daha fazla bilgi için.

```cpp
// C4996_checked.cpp
// compile with: /EHsc /W4 /MDd C4996_checked.cpp
#define _ITERATOR_DEBUG_LEVEL 2

#include <algorithm>
#include <iterator>

using namespace std;
using namespace stdext;

int main() {
    int a[] = { 1, 2, 3 };
    int b[] = { 10, 11, 12 };
    copy(a, a + 3, b + 1);   // C4996
    // try the following line instead:
    // copy(a, a + 3, checked_array_iterator<int *>(b, 3));   // OK
}
```

### <a name="unsafe-mfc-or-atl-code"></a>Güvenli olmayan MFC veya ATL kodu

Güvenlik nedenleriyle kullanım dışı bırakılan MFC veya ATL işlevlerini kullanırsanız C4996 da meydana gelebilir.

Bu sorunu gidermek için güncelleştirilmiş işlevler kullanmayı kodunuzu değiştirmeniz önerilir.

Bu uyarıları bastırmak hakkında daha fazla bilgi için bkz. [_afx_secure_no_warnıngs](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings).

### <a name="obsolete-crt-functions-and-variables"></a>Eski CRT işlevleri ve değişkenler

**Bu işlev veya değişkeni kitaplığı veya işletim sisteminin daha yeni işlevler tarafından geçersiz kılınan. Kullanmayı** *NEW_ITEM* **yerine. Ayrıntılar için çevrimiçi yardıma bakın.**

Bazı kitaplık işlevleri ve genel değişkenler eski olarak kullanım dışı bırakılmıştır. Bu işlevler ve değişkenler Kitaplığı'nın gelecek sürümünde kaldırılabilir. Derleyici, bu öğeler için kullanımdan kaldırılma uyarı verir ve tercih edilen alternatif önerir.

Bu sorunu gidermek için önerilen işlev veya değişken kullanmak için kodunu değiştirmeniz önerilir.

Bu öğeler için kullanımdan kaldırılma uyarıları kapatmak için tanımladığınız  **\_CRT\_kullanımdan KALKTI\_Hayır\_uyarıları**. Daha fazla bilgi için kullanım dışı işlev veya değişkeni belgelerine bakın.

### <a name="marshalling-errors-in-clr-code"></a>CLR kod hatalarını taşıma

C4996, CLR sıralama kitaplığını kullandığınızda da meydana gelebilir. Bu durumda, C4996 bir uyarı değil hatadır. Bu hata oluşur [marshal_as](../../dotnet/marshal-as.md) gerektiren iki veri türleri arasında dönüştürme yapmak bir [; marshal_context Class](../../dotnet/marshal-context-class.md). Sıralama Kitaplığı bir dönüştürmeyi desteklemediğinde de bu hatayı alabilir. Sıralama Kitaplığı hakkında daha fazla bilgi için bkz. [Overview of Marshaling c++](../../dotnet/overview-of-marshaling-in-cpp.md).

Sıralama Kitaplığı dönüştürmek için bir bağlam gerektirdiğinden bu örneği C4996 oluşturur. bir `System::String` için bir `const char *`.

```cpp
// C4996_Marshal.cpp
// compile with: /clr
// C4996 expected
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = marshal_as<const char*>( message );
   return 0;
}
```

## <a name="example-user-defined-deprecated-function"></a>Örnek: Kullanıcı tanımlı kullanım dışı işlev

Artık belirli işlevlerin kullanılmasını önerdiğiniz çağıranlar uyar için kendi kodunuzda kullanım dışı özniteliği kullanabilirsiniz. Bu örnekte, C4996 şirket kullanım dışı işlev bildirildiği satır ve işlevin üzerinde kullanıldığı satır için oluşturulur.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

__declspec(deprecated) void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
