---
description: 'Hakkında daha fazla bilgi edinin: auto_handle sınıfı'
title: auto_handle Sınıfı
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::auto_handle::auto_handle
- msclr::auto_handle::get
- msclr::auto_handle::release
- msclr::auto_handle::reset
- msclr::auto_handle::swap
- msclr::auto_handle::operator->
- msclr::auto_handle::operator=
- msclr::auto_handle::operator auto_handle
- msclr::auto_handle::operator!
helpviewer_keywords:
- msclr::auto_handle class
ms.assetid: a65604d1-ecbb-44fd-ae2f-696ddeeed9d6
ms.openlocfilehash: 9ac93d6b141f24a430aceb97f82fc90046622866
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282659"
---
# <a name="auto_handle-class"></a>auto_handle Sınıfı

Bir sanal tanıtıcıyı yönetilen bir türe eklemek için kullanılabilen otomatik kaynak yönetimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _element_type>
ref class auto_handle;
```

### <a name="parameters"></a>Parametreler

*_element_type*<br/>
Katıştırılacak yönetilen tür.

## <a name="members"></a><a name="members"></a> Üyeleri

### <a name="public-constructors"></a>Ortak oluşturucular  

|Ad|Açıklama|  
|---------|-----------|  
|[auto_handle::auto_handle](#auto-handle)|`auto_handle`Oluşturucu.|  
|[auto_handle:: ~ auto_handle](#tilde-auto-handle)|`auto_handle`Yok edicisi.|  

### <a name="public-methods"></a>Ortak Yöntemler  

|Ad|Açıklama|  
|---------|-----------|  
|[auto_handle::get](#get)|İçerilen nesneyi alır.|  
|[auto_handle::release](#release)|Nesneyi yönetimden serbest bırakır `auto_handle` .|
|[auto_handle::reset](#reset)|Geçerli sahip olan nesneyi yok edin ve isteğe bağlı olarak yeni bir nesne sahipliğini alın.|
|[auto_handle::swap](#swap)|Nesneleri başka bir metinle değiştirir `auto_handle` .|  

### <a name="public-operators"></a>Ortak işleçler

|Ad|Açıklama|  
|---------|-----------|
|[auto_handle:: operator-&gt;](#operator-arrow)|Üye erişim işleci.|
|[auto_handle::operator=](#operator-assign)|Atama işleci.|
|[auto_handle::operator auto_handle](#operator-auto-handle)|Ve uyumlu türler arasında tür atama işleci `auto_handle` .|  
|[auto_handle::operator bool](#operator-bool)|`auto_handle`Bir koşullu ifadede kullanmak için işleci.|
|[auto_handle:: operator!](#operator-logical-not)|`auto_handle`Bir koşullu ifadede kullanmak için işleci.|  

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası**\<msclr\auto_handle.h>

**Ad alanı** msclr

## <a name="auto_handleauto_handle"></a><a name="auto-handle"></a> auto_handle:: auto_handle

`auto_handle`Oluşturucu.

```cpp
auto_handle();
auto_handle(
   _element_type ^ _ptr
);
auto_handle(
   auto_handle<_element_type> % _right
);
template<typename _other_type>
auto_handle(
   auto_handle<_other_type> % _right
);
```

### <a name="parameters"></a>Parametreler

*_ptr*<br/>
Kendisine ait nesne.

*_right*<br/>
Mevcut bir `auto_handle` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_auto_handle.cpp
// compile with: /clr
#include "msclr\auto_handle.h"

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

int main()
{
   {
      auto_handle<RefClassA> a(gcnew RefClassA( "first" ) );
      a->PrintHello();
   }

   {
      auto_handle<RefClassB> b(gcnew RefClassB( "second" ) );
      b->PrintHello();
      auto_handle<RefClassA> a(b); //construct from derived type
      a->PrintHello();
      auto_handle<RefClassA> a2(a); //construct from same type
      a2->PrintHello();
   }

   Console::WriteLine("done");
}
```

