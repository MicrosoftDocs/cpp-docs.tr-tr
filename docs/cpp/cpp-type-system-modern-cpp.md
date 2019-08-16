---
title: C++ Tür Sistemi (Modern C++)
ms.date: 11/19/2018
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: b947bd6955a80e051d1dab81061b4b2bf2ab19c8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498636"
---
# <a name="c-type-system-modern-c"></a>C++ Tür Sistemi (Modern C++)

*Türü* kavramı içinde C++çok önemlidir. Her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri; derlenebilmeleri için bir türe sahip olmalıdır. Ayrıca, her ifadeye (değişmez değerler dahil), değerlendirilmeden önce derleyicisi tarafından dolaylı olarak bir tür tanımlanır. Türlerin bazı örnekleri, tam sayı değerlerini depolamak için **int** , kayan nokta değerlerini depolamak için **Double** ( *skaler* veri türleri olarak da bilinir) veya standart kitaplık sınıfı [std:: basic_string](../standard-library/basic-string-class.md) ' i içerir. Bir **sınıf** veya **Yapı**tanımlayarak kendi türünü oluşturabilirsiniz. Tür, değişken (veya ifade sonucu) için atanacak bellek miktarını, bu değişkende depolanabilecek değer türlerini, bu değerlerin (bit modelleri olarak) nasıl yorumlanacağını ve gerçekleştirilebilecek işlemleri belirtir. Bu makale, C++ tür sistemiyle ilgili önemli özellikleri basit bir şekilde inceler.

## <a name="terminology"></a>Terminoloji

**Değişken**: Adın, tanımlandıkları kodun kapsamı boyunca başvurduğu verilere erişmek için kullanılabilmesi adına, verilerin bir miktarın simgesel adı. ' C++De, *değişken* genellikle skaler veri türü örneklerine başvurmak için kullanılır, ancak diğer türlerin örnekleri genellikle *nesneler*olarak adlandırılır.

**Nesne**: Kolaylık ve tutarlılık için bu makale, bir sınıf veya yapının herhangi bir örneğine başvurmak için Term *nesnesini* kullanır ve genel anlamda kullanıldığında tüm türler, hatta skaler değişkenler içerir.

**Pod türü** (düz eski veriler): İçindeki C++ veri türlerinin bu resmi olmayan kategorisi, skaler olan türlere başvurur (temel türler bölümüne bakın) veya *Pod sınıflarıdır*. POD olmayan statik veri üyeleri, kullanıcı tanımlı oluşturucular veya kullanıcı tanımlı atama işleçleri POD sınıfına dahil değildir. Ayrıca, bir POD sınıfının hiçbir sanal işlevi, hiçbir temel sınıfı ve hiçbir özel veya korumalı statik olmayan veri üyesi bulunmaz. POD türleri genellikle dış veri değişimi için örneğin, (yalnızca POD türleri olan) C dilinde yazılmış bir modül ile birlikte kullanılır.

## <a name="specifying-variable-and-function-types"></a>Değişken ve işlev türlerini belirtme

C++*türü kesin belirlenmiş* bir dildir ve ayrıca statik olarak *türdedir*; her nesne bir türe sahiptir ve bu tür hiçbir değişiklik değiştirmez (statik veri nesneleriyle karıştırılmamalıdır).
Kodunuzda **bir değişken bildirdiğinizde** türünü açıkça belirtmeli ya da derleyiciye türü başlatıcıdan almasını istemek için **Auto** anahtar sözcüğünü kullanmanız gerekir.
Kodunuzda **bir işlev bildirdiğinizde** , her bağımsız değişkenin ve dönüş değerinin türünü belirtmeniz gerekir ya da işlev tarafından hiçbir değer döndürülmezse **void** . Rasgele türden bağımsız değişkenlere izin veren işlev şablonları kullandığınızda bu bir özel durumdur.

İlk kez bir değişken bildirdikten sonra belirli bir süre geçtikten sonra türünü değiştiremezsiniz. Ancak değişkenin değerini veya bir işlevin dönüş değerini başka türdeki farklı bir değişkene kopyalayabilirsiniz. Bu gibi işlemler, bazen gerekli olan ancak aynı zamanda olası veri kaybı veya yanlışlık kaynakları olan *tür dönüştürmeleri*olarak adlandırılır.

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

