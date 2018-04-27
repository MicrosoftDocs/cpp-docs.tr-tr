---
title: '&lt;bellek&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
dev_langs:
- C++
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c695aae2a15bc2536ee4f8e05764b2a73900cff5
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltmemorygt-operators"></a>&lt;bellek&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[işleci&gt;](#op_gt)|[işleci&gt;=](#op_gt_eq)|
|[işleci&lt;](#op_lt)|[işleci&lt;&lt;](#op_lt_lt)|[işleci&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

Testleri eşitsizlik açısından nesneler arasında.

```cpp
template <class Type, class Other>
bool operator!=(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class T, class Del1, class U, class Del2>
bool operator!=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator!=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Eşitsizlik için sınanacak nesnelerinden biri.

`right` Eşitsizlik için sınanacak nesnelerinden biri.

`Ty1` Sol paylaşılan işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ paylaşılan işaretçiyi tarafından denetlenen türü.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneleri eşit; değilse **false** nesneleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci false değerini döndürür. (Tüm varsayılan allocators eşit.)

İkinci ve üçüncü şablon işleçleri dönmek `!(left == right)`.

### <a name="example"></a>Örnek

```cpp
// memory_op_me.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<double> Alloc;
   vector <char>:: allocator_type v1Alloc;

   if ( Alloc != v1Alloc )
      cout << "The allocator objects Alloc & v1Alloc not are equal."
           << endl;
   else
      cout << "The allocator objects Alloc & v1Alloc are equal."
           << endl;
}
```

```Output
The allocator objects Alloc & v1Alloc are equal.
```

### <a name="example"></a>Örnek

```cpp
// std__memory__operator_ne.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 != sp0 == " << std::boolalpha
        << (sp0 != sp0) << std::endl;
    std::cout << "sp0 != sp1 == " << std::boolalpha
        << (sp0 != sp1) << std::endl;

    return (0);
    }

```

```Output
sp0 != sp0 == false
sp0 != sp1 == true
```

## <a name="op_eq_eq"></a>  operator ==

Nesneler arasındaki eşitlik için test.

```cpp
template <class Type, class Other>
bool operator==(
    const allocator<Type>& left,
    const allocator<Other>& right) throw();

template <class Ty1, class Del1, class Ty2, class Del2>
bool operator==(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2, Del2>& right);

template <class Ty1, class Ty2>
bool operator==(
    const shared_ptr<Ty1>& left;,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Bir nesnenin eşitlik için test edilmelidir.

`right` Bir nesnenin eşitlik için test edilmelidir.

`Ty1` Sol paylaşılan işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ paylaşılan işaretçiyi tarafından denetlenen türü.

### <a name="return-value"></a>Dönüş Değeri

`true` nesneleri eşitse `false` nesneleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci true değerini döndürür. (Tüm varsayılan allocators eşit.)

İkinci ve üçüncü şablon işleçleri dönmek ` left.get() ==  right.get()`.

### <a name="example"></a>Örnek

```cpp
// memory_op_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>
#include <vector>

using namespace std;

int main( )
{
   allocator<char> Alloc;
   vector <int>:: allocator_type v1Alloc;

   allocator<char> cAlloc(Alloc);
   allocator<int> cv1Alloc(v1Alloc);

   if ( cv1Alloc == v1Alloc )
      cout << "The allocator objects cv1Alloc & v1Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cv1Alloc & v1Alloc are not equal."
           << endl;

   if ( cAlloc == Alloc )
      cout << "The allocator objects cAlloc & Alloc are equal."
           << endl;
   else
      cout << "The allocator objects cAlloc & Alloc are not equal."
           << endl;
}
```

```Output
The allocator objects cv1Alloc & v1Alloc are equal.
The allocator objects cAlloc & Alloc are equal.
```

### <a name="example"></a>Örnek

```cpp
// std__memory__operator_eq.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(0));
    std::shared_ptr<int> sp1(new int(0));

    std::cout << "sp0 == sp0 == " << std::boolalpha
        << (sp0 == sp0) << std::endl;
    std::cout << "sp0 == sp1 == " << std::boolalpha
        << (sp0 == sp1) << std::endl;

    return (0);
    }

```

```Output
sp0 == sp0 == true
sp0 == sp1 == false
```

## <a name="op_gt_eq"></a>  işleci&gt;=

Testler için ikinci bir nesneye eşit veya daha büyük olan bir nesne.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator>=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U, Del2>& right);

template <class Ty1, class Ty2>
bool operator>=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Bir Karşılaştırılacak nesne.

`right` Bir Karşılaştırılacak nesne.

`Ty1` Sol paylaşılan işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ paylaşılan işaretçiyi tarafından denetlenen türü.

### <a name="remarks"></a>Açıklamalar

Şablon işleçleri dönmek `left.get() >= right.get()`.

## <a name="op_lt"></a>  işleci&lt;

Testler için bir nesne olma ikinci nesneden küçüktür.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Bir Karşılaştırılacak nesne.

`right` Bir Karşılaştırılacak nesne.

`Ty1` Sol işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ işaretçiyi tarafından denetlenen türü.

## <a name="op_lt_eq"></a>  işleci&lt;=

Testler için ikinci bir nesneye eşit veya daha az olan bir nesne.

```cpp
template <class T, class Del1, class U, class Del2>
bool operator<=(
    const unique_ptr<T, Del1>& left,
    const unique_ptr<U&, Del2>& right);

template <class Ty1, class Ty2>
bool operator<=(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Bir Karşılaştırılacak nesne.

`right` Bir Karşılaştırılacak nesne.

`Ty1` Sol paylaşılan işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ paylaşılan işaretçiyi tarafından denetlenen türü.

### <a name="remarks"></a>Açıklamalar

Şablon işleçleri Döndür `left.get() <= right.get()`

## <a name="op_gt"></a>  işleci&gt;

Testleri bir ikinci nesneden büyük olan bir nesne için.

```cpp
template <class Ty1, class Del1, class Ty2, class Del2>
bool operator>(
    const unique_ptr<Ty1, Del1>& left,
    const unique_ptr<Ty2&, Del2gt;& right);

template <class Ty1, class Ty2>
bool operator>(
    const shared_ptr<Ty1>& left,
    const shared_ptr<Ty2>& right);
```

### <a name="parameters"></a>Parametreler

`left` Bir Karşılaştırılacak nesne.

`right` Bir Karşılaştırılacak nesne.

`Ty1` Sol paylaşılan işaretçiyi tarafından denetlenen türü.

`Ty2` Sağ paylaşılan işaretçiyi tarafından denetlenen türü.

## <a name="op_lt_lt"></a>  işleci&lt;&lt;

Paylaşılan işaretçi akışa yazar.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametreler

`Elem` Akış öğesi türü.

`Tr` Tür akış öğesi nitelikler.

`Ty` Paylaşılan işaretçiyi tarafından denetlenen türü.

`out` Çıkış akışı.

`sp` Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi döndürür `out << sp.get()`.

### <a name="example"></a>Örnek

```cpp
// std__memory__operator_sl.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "sp0 == " << sp0 << " (varies)" << std::endl;

    return (0);
    }

```

```Output
sp0 == 3f3040 (varies)
```

## <a name="see-also"></a>Ayrıca bkz.

[\<bellek >](../standard-library/memory.md)<br/>
