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
ms.openlocfilehash: 14841662235f075d74120673208dd54531763c09
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456706"
---
# <a name="autoptr-class"></a>auto_ptr Sınıfı

Denetim bir blok ayrıldığında kaynağın otomatik olarak yok edilmesini sağlayan bir kaynak etrafında akıllı bir işaretçi sarar.

Daha yetenekli `unique_ptr` sınıf yerini alır `auto_ptr`. Daha fazla bilgi için bkz. [Unique_ptr Class](../standard-library/unique-ptr-class.md).

Ve özel durum işleme `throw()` hakkında daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).

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
`auto_ptr` Mevcut bir kaynağın alınacağı kaynak.

*kaydetmeye*\
Saklı işaretçinin yerini alacak şekilde belirtilen işaretçi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, ayrılmış bir nesneye `auto_ptr`, olarak adlandırılan akıllı bir işaretçi tanımlar. İşaretçi null olmalı veya **Yeni**tarafından ayrılmış bir nesne belirlemelidir. Depolanan değeri başka bir nesneye atanmışsa sahipliği aktarır.`auto_ptr` (Bir null işaretçiyle bir aktarımdan sonra saklı değeri değiştirir.) İçin `auto_ptr<Type>` yıkıcısı, ayrılan nesneyi siler. , `auto_ptr<Type>` Denetim bir blok dışında ayrıldığında, ayrılmış bir nesnenin otomatik olarak silinmesini sağlar. Aynı nesneye sahip iki `auto_ptr<Type>` nesne oluşturmamalıdır.