Diğer dillerden farklı olarak, C++, diğer tüm türlerin türetildiği bir evrensel temel türe sahip değildir. Dil, *Yerleşik türler*olarak da bilinen birçok *temel tür*içerir. Bu, sırasıyla ASCII ve UNICODE karakterleri için **int**, **Double**, **Long**, **bool**ve **char** ve **wchar_t** türleri gibi sayısal türler içerir. Çoğu temel türlerin ( **bool**, **Double**, **wchar_t** ve ilgili türler hariç), değişkenin depolayabileceği değer aralığını değiştiren işaretsiz sürümler vardır. Örneğin, 32 bitlik işaretli bir tamsayıyı depolayan bir **int**,-2.147.483.648 ile 2.147.483.647 arasında bir değer temsil edebilir. 32 bit olarak da depolanan **işaretsiz bir int**, 0 ile 4.294.967.295 arasında bir değer depolayabilirler. Her durumda olası değerlerin toplam sayısı aynıdır; yalnızca aralık farklıdır.

Temel türler, üzerlerinde gerçekleştirebileceğiniz işlemleri ve bunların diğer temel türlere nasıl dönüştürülebileceğini yöneten yerleşik kurallara sahip derleyici tarafından tanınır. Yerleşik türlerin tam listesi ve bunların boyut ve sayısal sınırları için bkz. [temel türler](../cpp/fundamental-types-cpp.md).

Aşağıdaki çizim, yerleşik türlerin göreli boyutlarını gösterir:

![&#45;]Yerleşik türlerin(../cpp/media/built-intypesizes.png "&#45;bayt cinsinden") yerleşik tür boyutunun bayt cinsinden boyutu

Aşağıdaki tablo en sık kullanılan temel türleri listeler:

|Tür|Boyut|Yorum|
|----------|----------|-------------|
|int|4 bayt|Tamsayı değerler için varsayılan seçim.|
|çift|8 bayt|Kayan nokta değerleri için varsayılan seçim.|
|bool|1 bayt|True veya false olabilen değerleri temsil eder.|
|char|1 bayt|Daha eski C stili dizelerde veya std::string nesnelerde UNICODE'a dönüştürülmesi hiçbir zaman gerekmeyecek ASCII karakterler için kullanın.|
|wchar_t|2 bayt|UNICODE biçiminde (Windows'ta UTF-16, diğer işletim sistemlerinde değişiklik gösterebilir) kodlanmış olabilecek "geniş" karakter değerlerini temsil eder. Bu, türü `std::wstring`dizelerde kullanılan karakter türüdür.|
|işaretsiz&nbsp;karakter|1 bayt|C++yerleşik `byte` bir türü yoktur.  Bayt değerini göstermek için unsigned char kullanın.|
|unsigned int|4 bayt|Bit bayrakları için varsayılan seçimdir.|
|long long|8 bayt|Çok büyük tamsayı değerlerini temsil eder.|

## <a name="the-void-type"></a>Void türü

**Void** türü özel bir türdür; **void**türünde bir değişken bildiremezsiniz, ancak, ham (türsüz) bellek ayrılırken bazen gerekli olan __void \*__  ( **void**işaretçisi) türünde bir değişken bildirebilirsiniz. Ancak, **void** işaretçileri tür açısından güvenli değildir ve genellikle modern C++bir şekilde kullanılması önerilmez. Bir işlev bildiriminde, **void** dönüş değeri işlevin bir değer döndürmeyeceği anlamına gelir; Bu ortak ve kabul edilebilir bir **void**kullanımı. C dili, parametre listesinde **void** bildirmek için sıfır parametreye sahip işlevler gerektirirken, örneğin, `fou(void)`bu uygulama modern C++ değildir ve bildirilmelidir `fou()`. Daha fazla bilgi için bkz. [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const türü niteleyici

Herhangi bir yerleşik veya kullanıcı tanımlı tür, const anahtar sözcük aracılığıyla nitelendirilebilir. Ayrıca, üye işlevleri **const**nitelenmiş ve hatta **const**aşırı yüklenmiş olabilir. **Const** türünün değeri başlatıldıktan sonra değiştirilemez.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

**Const** niteleyicisi, işlev ve değişken bildirimlerinde yaygın olarak kullanılır ve "const doğruluk" bölümünde C++önemli bir kavramdır; Temelde, derleme zamanında değerlerin istenmeden değiştirilmeyeceği garantisi için **const** kullanılması anlamına gelir. Daha fazla bilgi için bkz. [const](../cpp/const-cpp.md).

**Const** türü, sabit olmayan sürümünden farklıdır; Örneğin, **const int** , **int**'ten farklı bir türdür. Bir değişkenden *const* kullanımını C++ kaldırmanız gerektiğinde nadir durumlarda **const_cast** işlecini kullanabilirsiniz. Daha fazla bilgi için bkz. [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Dize türleri

Kesinlikle konuşurken, C++ dilin yerleşik dize türü yoktur; **char** ve **wchar_t** depolama tek karakterler-bir dizeyi tahmin etmek için bu türlerin bir dizisini bildirmeniz gerekir, dizi öğesine en son geçerli karakteri (örneğin, ASCII `'\0'`) geçmiş bir *C stili dize*). C stili dizeler çok daha fazla kodun yazılmasını veya harici dize yardımcı program kitaplığı işlevlerini gerektirmekteydi. Ancak modern C++bir, standart kitaplık türlerine `std::string` (8 bitlik karakter türü karakter dizeleri için) veya `std::wstring` (16 bit **wchar_t**-Type karakter dizeleri için) sahiptir. Bu C++ standart kitaplık kapsayıcıları, herhangi bir uyumlu C++ derleme ortamında yer alan standart kitaplıkların bir parçası olduklarından yerel dize türleri olarak düşünülebilir. Yalnızca bu türleri `#include <string>` programınızda kullanılabilir hale getirmek için yönergesini kullanın. (MFC veya ATL kullanıyorsanız, CString sınıfı da ayrıca kullanılabilir ancak C++ standardının bir parçası değildir.) Boş sonlandırılmış karakter dizilerinin kullanımı (daha önce bahsedilen C stili dizeler) modern C++ içinde önerilmez.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

Bir **sınıf**, **Yapı**, **birleşim**veya **enum**tanımladığınızda, bu yapı, kodunuzun geri kalanında temel bir tür gibi kullanılır. Bellekte bilinen bir boyuta sahiptir ve derleme zamanı denetimi için, çalışma zamanında ve programınızın kullanım süresi boyunca uygulanmak üzere nasıl kullanılacağına ilişkin belirli kuralları içerir. Temel yerleşik türler ve kullanıcı tanımlı türler arasındaki temel farklar şunlardır:

- Derleyici kullanıcı tanımlı türde yerleşik bilgi içermez. Derleme işlemi sırasında tanımdan ilk kez karşılaştığında türü öğrenir.

- Türünüz üzerinde gerçekleştirilebilecek işlemleri ve diğer türlere nasıl dönüştürülebileceğini, ilgili operatörleri sınıf üyeleri veya üye harici işlevler olarak tanımlayarak (aşırı yükleme ile) siz belirtirsiniz. Daha fazla bilgi için bkz. [Işlev aşırı yüklemesi](function-overloading.md)

## <a name="pointer-types"></a>İşaretçi türleri

C dilinin en eski sürümlerine göz atma, C++ özel bildirimcisini `*` (yıldız işareti) kullanarak bir işaretçi türü değişkenini bildirmenize olanak vermeye devam eder. İşaretçi türü, gerçek veri değerinin depolandığı bellekteki konumun adresini saklar. Modern C++bir deyişle, bunlar *ham işaretçiler*olarak adlandırılır ve kodunuzda özel işleçler `*` (yıldız işareti) veya `->` (büyüktür işareti olan tire) aracılığıyla erişilir. Buna *başvuru başvurusu*adı verilir ve bu, kullandığınız bir işaretçinin bir işaretçi ya da nesnedeki bir işaretçiyle ilgili bir işaretçiye başvuru yapılıp yapılmayacağını bağlıdır. İşaretçi türleri ile çalışma, uzun süredir C ve C++ program geliştirmenin en zor ve en kafa karıştırıcı taraflarından biri olmuştur. Bu bölümde, isterseniz ham işaretçiler kullanılmasına yardımcı olacak bazı olguları ve uygulamalar özetlenmektedir, ancak modern C++ (veya önerilir) [akıllı işaretçinin](../cpp/smart-pointers-modern-cpp.md) evriminin (daha fazla ele alındığı) dolayı Bu bölümün sonunda). Nesneleri gözlemlemek için ham işaretçilerin kullanılması yararlıdır; ancak, bunları nesne sahipliği için kullanmanız gerekiyorsa bunu dikkatli bir şekilde yapmanız ve bunlara sahip olan nesnelerin nasıl oluşturulduğunu ve nasıl yok edildiğini dikkatle değerlendirmeniz gerekir.

Bilmeniz gereken ilk şey, bir ham işaretçi değişkeni bildirmenin, yalnızca başvuru kaldırıldığında işaretçinin başvuracağı bellek konumunun adresini depolamak için gereken belleği ayıracağıdır. Veri değerinin kendisi için bellek ayırması ( *yedekleme deposu*olarak da bilinir) henüz ayrılmamıştır. Diğer bir deyişle, bir ham işaretçi değişkeni bildirerek gerçek bir veri değişkeni yerine bir bellek adresi değişkeni oluşturursunuz. Bir yedekleme belleğine geçerli bir adres içerdiğinden emin olmadan önce, bir işaretçi değişkeninin başvurusunun kaldırılması, programınızda tanımlanmamış bir davranışa (genellikle önemli bir hata) neden olabilir. Aşağıdaki örnek bu türde bir hata gösterir.

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

Düzeltilen kod örneği, işaret eden `pNumber` yedekleme deposunu oluşturmak için yerel yığın belleğini kullanır. Kolaylık olması için bir temel türü kullanıyoruz. Pratikte, işaretçilerin yedekleme deposu, **Yeni** bir anahtar sözcük Ifadesi (C stili programlamada daha eski )kullanılarakyığın(veyaücretsizdepo)olarakadlandırılanbellekalanındadinamikolarakayrılanKullanıcıtanımlıtürlerdir.`malloc()` C çalışma zamanı kitaplığı işlevi kullanıldı). Bu değişkenler, ayrıldıktan sonra genellikle nesne olarak anılır, özellikle de bir sınıf tanımına dayalıdır. **New** ile ayrılmış bellek, karşılık gelen **Delete** ifadesiyle (veya ayırmak için `malloc()` işlevi kullandıysanız, C çalışma zamanı işlevi `free()`) silinmelidir.

