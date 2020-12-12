---
description: 'Hakkında daha fazla bilgi edinin: auto_gcroot sınıfı'
title: auto_gcroot Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot::auto_gcroot
- msclr::auto_gcroot::attach
- msclr::auto_gcroot::get
- msclr::auto_gcroot::release
- msclr::auto_gcroot::reset
- msclr::auto_gcroot::swap
- msclr::auto_gcroot::operator=
- msclr::auto_gcroot::operator->
- msclr::auto_gcroot::operator!
- msclr::auto_gcroot::operator auto_gcroot
helpviewer_keywords:
- msclr::auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
ms.openlocfilehash: 9c763883a10906a8f63b7ba265576ab547750b66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282802"
---
# <a name="auto_gcroot-class"></a>auto_gcroot Sınıfı

Bir sanal tanıtıcıyı yerel bir türe eklemek için kullanılabilen otomatik kaynak yönetimi ( [Auto_ptr Class](../standard-library/auto-ptr-class.md)gibi).

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _element_type>
class auto_gcroot;
```

### <a name="parameters"></a>Parametreler

*_element_type*<br/>
Katıştırılacak yönetilen tür.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak oluşturucular

|Ad|Açıklama|
|---------|-----------|
|[auto_gcroot:: auto_gcroot](#auto-gcroot)|`auto_gcroot`Oluşturucu.|
|[auto_gcroot::~auto_gcroot](#tilde-auto-gcroot)|`auto_gcroot`Yok edicisi.
|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|---------|-----------|
|[auto_gcroot::attach](#attach)|`auto_gcroot`Bir nesneye iliştirme.|
|[auto_gcroot::get](#get)|İçerilen nesneyi alır.|
|[auto_gcroot::release](#release)|Nesneyi yönetimden serbest bırakır `auto_gcroot` .|
|[auto_gcroot::reset](#reset)|Geçerli sahip olan nesneyi yok edin ve isteğe bağlı olarak yeni bir nesne sahipliğini alın.|
|[auto_gcroot::swap](#swap)|Nesneleri başka bir metinle değiştirir `auto_gcroot` .|

### <a name="public-operators"></a>Ortak işleçler

|Ad|Açıklama|
|---------|-----------|
|[auto_gcroot:: operator-&gt;](#operator-arrow)|Üye erişim işleci.|  
|[auto_gcroot:: operator =](#operator-assign)|Atama işleci.|
|[auto_gcroot:: operator &nbsp; auto_gcroot](#operator-auto-gcroot)|Ve uyumlu türler arasında tür atama işleci `auto_gcroot` .|
|[auto_gcroot:: operator &nbsp; bool](#operator-bool)|`auto_gcroot`Bir koşullu ifadede kullanmak için işleci.|  
|[auto_gcroot::operator!](#operator-logical-not)|`auto_gcroot`Bir koşullu ifadede kullanmak için işleci.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\auto_gcroot.h>

**Ad alanı** msclr

## <a name="auto_gcrootauto_gcroot"></a><a name="auto-gcroot"></a> auto_gcroot:: auto_gcroot

`auto_gcroot`Oluşturucu.

```cpp
auto_gcroot(
   _element_type _ptr = nullptr
);
auto_gcroot(
   auto_gcroot<_element_type> & _right
);
template<typename _other_type>
auto_gcroot(
   auto_gcroot<_other_type> & _right
);
```

### <a name="parameters"></a>Parametreler

*_ptr*<br/>
Kendisine ait nesne.

*_right*<br/>
Mevcut bir `auto_gcroot` .

### <a name="remarks"></a>Açıklamalar

`auto_gcroot`Varolan bir ' dan oluştururken `auto_gcroot` , var olan bir `auto_gcroot` nesne, nesnenin sahipliğini yeni bir öğesine aktarmadan önce nesnesini serbest bırakır `auto_gcroot` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class RefClassA {
protected:
   String^ m_s;
public:
   RefClassA(String^ s) : m_s(s) {
      Console::WriteLine( "in RefClassA constructor: " + m_s );
   }
   ~RefClassA() {
      Console::WriteLine( "in RefClassA destructor: " + m_s );
   }

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class RefClassB : RefClassA {
public:
   RefClassB( String^ s ) : RefClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

class ClassA { //unmanaged class
private:
   auto_gcroot<RefClassA^> m_a;

public:
   ClassA() : m_a( gcnew RefClassA( "unmanaged" ) ) {}
   ~ClassA() {} //no need to delete m_a

   void DoSomething() {
      m_a->PrintHello();
   }
};

int main()
{
   {
      ClassA a;
      a.DoSomething();
   } // a.m_a is automatically destroyed as a goes out of scope

   {
      auto_gcroot<RefClassA^> a(gcnew RefClassA( "first" ) );
      a->PrintHello();
   }

   {
      auto_gcroot<RefClassB^> b(gcnew RefClassB( "second" ) );
      b->PrintHello();
      auto_gcroot<RefClassA^> a(b); //construct from derived type
      a->PrintHello();
      auto_gcroot<RefClassA^> a2(a); //construct from same type
      a2->PrintHello();
   }

   Console::WriteLine("done");
}
```