```Output
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

## <a name="auto_handleauto_handle"></a><a name="tilde-auto-handle"></a> auto_handle:: ~ auto_handle

`auto_handle`Yok edicisi.

```cpp
~auto_handle();
```

### <a name="remarks"></a>Açıklamalar

Yıkıcı, sahip olunan nesnenin yapılarını da kaldırır.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_dtor.cpp
// compile with: /clr
#include "msclr\auto_handle.h"

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
      auto_handle<ClassA> a = gcnew ClassA;
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

## <a name="auto_handleget"></a><a name="get"></a> auto_handle:: Get

İçerilen nesneyi alır.

```cpp
_element_type ^ get();
```

### <a name="return-value"></a>Döndürülen değer

Kapsanan nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_get.cpp
// compile with: /clr
#include "msclr\auto_handle.h"

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
   auto_handle<ClassA> a = gcnew ClassA( "first" );
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

## <a name="auto_handlerelease"></a><a name="release"></a> auto_handle:: Release

Nesneyi yönetimden serbest bırakır `auto_handle` .

```cpp
_element_type ^ release();
```

### <a name="return-value"></a>Döndürülen değer

Yayınlanan nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_release.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

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
      auto_handle<ClassA> agc1 = gcnew ClassA( "first" );
      auto_handle<ClassA> agc2 = gcnew ClassA( "second" );
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

## <a name="auto_handlereset"></a><a name="reset"></a> auto_handle:: Reset

Geçerli sahip olan nesneyi yok edin ve isteğe bağlı olarak yeni bir nesne sahipliğini alın.

```cpp
void reset(
   _element_type ^ _new_ptr
);
void reset();
```

### <a name="parameters"></a>Parametreler

*_new_ptr*<br/>
Seçim Yeni nesne.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_reset.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

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
   auto_handle<ClassA> agc1 = gcnew ClassA( "first" );
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

## <a name="auto_handleswap"></a><a name="swap"></a> auto_handle:: swap

Nesneleri başka bir metinle değiştirir `auto_handle` .

```cpp
void swap(
   auto_handle<_element_type> % _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
`auto_handle`Nesneleri takas edilecek.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_swap.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1 = "string one";
   auto_handle<String> s2 = "string two";

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

## <a name="auto_handleoperator-gt"></a><a name="operator-arrow"></a> auto_handle:: operator-&gt;

Üye erişim işleci.

```cpp
_element_type ^ operator->();
```

### <a name="return-value"></a>Döndürülen değer

Tarafından Sarmalanan nesne `auto_handle` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_op_arrow.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

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
   auto_handle<ClassA> a( gcnew ClassA( "first" ) );
   a->PrintHello();

   a->m_i = 5;
   Console::WriteLine( "a->m_i = {0}", a->m_i );
}
```

```Output
Hello from first A!
a->m_i = 5
```

## <a name="auto_handleoperator"></a><a name="operator-assign"></a> auto_handle:: operator =

Atama işleci.

```cpp
auto_handle<_element_type> % operator=(
   auto_handle<_element_type> % _right
);
template<typename _other_type>
auto_handle<_element_type> % operator=(
   auto_handle<_other_type> % _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
`auto_handle`Geçerli öğesine atanacak `auto_handle` .

### <a name="return-value"></a>Döndürülen değer

Geçerli `auto_handle` , artık sahip `_right` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_op_assign.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

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
   auto_handle<ClassA> a;
   auto_handle<ClassA> a2(gcnew ClassA( "first" ) );
   a = a2; // assign from same type
   a->PrintHello();

   auto_handle<ClassB> b(gcnew ClassB( "second" ) );
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
Hello from second B!
in ClassA destructor: first
Hello from second A!
done
in ClassA destructor: second
```

## <a name="auto_handleoperator-auto_handle"></a><a name="operator-auto-handle"></a> auto_handle:: operator auto_handle

Ve uyumlu türler arasında tür atama işleci `auto_handle` .

```cpp
template<typename _other_type>
operator auto_handle<_other_type>();
```

### <a name="return-value"></a>Döndürülen değer

Geçerli `auto_handle` atama `auto_handle<_other_type>` .

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_op_auto_handle.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

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
   auto_handle<ClassB> b = gcnew ClassB("first");
   b->PrintHello();
   auto_handle<ClassA> a = (auto_handle<ClassA>)b;
   a->PrintHello();
}
```

```Output
Hello from first B!
Hello from first A!
```

## <a name="auto_handleoperator-bool"></a><a name="operator-bool"></a> auto_handle:: operator bool

`auto_handle`Bir koşullu ifadede kullanmak için işleci.

```cpp
operator bool();
```

### <a name="return-value"></a>Döndürülen değer

**`true`** Sarmalanan nesne geçerliyse; **`false`** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç gerçekten `_detail_class::_safe_bool` , **`bool`** bir integral türüne dönüştürülemediğinden daha güvenli olan öğesine dönüştürür.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_operator_bool.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1;
   auto_handle<String> s2 = "hi";
   if ( s1 ) Console::WriteLine( "s1 is valid" );
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );
   if ( s2 ) Console::WriteLine( "s2 is valid" );
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );
   s2.reset();
   if ( s2 ) Console::WriteLine( "s2 is now valid" );
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );
}
```

```Output
s1 is invalid
s2 is valid
s2 is now invalid
```

## <a name="auto_handleoperator"></a><a name="operator-logical-not"></a> auto_handle:: operator!

`auto_handle`Bir koşullu ifadede kullanmak için işleci.

```cpp
bool operator!();
```

### <a name="return-value"></a>Döndürülen değer

**`true`** Sarmalanan nesne geçersiz ise; **`false`** Aksi takdirde.

### <a name="example"></a>Örnek

```cpp
// msl_auto_handle_operator_not.cpp
// compile with: /clr
#include <msclr\auto_handle.h>

using namespace System;
using namespace msclr;

int main() {
   auto_handle<String> s1;
   auto_handle<String> s2 = "something";
   if ( s1) Console::WriteLine( "s1 is valid" );
   if ( !s1 ) Console::WriteLine( "s1 is invalid" );
   if ( s2 ) Console::WriteLine( "s2 is valid" );
   if ( !s2 ) Console::WriteLine( "s2 is invalid" );
   s2.reset();
   if ( s2 ) Console::WriteLine( "s2 is now valid" );
   if ( !s2 ) Console::WriteLine( "s2 is now invalid" );
}
```

```Output
s1 is invalid
s2 is valid
s2 is now invalid
```
