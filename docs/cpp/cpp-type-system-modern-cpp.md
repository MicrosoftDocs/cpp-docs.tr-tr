---
title: C++ Tür Sistemi (Modern C++)
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: ea4d8da9af10df2fb930daaad8374d70b6704d28
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220679"
---
# <a name="c-type-system-modern-c"></a>C++ Tür Sistemi (Modern C++)

Kavramını *türü* C++'da çok önemlidir. Her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri; derlenebilmeleri için bir türe sahip olmalıdır. Ayrıca, her ifadeye (değişmez değerler dahil), değerlendirilmeden önce derleyicisi tarafından dolaylı olarak bir tür tanımlanır. Bazı tür örnekleri, **int** tamsayı değerlerini saklamak için **çift** kayan nokta değerini (olarak da bilinen *skaler* veri türleri), veya standart kitaplık sınıfı [std::basic_string](../standard-library/basic-string-class.md) metin depolamak için. Tanımlayarak kendi türünüzü oluşturabilirsiniz bir **sınıfı** veya **yapı**. Tür, değişken (veya ifade sonucu) için atanacak bellek miktarını, bu değişkende depolanabilecek değer türlerini, bu değerlerin (bit modelleri olarak) nasıl yorumlanacağını ve gerçekleştirilebilecek işlemleri belirtir. Bu makale, C++ tür sistemiyle ilgili önemli özellikleri basit bir şekilde inceler.

## <a name="terminology"></a>Terminoloji

**Değişken**: Simgesel Adı başvurduğu için tanımlanmış olduğu yerlerde kod kapsamında verilere erişmek için kullanılabilir, böylece veri miktarını adı. C++ ' ta *değişkeni* diğer örnek türleri genellikle olarak adlandırılır genelde skalar veri türlerine örneğine başvurmak için kullanılan *nesneleri*.

**Nesne**: Kolaylık ve tutarlılık için bu makalede terimi kullanılmaktadır *nesne* başvurmak için herhangi bir örneği ve bir sınıf veya yapının genel anlamda kullanıldığında tüm türleri içerir bile skalar değişkenler.

**POD türü** (düz eski veriler): C++ içindeki veri türleri için resmi olmayan bu kategori skalar türlere başvurur (temel türler bölümüne bakın) veya *POD sınıflarıdır*. POD olmayan statik veri üyeleri, kullanıcı tanımlı oluşturucular veya kullanıcı tanımlı atama işleçleri POD sınıfına dahil değildir. Ayrıca, bir POD sınıfının hiçbir sanal işlevi, hiçbir temel sınıfı ve hiçbir özel veya korumalı statik olmayan veri üyesi bulunmaz. POD türleri genellikle dış veri değişimi için örneğin, (yalnızca POD türleri olan) C dilinde yazılmış bir modül ile birlikte kullanılır.

## <a name="specifying-variable-and-function-types"></a>Değişken ve işlev türlerini belirtme

C++; bir *kesin tür belirtilmiş* dil ve onu *türü statik belirlenmiştir*; her nesne bir türe sahiptir ve bu tür asla değişmez (statik veri nesneleriyle karıştırılmamalıdır için).
**Bir değişken bildirdiğinizde** kodunuzda, türünü açıkça belirtmeniz veya kullanın **otomatik** anahtar sözcüğünü kullanarak derleyicinin türü başlatıcıdan almasını.
**Bir işlev bildirdiğinizde** kodunuzda, her bir bağımsız değişkenin ve dönüş değerinin türünü belirtmeniz gerekir veya **void** işlevi tarafından döndürülen değer varsa. Rasgele türden bağımsız değişkenlere izin veren işlev şablonları kullandığınızda bu bir özel durumdur.

İlk kez bir değişken bildirdikten sonra belirli bir süre geçtikten sonra türünü değiştiremezsiniz. Ancak değişkenin değerini veya bir işlevin dönüş değerini başka türdeki farklı bir değişkene kopyalayabilirsiniz. Bu işlemler *tür dönüştürmeleri*, bazen gerekli ama aynı zamanda olası veri kaybı veya yanlışlık kaynakları olan.

