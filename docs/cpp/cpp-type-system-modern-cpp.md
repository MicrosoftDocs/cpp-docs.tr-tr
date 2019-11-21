---
title: C++ type system
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 553c0ed6-77c4-43e9-87b1-c903eec53e80
ms.openlocfilehash: 1f12f7505438dc995aaf8a045fd903488e9ff092
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2019
ms.locfileid: "74246596"
---
# <a name="c-type-system"></a>C++ type system

The concept of *type* is very important in C++. Her değişken, işlev bağımsız değişkeni ve işlev dönüş değeri; derlenebilmeleri için bir türe sahip olmalıdır. Ayrıca, her ifadeye (değişmez değerler dahil), değerlendirilmeden önce derleyicisi tarafından dolaylı olarak bir tür tanımlanır. Some examples of types include **int** to store integral values, **double** to store floating-point values (also known as *scalar* data types), or the Standard Library class [std::basic_string](../standard-library/basic-string-class.md) to store text. You can create your own type by defining a **class** or **struct**. Tür, değişken (veya ifade sonucu) için atanacak bellek miktarını, bu değişkende depolanabilecek değer türlerini, bu değerlerin (bit modelleri olarak) nasıl yorumlanacağını ve gerçekleştirilebilecek işlemleri belirtir. Bu makale, C++ tür sistemiyle ilgili önemli özellikleri basit bir şekilde inceler.

## <a name="terminology"></a>Terminoloji

**Variable**: The symbolic name of a quantity of data so that the name can be used to access the data it refers to throughout the scope of the code where it is defined. In C++, *variable* is generally used to refer to instances of scalar data types, whereas instances of other types are usually called *objects*.

**Object**: For simplicity and consistency, this article uses the term *object* to refer to any instance of a class or structure, and when it is used in the general sense includes all types, even scalar variables.

**POD type** (plain old data): This informal category of data types in C++ refers to types that are scalar (see the Fundamental types section) or are *POD classes*. POD olmayan statik veri üyeleri, kullanıcı tanımlı oluşturucular veya kullanıcı tanımlı atama işleçleri POD sınıfına dahil değildir. Ayrıca, bir POD sınıfının hiçbir sanal işlevi, hiçbir temel sınıfı ve hiçbir özel veya korumalı statik olmayan veri üyesi bulunmaz. POD türleri genellikle dış veri değişimi için örneğin, (yalnızca POD türleri olan) C dilinde yazılmış bir modül ile birlikte kullanılır.

## <a name="specifying-variable-and-function-types"></a>Değişken ve işlev türlerini belirtme

C++ is a *strongly typed* language and it is also *statically-typed*; every object has a type and that type never changes (not to be confused with static data objects).
**When you declare a variable** in your code, you must either specify its type explicitly, or use the **auto** keyword to instruct the compiler to deduce the type from the initializer.
**When you declare a function** in your code, you must specify the type of each argument and its return value, or **void** if no value is returned by the function. Rasgele türden bağımsız değişkenlere izin veren işlev şablonları kullandığınızda bu bir özel durumdur.

İlk kez bir değişken bildirdikten sonra belirli bir süre geçtikten sonra türünü değiştiremezsiniz. Ancak değişkenin değerini veya bir işlevin dönüş değerini başka türdeki farklı bir değişkene kopyalayabilirsiniz. Such operations are called *type conversions*, which are sometimes necessary but are also potential sources of data loss or incorrectness.

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

Diğer dillerden farklı olarak, C++, diğer tüm türlerin türetildiği bir evrensel temel türe sahip değildir. The language includes many *fundamental types*, also known as *built-in types*. This includes numeric types such as **int**, **double**, **long**, **bool**, plus the **char** and **wchar_t** types for ASCII and UNICODE characters, respectively. Most fundamental types (except **bool**, **double**, **wchar_t** and related types) all have unsigned versions, which modify the range of values that the variable can store. For example, an **int**, which stores a 32-bit signed integer, can represent a value from -2,147,483,648 to 2,147,483,647. An **unsigned int**, which is also stored as 32-bits, can store a value from 0 to 4,294,967,295. Her durumda olası değerlerin toplam sayısı aynıdır; yalnızca aralık farklıdır.

Temel türler, üzerlerinde gerçekleştirebileceğiniz işlemleri ve bunların diğer temel türlere nasıl dönüştürülebileceğini yöneten yerleşik kurallara sahip derleyici tarafından tanınır. For a complete list of built-in types and their size and numeric limits, see [Fundamental Types](../cpp/fundamental-types-cpp.md).

Aşağıdaki çizim, yerleşik türlerin göreli boyutlarını gösterir:

![Size in bytes of built&#45;in types](../cpp/media/built-intypesizes.png "Size in bytes of built&#45;in types")

Aşağıdaki tablo en sık kullanılan temel türleri listeler:

|Tür|Boyut|Yorum|
|----------|----------|-------------|
|int|4 bayt|Tamsayı değerler için varsayılan seçim.|
|çift|8 bytes|Kayan nokta değerleri için varsayılan seçim.|
|bool|1 bayt|True veya false olabilen değerleri temsil eder.|
|char|1 bayt|Daha eski C stili dizelerde veya std::string nesnelerde UNICODE'a dönüştürülmesi hiçbir zaman gerekmeyecek ASCII karakterler için kullanın.|
|wchar_t|2 bytes|UNICODE biçiminde (Windows'ta UTF-16, diğer işletim sistemlerinde değişiklik gösterebilir) kodlanmış olabilecek "geniş" karakter değerlerini temsil eder. This is the character type that is used in strings of type `std::wstring`.|
|unsigned&nbsp;char|1 bayt|C++ has no built-in `byte` type.  Bayt değerini göstermek için unsigned char kullanın.|
|unsigned int|4 bayt|Bit bayrakları için varsayılan seçimdir.|
|long long|8 bytes|Çok büyük tamsayı değerlerini temsil eder.|

## <a name="the-void-type"></a>Void türü

The **void** type is a special type; you cannot declare a variable of type **void**, but you can declare a variable of type __void \*__ (pointer to **void**), which is sometimes necessary when allocating raw (un-typed) memory. However, pointers to **void** are not type-safe and generally their use is strongly discouraged in modern C++. In a function declaration, a **void** return value means that the function does not return a value; this is a common and acceptable use of **void**. While the C language required functions that have zero parameters to declare **void** in the parameter list, for example, `fou(void)`, this practice is discouraged in modern C++ and should be declared `fou()`. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="const-type-qualifier"></a>const türü niteleyici

Herhangi bir yerleşik veya kullanıcı tanımlı tür, const anahtar sözcük aracılığıyla nitelendirilebilir. Additionally, member functions may be **const**-qualified and even **const**-overloaded. The value of a **const** type cannot be modified after it is initialized.

```cpp

const double PI = 3.1415;
PI = .75 //Error. Cannot modify const variable.
```

The **const** qualifier is used extensively in function and variable declarations and "const correctness" is an important concept in C++; essentially it means to use **const** to guarantee, at compile time, that values are not modified unintentionally. For more information, see [const](../cpp/const-cpp.md).

A **const** type is distinct from its non-const version; for example, **const int** is a distinct type from **int**. You can use the C++ **const_cast** operator on those rare occasions when you must remove *const-ness* from a variable. For more information, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

## <a name="string-types"></a>Dize türleri

Strictly speaking, the C++ language has no built-in string type; **char** and **wchar_t** store single characters - you must declare an array of these types to approximate a string, adding a terminating null value (for example, ASCII `'\0'`) to the array element one past the last valid character (also called a *C-style string*). C stili dizeler çok daha fazla kodun yazılmasını veya harici dize yardımcı program kitaplığı işlevlerini gerektirmekteydi. But in modern C++, we have the Standard Library types `std::string` (for 8-bit **char**-type character strings) or `std::wstring` (for 16-bit **wchar_t**-type character strings). These C++ Standard Library containers can be thought of as native string types because they are part of the standard libraries that are included in any compliant C++ build environment. Simply use the `#include <string>` directive to make these types available in your program. (If you are using MFC or ATL, the CString class is also available, but is not part of the C++ standard.) The use of null-terminated character arrays (the C-style strings previously mentioned) is strongly discouraged in modern C++.

## <a name="user-defined-types"></a>Kullanıcı tanımlı türler

When you define a **class**, **struct**, **union**, or **enum**, that construct is used in the rest of your code as if it were a fundamental type. Bellekte bilinen bir boyuta sahiptir ve derleme zamanı denetimi için, çalışma zamanında ve programınızın kullanım süresi boyunca uygulanmak üzere nasıl kullanılacağına ilişkin belirli kuralları içerir. Temel yerleşik türler ve kullanıcı tanımlı türler arasındaki temel farklar şunlardır:

- Derleyici kullanıcı tanımlı türde yerleşik bilgi içermez. It learns of the type when it first encounters the definition during the compilation process.

- Türünüz üzerinde gerçekleştirilebilecek işlemleri ve diğer türlere nasıl dönüştürülebileceğini, ilgili operatörleri sınıf üyeleri veya üye harici işlevler olarak tanımlayarak (aşırı yükleme ile) siz belirtirsiniz. For more information, see [Function Overloading](function-overloading.md)

## <a name="pointer-types"></a>İşaretçi türleri

Dating back to the earliest versions of the C language, C++ continues to let you declare a variable of a pointer type by using the special declarator `*` (asterisk). İşaretçi türü, gerçek veri değerinin depolandığı bellekteki konumun adresini saklar. In modern C++, these are referred to as *raw pointers*, and are accessed in your code through special operators `*` (asterisk) or `->` (dash with greater-than). This is called *dereferencing*, and which one that you use depends on whether you are dereferencing a pointer to a scalar or a pointer to a member in an object. İşaretçi türleri ile çalışma, uzun süredir C ve C++ program geliştirmenin en zor ve en kafa karıştırıcı taraflarından biri olmuştur. This section outlines some facts and practices to help use raw pointers if you want to, but in modern C++ it’s no longer required (or recommended) to use raw pointers for object ownership at all, due to the evolution of the [smart pointer](../cpp/smart-pointers-modern-cpp.md) (discussed more at the end of this section). Nesneleri gözlemlemek için ham işaretçilerin kullanılması yararlıdır; ancak, bunları nesne sahipliği için kullanmanız gerekiyorsa bunu dikkatli bir şekilde yapmanız ve bunlara sahip olan nesnelerin nasıl oluşturulduğunu ve nasıl yok edildiğini dikkatle değerlendirmeniz gerekir.

Bilmeniz gereken ilk şey, bir ham işaretçi değişkeni bildirmenin, yalnızca başvuru kaldırıldığında işaretçinin başvuracağı bellek konumunun adresini depolamak için gereken belleği ayıracağıdır. Allocation of the memory for the data value itself (also called *backing store*) is not yet allocated. Diğer bir deyişle, bir ham işaretçi değişkeni bildirerek gerçek bir veri değişkeni yerine bir bellek adresi değişkeni oluşturursunuz. Bir yedekleme belleğine geçerli bir adres içerdiğinden emin olmadan önce, bir işaretçi değişkeninin başvurusunun kaldırılması, programınızda tanımlanmamış bir davranışa (genellikle önemli bir hata) neden olabilir. Aşağıdaki örnek bu türde bir hata gösterir.

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

The corrected code example uses local stack memory to create the backing store that `pNumber` points to. Kolaylık olması için bir temel türü kullanıyoruz. In practice, the backing store for pointers are most often user-defined types that are dynamically-allocated in an area of memory called the *heap* (or *free store*) by using a **new** keyword expression (in C-style programming, the older `malloc()` C runtime library function was used). Once allocated, these variables are usually referred to as objects, especially if they are based on a class definition. Memory that is allocated with **new** must be deleted by a corresponding **delete** statement (or, if you used the `malloc()` function to allocate it, the C runtime function `free()`).

However, it is easy to forget to delete a dynamically-allocated object- especially in complex code, which causes a resource bug called a *memory leak*. Bu nedenle, ham işaretçilerin modern C++'ta kullanılması önerilmez. It is almost always better to wrap a raw pointer in a [smart pointer](../cpp/smart-pointers-modern-cpp.md), which will automatically release the memory when its destructor is invoked (when the code goes out of scope for the smart pointer); by using smart pointers you virtually eliminate a whole class of bugs in your C++ programs. In the following example, assume `MyClass` is a user-defined type that has a public method `DoSomeWork();`

```cpp
void someFunction() {
    unique_ptr<MyClass> pMc(new MyClass);
    pMc->DoSomeWork();
}
  // No memory leak. Out-of-scope automatically calls the destructor
  // for the unique_ptr, freeing the resource.
```

For more information about smart pointers, see [Smart Pointers](../cpp/smart-pointers-modern-cpp.md).

For more information about pointer conversions, see [Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md).

For more information about pointers in general, see [Pointers](../cpp/pointers-cpp.md).

## <a name="windows-data-types"></a>Windows veri türleri

In classic Win32 programming for C and C++, most functions use Windows-specific typedefs and #define macros (defined in `windef.h`) to specify the types of parameters and return values. These Windows data types are mostly just special names (aliases) given to C/C++ built-in types. For a complete list of these typedefs and preprocessor definitions, see [Windows Data Types](/windows/win32/WinProg/windows-data-types). HRESULT ve LCID gibi bu tür tanımlarından bazıları kullanışlı ve açıklayıcıdır. INT gibi diğerlerinin özel bir anlamı yoktur ve bunlar yalnızca temel C++ türlerinin diğer adlarıdır. Diğer Windows veri türleri C programlama ve 16-bit işlemci günlerinden kalma adlara sahiptir ve bu adların modern donanım veya işletim sistemlerinde herhangi bir amacı ya da anlamı yoktur. There are also special data types associated with the Windows Runtime Library, listed as [Windows Runtime base data types](/windows/win32/WinRT/base-data-types). Modern C++ programlamada, Windows türü değerin nasıl yorumlanacağına ilişkin ek anlamlar iletmedikçe C++ temel türlerinin tercih edilmesi genel bir yönergedir.

## <a name="more-information"></a>Daha fazla bilgi

C++ tür sistemi hakkında daha fazla bilgi için aşağıdaki konulara bakın.

|||
|-|-|
|[Değer Türleri](../cpp/value-types-modern-cpp.md)|Describes *value types* along with issues relating to their use.|
|[Type Conversions and Type Safety](../cpp/type-conversions-and-type-safety-modern-cpp.md)|Ortak tür dönüştürme sorunlarını açıklar ve bunları nasıl engelleyeceğinizi gösterir.|

## <a name="see-also"></a>Ayrıca bkz.

[Welcome back to C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
