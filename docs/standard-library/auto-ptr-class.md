---
description: 'Hakkında daha fazla bilgi edinin: auto_ptr sınıfı'
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
ms.openlocfilehash: e656da9f5ffdaf4dfe85b1cbd75ef79ba41adb64
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321672"
---
# <a name="auto_ptr-class"></a>auto_ptr Sınıfı

Denetim bir blok ayrıldığında kaynağın otomatik olarak yok edilmesini sağlayan bir kaynak etrafında akıllı bir işaretçi sarar.

Daha yetenekli `unique_ptr` sınıf yerini alır `auto_ptr` . Daha fazla bilgi için bkz. [Unique_ptr sınıfı](../standard-library/unique-ptr-class.md).

Ve özel durum işleme hakkında daha fazla bilgi için `throw()` bkz. [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).

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

*Right*\
`auto_ptr`Mevcut bir kaynağın alınacağı kaynak.

*kaydetmeye*\
Saklı işaretçinin yerini alacak şekilde belirtilen işaretçi.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, ayrılmış bir nesneye, olarak adlandırılan akıllı bir işaretçi tanımlar `auto_ptr` . İşaretçi null olmalıdır veya tarafından ayrılan bir nesne atamalısınız **`new`** . `auto_ptr`Depolanan değeri başka bir nesneye atanmışsa sahipliği aktarır. (Bir null işaretçiyle bir aktarımdan sonra saklı değeri değiştirir.) İçin yıkıcısı, `auto_ptr<Type>` ayrılan nesneyi siler. , `auto_ptr<Type>` Denetim bir blok dışında ayrıldığında, ayrılmış bir nesnenin otomatik olarak silinmesini sağlar. `auto_ptr<Type>`Aynı nesneye sahip iki nesne oluşturmamalıdır.

