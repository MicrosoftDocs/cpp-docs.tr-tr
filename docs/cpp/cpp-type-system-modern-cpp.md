---
description: 'Daha fazla bilgi edinin: C++ tür sistemi'
title: C++ tür sistemi
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1be39124e51fc2e812ce5a2779ce701d727c81e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339585"
---
# <a name="c-type-system"></a>C++ tür sistemi

*Türü* kavramı C++ ' da çok önemlidir. Her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri; derlenebilmeleri için bir türe sahip olmalıdır. Ayrıca, her ifadeye (değişmez değerler dahil), değerlendirilmeden önce derleyicisi tarafından dolaylı olarak bir tür tanımlanır. Türlerin bazı örnekleri **`int`** , **`double`** kayan nokta değerlerini ( *skaler* veri türleri olarak da bilinir) depolamak için tamsayı değerlerini depolamak, ya da metin depolamak için [std:: basic_string](../standard-library/basic-string-class.md) standart kitaplık sınıfını içerir. Bir veya tanımlayarak kendi türünü oluşturabilirsiniz **`class`** **`struct`** . Tür, değişken (veya ifade sonucu) için atanacak bellek miktarını, bu değişkende depolanabilecek değer türlerini, bu değerlerin (bit modelleri olarak) nasıl yorumlanacağını ve gerçekleştirilebilecek işlemleri belirtir. Bu makale, C++ tür sistemiyle ilgili önemli özellikleri basit bir şekilde inceler.

## <a name="terminology"></a>Terminoloji

**Değişken**: bir veri miktarının sembolik adı, bu sayede ad, tanımlandıkları kodun kapsamı boyunca başvurduğu verilere erişmek için kullanılabilir. C++ ' da, *değişken* genellikle skaler veri türü örneklerine başvurmak için kullanılır, ancak diğer türlerin örnekleri genellikle *nesneler* olarak adlandırılır.

**Nesne**: kolaylık ve tutarlılık için bu makale, bir sınıf veya yapının herhangi bir örneğine başvurmak için Term *nesnesini* kullanır ve genel anlamda kullanıldığında, tüm türler, hatta skaler değişkenler içerir.

**Pod türü** (düz eski veriler): C++ içindeki veri türleri resmi olmayan bu kategorisi, skaler olan türler (temel türler bölümüne bakın) veya *Pod sınıfları* olduğunu ifade eder. POD olmayan statik veri üyeleri, kullanıcı tanımlı oluşturucular veya kullanıcı tanımlı atama işleçleri POD sınıfına dahil değildir. Ayrıca, bir POD sınıfının hiçbir sanal işlevi, hiçbir temel sınıfı ve hiçbir özel veya korumalı statik olmayan veri üyesi bulunmaz. POD türleri genellikle dış veri değişimi için örneğin, (yalnızca POD türleri olan) C dilinde yazılmış bir modül ile birlikte kullanılır.

## <a name="specifying-variable-and-function-types"></a>Değişken ve işlev türlerini belirtme

C++ türü *kesin belirlenmiş* bir dildir ve ayrıca statik olarak *türdedir*; her nesne bir türe sahiptir ve bu tür hiçbir değişiklik değiştirmez (statik veri nesneleriyle karıştırılmamalıdır). Kodunuzda bir değişken bildirdiğinizde türünü açıkça belirtmeniz veya **`auto`** derleyicinin türü başlatıcıdan almasını bildirmek için anahtar sözcüğünü kullanmanız gerekir. Kodunuzda bir işlev bildirdiğinizde, her bağımsız değişkenin ve dönüş değerinin türünü ya da **`void`** işlev tarafından hiçbir değer döndürülmeyeceğini belirtmeniz gerekir. Rasgele türden bağımsız değişkenlere izin veren işlev şablonları kullandığınızda bu bir özel durumdur.

İlk kez bir değişken bildirdikten sonra belirli bir süre geçtikten sonra türünü değiştiremezsiniz. Ancak değişkenin değerini veya bir işlevin dönüş değerini başka türdeki farklı bir değişkene kopyalayabilirsiniz. Bu gibi işlemler, bazen gerekli olan ancak aynı zamanda olası veri kaybı veya yanlışlık kaynakları olan *tür dönüştürmeleri* olarak adlandırılır.

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

