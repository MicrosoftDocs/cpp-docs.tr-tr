---
title: '&lt;özel durum&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- exception/std::current_exception
- exception/std::get_terminate
- exception/std::get_unexpected
- exception/std::make_exception_ptr
- exception/std::rethrow_exception
- exception/std::set_terminate
- exception/std::set_unexpected
- exception/std::terminate
- exception/std::uncaught_exception
- exception/std::unexpected
ms.assetid: c09ac569-5e35-4fe8-872d-ca5810274dd7
helpviewer_keywords:
- std::current_exception [C++]
- std::get_terminate [C++]
- std::get_unexpected [C++]
- std::make_exception_ptr [C++]
- std::rethrow_exception [C++]
- std::set_terminate [C++]
- std::set_unexpected [C++]
- std::terminate [C++]
- std::uncaught_exception [C++]
- std::unexpected [C++]
ms.openlocfilehash: 4aab46fa771b88d1baad311aa631a57afce4911e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847835"
---
# <a name="ltexceptiongt-functions"></a>&lt;özel durum&gt; işlevleri

||||
|-|-|-|
|[current_exception](#current_exception)|[get_terminate](#get_terminate)|[get_unexpected](#get_unexpected)|
|[make_exception_ptr](#make_exception_ptr)|[rethrow_exception](#rethrow_exception)|[set_terminate](#set_terminate)|
|[set_unexpected](#set_unexpected)|[Sonlandırma](#terminate)|[uncaught_exception](#uncaught_exception)|
|[beklenmeyen](#unexpected)|

## <a name="current_exception"></a>  current_exception

Geçerli özel durum için bir akıllı işaretçi alır.

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>Dönüş Değeri

Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) geçerli özel durumu işaret eden nesne.

### <a name="remarks"></a>Açıklamalar

Çağrı `current_exception` işlevi bir catch bloğu içinde. Uçuş modunda bir özel durum ise ve catch bloğu özel durum yakalayabilir `current_exception` işlev döndürür bir `exception_ptr` başvuruda bulunan özel durum nesnesi. Aksi takdirde işlevi null değeri döndürür `exception_ptr` nesnesi.

`current_exception` İşlevi yakalar mı bağımsız olarak yürütülen özel durum `catch` deyimi belirten bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) deyimi.

Geçerli özel durumun yıkıcı sonunda çağrılır `catch` , özel durumun yeniden oluşturulması değil, engelleyin. Ancak, bile çağırırsanız `current_exception` işlev yıkıcı işlevi döndürür bir `exception_ptr` geçerli özel durumun başvuran nesne.

Art arda çağrılar `current_exception` işlev dönüş `exception_ptr` geçerli özel durumun farklı kopyalarını başvuran nesneleri. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

## <a name="make_exception_ptr"></a>  make_exception_ptr

Oluşturur bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) bir özel durum bir kopyasını içeren nesne.

```cpp
template <class E>
exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>Parametreler

`Except` Kopyalamak için özel durum ile sınıf. Genellikle, belirttiğiniz bir [özel durum sınıfı](../standard-library/exception-class.md) bağımsız değişkeni olarak nesne `make_exception_ptr` herhangi bir sınıf nesnesi bağımsız değişkeni olsa da, işlev.

### <a name="return-value"></a>Dönüş Değeri

Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) nesnesi için geçerli özel durumun bir kopyasını işaret eden `Except`.

### <a name="remarks"></a>Açıklamalar

Çağırma `make_exception_ptr` işlevi C++ özel durum atma, bir catch bloğu içinde yakalama ve ardından çağırmak için eşdeğer [current_exception](../standard-library/exception-functions.md#current_exception) döndürülecek işlevi bir `exception_ptr` başvuruda bulunan özel durum nesnesi. Microsoft uyarlamasını `make_exception_ptr` işlevidir atma ve bir özel durum yakalama daha verimlidir.

Bir uygulama tarafından genellikle gerektirmez `make_exception_ptr` işlevi ve biz kullanımı önerilmemektedir.

## <a name="rethrow_exception"></a>  rethrow_exception

Bir parametre olarak geçirilen bir özel durum oluşturur.

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>Parametreler

`P` Yeniden vermesini Yakalanan özel durum. Varsa `P` bir null [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), işlev oluşturur [std::bad_exception](../standard-library/bad-exception-class.md).

### <a name="remarks"></a>Açıklamalar

Yakalanan bir özel durum depolamak sonra bir `exception_ptr` nesnesi, birincil iş parçacığı nesne işleyebilir. Birincil iş parçacığı arama `rethrow_exception` ile birlikte çalışması `exception_ptr` nesnesi bağımsız değişkeni olarak. `rethrow_exception` İşlevi ayıklar özel durumundan `exception_ptr` nesne ve ardından birincil iş parçacığının bağlamında özel durum oluşturur.

## <a name="get_terminate"></a>  get_terminate

Geçerli edinir `terminate_handler` işlevi.

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a>  set_terminate

Yeni bir kurar `terminate_handler` program sonlandırma sırasında çağrılabilir.

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

`fnew` Sonlandırmanın çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırmanın çağrılması için kullanılan önceki işlevi adresi.

### <a name="remarks"></a>Açıklamalar

Yeni bir işlev oluşturur [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler) işlevi olarak * `fnew`. Bu nedenle, `fnew` null işaretçi olmaması gerekir. Önceki adresini işlevi döndürür işleyici sonlandırılacak.

### <a name="example"></a>Örnek

```cpp
// exception_set_terminate.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void termfunction()
{
    cout << "My terminate function called." << endl;
    abort();
}

int main()
{
    terminate_handler oldHandler = set_terminate(termfunction);

    // Throwing an unhandled exception would also terminate the program
    // or we could explicitly call terminate();

    //throw bad_alloc();
    terminate();
}

```

## <a name="get_unexpected"></a>  get_unexpected

Geçerli edinir `unexpected_handler` işlevi.

```cpp
unexpected_handler get_unexpected();
```

## <a name="set_unexpected"></a>  set_unexpected

Yeni bir kurar `unexpected_handler` olması için ne zaman beklenmeyen bir özel durum karşılaştı.

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

`fnew` Beklenmeyen bir özel durum oluştuğunda çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Önceki adresini `unexpected_handler`.

### <a name="remarks"></a>Açıklamalar

`fnew` null işaretçinin olması gerekir.

C++ Standart gerektiren `unexpected` bir işlev kendi throw listesinde yer almayan bir özel durum oluşturduğunda olarak adlandırılır. Geçerli uygulama bu desteklemez. Aşağıdaki örnek çağrıları `unexpected` doğrudan sonra çağıran `unexpected_handler`.

### <a name="example"></a>Örnek

```cpp
// exception_set_unexpected.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>

using namespace std;

void uefunction()
{
    cout << "My unhandled exception function called." << endl;
    terminate(); // this is what unexpected() calls by default
}

int main()
{
    unexpected_handler oldHandler = set_unexpected(uefunction);

    unexpected(); // library function to force calling the
                  // current unexpected handler
}

```

## <a name="terminate"></a>  Sonlandırma

Bir sonlandırıcı işleyici çağırır.

```cpp
void terminate();
```

### <a name="remarks"></a>Açıklamalar

Bir işlev türü bir sonlandırma işleyicisi işlevi çağırır `void`. Varsa **Sonlandır** doğrudan program tarafından sonlandırma işleyicisi adlı bir en son yapılan bir çağrı tarafından ayarlanan [set_terminate](../standard-library/exception-functions.md#set_terminate). Varsa **Sonlandır** çağrılır herhangi bir throw ifadesi değerlendirmesi sırasında diğer çeşitli nedenlerle sonlandırma işleyicisi bir throw deyimi hemen değerlendirdikten sonra etkindir.

Sonlandırma işleyicisi çağırıcısına döndürmeyebilir. Program başlangıcında çağıran bir işlev Sonlandır işleyicisidir **abort**.

### <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek **sonlandırmak**.

## <a name="uncaught_exception"></a>  uncaught_exception

Döndürür `true` oluşturulan bir özel durum yalnızca şu anda işleniyor durumunda.

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür `true` değerlendirme throw ifadesinin ve özel durum bildirimi eşleşen işleyici veya arama başlatılması tamamlanmadan önce tamamladıktan sonra [beklenmeyen](../standard-library/exception-functions.md#unexpected) throw ifadesi sonucu. Özellikle, `uncaught_exception` döndürülecek `true` bir özel durum geriye doğru izleme sırasında çağrılan bir yıkıcı çağrıldığında. Aygıtlarda, `uncaught_exception` yalnızca Windows CE 5.00 ve Windows Mobile 2005 platformları da dahil olmak üzere daha sonraki sürümler desteklenir.

### <a name="example"></a>Örnek

```cpp
// exception_uncaught_exception.cpp
// compile with: /EHsc
#include <exception>
#include <iostream>
#include <string>

class Test
{
public:
   Test( std::string msg ) : m_msg( msg )
   {
      std::cout << "In Test::Test(\"" << m_msg << "\")" << std::endl;
   }
   ~Test( )
   {
      std::cout << "In Test::~Test(\"" << m_msg << "\")" << std::endl
         << "        std::uncaught_exception( ) = "
         << std::uncaught_exception( )
         << std::endl;
   }
private:
    std::string m_msg;
};

// uncaught_exception will be true in the destructor
// for the object created inside the try block because
// the destructor is being called as part of the unwind.

int main( void )
   {
      Test t1( "outside try block" );
      try
      {
         Test t2( "inside try block" );
         throw 1;
      }
      catch (...) {
   }
}
```

```Output
In Test::Test("outside try block")
In Test::Test("inside try block")
In Test::~Test("inside try block")
        std::uncaught_exception( ) = 1
In Test::~Test("outside try block")
        std::uncaught_exception( ) = 0
```

## <a name="unexpected"></a>  beklenmeyen

Beklenmeyen işleyiciyi çağırır.

```cpp
void unexpected();
```

### <a name="remarks"></a>Açıklamalar

C++ Standart gerektiren `unexpected` bir işlev kendi throw listesinde yer almayan bir özel durum oluşturduğunda olarak adlandırılır. Geçerli uygulama bu desteklemez. Örnek aramalar `unexpected` çağıran doğrudan beklenmeyen işleyici.

Bir işlev türünde beklenmeyen bir işleyici işlevi çağırır `void`. Varsa `unexpected` doğrudan program tarafından beklenmeyen işleyici adlı bir en son yapılan bir çağrı tarafından ayarlanan [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

Beklenmeyen bir işleyici çağırıcısına döndürmeyebilir. Yürütme tarafından sonlandırabilir:

- Özel durum belirtimi veya herhangi bir türde bir nesne beklenmeyen işleyici doğrudan program tarafından çağrıldıklarında listelenen türünde bir nesne oluşturma.

- Türünde bir nesne atma [bad_exception](../standard-library/bad-exception-class.md).

- Çağırma [sonlandırmak](../standard-library/exception-functions.md#terminate), **abort** veya **çıkmak**( `int`).

Program başlatma sırasında beklenmeyen çağıran bir işlev işleyicidir [sonlandırmak](../standard-library/exception-functions.md#terminate).

### <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek **beklenmeyen.**

## <a name="see-also"></a>Ayrıca bkz.

[\<Özel Durum >](../standard-library/exception.md)<br/>
