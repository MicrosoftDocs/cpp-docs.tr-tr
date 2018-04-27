---
title: auto_ptr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::auto_ptr
- memory/std::auto_ptr::element_type
- memory/std::auto_ptr::get
- memory/std::auto_ptr::release
- memory/std::auto_ptr::reset
dev_langs:
- C++
helpviewer_keywords:
- std::auto_ptr [C++]
- std::auto_ptr [C++], element_type
- std::auto_ptr [C++], get
- std::auto_ptr [C++], release
- std::auto_ptr [C++], reset
ms.assetid: 7f9108b6-9eb3-4634-b615-cf7aa814f23b
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ac5eca0def751212ed119377179239a74d326653
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="autoptr-class"></a>auto_ptr Sınıfı

Kaynak denetim bloğu ayrıldığında otomatik olarak kaldırıldığı sağlayan bir kaynak geçici akıllı bir işaretçi sarmalar.

Daha fazla özellikli `unique_ptr` sınıfı yerini `auto_ptr`. Daha fazla bilgi için bkz: [unique_ptr sınıfı](../standard-library/unique-ptr-class.md).

Hakkında daha fazla bilgi için `throw()` ve özel durum işleme, bkz: [özel durum belirtimleri (throw)](../cpp/exception-specifications-throw-cpp.md).

## <a name="syntax"></a>Sözdizimi

```cpp
class auto_ptr {
public:
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

`right` `auto_ptr` Mevcut bir kaynağı alınacağı.

`ptr` Saklı işaretçiyi değiştirmek için belirtilen işaretçi.

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı olarak adlandırılan bir akıllı işaretçi açıklar bir `auto_ptr`, ayrılmış bir nesneye. İşaretçi ya da olmalıdır null veya tarafından ayrılmış bir nesne atarsınız `new`. `auto_ptr` Saklı değerini başka bir nesneye atanmışsa sahipliği aktarır. (Depolanan değer sonra bir aktarımı null işaretçisi ile değiştirir.) Yıkıcı için `auto_ptr<Type>` ayrılmış nesneyi siler. `auto_ptr<Type>` Denetim bile oluşturulan bir özel durum ile bir blok ayrıldığında ayrılmış bir nesne otomatik olarak silinir sağlar. İki oluşturmalısınız değil `auto_ptr<Type>` aynı nesne kendisine nesneleri.

Geçirebilirsiniz bir `auto_ptr<Type>` değer işlev çağrısı için bağımsız değişken olarak nesnesiyle. Bir `auto_ptr` herhangi bir standart kitaplığı kapsayıcısına öğesi olamaz. Bir dizi güvenilir bir şekilde yönetemez `auto_ptr<Type>` C++ Standart Kitaplığı kapsayıcı nesneleri.

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[auto_ptr](#auto_ptr)|Nesne türü Oluşturucusu `auto_ptr`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[element_type](#element_type)|Şablon parametresi için bir eş anlamlı türüdür `Type`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[get](#get)|Üye fonksiyonu saklı işaretçi döndüren `myptr`.|
|[Sürüm](#release)|Üye saklı işaretçi değiştirir `myptr` null işaretçiyle ve daha önce depolanan işaretçi döndürür.|
|[Sıfırla](#reset)|Üye işlevini ifadeyi hesaplar `delete myptr`, ancak yalnızca depolanmış işaretçi değeri `myptr` işlev çağrısının sonucunda değişiklikleri. Ardından saklı işaretçisi ile değiştirir `ptr`.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator=](#op_eq)|Sahipliği birinden aktaran bir atama işleci `auto_ptr` başka bir nesne.|
|[işleç *](#op_star)|Türündeki nesneler için bilgileri başvuru kaldırma işleci `auto_ptr`.|
|[-> işleci](#op_arrow)|Üye erişimi izin vermekle işleci.|
|[işleç auto_ptr\<diğer >](#op_auto_ptr_lt_other_gt)|Bir tür bıraktığı `auto_ptr` başka bir tür için `auto_ptr`.|
|[işleç auto_ptr_ref\<diğer >](#op_auto_ptr_ref_lt_other_gt)|Gelen bıraktığı bir `auto_ptr` için bir `auto_ptr_ref`.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="auto_ptr"></a>  auto_ptr::auto_ptr

Nesne türü Oluşturucusu `auto_ptr`.

```cpp
explicit auto_ptr(Type* ptr  = 0) throw();

auto_ptr(auto_ptr<Type>& right) throw();

auto_ptr(auto _ptr_ref<Type> right) throw();

template <class Other>
auto _ptr(auto _ptr<Other>& right) throw();
```

### <a name="parameters"></a>Parametreler

`ptr` Nesne işaretçisine, `auto_ptr` yalıtır.

`right` `auto_ptr` Oluşturucusu tarafından kopyalanacak nesne.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucusu depoları `ptr` içinde **myptr**, ayrılmış nesnesine saklı işaretçi. İkinci oluşturucu aktarır depolanan işaretçi sahipliğini `right`, depolayarak `right`. [Yayın](#release) içinde **myptr**.

Depoladığı dışında üçüncü Oluşturucusu ikinci ile aynı şekilde davranır **sağ**. `ref`. **Yayın** içinde **myptr**, burada `ref` başvuru depolanan `right`.

Şablon Oluşturucusu aynı şekilde davranır gösteren bir işaretçi sağlanan ikinci oluşturucu **diğer** örtük olarak bir işaretçi dönüştürülebilir **türü**.

### <a name="example"></a>Örnek

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

## <a name="element_type"></a>  auto_ptr::ELEMENT_TYPE

Şablon parametresi için bir eş anlamlı türüdür **türü**.

```cpp

