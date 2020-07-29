---
title: '&lt;özel durum &gt; işlevleri'
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
ms.openlocfilehash: 849f3c8406c43b0efc2d34837e00fee6ff64e52a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87193789"
---
# <a name="ltexceptiongt-functions"></a>&lt;özel durum &gt; işlevleri

## <a name="current_exception"></a><a name="current_exception"></a>current_exception

Geçerli özel durum için bir akıllı işaretçi alır.

```cpp
exception_ptr current_exception();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli özel durumu işaret eden bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) nesnesi.

### <a name="remarks"></a>Açıklamalar

`current_exception`Bir catch bloğunda işlevi çağırın. Bir özel durum uçuş durumunda ve catch bloğu özel durumu yakalayabiliyorsanız, `current_exception` işlev `exception_ptr` özel duruma başvuran bir nesne döndürür. Aksi takdirde, işlev null bir `exception_ptr` nesne döndürür.

`current_exception`İşlevi, **`catch`** deyimin bir [özel durum bildirimi](../cpp/try-throw-and-catch-statements-cpp.md) bildirimi belirttiğinden bağımsız olarak, uçuştaki özel durumu yakalar.

Özel durumu yeniden oluşturmayadıysanız, geçerli özel durumun yıkıcısı bloğunun sonunda çağırılır **`catch`** . Ancak, `current_exception` işlevi yıkıcıda çağırsanız bile, işlev `exception_ptr` geçerli özel duruma başvuran bir nesne döndürür.

İşleve art arda yapılan çağrılar `current_exception` `exception_ptr` , geçerli özel durumun farklı kopyalarına başvuran nesneler döndürür. Sonuç olarak, kopyalar aynı ikili değerde olsalar da farklı kopyalara başvurduklarından, nesneler eşit olmayarak karşılaştırılır.

## <a name="make_exception_ptr"></a><a name="make_exception_ptr"></a>make_exception_ptr

Bir özel durumun kopyasını tutan [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) nesnesi oluşturur.

```cpp
template <class E>
    exception_ptr make_exception_ptr(E Except);
