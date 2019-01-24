---
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
ms.openlocfilehash: ad98bfa9ff447f08c458427961b427e0f2087e62
ms.sourcegitcommit: 9813e146a4eb30929d8352872859e8fcb7ff6d2f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54806013"
---
# <a name="autohandle-class"></a>auto_handle Sınıfı

Otomatik kaynak yönetimi, yönetilen bir türe sanal bir işleyici eklemek için kullanılabilir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename _element_type>
ref class auto_handle;
```

### <a name="parameters"></a>Parametreler

*_element_type*<br/>
Katıştırılmış yönetilen türü.

## <a name="members"></a>Üyeleri 

### <a name="public-constructors"></a>Genel oluşturucular  

|Ad|Açıklama|  
|---------|-----------|  
|[auto_handle::auto_handle](#auto-handle)|`auto_handle` Oluşturucusu.|  
|[auto_handle::~auto_handle](#tilde-auto-handle)|`auto_handle` Yıkıcı.|  

### <a name="public-methods"></a>Genel yöntemler  

|Ad|Açıklama|  
|---------|-----------|  
|[auto_handle::get](#get)|Kapsanan nesne alır.|  
|[auto_handle::release](#release)|Nesneden serbest `auto_handle` yönetimi.|
|[auto_handle::reset](#reset)|Geçerli ait bir nesneyi yok ve isteğe bağlı olarak yeni bir nesne elinde gerçekleştirin.| 
|[auto_handle::swap](#swap)|Başka bir nesneyle değiştirir `auto_handle`.|  

### <a name="public-operators"></a>Genel işleçler 

|Ad|Açıklama|  
|---------|-----------| 
|[auto_handle::operator-&gt;](#operator-arrow)|Üye erişimi işleci.|   
|[auto_handle::operator=](#operator-assign)|Atama işleci.| 
|[auto_handle::operator auto_handle](#operator-auto-handle)|Tür atama işleci arasında `auto_handle` ve uyumlu türleri.|  
|[auto_handle::operator bool](#operator-bool)|Kullanarak işleci `auto_handle` koşullu ifadede.|   
|[auto_handle::operator!](#operator-logical-not)|Kullanarak işleci `auto_handle` koşullu ifadede.|  

## <a name="requirements"></a>Gereksinimler

**Üst bilgi dosyası** \<msclr\auto_handle.h >

**Namespace** msclr

## <a name="auto-handle"></a>auto_handle::auto_handle

`auto_handle` Oluşturucusu.

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
Kendi hedef nesne.

*_right*<br/>
Mevcut bir `auto_handle`.

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

## <a name="tilde-auto-handle"></a>auto_handle:: ~ auto_handle

`auto_handle` Yıkıcı.

```cpp
~auto_handle();
```

### <a name="remarks"></a>Açıklamalar

Yok Edicisi de sahip olduğu nesne destructs.

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

## <a name="get"></a>auto_handle::get

Kapsanan nesne alır.

```cpp
_element_type ^ get();
```

### <a name="return-value"></a>Dönüş değeri

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

## <a name="release"></a>auto_handle::Release

Nesneden serbest `auto_handle` yönetimi.

```cpp
_element_type ^ release();
```

### <a name="return-value"></a>Dönüş değeri

Yayımlanan nesne.

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

## <a name="reset"></a>auto_handle::reset

Geçerli ait bir nesneyi yok ve isteğe bağlı olarak yeni bir nesne elinde gerçekleştirin.


```cpp
void reset(
   _element_type ^ _new_ptr
);
void reset();
```

### <a name="parameters"></a>Parametreler

*_new_ptr*<br/>
(İsteğe bağlı) Yeni nesne.

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

## <a name="swap"></a>auto_handle::Swap

Başka bir nesneyle değiştirir `auto_handle`.

```cpp
void swap(
   auto_handle<_element_type> % _right
);
```

### <a name="parameters"></a>Parametreler

*_right*<br/>
`auto_handle` Hangi ile takas nesneleri.

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

## <a name="operator-arrow"></a>auto_handle::operator-&gt;

Üye erişimi işleci.

```cpp
_element_type ^ operator->();
```

### <a name="return-value"></a>Dönüş değeri

Tarafından Sarmalanan nesne `auto_handle`.

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

## <a name="operator-assign"></a>auto_handle::operator =

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
`auto_handle` Geçerli atanacak `auto_handle`.

### <a name="return-value"></a>Dönüş değeri

Geçerli `auto_handle`, artık sahip olan `_right`.

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

## <a name="operator-auto-handle"></a>auto_handle::operator auto_handle

Tür atama işleci arasında `auto_handle` ve uyumlu türleri.


```cpp
template<typename _other_type>
operator auto_handle<_other_type>();
```

### <a name="return-value"></a>Dönüş değeri

Geçerli `auto_handle` başvurusuna `auto_handle<_other_type>`.

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

## <a name="operator-bool"></a>auto_handle::operator bool

Kullanarak işleci `auto_handle` koşullu ifadede.

```cpp
operator bool();
```

### <a name="return-value"></a>Dönüş değeri

`true` Sarmalanan nesne geçerli değil `false` Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu işleç gerçekten dönüştürür `_detail_class::_safe_bool` daha güvenli olan `bool` bir integral türe dönüştürülemediğinden.

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

## <a name="operator-logical-not"></a>auto_handle::operator!

Kullanarak işleci `auto_handle` koşullu ifadede.

```cpp
bool operator!();
```

### <a name="return-value"></a>Dönüş değeri

`true` Sarmalanan Nesne geçersiz `false` Aksi takdirde.

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