typedef Type element  _type;
```

## <a name="get"></a>  auto_ptr::get

Üye fonksiyonu saklı işaretçi döndüren **myptr**.

```cpp
Type *get() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Saklı işaretçi **myptr**.

### <a name="example"></a>Örnek

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

## <a name="op_eq"></a>  auto_ptr::operator =

Sahipliği birinden aktaran bir atama işleci `auto_ptr` başka bir nesne.

```cpp
template <class Other>
auto_ptr<Type>& operator=(auto_ptr<Other>& right) throw();
auto_ptr<Type>& operator=(auto_ptr<Type>& right) throw();
auto_ptr<Type>& operator=(auto_ptr_ref<Type> right) throw();
```

### <a name="parameters"></a>Parametreler

`right` Türünde bir nesne `auto_ptr`.

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru türünde bir nesne `auto_ptr` \< **türü**>.

### <a name="remarks"></a>Açıklamalar

Atama ifadeyi hesaplar **myptr silmek**, ancak yalnızca saklı işaretçi **myptr** değişiklikleri atama sonucu. Ardından işaretçiyi _ içinde depolanan sahipliğini aktarır *sağ*, depolayarak \_ *sağ*. [Yayın](#release) içinde **myptr**. İşlevi döndürür  **\*bu**.

### <a name="example"></a>Örnek

Üye işleci kullanımı örneği için bkz: [auto_ptr::auto_ptr](#auto_ptr).

## <a name="op_star"></a>  auto_ptr::operator *

Türündeki nesneler için bilgileri başvuru kaldırma işleci `auto_ptr`.

```cpp
Type& operator*() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru türünde bir nesne **türü** işaretçinin sahip.

### <a name="remarks"></a>Açıklamalar

İndirection işleci döndürür `*` [almak](#get). Bu nedenle, depolanan işaretçisi null olmamalıdır.

### <a name="example"></a>Örnek

Üye işlevini kullanma örneği için bkz: [auto_ptr::auto_ptr](#auto_ptr).

## <a name="op_arrow"></a>  auto_ptr::operator-&gt;

Üye erişimi izin vermekle işleci.

```cpp
Type * operator->() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne üyesi, **auto_ptr** sahip.

### <a name="remarks"></a>Açıklamalar

Seçim operatörü döndürür [almak](#get)`( )`, böylece ifade *ap*-> **üye** aynı şekilde davranır ( *ap*. **Alma**()) -> **üye**, burada *ap* sınıfın bir nesnesi olup `auto_ptr` \< **türü**>. Bu nedenle, depolanan işaretçisi null olmamalıdır ve **türü** bir sınıf, yapı veya birleşim türü ile olmalıdır bir **üye** üyesi.

### <a name="example"></a>Örnek

Üye işlevini kullanma örneği için bkz: [auto_ptr::auto_ptr](#auto_ptr).

## <a name="op_auto_ptr_lt_other_gt"></a>  auto_ptr::operator auto_ptr&lt;diğer&gt;

Bir tür bıraktığı `auto_ptr` başka bir tür için `auto_ptr`.

```cpp
template <class Other>
operator auto _ptr<Other>() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türe işleci döndürür `auto_ptr` \< **diğer**> (  **\*bu**).

### <a name="example"></a>Örnek

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

## <a name="op_auto_ptr_ref_lt_other_gt"></a>  auto_ptr::operator auto_ptr_ref&lt;diğer&gt;

Gelen bıraktığı bir `auto_ptr` için bir **auto_ptr_ref**.

```cpp
template <class Other>
operator auto _ptr  _ref<Other>() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türe işleci döndürür **auto_ptr_ref** \< **diğer**> (  **\*bu**).

### <a name="example"></a>Örnek

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

## <a name="release"></a>  auto_ptr::Release

Üye saklı işaretçi değiştirir **myptr** null işaretçiyle ve daha önce depolanan işaretçi döndürür.

```cpp
Type *release() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Daha önce depolanan işaretçi.

### <a name="remarks"></a>Açıklamalar

Üye saklı işaretçi değiştirir **myptr** null işaretçiyle ve daha önce depolanan işaretçi döndürür.

### <a name="example"></a>Örnek

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

## <a name="reset"></a>  auto_ptr::reset

Üye işlevini ifadeyi hesaplar **silmek** **myptr**, ancak yalnızca depolanmış işaretçi değeri **myptr** işlev çağrısının sonucunda değişiklikleri. Ardından saklı işaretçisi ile değiştirir **ptr**.

```cpp
void reset(Type* ptr = 0);
```

### <a name="parameters"></a>Parametreler

`ptr` Saklı işaretçiyi değiştirmek için belirtilen işaretçi **myptr**.

### <a name="example"></a>Örnek

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

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[unique_ptr Sınıfı](../standard-library/unique-ptr-class.md)<br/>