POD türünde bir değişken bildirdiğinizde başlangıç değeri vermenizi öneririz. Bir değişkeni başlatana kadar o bellek konumunda daha önce mevcut olan bit değerlerini içeren "çöp" değerine sahiptir. Bu önemli bir C++ özelliğidir, özellikle başlatmayı sizin için yapan başka bir dilden geçiş yapıyorsanız. POD harici sınıf türünde bir değişken bildirirken oluşturucu başlatmayı işler.

Aşağıdaki örnek, her biri için bazı açıklamalar ile birlikte bazı basit değişken bildirimlerini gösterir. Örnek ayrıca derleyicinin tür bilgisini değişkende bulunan belirli sonraki işlemlere izin vermek veya bunları yasaklamak için nasıl kullandığını gösterir.

```cpp
int result = 0;              // Declare and initialize an integer.
double coefficient = 10.8;   // Declare and initialize a floating
                             // point value.
auto name = "Lady G.";       // Declare a variable and let compiler
                             // deduce the type.
auto address;                // error. Compiler cannot deduce a type
                             // without an intializing value.
age = 12;                    // error. Variable declaration must
                             // specify a type or use auto!
result = "Kenny G.";         // error. Can’t assign text to an int.
string result = "zero";      // error. Can’t redefine a variable with
                             // new type.
int maxValue;                // Not recommended! maxValue contains
                             // garbage bits until it is initialized.
```

## <a name="fundamental-built-in-types"></a>Temel (yerleşik) türler

Diğer dillerden farklı olarak, C++, diğer tüm türlerin türetildiği bir evrensel temel türe sahip değildir. Çok dil Visual C++ uygulamasını içeren *temel türler*olarak da bilinen *yerleşik türler*. Bu gibi sayısal türler içerir **int**, **çift**, **uzun**, **bool**, artı **char** ve **wchar_t** ASCII ve UNICODE karakterleri için sırayla türleri. En temel türlerin (dışında **bool**, **çift**, **wchar_t** ve ilgili türler) tüm imzalanmamış değişkenin saklayabildiği değer aralığını değiştiren sürümlere sahiptir. Örneğin, bir **int**, 32-bit işaretli tamsayı depolayan bir değeri temsil edebilir -2.147.483.648 ila 2.147.483.647 arasında. Bir **işaretsiz int**, 32-bit olarak da depolandığı 0'dan 4.294.967.295'e kadar bir değeri saklayabilir. Her durumda olası değerlerin toplam sayısı aynıdır; yalnızca aralık farklıdır.

Temel türler, üzerlerinde gerçekleştirebileceğiniz işlemleri ve bunların diğer temel türlere nasıl dönüştürülebileceğini yöneten yerleşik kurallara sahip derleyici tarafından tanınır. Yerleşik türler ve boyutları ile sayısal sınırlarının eksiksiz listesi için bkz [temel türler](../cpp/fundamental-types-cpp.md).

Aşağıdaki çizim, yerleşik türlerin göreli boyutlarını gösterir:

![Bayt cinsinden boyutu yerleşik&#45;türlerinde](../cpp/media/built-intypesizes.png "bayt cinsinden boyutu yerleşik&#45;türleri")

Aşağıdaki tablo en sık kullanılan temel türleri listeler:

|Tür|Boyut|Yorum|
|----------|----------|-------------|
|int|4 bayt|Tamsayı değerler için varsayılan seçim.|
|çift|8 bayt|Kayan nokta değerleri için varsayılan seçim.|
|bool|1 bayt|True veya false olabilen değerleri temsil eder.|
|char|1 bayt|Daha eski C stili dizelerde veya std::string nesnelerde UNICODE'a dönüştürülmesi hiçbir zaman gerekmeyecek ASCII karakterler için kullanın.|
|wchar_t|2 bayt|UNICODE biçiminde (Windows'ta UTF-16, diğer işletim sistemlerinde değişiklik gösterebilir) kodlanmış olabilecek "geniş" karakter değerlerini temsil eder. Bu türü dizelerde kullanılan karakter türüdür `std::wstring`.|
|İmzasız&nbsp;char|1 bayt|C++ hiçbir yerleşik olan `byte` türü.  Bayt değerini göstermek için unsigned char kullanın.|
|unsigned int|4 bayt|Bit bayrakları için varsayılan seçimdir.|
|long long|8 bayt|Çok büyük tamsayı değerlerini temsil eder.|

## <a name="the-void-type"></a>Void türü

**Void** türü özel bir türdür; türünde bir değişken bildirimini yapamazsınız **void**, ancak türünde bir değişken bildirebilir __void \*__  ( işaretçisine**void**), hangi gereklidir bazen ham (türsüz) bellek atarken. Ancak, işaretçiler **void** olan tür açısından güvenli değildir ve genelde modern C++'da kesinlikle önerilmez. Bir işlev bildiriminde bir **void** dönüş değeri işlevin bir değer döndürmeyeceği anlamına gelir; bu sık karşılaşılan ve kabul edilebilir kullanımını **void**. While bildirmek için sıfır parametreye sahip C dili işlevler **void** parametre listesinde, örneğin, `fou(void)`, bu yaklaşım modern C++ ile kullanılmamaktadır ve bildirilmelidir `fou()`. Daha fazla bilgi için [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const türü niteleyici

Herhangi bir yerleşik veya kullanıcı tanımlı tür, const anahtar sözcük aracılığıyla nitelendirilebilir. Ayrıca, üye işlevleri olabilir **const**-tam ve hatta **const**-aşırı yüklendi. Değerini bir **const** türü başlatıldıktan sonra değiştirilemez.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

**Const** niteleyicisi işlevde ve değişken bildirimlerinde yaygın olarak kullanılır ve "const correctness" C++'da önemli bir kavramdır; temel olarak kullanmanın ne demek **const** , derleme zamanında güvence altına almak için değerleri olmadığına istemsiz. Daha fazla bilgi için [const](../cpp/const-cpp.md).

A **const** türüdür, sabit olmayan sürümünden farklıdır; Örneğin, **const int** ayrı türünden **int**. C++ kullanabilirsiniz **const_cast** gerekir kaldırdığınızda bu nadir durumlarda işlecinin *const-ness* öğesini bir değişkenden. Daha fazla bilgi için [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Dize türleri

NET olarak söylemek gerekirse, C++ dili yerleşik dize türü yok; **char** ve **wchar_t** tek karakterleri depolar - bu tür bir dize yaklaşık olarak belirlemenizi sağlayan bir dizi Sonlandırıcı null değer ekleme bildirmeniz gerekir (örneğin, ASCII `'\0'`) için dizi öğesinde son geçerli karakterden Geçmiş (olarak da adlandırılan bir *C stili dize*). C stili dizeler çok daha fazla kodun yazılmasını veya harici dize yardımcı program kitaplığı işlevlerini gerektirmekteydi. Ancak modern C++ programlamada standart kitaplık türleri sahibiz `std::string` (8-bit **char**-türü karakter dizeleri) veya `std::wstring` (16-bit **wchar_t**-türü karakter dizeleri). Uyumlu bir C++ yapı ortamına dahil olan standart kitaplıkların parçasıdır çünkü bu C++ Standart Kitaplığı kapsayıcıları, yerel dize türleri olarak düşünülebilir. Sadece kullanın `#include <string>` yapmayı yönergesi türleri programınızdaki kullanılabilir. (MFC veya ATL kullanıyorsanız, CString sınıfı da ayrıca kullanılabilir ancak C++ standardının bir parçası değildir.) Boş sonlandırılmış karakter dizilerinin kullanımı (daha önce bahsedilen C stili dizeler) modern C++ içinde önerilmez.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

Tanımladığınızda bir **sınıfı**, **yapı**, **birleşim**, veya **enum**, bu yapı temel tür gibi kodunuzun geri kalanında kullanılır . Bellekte bilinen bir boyuta sahiptir ve derleme zamanı denetimi için, çalışma zamanında ve programınızın kullanım süresi boyunca uygulanmak üzere nasıl kullanılacağına ilişkin belirli kuralları içerir. Temel yerleşik türler ve kullanıcı tanımlı türler arasındaki temel farklar şunlardır:

- Derleyici kullanıcı tanımlı türde yerleşik bilgi içermez. Derleme işlemi sırasında tanımla ilk karşılaştığında türü öğrenir.

- Türünüz üzerinde gerçekleştirilebilecek işlemleri ve diğer türlere nasıl dönüştürülebileceğini, ilgili operatörleri sınıf üyeleri veya üye harici işlevler olarak tanımlayarak (aşırı yükleme ile) siz belirtirsiniz. Daha fazla bilgi için [işlev aşırı yüklemesi](function-overloading.md).

- Bunların statik türlü olması gerekmez (bir nesne türünün asla değişmeme kuralı). Sistemleri aracılığıyla *devralma* ve *çok biçimlilik*, kullanıcı tanımlı türü (sınıfın nesne örneği olarak adlandırılır) olarak bildirilen bir değişken, çalışma zamanında farklı bir tür olabilir derleme zamanı. Daha fazla bilgi için [devralma](../cpp/inheritance-cpp.md).

## <a name="pointer-types"></a>İşaretçi türleri

Geri için sürümlerinden C dilinin ilk, bir işaretçi türünün bir değişkeni özel bildirimcisini kullanarak bildirmenize olanak C++ devam `*` (yıldız işareti). İşaretçi türü, gerçek veri değerinin depolandığı bellekteki konumun adresini saklar. Modern C++'da, bunlar denir *ham işaretçiler*ve özel işleçler aracılığıyla kodunuza erişir `*` (yıldız işareti) veya `->` (çizgi büyük-daha). Bu adlandırılır *başvuruluyor*, ve hangisini kullandığınız, bir işaretçinin skalar veya bir nesne içindeki üyeye bir işaretçiye başvuruluyor üzerinde bağlıdır. İşaretçi türleri ile çalışma, uzun süredir C ve C++ program geliştirmenin en zor ve en kafa karıştırıcı taraflarından biri olmuştur. Bu bölümde bazı gerçekleri ve uygulamaları anlatır ancak modern C++'da artık gerekli (veya önerilen) istiyorsanız ham işaretçiler kullanma amacıyla özetler ham işaretçiler Nesne sahipliği için hiç gelişimi nedeniyle kullanmak için [akıllı işaretçi](../cpp/smart-pointers-modern-cpp.md) () "daha bu bölümün sonuna açıklanmıştır). Nesneleri gözlemlemek için ham işaretçilerin kullanılması yararlıdır; ancak, bunları nesne sahipliği için kullanmanız gerekiyorsa bunu dikkatli bir şekilde yapmanız ve bunlara sahip olan nesnelerin nasıl oluşturulduğunu ve nasıl yok edildiğini dikkatle değerlendirmeniz gerekir.

Bilmeniz gereken ilk şey, bir ham işaretçi değişkeni bildirmenin, yalnızca başvuru kaldırıldığında işaretçinin başvuracağı bellek konumunun adresini depolamak için gereken belleği ayıracağıdır. Veri değerinin kendisi için bellek ayırması (olarak da adlandırılan *yedekleme deposu*) henüz yapılmamıştır. Diğer bir deyişle, bir ham işaretçi değişkeni bildirerek gerçek bir veri değişkeni yerine bir bellek adresi değişkeni oluşturursunuz. Bir yedekleme belleğine geçerli bir adres içerdiğinden emin olmadan önce, bir işaretçi değişkeninin başvurusunun kaldırılması, programınızda tanımlanmamış bir davranışa (genellikle önemli bir hata) neden olabilir. Aşağıdaki örnek bu türde bir hata gösterir.

```cpp
int* pNumber;       // Declare a pointer-to-int variable.
*pNumber = 10;      // error. Although this may compile, it is
                    // a serious error. We are dereferencing an
                    // uninitialized pointer variable with no
                    // allocated memory to point to.
```

Örnek, gerçek tamsayı verisini depolamak için ayrılmış herhangi bir belleği veya atanmış geçerli bir bellek adresi olmayan bir işaretçi türünün başvurusunu kaldırır. Aşağıdaki kod bu hataları düzeltir:

```cpp
    int number = 10;          // Declare and initialize a local integer
                              // variable for data backing store.
    int* pNumber = &number;   // Declare and initialize a local integer
                              // pointer variable to a valid memory
                              // address to that backing store.
...
    *pNumber = 41;            // Dereference and store a new value in
                              // the memory pointed to by
                              // pNumber, the integer variable called
                              // "number". Note "number" was changed, not
                              // "pNumber".
```

Deposunu oluşturmak için düzeltilen kod örneği kullanan yerel yığın belleğini `pNumber` işaret eder. Kolaylık olması için bir temel türü kullanıyoruz. Pratikte, işaretçilerin yedekleme deposu olduğu bir adlandırılan bellek alanında dinamik olarak ayrılan kullanıcı tanımlı türlerdir *yığın* (veya *ücretsiz depolama*) kullanarak bir **yeni** anahtar sözcüğü (C stili programlamada, eskiden `malloc()` C çalışma zamanı kitaplığı işlevi kullanılıyordu). Özellikle bunlar bir sınıf tanımını temel alıyorlarsa atandıktan sonra bu değişkenler genellikle nesneler olarak bilinir. Atanan bellek **yeni** karşılık gelen tarafından silinmesi gerekir **Sil** deyimi (veya kullandıysanız `malloc()` işlevi C çalışma zamanı işlevi ayrılacak `free()`).

Ancak, bir dinamik olarak ayrılan bir nesneyi denen bir kaynak hatası özellikle karmaşık kodlarda silmeyi unutmak çok kolaydır bu durumda bir *bellek sızıntısı*. Bu nedenle, ham işaretçilerin modern C++'ta kullanılması önerilmez. Neredeyse her zaman bir ham işaretçi içinde sarmalamak daha iyi bir [akıllı işaretçi](../cpp/smart-pointers-modern-cpp.md), hangi otomatik olarak bellek serbest bırakılır (kod akıllı işaretçinin kapsamı dışına çıktığında) yok edici çağrıldığında; akıllı işaretçiler kullanarak, neredeyse bir tam Sınıf C++ programlarınızda hatalarını ortadan kaldırabilirsiniz. Aşağıdaki örnekte, varsayalım `MyClass` genel bir yöntemi olan bir kullanıcı tanımlı tür `DoSomeWork();`

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

Akıllı işaretçiler hakkında daha fazla bilgi için bkz. [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md).

İşaretçi dönüştürmeleri hakkında daha fazla bilgi için bkz. [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

Genel olarak, işaretçiler hakkında daha fazla bilgi için bkz [işaretçileri](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows veri türleri

C ve C++ için Klasik Win32 programlamada çoğu işlev Windows özgü tür tanımlarını kullanın ve #define makroları (tanımlanan `windef.h`) dönüş değerleri ve parametre türlerini belirtmek için. Bu Windows veri türleri, genellikle C/C++ yerleşik türlerine verilmiş olan özel adlardır (takma adlardır) var. Bu tür tanımlarının ve önişlemci tanımlarının eksiksiz listesi için bkz [Windows veri türleri](/windows/desktop/WinProg/windows-data-types). HRESULT ve LCID gibi bu tür tanımlarından bazıları kullanışlı ve açıklayıcıdır. INT gibi diğerlerinin özel bir anlamı yoktur ve bunlar yalnızca temel C++ türlerinin diğer adlarıdır. Diğer Windows veri türleri C programlama ve 16-bit işlemci günlerinden kalma adlara sahiptir ve bu adların modern donanım veya işletim sistemlerinde herhangi bir amacı ya da anlamı yoktur. Olarak listelenen Windows Runtime library ile ilişkilendirilmiş özel veri türleri de vardır [Windows çalışma zamanı temel veri türlerini](/windows/desktop/WinRT/base-data-types). Modern C++ programlamada, Windows türü değerin nasıl yorumlanacağına ilişkin ek anlamlar iletmedikçe C++ temel türlerinin tercih edilmesi genel bir yönergedir.

## <a name="more-information"></a>Daha fazla bilgi

C++ tür sistemi hakkında daha fazla bilgi için aşağıdaki konulara bakın.

|||
|-|-|
|[Değer Türleri](../cpp/value-types-modern-cpp.md)|Açıklar *değer türleri* kullanımlarıyla bağlantılı sorunlarla birlikte.|
|[Tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Ortak tür dönüştürme sorunlarını açıklar ve bunları nasıl engelleyeceğinizi gösterir.|

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