Bir `auto_ptr<Type>` nesneyi değere göre bir işlev çağrısına bağımsız değişken olarak geçirebilirsiniz. `auto_ptr` Herhangi bir standart kitaplık kapsayıcısının öğesi olamaz. Standart Kitaplık kapsayıcısıyla bir `auto_ptr<Type>` nesne dizisini güvenilir bir şekilde yönetemezsiniz. C++

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|||
|-|-|
|[auto_ptr](#auto_ptr)|Türündeki `auto_ptr`nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[element_type](#element_type)|Tür, şablon parametresi `Type`için bir eş anlamlı.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[get](#get)|Üye işlevi, saklı işaretçiyi `myptr`döndürür.|
|[Yayın](#release)|Üye, saklı işaretçiyi `myptr` null işaretçiyle değiştirir ve daha önce depolanmış işaretçiyi döndürür.|
|[döndürmek](#reset)|Üye işlevi, yalnızca saklı işaretçi `delete myptr`değeri `myptr` işlev çağrısının sonucu olarak değişirse ifadeyi değerlendirir. Ardından, saklı işaretçinin *PTR*ile yerini alır.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator=](#op_eq)|Bir `auto_ptr` nesneden diğerine sahiplik aktaran atama işleci.|
|[işlecinde](#op_star)|Türündeki `auto_ptr`nesneler için başvuru kaldırma işleci.|
|[operator->](#op_arrow)|Üye erişimine izin vermek için işleç.|
|[operator auto_ptr\<diğer >](#op_auto_ptr_lt_other_gt)|Bir türden `auto_ptr` başka bir `auto_ptr`türe yayınlar.|
|[operator auto_ptr_ref\<diğer >](#op_auto_ptr_ref_lt_other_gt)|`auto_ptr` Bir`auto_ptr_ref`' dan ' a yayınlar.|

### <a name="auto_ptr"></a>auto_ptr

Türündeki `auto_ptr`nesneler için Oluşturucu.

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Sarmalayan `auto_ptr` nesnenin işaretçisi.

*Right*\
Oluşturucu tarafından kopyalanacak nesne. `auto_ptr`

#### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, `myptr`içindeki *PTR* 'yi, ayrılan nesneye saklı işaretçi olarak depolar. İkinci *Oluşturucu,* *sağdan*depolanan işaretçinin sahipliğini doğrudan depolayarak aktarır. [](#release) içindeki`myptr`yayın.

Üçüncü Oluşturucu, ikinci ile aynı şekilde davranır, ancak depolar `right`hariç olur. `ref`. `release`' `myptr`de, `ref` burada depolanan `right`başvurudur.

Şablon Oluşturucusu ikinci Oluşturucu ile aynı şekilde davranır `Other` `Type`. Bu, işaretçisine örtük olarak bir işaretçiye dönüştürülebilir.

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

Tür, şablon parametresi `Type`için bir eş anlamlı.

```cpp
typedef Type element  _type;
```

### <a name="get"></a>Al

Üye işlevi, saklı işaretçiyi `myptr`döndürür.

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

Bir `auto_ptr` nesneden diğerine sahiplik aktaran atama işleci.

```cpp
template <class Other>
    auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

#### <a name="parameters"></a>Parametreler

*Right*\
Türünde `auto_ptr`bir nesne.

#### <a name="return-value"></a>Dönüş Değeri

Türündeki `auto_ptr<Type>`bir nesneye başvuru.

#### <a name="remarks"></a>Açıklamalar

Atama, ancak yalnızca saklı `delete myptr`işaretçi `myptr` atamanın sonucu olarak değişirse ifadeyi değerlendirir. Daha sonra *sağ* *olarak depolanan*işaretçinin sahipliğini doğrudan depolayarak aktarır. [](#release) içindeki`myptr`yayın. İşlevi  __\*bunu__döndürür.

#### <a name="example"></a>Örnek

Üye işlecinin kullanımına bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_star"></a>işlecinde

Türündeki `auto_ptr`nesneler için başvuru kaldırma işleci.

```cpp
Type& operator*() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

İşaretçinin sahip olduğu türü `Type` bir nesneye başvuru.

#### <a name="remarks"></a>Açıklamalar

Yöneltme işleci [Get](#get)döndürüyor `*`. Bu nedenle, saklı işaretçi null olmamalıdır.

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_arrow"></a>işlecinde&gt;

Üye erişimine izin vermek için işleç.

```cpp
Type * operator->() const throw();
```

#### <a name="return-value"></a>Dönüş Değeri

`auto_ptr` Sahip olunan nesnenin üyesi.

#### <a name="remarks"></a>Açıklamalar

Seçim işleci [Get](#get)`( )`değerini döndürür, böylece ifade *AP*-> **üyesi** ( *AP*) ile aynı şekilde davranır. **Al** ())-> **üye**, burada *AP* , > sınıf `auto_ptr` \< **türünde**bir nesnedir. Bu nedenle, saklı işaretçi null olmamalı ve `Type` bir sınıf, yapı veya `member` üye içeren birleşim türü olmalıdır.

#### <a name="example"></a>Örnek

Üye işlevini nasıl kullanacağınızı gösteren bir örnek için bkz. [auto_ptr](#auto_ptr).

### <a name="op_auto_ptr_lt_other_gt"></a>operator auto_ptr&lt;diğer&gt;

Bir türden `auto_ptr` başka bir `auto_ptr`türe yayınlar.

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci **diğer**> `auto_ptr` (  **\*this**) döndürür. \<

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

### <a name="op_auto_ptr_ref_lt_other_gt"></a>operator auto_ptr_ref&lt;diğer&gt;

`auto_ptr` Bir`auto_ptr_ref`' dan ' a yayınlar.

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür atama işleci **auto_ptr_ref** \< **diğer**> (  **\*this**) döndürür.

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

### <a name="reset"></a>döndürmek

Üye işlevi, yalnızca saklı işaretçi `delete myptr`değeri `myptr` bir işlev çağrısının sonucu olarak değişirse ifadeyi değerlendirir. Ardından, saklı işaretçinin ile `ptr`değiştirir.

```cpp
void reset(Type* ptr = 0);
```

#### <a name="parameters"></a>Parametreler

*kaydetmeye*\
Saklı işaretçinin `myptr`yerini alacak şekilde belirtilen işaretçi.

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
