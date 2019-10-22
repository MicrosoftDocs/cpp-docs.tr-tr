---
title: auto_ptr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
ms.openlocfilehash: 6b429b0e5c734f81216c988e372c02021528cffd
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72690036"
---
# <a name="auto_ptr-class"></a>auto_ptr Sınıfı

Denetim bir blok ayrıldığında kaynağın otomatik olarak yok edilmesini sağlayan bir kaynak etrafında akıllı bir işaretçi sarar.

Daha uyumlu `unique_ptr` sınıf `auto_ptr` yerini alır. Daha fazla bilgi için bkz. [Unique_ptr Class](../standard-library/unique-ptr-class.md).

@No__t_0 ve özel durum işleme hakkında daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class auto_ptr {
    typedef Type element_type;
    explicit auto_ptr(Type* ptr = 0) throw();
    auto_ptr(auto_ptr<Type>& right) throw()
        ;
    template <class Other>
    operator auto_ptr<Other>() throw();
    template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
    template <class Other>
    auto_ptr(auto_ptr<Other>& right);
    auto_ptr<Type>& operator=(auto_ptr<Type>& right);
    ~auto_ptr();
    Type& operator*() const throw();
    Type * operator->()const throw();
    Type *get() const throw();
    Type *release()throw();
    void reset(Type* ptr = 0);
};
```

### <a name="parameters"></a>Parametreler

*sağ* \
Mevcut bir kaynağın alınacağı `auto_ptr`.

*ptr* \
Saklı işaretçinin yerini alacak şekilde belirtilen işaretçi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, ayrılmış bir nesneye `auto_ptr` olarak adlandırılan akıllı bir işaretçi tanımlar. İşaretçi null olmalı veya **Yeni**tarafından ayrılmış bir nesne belirlemelidir. @No__t_0, depolanan değeri başka bir nesneye atanırsa sahipliği aktarır. (Bir null işaretçiyle bir aktarımdan sonra saklı değeri değiştirir.) @No__t_0 için yıkıcı, ayrılan nesneyi siler. @No__t_0, denetim bir blok dışında ayrıldığında, ayrılmış bir nesnenin otomatik olarak silinmesini sağlar. Aynı nesneye sahip olan iki `auto_ptr<Type>` nesnesi oluşturmamalıdır.

Bir `auto_ptr<Type>` nesnesini, bir işlev çağrısının bağımsız değişkeni olarak değere geçirebilirsiniz. Bir `auto_ptr` herhangi bir standart kitaplık kapsayıcısının öğesi olamaz. C++ Standart kitaplık kapsayıcısıyla `auto_ptr<Type>` nesneleri dizisini güvenilir bir şekilde yönetemezsiniz.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[auto_ptr](#auto_ptr)|@No__t_0 türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[element_type](#element_type)|Tür, `Type` şablon parametresi için bir eş anlamlı.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[get](#get)|Üye işlevi `myptr` saklı işaretçiyi döndürür.|
|[Yayın](#release)|Üye, bir null işaretçiyle `myptr` saklı işaretçinin yerini alır ve daha önce depolanan işaretçiyi döndürür.|
|[döndürmek](#reset)|Üye işlevi `delete myptr` ifadeyi değerlendirir, ancak yalnızca saklı işaretçi değeri `myptr` işlev çağrısının sonucu olarak değişirse değişir. Ardından, saklı işaretçinin *PTR*ile yerini alır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](#op_eq)|Bir `auto_ptr` nesnesinden diğerine sahiplik aktaran atama işleci.|
|[işlecinde](#op_star)|@No__t_0 türündeki nesneler için başvuru kaldırma işleci.|
|[operator->](#op_arrow)|Üye erişimine izin vermek için işleç.|
|[operator auto_ptr \<Other >](#op_auto_ptr_lt_other_gt)|@No__t_0 bir türden `auto_ptr` başka bir türe yayınlar.|
|[operator auto_ptr_ref \<Other >](#op_auto_ptr_ref_lt_other_gt)|Bir `auto_ptr` `auto_ptr_ref`.|

### <a name="auto_ptr"></a>auto_ptr

@No__t_0 türündeki nesneler için Oluşturucu.

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>Parametreler

*ptr* \
@No__t_0 kapsülleyen nesnenin işaretçisi.

*sağ* \
Oluşturucu tarafından kopyalanacak `auto_ptr` nesnesi.

#### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, ayrılmış nesnenin saklı işaretçisi olan `myptr` *PTR* 'yi depolar. İkinci Oluşturucu, *sağdan*depolanan işaretçinin *sahipliğini doğrudan depolayarak*aktarır. `myptr` [yayın](#release) .

Üçüncü Oluşturucu, `right` depolanmasının dışında ikinci ile aynı şekilde davranır. `ref`. `myptr` `release`, burada `ref` `right` içinde saklanan başvurudur.

Şablon Oluşturucusu ikinci Oluşturucu ile aynı şekilde davranır. Bu, `Other` işaretçisinin örtük olarak `Type` işaretçisine dönüştürülebileceği şekilde yapılır.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
   Int(int i)
   {
      cout << "Constructing " << ( void* )this  << endl;
      x = i;
      bIsConstructed = true;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << endl;
      bIsConstructed = false;
   };
   Int &operator++( )
   {
      x++;
      return *this;
   };
   int x;
private:
   bool bIsConstructed;
};

void function ( auto_ptr<Int> &pi )
{
   ++( *pi );
   auto_ptr<Int> pi2( pi );
   ++( *pi2 );
   pi = pi2;
}

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   cout << pi->x << endl;
   function( pi );
   cout << pi->x << endl;
}
```