Ancak, özellikle karmaşık kodda dinamik olarak ayrılan bir nesneyi silmeyi unutmak kolaydır, bu da bir kaynak hatasına *bellek sızıntısı*olarak adlandırılır. Bu nedenle, ham işaretçilerin modern C++'ta kullanılması önerilmez. Bir ham işaretçiyi [akıllı bir işaretçiye](../cpp/smart-pointers-modern-cpp.md)kaydırmak neredeyse her zaman daha iyidir. Bu, yıkıcı çağrıldığında belleği otomatik olarak serbest bırakacaktır (kod akıllı işaretçinin kapsamı dışına geçtiğinde); Akıllı işaretçileri kullanarak, C++ programlarınızda bir hata sınıfının tamamını neredeyse ortadan kaldırabilirsiniz. Aşağıdaki örnekte, bir public yöntemi `MyClass` olan Kullanıcı tanımlı bir tür olduğunu varsayalım`DoSomeWork();`

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

C ve C++için Klasik Win32 programlamada çoğu işlev, parametre türlerini ve dönüş değerlerini belirtmek için Windows 'a özgü tür tanımlarını ve `windef.h`#define makrolarını (içinde tanımlanmıştır) kullanır. Bu Windows veri türleri genellikle C/C++ yerleşik türlere verilen özel adlardır (diğer adlar). Bu tür tanımları ve önişlemci tanımlarının tüm listesi için bkz. [Windows veri türleri](/windows/win32/WinProg/windows-data-types). HRESULT ve LCID gibi bu tür tanımlarından bazıları kullanışlı ve açıklayıcıdır. INT gibi diğerlerinin özel bir anlamı yoktur ve bunlar yalnızca temel C++ türlerinin diğer adlarıdır. Diğer Windows veri türleri C programlama ve 16-bit işlemci günlerinden kalma adlara sahiptir ve bu adların modern donanım veya işletim sistemlerinde herhangi bir amacı ya da anlamı yoktur. Ayrıca, [Windows çalışma zamanı temel veri türleri](/windows/win32/WinRT/base-data-types)olarak listelenen Windows çalışma zamanı kitaplığıyla ilişkili özel veri türleri de vardır. Modern C++ programlamada, Windows türü değerin nasıl yorumlanacağına ilişkin ek anlamlar iletmedikçe C++ temel türlerinin tercih edilmesi genel bir yönergedir.

## <a name="more-information"></a>Daha fazla bilgi

C++ tür sistemi hakkında daha fazla bilgi için aşağıdaki konulara bakın.

|||
|-|-|
|[Değer Türleri](../cpp/value-types-modern-cpp.md)|*Değer türlerini* , kullanımlarıyla ilgili sorunlarla birlikte açıklar.|
|[Tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Ortak tür dönüştürme sorunlarını açıklar ve bunları nasıl engelleyeceğinizi gösterir.|

## <a name="see-also"></a>Ayrıca bkz.

[C++'a (Modern C++) Tekrar Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
