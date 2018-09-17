---
title: '&lt;Yeni&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: 6192805f0f427f86267a646b11d9f1d3365a1d57
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716046"
---
# <a name="ltnewgt-functions"></a>&lt;Yeni&gt; işlevleri

|||
|-|-|
|[nothrow](#nothrow)|[set_new_handler](#set_new_handler)|

## <a name="nothrow"></a>  nothrow

Bir bağımsız değişken olarak kullanılacak nesne sağlar **nothrow** sürümlerini **yeni** ve **Sil**.

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Açıklamalar

Nesne parametre türüyle eşleşecek şekilde bir işlev bağımsız değişken olarak kullanılan [std::nothrow_t](../standard-library/nothrow-t-structure.md).

### <a name="example"></a>Örnek

Bkz: [new işleci](../standard-library/new-operators.md#op_new) ve [new işleci&#91; &#93; ](../standard-library/new-operators.md#op_new_arr) örnekleri için `std::nothrow_t` işlevi parametre olarak kullanılır.

## <a name="set_new_handler"></a>  set_new_handler

Ne zaman çağrılacak olan bir kullanıcı işlevi yükler **new işleci** bellek ayırmak için kendi denemesi başarısız olur.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>Parametreler

*Pnew*<br/>
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

## <a name="see-also"></a>Ayrıca bkz.

[\<Yeni >](../standard-library/new.md)<br/>