```

### <a name="parameters"></a>Parametreler

*Kullanıldıkları*\
Kopyalanacak özel duruma sahip sınıf. Genellikle, işlev bağımsız değişkeni olarak bir [özel durum sınıfı](../standard-library/exception-class.md) nesnesi belirtirsiniz `make_exception_ptr` , ancak herhangi bir sınıf nesnesi bağımsız değişken olabilir.

### <a name="return-value"></a>Dönüş Değeri

*Dışında*, geçerli özel durumun bir kopyasına işaret eden bir [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) nesnesi.

### <a name="remarks"></a>Açıklamalar

İşlevi çağırmak `make_exception_ptr` , bir C++ özel durumu oluşturma, bunu bir catch bloğunda yakalama ve sonra özel duruma başvuran bir nesne döndürmek için [current_exception](../standard-library/exception-functions.md#current_exception) işlevini çağırma ile eşdeğerdir `exception_ptr` . İşlevin Microsoft uygulamasında uygulanması `make_exception_ptr` daha etkilidir ve bir özel durum yakalanmasıdır.

Uygulama genellikle `make_exception_ptr` işlevi gerektirmez ve kullanımını önermiyoruz.

## <a name="rethrow_exception"></a><a name="rethrow_exception"></a>rethrow_exception

Bir parametre olarak geçirilen bir özel durum oluşturur.

```cpp
void rethrow_exception(exception_ptr P);
```

### <a name="parameters"></a>Parametreler

*Lama*\
Yeniden oluşturulması için bir özel durum yakalandı. *P* null [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr), işlev [std:: bad_exception](../standard-library/bad-exception-class.md)atar.

### <a name="remarks"></a>Açıklamalar

Bir nesnede yakalanan bir özel durum depoladıktan sonra `exception_ptr` , birincil iş parçacığı nesneyi işleyebilir. Birincil iş parçacığın `rethrow_exception` `exception_ptr` bağımsız değişkeni olarak nesnesiyle birlikte işlevi çağırın. `rethrow_exception`İşlevi nesnesinden özel durumu ayıklar `exception_ptr` ve ardından birincil iş parçacığı bağlamında özel durumu oluşturur.

## <a name="get_terminate"></a><a name="get_terminate"></a>get_terminate

Geçerli işlevi alır `terminate_handler` .

```cpp
terminate_handler get_terminate();
```

## <a name="set_terminate"></a><a name="set_terminate"></a>set_terminate

`terminate_handler`Programın sonlandırılması sırasında çağrılması için yeni bir oluşturur.

```cpp
terminate_handler set_terminate(terminate_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

*fnew*\
Sonlandırmada çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Sonlandırma sırasında çağrılması için kullanılan önceki işlevin adresi.

### <a name="remarks"></a>Açıklamalar

İşlevi, * *fnew*işlevi olarak yeni bir [terminate_handler](../standard-library/exception-typedefs.md#terminate_handler) oluşturur. Bu nedenle, *fnew* bir null işaretçi olmamalıdır. İşlevi, önceki sonlandırma işleyicisinin adresini döndürür.

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

## <a name="get_unexpected"></a><a name="get_unexpected"></a>get_unexpected

Geçerli işlevi alır `unexpected_handler` .

```cpp
unexpected_handler get_unexpected();
```

## <a name="rethrow_if_nested"></a><a name="rethrow_if_nested"></a>rethrow_if_nested

```cpp
template <class E>
    void rethrow_if_nested(const E& e);
```

### <a name="remarks"></a>Açıklamalar

Polimorfik bir sınıf türü değilse veya `nested_exception` erişilemez ya da belirsiz ise, hiçbir etkisi olmaz. Aksi takdirde, dinamik bir dönüştürme gerçekleştirir.

## <a name="set_unexpected"></a><a name="set_unexpected"></a>set_unexpected

`unexpected_handler`Beklenmeyen bir özel durumla karşılaşıldığında yeni bir oluşturur.

```cpp
unexpected_handler set_unexpected(unexpected_handler fnew) throw();
```

### <a name="parameters"></a>Parametreler

*fnew*\
Beklenmeyen bir özel durumla karşılaşıldığında çağrılacak işlev.

### <a name="return-value"></a>Dönüş Değeri

Önceki adresi `unexpected_handler` .

### <a name="remarks"></a>Açıklamalar

*fnew* , boş bir işaretçi olmamalıdır.

C++ standardı, `unexpected` bir işlev kendi throw listesinde olmayan bir özel durum oluşturduğunda çağrılmalıdır. Geçerli uygulama bunu desteklemiyor. Aşağıdaki örnek doğrudan çağırır ve `unexpected` sonra öğesini çağırır `unexpected_handler` .

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

## <a name="terminate"></a><a name="terminate"></a>sonlandırmayı

Bir sonlandırıcı işleyici çağırır.

```cpp
void terminate();
```

### <a name="remarks"></a>Açıklamalar

İşlevi, türünde bir işlev olan bir sonlandırma işleyicisi çağırır **`void`** . `terminate`Program tarafından doğrudan çağrılırsa, sonlandırma işleyicisi en son bir [set_terminate](../standard-library/exception-functions.md#set_terminate)çağrısıyla ayarlanır. `terminate`Bir throw ifadesinin değerlendirmesi sırasında birkaç başka nedenden dolayı çağrılırsa, sonlandırma işleyicisi throw ifadesi hesaplandıktan hemen sonra devreye girer.

Bir sonlandırma işleyicisi çağırana geri dönemeyebilir. Program başlangıcında, sonlandırma işleyicisi çağıran bir işlevdir `abort` .

### <a name="example"></a>Örnek

Öğesinin [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek için bkz. set_unexpected `terminate` .

## <a name="throw_with_nested"></a><a name="throw_with_nested"></a>throw_with_nested

```cpp
template <class T> [[noreturn]]
    void throw_with_nested(T&& t);
```

### <a name="remarks"></a>Açıklamalar

İç içe özel durumlarla özel durum oluşturur.

## <a name="uncaught_exception"></a><a name="uncaught_exception"></a>uncaught_exception

**`true`** Yalnızca oluşturulan bir özel durum şu anda işleniyorsa döndürür.

```cpp
bool uncaught_exception();
```

### <a name="return-value"></a>Dönüş Değeri

**`true`** Bir throw ifadesinin değerlendirilmesinden ve eşleşen işleyicide özel durum bildiriminin başlatılmasını tamamlamadan önce ve throw ifadesinin sonucu olarak [beklenmeyen](../standard-library/exception-functions.md#unexpected) şekilde çağrılmadan önce döndürür. Özellikle, `uncaught_exception` **`true`** özel durum geriye doğru çağrıldığında çağrılan yıkıcıdan çağrıldığında döndürülür. Cihazlarda, `uncaught_exception` Windows Mobile 2005 platformları dahil olmak üzere yalnızca Windows CE 5,00 ve üzeri sürümlerde desteklenir.

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

## <a name="unexpected"></a><a name="unexpected"></a>bek

Beklenmeyen işleyiciyi çağırır.

```cpp
void unexpected();
```

### <a name="remarks"></a>Açıklamalar

C++ standardı, `unexpected` bir işlev kendi throw listesinde olmayan bir özel durum oluşturduğunda çağrılmalıdır. Geçerli uygulama bunu desteklemiyor. Örnek, `unexpected` beklenmeyen işleyiciyi çağıran doğrudan çağırır.

İşlevi, türünde bir işlev olan beklenmeyen bir işleyici çağırır **`void`** . `unexpected`Program tarafından doğrudan çağrılırsa, beklenmeyen işleyici bir [set_unexpected](../standard-library/exception-functions.md#set_unexpected)çağrısıyla en son ayarlanan bir programdır.

Beklenmeyen bir işleyici çağırana geri dönemeyebilir. Yürütmeyi şu şekilde sonlandıramayabilir:

- Beklenmeyen işleyici doğrudan program tarafından çağrılırsa, özel durum belirtiminde veya herhangi bir türde bir nesne olarak listelenen bir türün nesnesi oluşturuluyor.

- [Bad_exception](../standard-library/bad-exception-class.md)türünde bir nesne oluşturuluyor.

- [Sonlandırma](../standard-library/exception-functions.md#terminate)veya çağırma `abort` `exit` .

Program başlangıcında, beklenmeyen işleyici, [Sonlandır](../standard-library/exception-functions.md#terminate)çağıran bir işlevdir.

### <a name="example"></a>Örnek

Öğesinin [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek için bkz. set_unexpected `unexpected` .