Diğer dillerden farklı olarak, C++, diğer tüm türlerin türetildiği bir evrensel temel türe sahip değildir. Dil, *Yerleşik türler* olarak da bilinen birçok *temel tür* içerir. Bu,,,, ve gibi sayısal türler **`int`** **`double`** **`long`** **`bool`** **`char`** ve **`wchar_t`** sırasıyla ASCII ve UNICODE karakterleri için türler içerir. Çoğu integral temel tür ( **`bool`** ,, **`double`** **`wchar_t`** ve ilgili türler hariç), tüm sürümlere sahiptir ve bu da **`unsigned`** değişkenin depolayabileceği değer aralığını değiştirir. Örneğin, **`int`** 32 bitlik işaretli bir tamsayıyı depolayan bir,-2.147.483.648 ile 2.147.483.647 arasında bir değer temsil edebilir. **`unsigned int`** Ayrıca, 32 bit olarak depolanan bir değeri, 0 ile 4.294.967.295 arasında bir değer depolayabilirler. Her durumda olası değerlerin toplam sayısı aynıdır; yalnızca aralık farklıdır.

Temel türler, üzerlerinde gerçekleştirebileceğiniz işlemleri ve bunların diğer temel türlere nasıl dönüştürülebileceğini yöneten yerleşik kurallara sahip derleyici tarafından tanınır. Yerleşik türlerin tam listesi ve bunların boyut ve sayısal sınırları için bkz. [Yerleşik türler](../cpp/fundamental-types-cpp.md).

Aşağıdaki çizimde, Microsoft C++ uygulamasındaki yerleşik türlerin göreli boyutları gösterilmektedir:

