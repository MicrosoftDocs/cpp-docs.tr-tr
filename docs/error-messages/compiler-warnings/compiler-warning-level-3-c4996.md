---
title: Derleyici Uyarısı (Düzey 3) C4996 | Microsoft Docs
ms.custom: ''
ms.date: 11/17/2017
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C4996
dev_langs:
- C++
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
caps.latest.revision: 34
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c0c41ce646f635e32f6e1e34d0361c738d0bb6b0
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="compiler-warning-level-3-c4996"></a>Derleyici Uyarısı (Düzey 3) C4996

Derleyici kullanım dışı bir bildirimi ile karşılaşıldı. **Bu uyarı her zaman bir kasıtlı kitaplık veya içerdiği üstbilgi dosyası, kullanım dışı simgenin sonuçları anlama olmadan kullanmaması gerektiğini yazarı iletisidir.** Gerçek uyarı iletisi kullanımdan değiştiricisi veya öznitelik bildirimi sitede belirtilir. 

C çalışma zamanı kitaplığı ve standart kitaplığı, ancak kapsamlı bir liste tarafından oluşturulan bazı ortak C4996 iletileri şunlardır. Bağlantıları izleyin veya yolları sorunu düzeltin veya uyarıyı kapatmak için okumaya devam edin. 

- [Bu öğe için POSIX ad kullanım dışıdır. Bunun yerine, ISO C ve C++ uyumluluğunu adını kullanın: *new_name*. Ayrıntılar için çevrimiçi yardıma bakın.](#posix-function-names)

- [Bu işlev veya değişken güvenli olmayabilir. Kullanmayı *safe_version* yerine. Kullanımdan kaldırma devre dışı bırakmak için \_CRT\_güvenli\_Hayır\_uyarıları.  Ayrıntılar için çevrimiçi yardıma bakın.](#unsafe-crt-library-functions)

- [' std::*işlev_adı*::\_işaretlenmemiş\_yineleyiciler::\_Deprecate' çağrısı std::*işlev_adı*bu çağrıyı - olmayabilecek parametrelerle kullanır geçirilen değerlerin doğru olup olmadığını denetleyin çağırıcı. Bu uyarıyı devre dışı bırakmak için -D_SCL_SECURE_NO_WARNINGS kullanın. Visual C++ 'İşaretli yineleyiciler' kullanımı konusunda belgelerine bakın](#unsafe-standard-library-functions)

- [Bu işlev veya değişken kitaplığı veya işletim sistemi daha yeni işlevselliğe göre kılınan. Kullanmayı *NEW_ITEM* yerine. Ayrıntılar için çevrimiçi yardıma bakın.](#obsolete-crt-functions-and-variables)

## <a name="cause"></a>Sebep

C4996 derleyici bir işlevi veya olarak işaretlenmiş değişken karşılaştığında oluşur [kullanım dışı](../../cpp/deprecated-cpp.md) kullanarak bir `__declspec(deprecated)` değiştiricisi, veya bir işlev, sınıf üyesi veya C ++ 14 sahip typedef erişmeye çalıştığınızda [ \[ \[kullanım dışı\] \] ](../../cpp/attributes.md) özniteliği. Kullanabileceğiniz `__declspec(deprecated)` değiştiricisi veya `[[deprecated]]` kendiniz kitaplıkları ya da istemcilerinizin kullanım dışı bırakılan İşlevler, değişkenleri, üyeleri veya tür tanımları hakkında uyarmak için üstbilgi dosyaları özniteliği.

## <a name="remarks"></a>Açıklamalar

Birçok işlevleri, üye işlevleri, şablon işlevleri ve genel değişkenler kitaplıklarında Visual Studio'da olarak işaretlenmiş *kullanım dışı*. Bunlar farklı bir tercih edilen ada sahip, güvenli olmayan sahip olabilir veya daha güvenli bir değişken çünkü bu işlevler kullanım dışı veya geçersiz olabilir. Birçok kullanımdan iletileri kullanım dışı işlev veya genel değişkeni için önerilen yenileme içerir.

Bu sorunu gidermek için genellikle önerilen daha güvenli veya güncelleştirilmiş işlevler ve genel değişkenler kullanmayı kodunuzu değiştirmek öneririz. Var olan işlevler veya değişkenleri taşınabilirlik nedenlerle kullanmanız gerekiyorsa, uyarıyı devre dışı.

### <a name="to-turn-the-warning-off-without-fixing-the-issue"></a>Sorunu düzeltmek olmadan uyarıyı kapatmak için

Belirli bir kod satırı için uyarı kullanarak devre dışı bırakabilirsiniz [uyarı](../../preprocessor/warning.md) pragma, `#pragma warning(suppress : 4996)`. Ayrıca uyarı dosyanın içinde uyarı pragma kullanarak kapatabilirsiniz `#pragma warning(disable : 4996)`.

Uyarıyı genel olarak komut satırı derlemeleri kullanarak kapatabilirsiniz **/wd4996** komut satırı seçeneği.

Visual Studio IDE içinde tüm proje için uyarı devre dışı bırakmak için:

- Açık **özellik sayfaları** projeniz için iletişim kutusu. Özellik sayfaları iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz: [özellik sayfaları](../../ide/property-pages-visual-cpp.md).
- Seçin **yapılandırma özellikleri**, **C/C++**, **Gelişmiş** sayfası.
- Düzen **belirli uyarıları devre dışı** eklemek üzere özellik `4996`. Seçin **Tamam** değişikliklerinizi uygulamak için.

Önişlemci makroları, belirli sınıflar kitaplıklarda kullanılan kullanımdan kaldırma uyarıları devre dışı bırakmak için de kullanabilirsiniz. Bu makroları aşağıda açıklanmıştır.

Visual Studio'da önişlemci makrosu tanımlamak için:

- Açık **özellik sayfaları** projeniz için iletişim kutusu. Özellik sayfaları iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz: [özellik sayfaları](../../ide/property-pages-visual-cpp.md).
- Genişletme **yapılandırma özellikleri > C/C++ > önişlemci**.
- İçinde **önişlemci tanımları** özelliği, makro adını ekleyin. Seçin **Tamam** kaydedin ve projenizi yeniden derleyin.

Yalnızca belirli bir kaynak dosyalarında makro tanımlamak için bir satır gibi eklemek `#define EXAMPLE_MACRO_NAME` üstbilgi dosyası içeren herhangi bir satırı önce.

## <a name="specific-c4996-messages"></a>Belirli C4996 iletileri

Ortak kaynakları C4996 uyarı ve hataların bazıları aşağıda verilmiştir.

### <a name="posix-function-names"></a>POSIX işlev adları

**Bu öğe için POSIX ad kullanım dışıdır. Bunun yerine, ISO C ve C++ uyumluluğunu adını kullanın:** *new_name*. **Ayrıntılar için çevrimiçi yardıma bakın.**

Microsoft, bazı C99 ve C ++ 03 kuralları uygulama tanımlı genel işlev adları için uygun olması için CRT POSIX işlevlerde yeniden adlandırıldı. Yalnızca özgün POSIX adlarını kullanım dışı bırakılmıştır, işlevleri kendilerini. Çoğu durumda, bir standart uyumluluğunu adı oluşturmak için POSIX işlev adı önde gelen bir alt çizgi eklendi. Derleyici özgün işlev adı için bir kullanımdan kaldırma uyarısı sorunları ve tercih edilen ad önerir.

Bu sorunu gidermek için genellikle önerilen işlev adlarını kullanmanız için kodunu değiştirmeniz öneririz. Ancak, güncelleştirilmiş Microsoft özgü adlardır. Taşınabilirlik nedenleri için varolan işlev adlarını kullanmanız gerekiyorsa, bu uyarıların devre dışı bırakabilirsiniz. POSIX işlevleri özgün adlarını altında Kitaplığı'nda yine kullanılabilir durumdadır.

Bu işlevler için kullanımdan kaldırma uyarıları kapatmak için önişlemci makrosu tanımlama  **\_CRT\_NONSTDC\_Hayır\_uyarıları**. Komut satırında bu makrosu seçeneğini ekleyerek tanımlayabilirsiniz `/D_CRT_NONSTDC_NO_WARNINGS`.


### <a name="unsafe-crt-library-functions"></a>Güvenli olmayan CRT kitaplık işlevleri

 **Bu işlev veya değişken güvenli olmayabilir. Kullanmayı** *safe_version* **yerine. Kullanımdan kaldırma devre dışı bırakmak için \_CRT\_güvenli\_Hayır\_uyarıları.  Ayrıntılar için çevrimiçi yardıma bakın.**

 Bazı CRT ve C++ Standart Kitaplığı işlevler ve genel öğeleri daha güvenli sürümleri lehinde Microsoft kullanım dışı. Çoğu durumda, kullanım dışı bırakılan işlevler denetlenmeyen okuma veya yazma erişimi ciddi güvenlik sorunlarına yol açabilir arabellekleri izin verir. Derleyici kullanımdan kaldırma uyarısı bu işlevler için sorunları ve tercih edilen işlevi önerir.

 Bu sorunu gidermek için işlev veya değişken kullanmanızı öneririz *safe_version* yerine. Arabellek üzerine yazma için mümkün değildir veya kodunuzu ve siz gerçekleşmesi için overread taşınabilirlik nedeniyle kodunu değiştiremezsiniz doğruladıysanız, uyarıyı devre dışı kapatabilirsiniz.
 
 CRT'deki bu işlevler için kullanımdan kaldırma uyarıları kapatmak için tanımlamak  **\_CRT\_güvenli\_Hayır\_uyarıları**. Kullanım dışı genel değişkenler hakkında uyarılar devre dışı bırakmak üzere tanımlamak  **\_CRT\_güvenli\_Hayır\_uyarıları\_GLOBALS**. Bu kullanım dışı bırakılan işlevler ve genel öğeleri hakkında daha fazla bilgi için bkz: [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md) ve [güvenli kitaplıklar: C++ Standart Kitaplığı](../../standard-library/safe-libraries-cpp-standard-library.md).

### <a name="unsafe-standard-library-functions"></a>Güvenli standart kitaplığı işlevleri

__' std::__*işlev_adı*__::\_işaretlenmemiş\_yineleyiciler::\_Deprecate' çağrısı std::__*işlev_adı* **- olmayabilecek parametrelerle geçirilen değerlerin doğru olduğunu kontrol etmek için arayan bu çağrıyı kullanır. Bu uyarıyı devre dışı bırakmak için -D kullanmak\_SCL\_güvenli\_Hayır\_uyarıları. Visual C++ 'İşaretli yineleyiciler' kullanımı konusunda belgelerine bakın**

Belirli C++ Standart kitaplığı şablon işlevleri parametreleri doğruluğunu denetleyin değil çünkü hata ayıklama derlemelerinde bu uyarı görüntülenir. Çoğu durumda, kapsayıcı sınırları denetlemek için işlev için yeterli bilgi bulunmadığından ya da yineleyiciler yanlış işlev ile kullanılan nedeni budur. Ciddi güvenlik açıklarını programınızdaki kaynağı olabileceğinden bu uyarı bu işlevi kullanımları belirlemenize yardımcı olur. Daha fazla bilgi için bkz: [işaretli yineleyiciler](../../standard-library/checked-iterators.md).

Örneğin, bir öğe işaretçisine başarılı olursa hata ayıklama modunda bu uyarı görüntülenir `std::copy` düz bir dizi yerine. Bu sorunu gidermek için uygun şekilde bildirilen dizi kitaplığı dizi kapsam denetleyin ve sınırları denetimi yapmak için kullanın.

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

Birkaç standart kitaplığı algoritmalar, C ++ 14'te "çift aralığı" sürümleri için güncelleştirildi. Çift aralığı sürümlerini kullanıyorsanız, ikinci aralığı denetimi gerekli sınırları sağlar:

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

Bu örnek, standart kitaplığı, yineleyici kullanımını denetlemek için kullanılabilecek çeşitli yöntemlerle gösterir ve ne zaman denetlenmeyen kullanım tehlikeli olabilir:

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

Kodunuzu bu uyarıyı tetikleyen standart kitaplığı işlevlerinde hata taşması olamaz doğruladıysanız bu uyarıyı devre dışı bırakmak isteyebilirsiniz. Bu işlevler için uyarıları kapatmak için tanımlamak  **\_SCL\_güvenli\_Hayır\_uyarıları**.

### <a name="checked-iterators-enabled"></a>Etkin işaretli yineleyiciler

C4996 da gerçekleşebilir ile derleme yapılırken denetlenen yineleyici kullanmayın `_ITERATOR_DEBUG_LEVEL` 1 veya 2 olarak tanımlanmış. Hata ayıklama modu yapıları için varsayılan olarak 2 ve 0 perakende yapılar için ayarlanır. Bkz: [işaretli yineleyiciler](../../standard-library/checked-iterators.md) daha fazla bilgi için.

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

### <a name="unsafe-mfc-or-atl-code"></a>Güvenli olmayan MFC ya da ATL kodu

Güvenlik nedenleriyle kullanım dışı bırakılan MFC ya da ATL işlevleri kullanırsanız C4996 da oluşabilir.

Bu sorunu gidermek için güncelleştirilmiş işlevler kullanmayı kodunu değiştirmeniz önerilir.

Bu uyarıları bastırma hakkında daha fazla bilgi için bkz: [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings).

### <a name="obsolete-crt-functions-and-variables"></a>Artık kullanılmayan CRT işlevleri ve değişkenler

**Bu işlev veya değişken kitaplığı veya işletim sistemi daha yeni işlevselliğe göre kılınan. Kullanmayı** *NEW_ITEM* **yerine. Ayrıntılar için çevrimiçi yardıma bakın.**

Bazı kitaplığı işlevler ve genel değişkenler kullanımdan kaldırılmış olarak kullanım dışı bırakılmıştır. Bu işlevleri ve değişkenler kitaplığı gelecek bir sürümünde kaldırılabilir. Derleyici kullanımdan kaldırma uyarısı bu öğeler için sorunları ve tercih edilen alternatif önerir.

Bu sorunu gidermek için önerilen işlev veya değişken kullanmak için kodunu değiştirmeniz önerilir.

Bu öğeler için kullanımdan kaldırma uyarıları kapatmak için tanımlamak  **\_CRT\_kullanımdan KALKTI\_Hayır\_uyarıları**. Daha fazla bilgi için kullanım dışı işlev veya değişken belgelerine bakın.

### <a name="marshalling-errors-in-clr-code"></a>CLR kod düzenleme hataları

CLR hazırlama kitaplığını kullandığınızda C4996 da oluşabilir. Bu durumda, C4996 bir uyarı değil hatadır. Bu hata oluşur [marshal_as](../../dotnet/marshal-as.md) gerektiren iki veri türleri arasında dönüştürme için bir [marshal_context sınıfı](../../dotnet/marshal-context-class.md). Hazırlama kitaplığını dönüştürme desteklemediğinde bu hata ayrıca alabilirsiniz. Hazırlama kitaplığını hakkında daha fazla bilgi için bkz: [, genel bakış hazırlama c++](../../dotnet/overview-of-marshaling-in-cpp.md).

Hazırlama kitaplığını dönüştürmek için bir bağlam gerektirdiğinden bu örnek C4996 oluşturur bir `System::String` için bir `const char *`.

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

## <a name="example-user-defined-deprecated-function"></a>Örnek: Kullanıcı tanımlı kullanım dışı işlevi

Artık belirli işlevlerin kullanılmasını öneririz arayanlar uyarmak üzere kendi kodunuzu kullanım dışı özniteliğini kullanabilirsiniz. Bu örnekte, C4996 işlevi kullanılan çizgi ve, kullanım dışı işlev bildirildiği satır için oluşturulur.

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
