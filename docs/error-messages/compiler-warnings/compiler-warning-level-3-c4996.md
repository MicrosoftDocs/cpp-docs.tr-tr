---
title: Derleyici Uyarısı (düzey 3) C4996
description: Derleyicinin Uyarı C4996 neden gerçekleştiğini açıklar ve bunun ne yapılacağını açıklar.
ms.date: 11/25/2019
f1_keywords:
- C4996
helpviewer_keywords:
- C4996
ms.assetid: 926c7cc2-921d-43ed-ae75-634f560dd317
ms.openlocfilehash: 98662dc0b5439c1f8857e4f2ad259793a4d03e41
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/08/2020
ms.locfileid: "79419380"
---
# <a name="compiler-warning-level-3-c4996"></a>Derleyici Uyarısı (düzey 3) C4996

Kodunuz, *kullanım dışı*olarak işaretlenmiş bir işlev, sınıf üyesi, değişken veya typedef kullanır. Semboller [__declspec (kullanım dışı)](../../cpp/deprecated-cpp.md) değiştiricisi veya c++ 14 [ \[ \[ kullanım dışı \] \] ](../../cpp/attributes.md) özniteliği kullanılarak kullanımdan kaldırılmıştır. Gerçek C4996 uyarı iletisi `deprecated` bildirimin değiştirici veya özniteliğiyle belirtilir.

> [!IMPORTANT]
> Bu uyarı, simgeyi bildiren üstbilgi dosyasının yazarından her zaman bir bilinçli iletisidir. Kullanılmayan sembolü sonuçları anlayamaksızın kullanmayın.

## <a name="remarks"></a>Açıklamalar

Visual Studio kitaplıklarında birçok işlev, üye işlevi, Şablon işlevleri ve genel değişkenler *kullanım dışıdır*. POSIX ve Microsoft 'a özgü işlevler gibi bazıları artık farklı bir tercih edilen ada sahip olduğundan kullanım dışıdır. Bazı C çalışma zamanı kitaplığı işlevleri, güvenli olduklarından ve daha güvenli bir varyanta sahip olduklarından kullanım dışıdır. Artık kullanılmıyor olduklarından diğerleri kullanımdan kaldırılmıştır. Kullanımdan kaldırılan iletiler, genellikle kullanım dışı işlev veya genel değişken için önerilen bir değiştirme içerir.

## <a name="turn-off-the-warning"></a>Uyarıyı kapat

Bir C4996 sorununu onarmak için genellikle kodunuzun değiştirilmesini öneririz. Bunun yerine önerilen işlevleri ve genel değişkenleri kullanın. Taşınabilirlik nedenleriyle mevcut işlevleri veya değişkenleri kullanmanız gerekiyorsa, uyarıyı kapatabilirsiniz.

Belirli bir kod satırıyla ilgili uyarıyı kapatmak için, [Uyarı](../../preprocessor/warning.md) pragmasını kullanın `#pragma warning(suppress : 4996)` .

Bir dosya içindeki uyarıyı kapatmak için, uyarı pragmasını kullanın `#pragma warning(disable : 4996)` .

Komut satırı Derlemeleriyle uyarı genel olarak devre dışı bırakmak için [/wd4996](../../build/reference/compiler-option-warning-level.md) komut satırı seçeneğini kullanın.

Visual Studio IDE 'deki bir projenin tamamına yönelik uyarıyı kapatmak için:

1. Projeniz için **Özellik sayfaları** iletişim kutusunu açın. Özellik sayfaları iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz. [Özellik sayfaları](../../build/reference/property-pages-visual-cpp.md).

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **Gelişmiş** sayfasını seçin.

1. Eklemek için **belirli uyarıları devre dışı bırak** özelliğini düzenleyin `4996` . Değişikliklerinizi uygulamak için **Tamam ' ı** seçin.

Ayrıca, kitaplıklarda kullanılan belirli bir kullanımdan kaldırma uyarılarını devre dışı bırakmak için Önişlemci makrolarını de kullanabilirsiniz. Bu makrolar aşağıda açıklanmıştır.

Visual Studio 'da bir önişlemci makrosu tanımlamak için:

1. Projeniz için **Özellik sayfaları** iletişim kutusunu açın. Özellik sayfaları iletişim kutusunu kullanma hakkında daha fazla bilgi için bkz. [Özellik sayfaları](../../build/reference/property-pages-visual-cpp.md).

1. **Yapılandırma özellikleri > C/C++ > Önişlemci**' yi genişletin.

1. Ön **Işlemci tanımları** özelliğinde makro adını ekleyin. Kaydetmek için **Tamam** ' ı seçin ve ardından projenizi yeniden derleyin.

Yalnızca belirli kaynak dosyalarında bir makro tanımlamak için, `#define EXAMPLE_MACRO_NAME` bir başlık dosyası içeren herhangi bir satırdan önce gibi bir satır ekleyin.

C4996 uyarı ve hataların yaygın kaynaklarından bazıları şunlardır:

## <a name="posix-function-names"></a>POSIX işlev adları