```Output
in RefClassA constructor: unmanaged
Hello from unmanaged A!
in RefClassA destructor: unmanaged
in RefClassA constructor: first
Hello from first A!
in RefClassA destructor: first
in RefClassA constructor: second
Hello from second B!
Hello from second A!
Hello from second A!
in RefClassA destructor: second
done
```

## <a name="auto_gcrootauto_gcroot"></a><a name="tilde-auto-gcroot"></a> auto_gcroot:: ~ auto_gcroot

`auto_gcroot`Yok edicisi.

```cpp
~auto_gcroot();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, sahip olunan nesnenin yapılarını da kaldırır.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_dtor.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
public:
   ClassA() { Console::WriteLine( "ClassA constructor" ); }
   ~ClassA() { Console::WriteLine( "ClassA destructor" ); }
};

int main()
{
   // create a new scope for a:
   {
      auto_gcroot<ClassA^> a = gcnew ClassA;
   }
   // a goes out of scope here, invoking its destructor
   // which in turns destructs the ClassA object.

   Console::WriteLine( "done" );
}
```

```Output
ClassA constructor
ClassA destructor
done
```

## <a name="auto_gcrootattach"></a><a name="attach"></a> auto_gcroot:: Attach

`auto_gcroot`Bir nesneye iliştirme.

```cpp
auto_gcroot<_element_type> & attach(
   _element_type _right
);
auto_gcroot<_element_type> & attach(
   auto_gcroot<_element_type> & _right
);
template<typename _other_type>
auto_gcroot<_element_type> & attach(
   auto_gcroot<_other_type> & _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
İliştirilecek nesne veya eklenecek `auto_gcroot` nesneyi içeren bir nesne.

### <a name="return-value"></a>Döndürülen değer

Geçerli `auto_gcroot`.

### <a name="remarks"></a>Açıklamalar

`_right`Bir ise `auto_gcroot` , nesne güncel iliştirilmadan önce nesnesinin sahipliğini yayınlar `auto_gcroot` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_attach.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {
      Console::WriteLine( "in ClassA constructor:" + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "in ClassA destructor:" + m_s );
   }

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String ^ s) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main() {
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );
   a->PrintHello();
   a.attach( gcnew ClassA( "second" ) ); // attach same type
   a->PrintHello();
   ClassA^ ha = gcnew ClassA( "third" );
   a.attach( ha ); // attach raw handle
   a->PrintHello();
   auto_gcroot<ClassB^> b( gcnew ClassB("fourth") );
   b->PrintHello();
   a.attach( b ); // attach derived type
   a->PrintHello();
}
```

```Output
in ClassA constructor:first
Hello from first A!
in ClassA constructor:second
in ClassA destructor:first
Hello from second A!
in ClassA constructor:third
in ClassA destructor:second
Hello from third A!
in ClassA constructor:fourth
Hello from fourth B!
in ClassA destructor:third
Hello from fourth A!
in ClassA destructor:fourth
```

## <a name="auto_gcrootget"></a><a name="get"></a> auto_gcroot:: Get

İçerilen nesneyi alır.

```cpp
_element_type get() const;
```

### <a name="return-value"></a>Döndürülen değer