```Output
Constructing 00311AF8
5
7
Destructing 00311AF8
```

### <a name="element_type"></a>element_type

Tür, `Type` şablon parametresi için bir eş anlamlı.

```cpp
typedef Type element  _type;
```

### <a name="get"></a>Al

Üye işlevi `myptr` saklı işaretçiyi döndürür.

```cpp
Type *get() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Saklı işaretçi `myptr`.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
   Int(int i)
   {
      x = i;
      cout << "Constructing " << ( void* )this  << " Value: " << x << endl;
   };
   ~Int( )
   {
      cout << "Destructing " << ( void* )this << " Value: " << x << endl;
   };

   int x;

};

int main( )
{
   auto_ptr<Int> pi ( new Int( 5 ) );
   pi.reset( new Int( 6 ) );
   Int* pi2 = pi.get ( );
   Int* pi3 = pi.release ( );
   if (pi2 == pi3)
      cout << "pi2 == pi3" << endl;
   delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="op_eq"></a>işleç =

Bir `auto_ptr` nesnesinden diğerine sahiplik aktaran atama işleci.

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>Parametreler

*sağ* \
@No__t_0 türünde bir nesne.

#### <a name="return-value"></a>Dönüş Değeri

@No__t_0 türündeki bir nesneye başvuru.

#### <a name="remarks"></a>Açıklamalar

Atama ifadesi `delete myptr` değerlendirir, ancak yalnızca saklı işaretçi atamanın sonucu olarak değişirse `myptr`. Daha sonra *sağ* *olarak depolanan işaretçinin sahipliğini doğrudan depolayarak*aktarır. `myptr` [yayın](#release) . İşlev __\*this__döndürür.

#### <a name="example"></a>Örnek

Üye işlecinin kullanımına bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_star"></a>işlecinde

@No__t_0 türündeki nesneler için başvuru kaldırma işleci.

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

İşaretçiye sahip `Type` türündeki bir nesneye başvuru.

#### <a name="remarks"></a>Açıklamalar

Yöneltme işleci `*`[Al](#get)döndürür. Bu nedenle, saklı işaretçi null olmamalıdır.

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_arrow"></a>operator-&gt;

Üye erişimine izin vermek için işleç.

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

@No__t_0 sahip olunan nesnenin üyesi.

#### <a name="remarks"></a>Açıklamalar

Seçim işleci [get](#get) `( )` döndürür, bu sayede *AP* -> **üyesi** ifadesi ( *AP*) ile aynı şekilde davranır. **Get**())-> **üyesi**; burada *AP* , `auto_ptr` sınıfının \< **tür**> bir nesnesidir. Bu nedenle, saklı işaretçi null olmamalı ve `Type` bir sınıf, yapı veya `member` üyesi olan birleşim türü olmalıdır.

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_auto_ptr_lt_other_gt"></a>operator auto_ptr &lt;Other &gt;

@No__t_0 bir türden `auto_ptr` başka bir türe yayınlar.

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci `auto_ptr` \< **diğer**> ( **\*this**) döndürür.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_op_auto_ptr.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;
int main()
{
   auto_ptr<int> pi ( new int( 5 ) );
   auto_ptr<const int> pc = ( auto_ptr<const int> )pi;
}
```

