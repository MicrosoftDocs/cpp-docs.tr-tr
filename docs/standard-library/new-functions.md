---
title: Yeni&gt; işlevleri &lt;
ms.date: 11/04/2016
f1_keywords:
- new/std::get_new_handler
- new/std::nothrow
- new/std::set_new_handler
ms.assetid: e250f06a-b025-4509-ae7a-5356d56aad7d
ms.openlocfilehash: c912e5be07ea0ebdd3148d30c80c39a5f8cfa1a5
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78854957"
---
# <a name="ltnewgt-functions"></a>Yeni&gt; işlevleri &lt;

## <a name="get_new_handler"></a>get_new_handler

```cpp
new_handler get_new_handler() noexcept;
```

### <a name="remarks"></a>Açıklamalar

Geçerli `new_handler`döndürür.

## <a name="launder"></a>eksik

```cpp
template <class T>
    constexpr T* launder(T* ptr) noexcept;
```

### <a name="parameters"></a>Parametreler

*ptr*\
Türü *T*'ye benzer bir nesneyi tutan bellekteki bir baytın adresi.

### <a name="return-value"></a>Dönüş Değeri

X 'e işaret eden *T\** türünde bir değer.

### <a name="remarks"></a>Açıklamalar

Ayrıca işaretçi iyileştirme engeli olarak da adlandırılır.

Bağımsız değişkeninin değeri sabit bir ifadede kullanılıyorsa, sabit bir ifade olarak kullanılır. Başka bir nesnenin kapladığı depolama alanında, benzer işaretçili bir nesne olan bir nesne için bir bayt depolama alanına ulaşılabilir.

### <a name="example"></a>Örnek

```cpp
struct X { const int n; };

X *p = new X{3};
const int a = p->n;
new (p) X{5}; // p does not point to new object because X::n is const
const int b = p->n; // undefined behavior
const int c = std::launder(p)->n; // OK
```

## <a name="nothrow"></a>nothrow

**New** ve **Delete**'in **nothrow** sürümleri için bağımsız değişken olarak kullanılacak bir nesne sağlar.

```cpp
extern const std::nothrow_t nothrow;
```

### <a name="remarks"></a>Açıklamalar

Nesne, [std:: nothrow_t](../standard-library/nothrow-t-structure.md)parametre türü ile eşleşen bir işlev bağımsız değişkeni olarak kullanılır.

### <a name="example"></a>Örnek

`std::nothrow_t` işlev parametresi olarak nasıl kullanıldığına ilişkin örnekler için [New işlecine](../standard-library/new-operators.md#op_new) ve [New&#91; ](../standard-library/new-operators.md#op_new_arr) işlecine bakın.

## <a name="set_new_handler"></a>set_new_handler

**Yeni işleç** , bellek ayırma denemesinde başarısız olduğunda çağrılacak bir Kullanıcı işlevi yüklüyor.

```cpp
new_handler set_new_handler(new_handler Pnew) throw();
```

### <a name="parameters"></a>Parametreler

*Pnew*\
Yüklenecek `new_handler`.

### <a name="return-value"></a>Dönüş Değeri

ilk çağrıda 0 ve sonraki çağrılarda önceki `new_handler`.

### <a name="remarks"></a>Açıklamalar

İşlevi, tuttuğu bir statik [yeni işleyici](../standard-library/new-typedefs.md#new_handler) Işaretçisine *pnew* ' i depolar ve daha önce işaretçide depolanan değeri döndürür. Yeni işleyici [New işleci](../standard-library/new-operators.md#op_new)(**size_t**) tarafından kullanılır.

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