**Bu ÖĞENIN POSIX adı kullanım dışıdır. Bunun yerine, ISO C ve C++ uyumlu adı kullanın:** *New-Name*. **Ayrıntılar için çevrimiçi yardıma bakın.**

Microsoft, ayrılmış ve genel uygulama tanımlı adlarla C99 ve C++ 03 kısıtlamalarına uyum sağlamak için CRT 'daki bazı POSIX ve Microsoft 'a özgü kitaplık işlevlerini yeniden adlandırdı. *İşlevlerin kendisi değil, yalnızca adlar kullanım dışıdır*. Çoğu durumda, uygun bir ad oluşturmak için işlev adına bir öncü alt çizgi eklenmiştir. Derleyici, özgün işlev adı için kullanımdan kaldırma uyarısı verir ve tercih edilen adı önerir.

Bu sorunu onarmak için genellikle kodunuzu önerilen işlev adlarını kullanacak şekilde değiştirmenizi öneririz. Ancak, güncelleştirilmiş adlar Microsoft 'a özgüdür. Taşınabilirlik nedenleriyle var olan işlev adlarını kullanmanız gerekiyorsa, bu uyarıları devre dışı bırakabilirsiniz. İşlevler, kitaplıkta orijinal adları altında hala kullanılabilir.

Bu işlevlere yönelik kullanımdan kaldırma uyarılarını kapatmak için, ön işlemci makrosunu ** \_ CRT olmayan bir \_ \_ \_ uyarı yok**tanımlayın. Bu makroyu komut satırında, seçeneğini ekleyerek tanımlayabilirsiniz `/D_CRT_NONSTDC_NO_WARNINGS` .

## <a name="unsafe-crt-library-functions"></a>Güvenli olmayan CRT kitaplığı işlevleri

**Bu işlev veya değişken güvenli olmayabilir. **Bunun yerine *güvenli sürüm* kullanmayı düşünün **. Kullanımdan kaldırmayı devre dışı bırakmak için \_ CRT \_ güvenli \_ uyarı yok ' u kullanın \_ .  Ayrıntılar için çevrimiçi yardıma bakın.**

Daha güvenli sürümler mevcut olduğundan Microsoft bazı CRT ve C++ standart kitaplık işlevlerini ve genel kullanım dışı bırakıldı. Kullanım dışı bırakılan işlevlerin çoğu arabelleklere denetlenmeyen okuma veya yazma erişimine izin verir. Kötüye kullanımı ciddi güvenlik sorunlarına neden olabilir. Derleyici bu işlevler için kullanımdan kaldırma uyarısı verir ve tercih edilen işlevi önerir.

Bu sorunu onarmak için bunun yerine işlevi veya değişkeni *güvenli sürüm* kullanmanız önerilir. Bazen taşınabilirlik veya geriye doğru uyumluluk nedenleriyle yapamazsınız. Kodunuzda bir arabellek üzerine yazma veya aşırı okuma için mümkün olmadığından emin olun. Ardından, uyarıyı devre dışı bırakabilirsiniz.

CRT 'daki bu işlevler için kullanımdan kaldırma uyarılarını kapatmak için, ** \_ CRT \_ güvenli \_ \_ uyarı yok**' u tanımlayın.

Kullanım dışı bırakılan Global değişkenlerle ilgili uyarıları kapatmak için ** \_ CRT \_ güvenli \_ olmayan \_ Uyarı \_ genel**değerleri tanımlayın.

Kullanım dışı bırakılan bu işlevler ve Globals hakkında daha fazla bilgi için bkz. CRT ve güvenli kitaplıklarda [güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md) [: C++ standart kitaplığı](../../standard-library/safe-libraries-cpp-standard-library.md).

## <a name="unsafe-standard-library-functions"></a>Güvenli olmayan standart kitaplık işlevleri

__' std::__*function_name*__:: \_ işaretlenmeyen \_ yineleyiciler:: \_ ' std:: function_name çağrısı__*function_name* **güvenli olmayabilecek parametrelerle-bu çağrı, geçirilen değerlerin doğru olup olmadığını denetlemek için çağrıyı yapana bağımlıdır. Bu uyarıyı devre dışı bırakmak için-D \_ SCL \_ güvenli \_ uyarı yok ' u kullanın \_ . ' Denetlenen yineleyiciler ' Visual C++ kullanımı hakkındaki belgelere bakın**

Bu uyarı, bazı C++ standart kitaplık şablonu işlevleri doğruluğu için parametreleri denetlemediğinden, hata ayıklama yapılarında görüntülenir. Genellikle bu durum, işlevin kapsayıcı sınırlarını denetlemek için yeterli bilgi olmadığı için kullanılır. Ya da yineleyiciler işlevle yanlış bir şekilde kullanılabilir. Bu uyarı, programınızda önemli güvenlik delikleri kaynağı olabileceğinden, bu işlevleri belirlemenize yardımcı olur. Daha fazla bilgi için bkz. [Checked Iterators](../../standard-library/checked-iterators.md).