### <a name="op_auto_ptr_ref_lt_other_gt"></a>operator auto_ptr_ref &lt;Other &gt;

Bir `auto_ptr` `auto_ptr_ref`.

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci, **auto_ptr_ref** \< **diğer**> ( **\*this**) döndürür.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_op_auto_ptr_ref.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class C {
public:
    C(int _i) : m_i(_i) {
    }
    ~C() {
        cout << "~C:  " << m_i << "\n";
    }
    C &operator =(const int &x) {
        m_i = x;
        return *this;
    }
    int m_i;
};
void f(auto_ptr<C> arg) {
};
int main()
{
    const auto_ptr<C> ciap(new C(1));
    auto_ptr<C> iap(new C(2));

    // Error: this implies transfer of ownership of iap's pointer
    // f(ciap);
    f(iap); // compiles, but gives up ownership of pointer

            // here, iap owns a destroyed pointer so the following is bad:
            // *iap = 5; // BOOM

    cout << "main exiting\n";
}
```

```Output
~C:  2
main exiting
~C:  1
```

### <a name="release"></a>Yayın

Üye, bir null işaretçiyle `myptr` saklı işaretçinin yerini alır ve daha önce depolanan işaretçiyi döndürür.

```cpp
Type *release() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Daha önce saklı işaretçi.

#### <a name="remarks"></a>Açıklamalar

Üye, bir null işaretçiyle `myptr` saklı işaretçinin yerini alır ve daha önce depolanan işaretçiyi döndürür.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_release.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>
using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int() {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;

};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

### <a name="reset"></a>döndürmek

Üye işlevi `delete myptr` ifadeyi değerlendirir, ancak yalnızca depolanan işaretçi değeri bir işlev çağrısının sonucu olarak değişirse `myptr`. Ardından, saklı işaretçiyi `ptr` değiştirir.

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>Parametreler

*ptr* \
Saklı işaretçinin `myptr` değiştirmek için belirtilen işaretçi.

#### <a name="example"></a>Örnek

```cpp
// auto_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

class Int
{
public:
    Int(int i)
    {
        x = i;
        cout << "Constructing " << (void*)this << " Value: " << x << endl;
    };
    ~Int()
    {
        cout << "Destructing " << (void*)this << " Value: " << x << endl;
    };

    int x;
};

int main()
{
    auto_ptr<Int> pi(new Int(5));
    pi.reset(new Int(6));
    Int* pi2 = pi.get();
    Int* pi3 = pi.release();
    if (pi2 == pi3)
        cout << "pi2 == pi3" << endl;
    delete pi3;
}
```

```Output
Constructing 00311AF8 Value: 5
Constructing 00311B88 Value: 6
Destructing 00311AF8 Value: 5
pi2 == pi3
Destructing 00311B88 Value: 6
```

## <a name="see-also"></a>Ayrıca bkz.

[unique_ptr Sınıfı](../standard-library/unique-ptr-class.md)