Kapsanan nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_get.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ){
      Console::WriteLine( "in ClassA constructor:" + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "in ClassA destructor:" + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

void PrintA( ClassA^ a ) {
   a->PrintHello();
}

int main() {
   auto_gcroot<ClassA^> a = gcnew ClassA( "first" );
   a->PrintHello();

   ClassA^ a2 = a.get();
   a2->PrintHello();

   PrintA( a.get() );
}
```

```Output
in ClassA constructor:first
Hello from first A!
Hello from first A!
Hello from first A!
in ClassA destructor:first
```

## <a name="auto_gcrootrelease"></a><a name="release"></a> auto_gcroot:: Release

Nesneyi yönetimden serbest bırakır `auto_gcroot` .

```cpp
_element_type release();
```

### <a name="return-value"></a>Döndürülen değer

Yayınlanan nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_release.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {
      Console::WriteLine( "ClassA constructor: " + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "ClassA destructor: " + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

int main()
{
   ClassA^ a;

   // create a new scope:
   {
      auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );
      auto_gcroot<ClassA^> agc2 = gcnew ClassA( "second" );
      a = agc1.release();
   }
   // agc1 and agc2 go out of scope here

   a->PrintHello();

   Console::WriteLine( "done" );
}
```

```Output
ClassA constructor: first
ClassA constructor: second
ClassA destructor: second
Hello from first A!
done
```

## <a name="auto_gcrootreset"></a><a name="reset"></a> auto_gcroot:: Reset

Geçerli sahip olan nesneyi yok edin ve isteğe bağlı olarak yeni bir nesne sahipliğini alın.

```cpp
void reset(
   _element_type _new_ptr = nullptr
);
```

### <a name="parameters"></a>Parametreler

*_new_ptr*<br/>
Seçim Yeni nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_reset.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {
      Console::WriteLine( "ClassA constructor: " + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "ClassA destructor: " + m_s );
   }

   void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

int main()
{
   auto_gcroot<ClassA^> agc1 = gcnew ClassA( "first" );
   agc1->PrintHello();

   ClassA^ ha = gcnew ClassA( "second" );
   agc1.reset( ha ); // release first object, reference second
   agc1->PrintHello();

   agc1.reset(); // release second object, set to nullptr

   Console::WriteLine( "done" );
}
```

```Output
ClassA constructor: first
Hello from first A!
ClassA constructor: second
ClassA destructor: first
Hello from second A!
ClassA destructor: second
done
```

## <a name="auto_gcrootswap"></a><a name="swap"></a> auto_gcroot:: swap

Nesneleri başka bir metinle değiştirir `auto_gcroot` .

```cpp
void swap(
   auto_gcroot<_element_type> & _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
`auto_gcroot`Nesneleri takas edilecek.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_swap.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s1 = "string one";
   auto_gcroot<String^> s2 = "string two";

   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
   s1.swap( s2 );
   Console::WriteLine( "s1 = '{0}', s2 = '{1}'",
      s1->ToString(), s2->ToString() );
}
```

```Output
s1 = 'string one', s2 = 'string two'
s1 = 'string two', s2 = 'string one'
```

## <a name="auto_gcrootoperator-gt"></a><a name="operator-arrow"></a> auto_gcroot:: operator-&gt;

Üye erişim işleci.

```cpp
_element_type operator->() const;
```

### <a name="return-value"></a>Döndürülen değer

Tarafından Sarmalanan nesne `auto_gcroot` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_op_arrow.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {}

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }

   int m_i;
};

int main() {
   auto_gcroot<ClassA^> a( gcnew ClassA( "first" ) );
   a->PrintHello();

   a->m_i = 5;
   Console::WriteLine( "a->m_i = {0}", a->m_i );
}
```

```Output
Hello from first A!
a->m_i = 5
```

## <a name="auto_gcrootoperator"></a><a name="operator-assign"></a> auto_gcroot:: operator =

Atama işleci.

```cpp
auto_gcroot<_element_type> & operator=(
   _element_type _right
);
auto_gcroot<_element_type> & operator=(
   auto_gcroot<_element_type> & _right
);
template<typename _other_type>
auto_gcroot<_element_type> & operator=(
   auto_gcroot<_other_type> & _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
Ya da geçerli bir nesneye `auto_gcroot` Atanacak `auto_gcroot` .

### <a name="return-value"></a>Döndürülen değer

Geçerli `auto_gcroot` , artık sahip `_right` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_operator_equals.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA(String^ s) : m_s(s) {
      Console::WriteLine( "in ClassA constructor: " + m_s );
   }
   ~ClassA() {
      Console::WriteLine( "in ClassA destructor: " + m_s );
   }

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String^ s ) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main()
{
   auto_gcroot<ClassA^> a;
   auto_gcroot<ClassA^> a2(gcnew ClassA( "first" ) );
   a = a2; // assign from same type
   a->PrintHello();

   ClassA^ ha = gcnew ClassA( "second" );
   a = ha; // assign from raw handle

   auto_gcroot<ClassB^> b(gcnew ClassB( "third" ) );
   b->PrintHello();
   a = b; // assign from derived type
   a->PrintHello();

   Console::WriteLine("done");
}
```

```Output
in ClassA constructor: first
Hello from first A!
in ClassA constructor: second
in ClassA destructor: first
in ClassA constructor: third
Hello from third B!
in ClassA destructor: second
Hello from third A!
done
in ClassA destructor: third
```

## <a name="auto_gcrootoperator-auto_gcroot"></a><a name="operator-auto-gcroot"></a> auto_gcroot:: operator auto_gcroot

Ve uyumlu türler arasında tür atama işleci `auto_gcroot` .

```cpp
template<typename _other_type>
operator auto_gcroot<_other_type>();
```

### <a name="return-value"></a>Döndürülen değer

Geçerli `auto_gcroot` atama `auto_gcroot<_other_type>` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_op_auto_gcroot.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

ref class ClassA {
protected:
   String^ m_s;
public:
   ClassA( String^ s ) : m_s( s ) {}

   virtual void PrintHello() {
      Console::WriteLine( "Hello from {0} A!", m_s );
   }
};

ref class ClassB : ClassA {
public:
   ClassB( String ^ s) : ClassA( s ) {}
   virtual void PrintHello() new {
      Console::WriteLine( "Hello from {0} B!", m_s );
   }
};

int main() {
   auto_gcroot<ClassB^> b = gcnew ClassB("first");
   b->PrintHello();
   auto_gcroot<ClassA^> a = (auto_gcroot<ClassA^>)b;
   a->PrintHello();
}
```

```Output
Hello from first B!
Hello from first A!
```

## <a name="auto_gcrootoperator-bool"></a><a name="operator-bool"></a> auto_gcroot:: operator bool

`auto_gcroot`Bir koşullu ifadede kullanmak için işleci.

```cpp
operator bool() const;
```

### <a name="return-value"></a>Döndürülen değer

**`true`** Sarmalanan nesne geçerliyse; **`false`** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç `_detail_class::_safe_bool` , **`bool`** bir integral türüne dönüştürülemediğinden daha güvenli olan ' a dönüştürülür.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s;
   if ( s ) Console::WriteLine( "s is valid" );
   if ( !s ) Console::WriteLine( "s is invalid" );
   s = "something";
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
   s.reset();
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
}
```

```Output
s is invalid
now s is valid
now s is invalid
```

## <a name="auto_gcrootoperator"></a><a name="operator-logical-not"></a> auto_gcroot:: operator!

`auto_gcroot`Bir koşullu ifadede kullanmak için işleci.

```cpp
bool operator!() const;
```

### <a name="return-value"></a>Döndürülen değer

**`true`** Sarmalanan nesne geçersiz ise; **`false`** Aksi takdirde.

### <a name="example"></a>Örnek

```cpp
// msl_auto_gcroot_operator_not.cpp
// compile with: /clr
#include <msclr\auto_gcroot.h>

using namespace System;
using namespace msclr;

int main() {
   auto_gcroot<String^> s;
   if ( s ) Console::WriteLine( "s is valid" );
   if ( !s ) Console::WriteLine( "s is invalid" );
   s = "something";
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
   s.reset();
   if ( s ) Console::WriteLine( "now s is valid" );
   if ( !s ) Console::WriteLine( "now s is invalid" );
}
```

```Output
s is invalid
now s is valid
now s is invalid
```
