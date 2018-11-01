---
title: '&lt;özel durum&gt; işlevleri'
ms.date: 11/04/2016
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
ms.openlocfilehash: 5bd05bbd16ee8bbd021fd6a3e0d88fec16729d39
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567004"
---
# <a name="ltexceptiongt-functions"></a>&lt;özel durum&gt; işlevleri

||||
|-|-|-|
|[current_exception](#current_exception)|[get_terminate](#get_terminate)|[get_unexpected](#get_unexpected)|
|[make_exception_ptr](#make_exception_ptr)|[rethrow_exception](#rethrow_exception)|[set_terminate](#set_terminate)|
|[set_unexpected](#set_unexpected)|[sonlandırma](#terminate)|[uncaught_exception](#uncaught_exception)|
|[beklenmeyen](#unexpected)|

## <a name="current_exception"></a>  current_exception

Geçerli özel durum için bir akıllı işaretçi alır.

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>Dönüş Değeri

Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) geçerli özel durumu gösteren nesne.

### <a name="remarks"></a>Açıklamalar

Çağrı `current_exception` işlevi bir catch bloğu içinde. Bir özel durum uçuştaysa ve yakalama bloğu özel durumu yakalayabilir `current_exception` işlevinin döndürdükleriyle bir `exception_ptr` özel duruma başvuran bir nesne. Aksi halde, işlev null döndürür `exception_ptr` nesne.

`current_exception` İşlevi yakalayan özel durum uçuştaki **catch** deyimi belirtir bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) deyimi.

Sonunda geçerli özel durumun yok Edicisi çağrılır **catch** özel durum oluşturmazsanız engelleyin. Ancak, çağırsanız bile `current_exception` işlevini yok edici içinde işlevi döndürür bir `exception_ptr` geçerli özel duruma başvuran bir nesne.

Art arda çağrılar `current_exception` işlev dönüş `exception_ptr` geçerli özel durumun farklı kopyalara başvuran nesneler. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

## <a name="make_exception_ptr"></a>  make_exception_ptr

Oluşturur bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) bir özel durumun kopyasını tutan nesne.

```cpp
template <class E>
exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>Parametreler

*Dışında*<br/>
Kopyalanacak özel duruma sahip sınıf. Genellikle, belirttiğiniz bir [özel durum sınıfı](../standard-library/exception-class.md) bağımsız değişkeni olarak bir nesne `make_exception_ptr` herhangi bir sınıf nesnesi bağımsız değişken olsa da, işlev.

### <a name="return-value"></a>Dönüş Değeri

Bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) nesne için geçerli olan özel bir kopyasına işaret eden *dışında*.

### <a name="remarks"></a>Açıklamalar

Çağırma `make_exception_ptr` işlev, bir C++ özel durum, bir catch bloğunda yakalamaya ve sonra çağırma eşdeğer [current_exception](../standard-library/exception-functions.md#current_exception) işlevini bir `exception_ptr` özel duruma başvuran bir nesne. Microsoft uyarlamasını `make_exception_ptr` işlevi oluşturmak ve ardından bir özel durum yakalamak daha verimlidir.

Bir uygulama genellikle gerektirmez `make_exception_ptr` işlevi ve kullanımı önerilmez.

## <a name="rethrow_exception"></a>  rethrow_exception

Bir parametre olarak geçirilen bir özel durum oluşturur.

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Yeniden oluşturulması için bir özel durum yakalandı. Varsa *P* null [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), işlevin [gt; Std::bad_exception &](../standard-library/bad-exception-class.md).

### <a name="remarks"></a>Açıklamalar

Yakalanan bir özel durumu depolamanızın ardından bir `exception_ptr` nesnesi, birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığı çağrı `rethrow_exception` ile birlikte çalışması `exception_ptr` ve bağımsız değişkeni olarak. `rethrow_exception` İşlevi, özel durumun ayıklar `exception_ptr` nesnesi ve ardından birincil iş parçacığının bağlamında özel durumu oluşturur.

## <a name="get_terminate"></a>  get_terminate

Geçerli alır `terminate_handler` işlevi.

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a>  set_terminate

Yeni bir kurar `terminate_handler` program sonlandırıldığında çağrılabilir.

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

*fnew*<br/>
Sonlandırma sırasında çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırma sırasında çağrılması için kullanılan önceki işlevi adresi.

### <a name="remarks"></a>Açıklamalar

Yeni bir işlev oluşturur [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler) işlevi olarak * *fnew*. Bu nedenle, *fnew* bir null işaretçi olmamalıdır. Önceki adresini işlevi döndürür sonlandırma işleyicisi.

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

Geçerli alır `unexpected_handler` işlevi.

```cpp
unexpected_handler get_unexpected();
```

## <a name="set_unexpected"></a>  set_unexpected

Yeni bir kurar `unexpected_handler` olacak şekilde, beklenmeyen bir özel durumla karşılaştı.

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

*fnew*<br/>
Beklenmeyen bir özel durum oluştuğunda çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Önceki adresini `unexpected_handler`.

### <a name="remarks"></a>Açıklamalar

*fnew* bir null işaretçi olmamalıdır.

C++ Standart gerektiren `unexpected` bir işlev, throw listede yer almayan bir özel durum oluşturduğunda çağrılır. Geçerli uygulama bu desteklemez. Aşağıdaki örnek çağrıları `unexpected` doğrudan, sonra çağıran `unexpected_handler`.

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

## <a name="terminate"></a>  sonlandırma

Bir sonlandırıcı işleyici çağırır.

```cpp
void terminate();
```

### <a name="remarks"></a>Açıklamalar

İşlevi bir işlev türünün bir sonlandırıcı işleyici çağırır **void**. Varsa `terminate` doğrudan program tarafından Sonlandırıcı işleyici olarak adlandırılan bir en son yapılan bir çağrıyla ayarlanır [set_terminate](../standard-library/exception-functions.md#set_terminate). Varsa `terminate` çağrılır herhangi bir throw ifadesi değerlendirmesi sırasında çeşitli nedenlerle Sonlandırıcı işleyici bir throw deyimi hemen değerlendirdikten sonra etkindir.

Bir sonlandırıcı işleyici çağırıcısına döndürmeyebilir. Program başlangıcında, sonlandırıcı işleyici çağırır işlevidir `abort`.

### <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek `terminate`.

## <a name="uncaught_exception"></a>  uncaught_exception

Döndürür **true** yalnızca oluşan bir özel durum şu anda işleniyorsa.

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>Dönüş Değeri

Döndürür **true** throw ifadesi ve bir özel durum bildirimi eşleşen işleyici veya arama başlatılması tamamlanmadan önce değerlendirmeyi tamamladıktan sonra [beklenmeyen](../standard-library/exception-functions.md#unexpected) sonucu olarak throw ifadesi. Özellikle, `uncaught_exception` döndüreceği **true** bir özel durumu geriye doğru izleme sırasında çağrılan bir yok edici çağrıldığında. Cihazlarda `uncaught_exception` yalnızca Windows CE 5.00 ve Windows Mobile 2005 platformları dahil olmak üzere daha yüksek sürümlerinde desteklenir.

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

Beklenmeyen bir işleyici çağırır.

```cpp
void unexpected();
```

### <a name="remarks"></a>Açıklamalar

C++ Standart gerektiren `unexpected` bir işlev, throw listede yer almayan bir özel durum oluşturduğunda çağrılır. Geçerli uygulama bu desteklemez. Örnek aramalar `unexpected` çağıran doğrudan, beklenmeyen bir işleyici.

Beklenmeyen bir işleyici, bir işlev türü işlev çağrıları **void**. Varsa `unexpected` doğrudan program tarafından beklenmeyen bir işleyici olarak adlandırılan bir en son yapılan bir çağrıyla ayarlanır [set_unexpected](../standard-library/exception-functions.md#set_unexpected).

Beklenmeyen bir işleyici çağırıcısına döndürmeyebilir. Yürütme onu Sıfırla sonlandıramayan:

- Özel durum belirtimi veya herhangi bir türde bir nesne doğrudan program tarafından beklenmeyen bir işleyici çağrılırsa listelenen bir türde bir nesne oluşturma.

- Türünde bir nesne [bad_exception](../standard-library/bad-exception-class.md).

- Çağırma [sonlandırmak](../standard-library/exception-functions.md#terminate), `abort` veya **çıkmak**(`int`).

Program başlangıcında beklenmeyen bir işleyici çağıran bir işlev olan [sonlandırmak](../standard-library/exception-functions.md#terminate).

### <a name="example"></a>Örnek

Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek `unexpected`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Özel Durum >](../standard-library/exception.md)<br/>