Bir `auto_ptr<Type>` nesneyi değere göre bir işlev çağrısına bağımsız değişken olarak geçirebilirsiniz. `auto_ptr`Herhangi bir standart kitaplık kapsayıcısının öğesi olamaz. `auto_ptr<Type>`C++ standart kitaplığı kapsayıcısı ile bir nesne dizisini güvenilir bir şekilde yönetemezsiniz.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|-|-|
|[auto_ptr](#auto_ptr)|Türündeki nesneler için Oluşturucu `auto_ptr` .|

### <a name="typedefs"></a>Tür tanımları

|Ad|Açıklama|
|-|-|
|[element_type](#element_type)|Tür, şablon parametresi için bir eş anlamlı `Type` .|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[Al](#get)|Üye işlevi, saklı işaretçiyi döndürür `myptr` .|
|[Yayın](#release)|Üye, saklı işaretçiyi `myptr` null işaretçiyle değiştirir ve daha önce depolanmış işaretçiyi döndürür.|
|[döndürmek](#reset)|Üye işlevi, `delete myptr` yalnızca saklı işaretçi değeri `myptr` işlev çağrısının sonucu olarak değişirse ifadeyi değerlendirir. Ardından, saklı işaretçinin *PTR* ile yerini alır.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir nesneden diğerine sahiplik aktaran atama işleci `auto_ptr` .|
|[işlecinde](#op_star)|Türündeki nesneler için başvuru kaldırma işleci `auto_ptr` .|
|[operator->](#op_arrow)|Üye erişimine izin vermek için işleç.|
|[işleç auto_ptr\<Other>](#op_auto_ptr_lt_other_gt)|Bir türden `auto_ptr` başka bir türe yayınlar `auto_ptr` .|
|[işleç auto_ptr_ref\<Other>](#op_auto_ptr_ref_lt_other_gt)|Bir ' dan ' a yayınlar `auto_ptr` `auto_ptr_ref` .|

### <a name="auto_ptr"></a><a name="auto_ptr"></a> auto_ptr

Türündeki nesneler için Oluşturucu `auto_ptr` .

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
`auto_ptr`Sarmalayan nesnenin işaretçisi.

*Right*\
`auto_ptr`Oluşturucu tarafından kopyalanacak nesne.

#### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, içindeki *PTR* `myptr` 'yi, ayrılan nesneye saklı işaretçi olarak depolar. İkinci Oluşturucu, *sağdan* depolanan işaretçinin *sahipliğini doğrudan depolayarak* aktarır. [](#release) içindeki yayın `myptr` .

Üçüncü Oluşturucu, ikinci ile aynı şekilde davranır, ancak depolar hariç olur `right` . `ref`. `release``myptr`' de, burada `ref` depolanan başvurudur `right` .

Şablon Oluşturucusu ikinci Oluşturucu ile aynı şekilde davranır. Bu, işaretçisine örtük olarak bir işaretçiye `Other` dönüştürülebilir `Type` .

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

### <a name="element_type"></a><a name="element_type"></a> element_type

Tür, şablon parametresi için bir eş anlamlı `Type` .

```cpp
typedef Type element  _type;
```

### <a name="get"></a><a name="get"></a> Al

Üye işlevi, saklı işaretçiyi döndürür `myptr` .

```cpp
Type *get() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Saklı işaretçi `myptr` .

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

### <a name="operator"></a><a name="op_eq"></a> işleç =

Bir nesneden diğerine sahiplik aktaran atama işleci `auto_ptr` .

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>Parametreler

*Right*\
`auto_ptr` türünün bir nesnesi.

#### <a name="return-value"></a>Dönüş Değeri

Türündeki bir nesneye başvuru `auto_ptr<Type>` .

#### <a name="remarks"></a>Açıklamalar

Atama, `delete myptr` ancak yalnızca saklı işaretçi `myptr` atamanın sonucu olarak değişirse ifadeyi değerlendirir. Daha sonra *sağ* *olarak depolanan işaretçinin sahipliğini doğrudan depolayarak* aktarır. [](#release) içindeki yayın `myptr` . İşlevi __\* bunu__ döndürür.

#### <a name="example"></a>Örnek

Üye işlecinin kullanımına bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="operator"></a><a name="op_star"></a> işlecinde

Türündeki nesneler için başvuru kaldırma işleci `auto_ptr` .

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

İşaretçinin sahip olduğu türü bir nesneye başvuru `Type` .

#### <a name="remarks"></a>Açıklamalar

Yöneltme işleci `*` [Get](#get)döndürüyor. Bu nedenle, saklı işaretçi null olmamalıdır.

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="operator-gt"></a><a name="op_arrow"></a> işlecinde&gt;

Üye erişimine izin vermek için işleç.

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Sahip olunan nesnenin üyesi `auto_ptr` .

#### <a name="remarks"></a>Açıklamalar

Seçim işleci [Get](#get)değerini döndürür `( )` , böylece ifade *AP* ->  **üyesi** ( *AP*) ile aynı şekilde davranır. **Get**())-> **üyesi**, burada *AP* sınıfının bir nesnesidir `auto_ptr` \< **Type**> . Bu nedenle, saklı işaretçi null olmamalı ve bir `Type` sınıf, yapı veya üye içeren birleşim türü olmalıdır `member` .

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="operator-auto_ptrltothergt"></a><a name="op_auto_ptr_lt_other_gt"></a> işleç auto_ptr &lt; diğer&gt;

Bir türden `auto_ptr` başka bir türe yayınlar `auto_ptr` .

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci `auto_ptr` \< **Other**> ( **\* this**) döndürür.

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

### <a name="operator-auto_ptr_refltothergt"></a><a name="op_auto_ptr_ref_lt_other_gt"></a> işleç auto_ptr_ref &lt; diğer&gt;

Bir ' dan ' a yayınlar `auto_ptr` `auto_ptr_ref` .

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci **auto_ptr_ref** \< **Other**> ( **\* this**) döndürür.

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

### <a name="release"></a><a name="release"></a> Yayın

Üye, saklı işaretçiyi `myptr` null işaretçiyle değiştirir ve daha önce depolanmış işaretçiyi döndürür.

```cpp
Type *release() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Daha önce saklı işaretçi.

#### <a name="remarks"></a>Açıklamalar

Üye, saklı işaretçiyi `myptr` null işaretçiyle değiştirir ve daha önce depolanmış işaretçiyi döndürür.

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

### <a name="reset"></a><a name="reset"></a> döndürmek

Üye işlevi, `delete myptr` yalnızca saklı işaretçi değeri `myptr` bir işlev çağrısının sonucu olarak değişirse ifadeyi değerlendirir. Ardından, saklı işaretçinin ile değiştirir `ptr` .

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Saklı işaretçinin yerini alacak şekilde belirtilen işaretçi `myptr` .

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