![Türlerde oluşturulan&#45;bayt cinsinden boyut](../cpp/media/built-intypesizes.png "Türlerde oluşturulan&#45;bayt cinsinden boyut")

Aşağıdaki tabloda en sık kullanılan temel türler ve boyutları Microsoft C++ uygulamasında listelenmektedir:

| Tür | Boyut | Yorum |
|--|--|--|
| **`int`** | 4 bayt | Tamsayı değerler için varsayılan seçim. |
| **`double`** | 8 bayt | Kayan nokta değerleri için varsayılan seçim. |
| **`bool`** | 1 bayt | True veya false olabilen değerleri temsil eder. |
| **`char`** | 1 bayt | Daha eski C stili dizelerde veya std::string nesnelerde UNICODE'a dönüştürülmesi hiçbir zaman gerekmeyecek ASCII karakterler için kullanın. |
| **`wchar_t`** | 2 bayt | UNICODE biçiminde (Windows'ta UTF-16, diğer işletim sistemlerinde değişiklik gösterebilir) kodlanmış olabilecek "geniş" karakter değerlerini temsil eder. Bu, türü dizelerde kullanılan karakter türüdür `std::wstring` . |
| **`unsigned char`** | 1 bayt | C++ içinde yerleşik bir bayt türü yoktur.  **`unsigned char`** Bir bayt değerini temsil etmek için kullanın. |
| **`unsigned int`** | 4 bayt | Bit bayrakları için varsayılan seçimdir. |
| **`long long`** | 8 bayt | Çok büyük tamsayı değerlerini temsil eder. |

Diğer C++ uygulamaları, belirli sayısal türler için farklı boyutlar kullanabilir. C++ standardına gereken boyut ve boyut ilişkileri hakkında daha fazla bilgi için bkz. [Yerleşik türler](fundamental-types-cpp.md).

## <a name="the-void-type"></a>Void türü

**`void`** Tür özel bir türdür; türünde bir değişken bildiremezsiniz **`void`** , ancak `void *` (işaretçiyle) türünde bir değişken bildirebilirsiniz **`void`** , bu, bazen ham (türsüz) bellek ayrılırken gerekli olabilir. Ancak, işaretçileri **`void`** tür açısından güvenli değildir ve genelde modern C++ ' ta kullanımı kesinlikle önerilmez. Bir işlev bildiriminde, bir **`void`** dönüş değeri işlevin bir değer döndürmeyeceği anlamına gelir; bu, ortak ve kabul edilebilir bir kullanımı **`void`** . C dili, parametre listesinde bildirmek için sıfır parametreye sahip işlevler gerektirirken, **`void`** Örneğin, `fou(void)` Bu yöntem modern C++ ' da önerilmez ve bildirilmelidir `fou()` . Daha fazla bilgi için bkz. [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const türü niteleyici

Herhangi bir yerleşik veya kullanıcı tanımlı tür, const anahtar sözcük aracılığıyla nitelendirilebilir. Ayrıca, üye işlevleri **`const`** nitelikli ve hatta **`const`** aşırı yüklenmiş olabilir. Bir türün değeri başlatıldıktan **`const`** sonra değiştirilemez.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

**`const`** Niteleyici, işlev ve değişken bildirimlerinde yaygın olarak kullanılır ve "const doğruluk" C++ ' da önemli bir kavramdır; temel olarak **`const`** , derleme zamanında değerlerin istenmeden değiştirilmediğinden emin olmak için kullanılması anlamına gelir. Daha fazla bilgi için bkz. [`const`](../cpp/const-cpp.md).

Bir **`const`** tür const olmayan sürümünden farklıdır; Örneğin, **`const int`** öğesinden farklı bir tür **`int`** . **`const_cast`** Bir değişkenden *const* olma durumunu kaldırmanız gerektiğinde, ender görülen durumlarda C++ işlecini kullanabilirsiniz. Daha fazla bilgi için bkz. [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Dize türleri

Kesinlikle konuşurken, C++ dilinin yerleşik dize türü yoktur; **`char`** ve **`wchar_t`** tek karakterleri depola-bir dizeyi tahmin etmek için bu türlerin bir dizisini bildirmeniz gerekir, `'\0'` dizi öğesine en son geçerli karakterden ( *C stili dize* olarak da adlandırılır) geçmiş bir null değer (örneğin, ASCII) ekleyebilirsiniz. C stili dizeler çok daha fazla kodun yazılmasını veya harici dize yardımcı program kitaplığı işlevlerini gerektirmekteydi. Ancak modern C++ ' da, standart kitaplık türleri `std::string` (8 bitlik **`char`** tür karakter dizeleri için) veya `std::wstring` (16 bit **`wchar_t`** tür karakter dizeleri için) vardır. Bu C++ standart kitaplığı kapsayıcıları, uyumlu bir C++ yapı ortamına dahil olan standart kitaplıkların bir parçası olduklarından yerel dize türleri olarak düşünülebilir. Yalnızca `#include <string>` Bu türleri programınızda kullanılabilir hale getirmek için yönergesini kullanın. (MFC veya ATL kullanıyorsanız, `CString` sınıfı da kullanılabilir ancak C++ standardının bir parçası değildir.) Null ile sonlandırılmış karakter dizilerinin kullanımı (daha önce bahsedilen C stili dizeler) modern C++ ' da kesinlikle önerilmez.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

,, Veya tanımladığınızda **`class`** , **`struct`** **`union`** **`enum`** Bu yapı, kodunuzun geri kalanında temel bir tür gibi kullanılır. Bellekte bilinen bir boyuta sahiptir ve derleme zamanı denetimi için, çalışma zamanında ve programınızın kullanım süresi boyunca uygulanmak üzere nasıl kullanılacağına ilişkin belirli kuralları içerir. Temel yerleşik türler ve kullanıcı tanımlı türler arasındaki temel farklar şunlardır:

- Derleyici kullanıcı tanımlı türde yerleşik bilgi içermez. Derleme işlemi sırasında tanımdan ilk kez karşılaştığında türü öğrenir.

- Türünüz üzerinde gerçekleştirilebilecek işlemleri ve diğer türlere nasıl dönüştürülebileceğini, ilgili operatörleri sınıf üyeleri veya üye harici işlevler olarak tanımlayarak (aşırı yükleme ile) siz belirtirsiniz. Daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md)

## <a name="pointer-types"></a>İşaretçi türleri

C dilinin en eski sürümlerine göz atma, C++, özel bildirimcisini (yıldız işareti) kullanarak bir işaretçi türünün değişkenini bildirmenize olanak vermeye devam eder **`*`** . İşaretçi türü, gerçek veri değerinin depolandığı bellekteki konumun adresini saklar. Modern C++ ' da, bunlar *ham işaretçiler* olarak adlandırılır ve kodunuzda özel işleçler **`*`** (yıldız işareti) veya **`->`** (büyüktür işareti olan tire) aracılığıyla erişilir. Buna *başvuru başvurusu* adı verilir ve bu, kullandığınız bir işaretçinin bir işaretçi ya da nesnedeki bir işaretçiyle ilgili bir işaretçiye başvuru yapılıp yapılmayacağını bağlıdır. İşaretçi türleri ile çalışma, uzun süredir C ve C++ program geliştirmenin en zor ve en kafa karıştırıcı taraflarından biri olmuştur. Bu bölümde, isterseniz ham işaretçiler kullanılmasına yardımcı olacak bazı olgu ve uygulamalar özetlenmektedir, ancak modern C++ ' ta, [akıllı işaretçinin](../cpp/smart-pointers-modern-cpp.md) evrimi (Bu bölümün sonunda daha fazla ele alınmıştır) nedeniyle, artık nesne sahipliği için ham işaretçiler kullanılması gerekmez. Nesneleri gözlemlemek için ham işaretçilerin kullanılması yararlıdır; ancak, bunları nesne sahipliği için kullanmanız gerekiyorsa bunu dikkatli bir şekilde yapmanız ve bunlara sahip olan nesnelerin nasıl oluşturulduğunu ve nasıl yok edildiğini dikkatle değerlendirmeniz gerekir.

Bilmeniz gereken ilk şey, bir ham işaretçi değişkeni bildirmenin, yalnızca başvuru kaldırıldığında işaretçinin başvuracağı bellek konumunun adresini depolamak için gereken belleği ayıracağıdır. Veri değerinin kendisi için bellek ayırması ( *yedekleme deposu* olarak da bilinir) henüz ayrılmamıştır. Diğer bir deyişle, bir ham işaretçi değişkeni bildirerek gerçek bir veri değişkeni yerine bir bellek adresi değişkeni oluşturursunuz. Bir yedekleme belleğine geçerli bir adres içerdiğinden emin olmadan önce, bir işaretçi değişkeninin başvurusunun kaldırılması, programınızda tanımlanmamış bir davranışa (genellikle önemli bir hata) neden olabilir. Aşağıdaki örnek bu türde bir hata gösterir.

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

Düzeltilen kod örneği, işaret eden yedekleme deposunu oluşturmak için yerel yığın belleğini kullanır `pNumber` . Kolaylık olması için bir temel türü kullanıyoruz. Pratikte, işaretçilerin yedekleme deposu genellikle bir anahtar sözcük ifadesi (  c stili programlamada eski c çalışma zamanı kitaplığı işlevi kullanılmıştır) kullanılarak yığın (veya *ücretsiz depo*) olarak adlandırılan bir bellek alanında dinamik olarak ayrılan Kullanıcı tanımlı türlerdir **`new`** `malloc()` . Bu değişkenler, ayrıldıktan sonra genellikle nesne olarak anılır, özellikle de bir sınıf tanımına dayalıdır. İle ayrılan bellek **`new`** , karşılık gelen bir ifade tarafından silinmelidir **`delete`** (veya, `malloc()` ayırmak için Işlevi kullandıysanız, C çalışma zamanı işlevi `free()` ).

Ancak, özellikle karmaşık kodda dinamik olarak ayrılan bir nesneyi silmeyi unutmak kolaydır, bu da bir kaynak hatasına *bellek sızıntısı* olarak adlandırılır. Bu nedenle, ham işaretçilerin modern C++'ta kullanılması önerilmez. Bir ham işaretçiyi [akıllı bir işaretçiye](../cpp/smart-pointers-modern-cpp.md)kaydırmak neredeyse her zaman daha iyidir. Bu, yıkıcı çağrıldığında belleği otomatik olarak serbest bırakacaktır (kod akıllı işaretçinin kapsamı dışına geçtiğinde); Akıllı işaretçiler kullanarak C++ programlarınızda bir hata sınıfının tamamını neredeyse ortadan kaldırabilirsiniz. Aşağıdaki örnekte, `MyClass` bir public yöntemi olan Kullanıcı tanımlı bir tür olduğunu varsayalım `DoSomeWork();`

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

Genel içindeki işaretçiler hakkında daha fazla bilgi için bkz. [işaretçiler](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows veri türleri

C ve C++ için Klasik Win32 programlamada, çoğu işlev `#define` `windef.h` parametre ve dönüş değeri türlerini belirtmek için Windows 'a özgü tür tanımlarını ve makroları (içinde tanımlanmıştır) kullanır. Bu Windows veri türleri çoğunlukla C/C++ yerleşik türlerine verilen özel adlardır (diğer adlar). Bu tür tanımları ve önişlemci tanımlarının tüm listesi için bkz. [Windows veri türleri](/windows/win32/WinProg/windows-data-types). Ve gibi bu Typedefs değerlerinden bazıları `HRESULT` `LCID` yararlı ve açıklayıcı bir seçenektir. , Gibi diğerlerinin `INT` özel bir anlamı yoktur ve yalnızca temel C++ türlerinin diğer adlarıdır. Diğer Windows veri türleri C programlama ve 16-bit işlemci günlerinden kalma adlara sahiptir ve bu adların modern donanım veya işletim sistemlerinde herhangi bir amacı ya da anlamı yoktur. Ayrıca, [Windows çalışma zamanı temel veri türleri](/windows/win32/WinRT/base-data-types)olarak listelenen Windows çalışma zamanı kitaplığıyla ilişkili özel veri türleri de vardır. Modern C++ programlamada, Windows türü değerin nasıl yorumlanacağına ilişkin ek anlamlar iletmedikçe C++ temel türlerinin tercih edilmesi genel bir yönergedir.

## <a name="more-information"></a>Daha fazla bilgi

C++ tür sistemi hakkında daha fazla bilgi için aşağıdaki konulara bakın.

[Değer türleri](../cpp/value-types-modern-cpp.md)\
*Değer türlerini* , kullanımlarıyla ilgili sorunlarla birlikte açıklar.

[Tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md)\
Ortak tür dönüştürme sorunlarını açıklar ve bunları nasıl engelleyeceğinizi gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[C++ ' a geri hoş geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ dil başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ standart kitaplığı](../standard-library/cpp-standard-library-reference.md)