Örneğin, düz dizi yerine öğesine bir öğe işaretçisi geçirirseniz, bu uyarı hata ayıklama modunda görüntülenir `std::copy` . Bu sorunu giderecek şekilde, uygun şekilde tanımlanmış bir dizi kullanın, böylece kitaplık dizi kapsamlarını denetleyebilir ve sınır denetimi yapabilir.

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

Birkaç standart kitaplık algoritması, C++ 14 ' te "çift aralıklı" sürümlere sahip olacak şekilde güncelleştirildi. İkili Aralık sürümlerini kullanıyorsanız, ikinci Aralık gerekli sınır denetimini sağlar:

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

Bu örnekte, standart kitaplığın yineleyici kullanımını denetlemek için kullanılabileceği ve işaretlenmeyen kullanım tehlikeli olabileceği birçok yol gösterilmektedir:

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

Kodunuzun arabellek taşması hatası olmadığını doğruladıysanız, bu uyarıyı devre dışı bırakabilirsiniz. Bu işlevlere yönelik uyarıları kapatmak için, ** \_ SCL \_ güvenli \_ \_ uyarı yok**' u tanımlayın.

## <a name="checked-iterators-enabled"></a>İşaretli yineleyiciler etkin

C4996, denetlenen Yineleyici kullanmıyorsanız `_ITERATOR_DEBUG_LEVEL` 1 veya 2 olarak tanımlandığında da oluşabilir. Hata ayıklama modu derlemeleri için varsayılan olarak 2 ' ye ve perakende derlemeler için 0 ' a ayarlanır. Daha fazla bilgi için bkz. [Checked Iterators](../../standard-library/checked-iterators.md).

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

## <a name="unsafe-mfc-or-atl-code"></a>Güvenli olmayan MFC veya ATL kodu

Güvenlik nedenleriyle kullanım dışı bırakılmış MFC veya ATL işlevlerini kullanırsanız, C4996 oluşabilir.

Bu sorunu gidermeye yönelik olarak, kodunuzu güncelleştirilmiş işlevleri kullanacak şekilde değiştirmenizi kesinlikle öneririz.

Bu uyarıları gösterme hakkında daha fazla bilgi için bkz. [_AFX_SECURE_NO_WARNINGS](../../mfc/reference/diagnostic-services.md#afx_secure_no_warnings).

## <a name="obsolete-crt-functions-and-variables"></a>Eski CRT işlevleri ve değişkenleri

**Bu işlevin veya değişkenin yerini yeni kitaplık veya işletim sistemi işlevselliği almıştır. ** *new_item* **Bunun yerine new_item kullanmayı düşünün. Ayrıntılar için çevrimiçi yardıma bakın.**

Bazı kitaplık işlevleri ve genel değişkenler kullanımdan kaldırılmıştır. Bu işlevler ve değişkenler, kitaplığın gelecek bir sürümünde kaldırılabilir. Derleyici bu öğeler için kullanımdan kaldırma uyarısı verir ve tercih edilen alternatifi önerir.

Bu sorunu gidermeye yönelik olarak, kodunuzu önerilen işlevi veya değişkeni kullanacak şekilde değiştirmenizi öneririz.

Bu öğeler için kullanımdan kaldırma uyarılarını kapatmak için, ** \_ CRT olmayan bir \_ \_ \_ uyarı yok**tanımlayın. Daha fazla bilgi için, kullanım dışı işlev veya değişken için belgelere bakın.

## <a name="marshaling-errors-in-clr-code"></a>CLR kodundaki hataları sıralama

C4996, CLR sıralama kitaplığını kullandığınızda da oluşabilir. Bu durumda, C4996 bir uyarı değil, bir hatadır. [Marshal_context sınıfı](../../dotnet/marshal-context-class.md)gerektiren iki veri türü arasında dönüştürmek için [marshal_as](../../dotnet/marshal-as.md) kullandığınızda hata oluşur. Sıralama kitaplığı bir dönüştürmeyi desteklemiyorsa da bu hatayı alabilirsiniz. Sıralama kitaplığı hakkında daha fazla bilgi için bkz. [C++ ' da sıralamaya genel bakış](../../dotnet/overview-of-marshaling-in-cpp.md).

Bu örnek, C4996 oluşturur, çünkü sıralama kitaplığı bir ' dan ' a dönüştürmek için bağlam gerektirir `System::String` `const char *` .

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

Artık belirli işlevlerin kullanımını önermeyiz çağıranlar uyarmak için kendi kodunuzda kullanım dışı bırakılmış özniteliğini kullanabilirsiniz. Bu örnekte, C4996 iki yerde oluşturulur: bir adet, kullanım dışı işlevin bildirildiği satır için, diğeri ise işlevin kullanıldığı çizgi için.

```cpp
// C4996.cpp
// compile with: /W3
// C4996 warning expected
#include <stdio.h>

// #pragma warning(disable : 4996)
void func1(void) {
   printf_s("\nIn func1");
}

[[deprecated]]
void func1(int) {
   printf_s("\nIn func2");
}

int main() {
   func1();
   func1(1);    // C4996
}
```
