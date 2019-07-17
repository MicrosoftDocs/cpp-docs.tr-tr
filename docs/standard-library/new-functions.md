---
title: '&lt;Yeni&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- new/std::get_new_handler
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: c912e5be07ea0ebdd3148d30c80c39a5f8cfa1a5
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68243662"
---
# <a name="ltnewgt-functions"></a>&lt;Yeni&gt; işlevleri

## <a name="get_new_handler"></a> get_new_handler

```cpp
new_handler get_new_handler() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Geçerli döndürür `new_handler`.

## <a name="launder"></a> launder

```cpp
template <class T>
    constexpr T* launder(T* ptr) noexcept;
```

### <a name="parameters"></a>Parametreler

*PTR*\
Bellekte bir nesne türü içeren bir bayt adresini benzer *T*.

### <a name="return-value"></a>Dönüş Değeri

Türünde bir değer *T\**  X işaret eder.

### <a name="remarks"></a>Açıklamalar

Bir işaretçi iyileştirme engel da bilinir.

Sabit bir ifadede, bağımsız değişkenin değeri kullanılabilir olduğunda, sabit bir ifade kullanılır. Depolama baytı ise başka bir nesne, benzer bir işaretçi bir nesne tarafından kullanılan depolama içinde bir nesneye işaret eden bir işaretçi değeri aracılığıyla erişilebilir.

### <a name="example"></a>Örnek

```cpp
struct X { const int n; };

X *p = new X{3};
const int a = p->n;
new (p) X{5}; // p does not point to new object because X::n is const
const int b = p->n; // undefined behavior
const int c = std::launder(p)->n; // OK
```

## <a name="nothrow"></a> nothrow

Bir bağımsız değişken olarak kullanılacak nesne sağlar **nothrow** sürümlerini **yeni** ve **Sil**.

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Açıklamalar

Nesne parametre türüyle eşleşecek şekilde bir işlev bağımsız değişken olarak kullanılan [std::nothrow_t](../standard-library/nothrow-t-structure.md).

### <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.

## <a name="set_new_handler"></a> set_new_handler

Ne zaman çağrılacak olan bir kullanıcı işlevi yükler **new işleci** bellek ayırmak için kendi denemesi başarısız olur.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>Parametreler

*Pnew*\
`new_handler` Yüklenecek.

### <a name="return-value"></a>Dönüş Değeri

İlk çağrı ve önceki 0 `new_handler` arka arkaya çağrı.

### <a name="remarks"></a>Açıklamalar

İşlev depoları *Pnew* statik olarak [yeni işleyici](../standard-library/new-typedefs.md#new_handler) bu tutar, işaretçi, ardından daha önce işaretçide depolanan değeri döndürür. Yeni işleyici tarafından kullanılan [new işleci](../standard-library/new-operators.md#op_new)(**size_t**).

### <a name="example"></a>Örnek

```cpp
// new_set_new_handler.cpp
// compile with: /EHsc
#include<new>
#include<iostream>

using namespace std;
void __cdecl newhandler( )
{
   cout << "The new_handler is called:" << endl;
   throw bad_alloc( );
   return;
}

int main( )
{
   set_new_handler (newhandler);
   try
   {
      while ( 1 )
      {
         new int[5000000];
         cout << "Allocating 5000000 ints." << endl;
      }
   }
   catch ( exception e )
   {
      cout << e.what( ) << endl;
   }
}
```

```Output
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
Allocating 5000000 ints.
The new_handler is called:
bad allocation
```
