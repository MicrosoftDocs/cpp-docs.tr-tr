---
title: C++ tür sistemi (Modern C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 82c017b7048c8b62f58068d22b8efefd72f31d4f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32418516"
---
# <a name="c-type-system-modern-c"></a>C++ Tür Sistemi (Modern C++)
Kavramı *türü* c++'ta çok önemlidir. Her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri; derlenebilmeleri için bir türe sahip olmalıdır. Ayrıca, her ifadeye (değişmez değerler dahil), değerlendirilmeden önce derleyicisi tarafından dolaylı olarak bir tür tanımlanır. Bazı örnekler türlerinin `int` tam sayı değerlerini depolamak için `double` kayan nokta değerlerini depolamak için (olarak da bilinen *skaler* veri türleri), veya standart kitaplığı sınıfı [std::basic_string](../standard-library/basic-string-class.md) metin depolamak için. Kendi türü tanımlayarak oluşturabileceğiniz bir `class` veya `struct`. Tür, değişken (veya ifade sonucu) için atanacak bellek miktarını, bu değişkende depolanabilecek değer türlerini, bu değerlerin (bit modelleri olarak) nasıl yorumlanacağını ve gerçekleştirilebilecek işlemleri belirtir. Bu makale, C++ tür sistemiyle ilgili önemli özellikleri basit bir şekilde inceler.  
  
## <a name="terminology"></a>Terminoloji  
 **Değişken**: simgesel ad başvurduğu nerede tanımlanan kapsam kodunun boyunca verilere erişmek için kullanılabilir böylece veri miktarını adı. C++ ' ta *değişkeni* diğer türleri örneklerini genellikle adlı ancak genellikle skaler veri türleri örneklerine başvurmak için kullanılan *nesneleri*.  
  
 **Nesne**: Basitlik ve tutarlılık için bu makalede terimini kullanır *nesne* başvurmak için herhangi bir örneği bir sınıf veya yapı ve genel anlamda kullanıldığında tüm türleri içerir bile skaler değişkenleri.  
  
 **POD türü** (düz eski verileri): skaler türleri için C++ içinde veri türlerinin resmi olmayan bu kategoriyi başvuruyor (temel türleri bölümüne bakın) veya *POD sınıfları*. POD olmayan statik veri üyeleri, kullanıcı tanımlı oluşturucular veya kullanıcı tanımlı atama işleçleri POD sınıfına dahil değildir. Ayrıca, bir POD sınıfının hiçbir sanal işlevi, hiçbir temel sınıfı ve hiçbir özel veya korumalı statik olmayan veri üyesi bulunmaz. POD türleri genellikle dış veri değişimi için örneğin, (yalnızca POD türleri olan) C dilinde yazılmış bir modül ile birlikte kullanılır.  
  
## <a name="specifying-variable-and-function-types"></a>Değişken ve işlev türlerini belirtme  
 C++ olan bir *kesin türü belirtilmiş* dil ve olduğunu da *statik olarak yazılan*; her nesne türüne sahip ve türü hiçbir zaman (statik veri nesneleri ile karıştırılmamalıdır) değiştirir.   
**Bir değişken bildirme zaman** kodunuzda türünü açıkça belirtmek, veya kullanmak `auto` Başlatıcı türünden türetme görevlendirin anahtar.   
**Bildirme ne zaman bir işlev** kodunuzda her bağımsız değişkeni ve onun dönüş değeri türünü belirtmeniz gerekir ya da `void` hiçbir değer işlev tarafından döndürülür. Rasgele türden bağımsız değişkenlere izin veren işlev şablonları kullandığınızda bu bir özel durumdur.  
  
 İlk kez bir değişken bildirdikten sonra belirli bir süre geçtikten sonra türünü değiştiremezsiniz. Ancak değişkenin değerini veya bir işlevin dönüş değerini başka türdeki farklı bir değişkene kopyalayabilirsiniz. Bu tür işlemler adlı *tür dönüştürmeleri*, bazen gerekli olmayan ama da olası veri kaybı veya incorrectness kaynaklardır.  
  
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
 Diğer dillerden farklı olarak, C++, diğer tüm türlerin türetildiği bir evrensel temel türe sahip değildir. Birçok dil Visual C++ uygulaması içerir *temel türleri*, olarak da bilinen *yerleşik türleri*. Bu gibi sayısal türler içerir `int`, `double`, `long`, `bool`, artı `char` ve `wchar_t` ASCII ve UNICODE karakterler için sırasıyla türleri. En temel türleri (dışında `bool`, `double`, `wchar_t` ve ilgili türleri) tüm değişkeni depolayabilir değerleri aralığı değiştirme sürümlerinde imzasız. Örneğin, bir `int`, 32 bit işaretli tamsayıyı depolayan temsil edebilen bir değer -2.147.483.648 2.147.483.647 için. Bir `unsigned int`, 32-bit da depolandığı bir değeri 0'dan 4.294.967.295 depolayabilir. Her durumda olası değerlerin toplam sayısı aynıdır; yalnızca aralık farklıdır.  
  
 Temel türler, üzerlerinde gerçekleştirebileceğiniz işlemleri ve bunların diğer temel türlere nasıl dönüştürülebileceğini yöneten yerleşik kurallara sahip derleyici tarafından tanınır. Yerleşik türler ve boyutu ve sayısal sınırlar tam listesi için bkz: [temel türleri](../cpp/fundamental-types-cpp.md).  
  
 Aşağıdaki çizim, yerleşik türlerin göreli boyutlarını gösterir:  
  
 ![Bayt cinsinden boyutu yerleşik&#45;türlerinde](../cpp/media/built-intypesizes.png "yerleşik inTYpeSizes")  
  
 Aşağıdaki tablo en sık kullanılan temel türleri listeler:  
  
|Tür|Boyut|Yorum|  
|----------|----------|-------------|  
|int|4 bayt|Tamsayı değerler için varsayılan seçim.|  
|çift|8 bayt|Kayan nokta değerleri için varsayılan seçim.|  
|bool|1 bayt|True veya false olabilen değerleri temsil eder.|  
|char|1 bayt|Daha eski C stili dizelerde veya std::string nesnelerde UNICODE'a dönüştürülmesi hiçbir zaman gerekmeyecek ASCII karakterler için kullanın.|  
|wchar_t|2 bayt|UNICODE biçiminde (Windows'ta UTF-16, diğer işletim sistemlerinde değişiklik gösterebilir) kodlanmış olabilecek "geniş" karakter değerlerini temsil eder. Bu tür dizelerde kullanılan karakter türüdür `std::wstring`.|  
|unsigned char|1 bayt|C++ sahip yerleşik bir `byte` türü.  Bayt değerini göstermek için unsigned char kullanın.|  
|unsigned int|4 bayt|Bit bayrakları için varsayılan seçimdir.|  
|long long|8 bayt|Çok büyük tamsayı değerlerini temsil eder.|  
  
## <a name="the-void-type"></a>Void türü  
 `void` Türü özel bir türü; türünde bir değişken bildiremezsiniz `void`, ancak türünde bir değişken bildirebilir `void *` (işaretçi `void`), olduğu bazen gerekli ham (atanmamış) bellek ayırırken. Ancak, işaretçiler `void` tür kullanımı uyumlu olan ve genellikle kullanımlarını modern C++'da kesinlikle kaçının. İşlevi bildiriminde bir `void` dönüş değeri anlamına gelir işlevi bir değer döndürmüyor; bu bir ortak ve kabul edilebilir kullanımını `void`. While bildirmek için sıfır parametrelere sahip C gerekli dil işlevlerini `void` parametre listesinde, örneğin, `fou(void)`, bu yöntem modern C++'da önerilmez ve bildirilmelidir `fou()`. Daha fazla bilgi için bkz: [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
## <a name="const-type-qualifier"></a>const türü niteleyici  
 Herhangi bir yerleşik veya kullanıcı tanımlı tür, const anahtar sözcük aracılığıyla nitelendirilebilir. Ek olarak, üye işlevleri olabilir `const`-tam ve hatta `const`-aşırı yüklendi. Değeri bir `const` türü başlatıldıktan sonra değiştirilemez.  
  
```cpp  
  
const double PI = 3.1415;  
PI = .75 //Error. Cannot modify const variable.  
  
```  
  
 `const` Niteleyicisi işlevi ve değişken bildirimleri yaygın olarak kullanılır ve "const doğruluk" c++ önemli bir kavram, temelde kullanılacak geldiğini `const` , derleme zamanında değerleri kasıtsız olarak değiştirilmez güvence altına almak için . Daha fazla bilgi için bkz: [const](../cpp/const-cpp.md).  
  
 A `const` türüdür kendi const olmayan sürümünden; ayrı Örneğin, `const int` öğesinden farklı bir tür `int`. C++ kullanabilirsiniz `const_cast` gerekir kaldırdığınızda bu nadir durumlarda işlecinin *const şahit* bir değişkenin. Daha fazla bilgi için bkz: [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
## <a name="string-types"></a>Dize türleri  
 NET olarak söylemek C++ dili yerleşik dize türü yok; `char` ve `wchar_t` tek karakter depolamak - sonlandırma null değer ekleme, bu tür bir dize yaklaşık bir dizi bildirmeniz gerekir (örneğin, ASCII `'\0'`) dizi öğesine bir son geçerli karakteri aşan (olarak da adlandırılan bir *C stili dize*). C stili dizeler çok daha fazla kodun yazılmasını veya harici dize yardımcı program kitaplığı işlevlerini gerektirmekteydi. Ancak modern C++'da standart kitaplığı türler sahibiz `std::string` (8 bit `char`-yazın karakter dizelerini) veya `std::wstring` (16 bit `wchar_t`-karakter dizelerini yazın). Hiçbir uyumlu C++ derleme ortamında dahil standart kitaplıkları parçası olduğundan bu C++ Standart Kitaplığı kapsayıcılar, yerel dize türleri olarak değerlendirilebilir. Yalnızca kullanmak `#include <string>` yapmayı yönergesi türleri programınızdaki kullanılabilir. (MFC veya ATL kullanıyorsanız, CString sınıfı da ayrıca kullanılabilir ancak C++ standardının bir parçası değildir.) Boş sonlandırılmış karakter dizilerinin kullanımı (daha önce bahsedilen C stili dizeler) modern C++ içinde önerilmez.  
  
## <a name="user-defined-types"></a>Kullanıcı tanımlı türler  
 Tanımladığınızda bir `class`, `struct`, `union`, veya `enum`, temel türü değilmiş gibi kodunuzun geri kalanı bu yapı kullanılır. Bellekte bilinen bir boyuta sahiptir ve derleme zamanı denetimi için, çalışma zamanında ve programınızın kullanım süresi boyunca uygulanmak üzere nasıl kullanılacağına ilişkin belirli kuralları içerir. Temel yerleşik türler ve kullanıcı tanımlı türler arasındaki temel farklar şunlardır:  
  
-   Derleyici kullanıcı tanımlı türde yerleşik bilgi içermez. İlk derleme işlemi sırasında tanımı karşılaştığında türünü öğrenir.  
  
-   Türünüz üzerinde gerçekleştirilebilecek işlemleri ve diğer türlere nasıl dönüştürülebileceğini, ilgili operatörleri sınıf üyeleri veya üye harici işlevler olarak tanımlayarak (aşırı yükleme ile) siz belirtirsiniz. Daha fazla bilgi için bkz: [işlev aşırı yüklemesi](function-overloading.md).  
  
-   Bunların statik türlü olması gerekmez (bir nesne türünün asla değişmeme kuralı). Mekanizmaları aracılığıyla *devralma* ve *çok biçimlilik*, (bir sınıfın bir nesnesi örneği olarak adlandırılır) sınıfının kullanıcı tarafından tanımlanan bir türü olarak bildirilen bir değişken farklı bir türde çalışma zamanında olması derleme zamanı. Daha fazla bilgi için bkz: [devralma](../cpp/inheritance-cpp.md).  
  
## <a name="pointer-types"></a>İşaretçi türleri  
 C dili erken sürümleri için geri dating, C++ özel bildirimcisi kullanarak bir işaretçi türünde bir değişken bildirme izin verecek şekilde devam `*` (yıldız). İşaretçi türü, gerçek veri değerinin depolandığı bellekteki konumun adresini saklar. Modern C++'da, bunlar denir *ham işaretçileri*ve kodunuzda özel işleçleri aracılığıyla erişilen `*` (yıldız) veya `->` (çizgiyle büyük-daha). Bu adlı *başvurusunun kaldırılmasının*, ve kullandığınız hangisinin bağlıdır olup, skaler bir işaretçi veya bir nesne üyesi için bir işaretçi başvurusunun kaldırılmasının üzerinde. İşaretçi türleri ile çalışma, uzun süredir C ve C++ program geliştirmenin en zor ve en kafa karıştırıcı taraflarından biri olmuştur. Bu bölümde bazı bulguları ve uygulamalar için ancak bu artık gerekli (veya önerilen) modern c++ istiyorsanız ham işaretçileri kullanmaya Yardım özetlenmektedir ham işaretçileri Nesne sahipliği hiç evrimi nedeniyle kullanmak için [akıllı işaretçi](../cpp/smart-pointers-modern-cpp.md) () "daha bu bölümün sonuna açıklanmıştır). Nesneleri gözlemlemek için ham işaretçilerin kullanılması yararlıdır; ancak, bunları nesne sahipliği için kullanmanız gerekiyorsa bunu dikkatli bir şekilde yapmanız ve bunlara sahip olan nesnelerin nasıl oluşturulduğunu ve nasıl yok edildiğini dikkatle değerlendirmeniz gerekir.  
  
 Bilmeniz gereken ilk şey, bir ham işaretçi değişkeni bildirmenin, yalnızca başvuru kaldırıldığında işaretçinin başvuracağı bellek konumunun adresini depolamak için gereken belleği ayıracağıdır. Veri değeri için bellek ayırma (olarak da bilinir *yedekleme deposu*) henüz ayrılmamış. Diğer bir deyişle, bir ham işaretçi değişkeni bildirerek gerçek bir veri değişkeni yerine bir bellek adresi değişkeni oluşturursunuz. Bir yedekleme belleğine geçerli bir adres içerdiğinden emin olmadan önce, bir işaretçi değişkeninin başvurusunun kaldırılması, programınızda tanımlanmamış bir davranışa (genellikle önemli bir hata) neden olabilir. Aşağıdaki örnek bu türde bir hata gösterir.  
  
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
  
 Yedekleme oluşturmak için düzeltilen kod örneği kullanan yerel yığın belleği depolamak `pNumber` işaret eder. Kolaylık olması için bir temel türü kullanıyoruz. Uygulamada, yedekleme deposu için işaretçileri olan dinamik olarak ayrılan bellek adı verilen bir alanda çoğu genellikle kullanıcı tanımlı türler *yığın* (veya *ücretsiz deposu*) kullanarak bir `new` anahtar sözcüğü ifade (C-style programlamada eski `malloc()` C çalışma zamanı kitaplığı işlevi kullanıldı). Bir sınıf tanımı üzerinde özellikle temel alıyorsa ayrılan sonra bu değişkenler genellikle nesneler olarak bilinir. İle ayrılan bellek `new` karşılık gelen tarafından silinmelidir `delete` deyimi (veya kullandıysanız `malloc()` , C çalışma zamanı işlevi ayrılacak işlevi `free()`).  
  
 Ancak, bir dinamik olarak ayrılan nesnesi-adlı bir kaynak hataya neden olan özellikle karmaşık kodda silmeyi unutursanız kolay bir *bellek sızıntısı*. Bu nedenle, ham işaretçilerin modern C++'ta kullanılması önerilmez. Neredeyse her zaman bir ham işaretçi sarmalamak daha iyi bir [akıllı işaretçi](../cpp/smart-pointers-modern-cpp.md), hangi otomatik olarak yayın bellek (kod akıllı işaretçi için kapsam dışına çıktığında) kendi yıkıcı çağrıldığında; akıllı işaretçiler kullanarak, neredeyse C++ programlarında hataların tam bir sınıf ortadan kaldırır. Aşağıdaki örnekte, varsayalım `MyClass` genel yöntem kullanıcı tarafından tanımlanan bir türü `DoSomeWork();`  
  
```cpp  
  
void someFunction() {  
    unique_ptr<MyClass> pMc(new MyClass);  
    pMc->DoSomeWork();  
}  
  // No memory leak. Out-of-scope automatically calls the destructor  
  // for the unique_ptr, freeing the resource.  
  
```  
  
 Akıllı işaretçiler hakkında daha fazla bilgi için bkz: [akıllı işaretçiler](../cpp/smart-pointers-modern-cpp.md).  
  
 İşaretçi dönüşümleri hakkında daha fazla bilgi için bkz: [tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md).  
  
 Genel olarak, işaretçiler hakkında daha fazla bilgi için bkz [işaretçileri](../cpp/pointers-cpp.md).  
  
## <a name="windows-data-types"></a>Windows veri türleri  
 C ve C++ için Klasik Win32 programlamada çoğu işlevleri Windows'a özgü tür tanımları kullanın ve # makroları define (tanımlanan `windef.h`) ve dönüş değerleri parametre türlerini belirtmek için. Bu Windows veri türleri genellikle C/C++ yerleşik türleri için verilen yalnızca özel (diğer adlar) adlardır. Bu tür tanımları ve önişlemci tanımları tam listesi için bkz: [Windows veri türleri](http://msdn.microsoft.com/en-us/4553cafc-450e-4493-a4d4-cb6e2f274d46). HRESULT ve LCID gibi bu tür tanımlarından bazıları kullanışlı ve açıklayıcıdır. INT gibi diğerlerinin özel bir anlamı yoktur ve bunlar yalnızca temel C++ türlerinin diğer adlarıdır. Diğer Windows veri türleri C programlama ve 16-bit işlemci günlerinden kalma adlara sahiptir ve bu adların modern donanım veya işletim sistemlerinde herhangi bir amacı ya da anlamı yoktur. Ayrıca özel veri türleri olarak listelenen Windows çalışma zamanı kitaplığı ile ilişkili olan [Windows çalışma zamanı temel veri türlerini](http://msdn.microsoft.com/en-us/b5735851-ec07-48c1-92b4-ca9f768096f6). Modern C++ programlamada, Windows türü değerin nasıl yorumlanacağına ilişkin ek anlamlar iletmedikçe C++ temel türlerinin tercih edilmesi genel bir yönergedir.  
  
## <a name="more-information"></a>Daha fazla bilgi  
 C++ tür sistemi hakkında daha fazla bilgi için aşağıdaki konulara bakın.  
  
|||  
|-|-|  
|[Değer Türleri](../cpp/value-types-modern-cpp.md)|Açıklar *değer türleri* bunların kullanılması ile ilgili sorunları.|  
|[Tür dönüştürmeleri ve tür güvenliği](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Ortak tür dönüştürme sorunlarını açıklar ve bunları nasıl engelleyeceğinizi gösterir.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ için yeniden Hoş Geldiniz](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C++ Dil Başvurusu](../cpp/cpp-language-reference.md)   
 [C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
