---
title: '&lt;bellek&gt; işleçler | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ad33ff04c688ab79fa4a73234829d3e13fd1b44d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38954241"
---
# <a name="ltmemorygt-operators"></a>&lt;bellek&gt; işleçleri

||||
|-|-|-|
|[operator!=](#op_neq)|[İşleci&gt;](#op_gt)|[İşleci&gt;=](#op_gt_eq)|
|[İşleci&lt;](#op_lt)|[İşleci&lt;&lt;](#op_lt_lt)|[İşleci&lt;=](#op_lt_eq)|
|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

Nesneleri arasındaki eşitsizliği sınar.

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

*Sol* eşitsizlik için test edilecek nesnelerden biri.

*doğru* eşitsizlik için test edilecek nesnelerden biri.

*Ty1* sol tarafından kontrol edilen tür paylaşılan işaretçi.

*Ty2* sağ tarafından kontrol edilen tür paylaşılan işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşit; değilse, **false** nesneler eşit ise.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlecini false döndürür. (Tüm varsayılan ayırıcılar eşit olur.)

İkinci ve üçüncü şablon işleçlerin dönüş `!(left == right)`.

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

## <a name="op_eq_eq"></a>  işleç ==

Nesneleri arasındaki eşitliği sınar.

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

*Sol* eşitlik için test edilecek nesnelerden biri.

*doğru* eşitlik için test edilecek nesnelerden biri.

*Ty1* sol tarafından kontrol edilen tür paylaşılan işaretçi.

*Ty2* sağ tarafından kontrol edilen tür paylaşılan işaretçi.

### <a name="return-value"></a>Dönüş Değeri

**doğru** nesneler eşitse **false** nesneler eşit değilse.

### <a name="remarks"></a>Açıklamalar

İlk şablon işlecini true değerini döndürür. (Tüm varsayılan ayırıcılar eşit olur.)

İkinci ve üçüncü şablon işleçlerin dönüş `left.get() ==  right.get()`.

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

## <a name="op_gt_eq"></a>  İşleci&gt;=

Bir nesnesinin değerinden büyük veya eşittir ikinci bir nesnesinin sınar.

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

*Sol* bir Karşılaştırılacak nesne.

*doğru* bir Karşılaştırılacak nesne.

*Ty1* sol tarafından kontrol edilen tür paylaşılan işaretçi.

*Ty2* sağ tarafından kontrol edilen tür paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işleçlerin dönüş `left.get() >= right.get()`.

## <a name="op_lt"></a>  İşleci&lt;

Bir nesnesinin değerinden küçük olmasını ikinci bir nesnesinin sınar.

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

*Sol* bir Karşılaştırılacak nesne.

*doğru* bir Karşılaştırılacak nesne.

*Ty1* sol işaretçiyle kontrol edilen tür.

*Ty2* doğru işaretçiyle kontrol edilen tür.

## <a name="op_lt_eq"></a>  İşleci&lt;=

Küçük veya buna eşit bir ikinci nesneye bir nesnesinin sınar.

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

*Sol* bir Karşılaştırılacak nesne.

*doğru* bir Karşılaştırılacak nesne.

*Ty1* sol tarafından kontrol edilen tür paylaşılan işaretçi.

*Ty2* sağ tarafından kontrol edilen tür paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işleçleri döndürür `left.get() <= right.get()`

## <a name="op_gt"></a>  İşleci&gt;

Bir nesnenin ikinci nesneden büyük olan sınar.

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

*Sol* bir Karşılaştırılacak nesne.

*doğru* bir Karşılaştırılacak nesne.

*Ty1* sol tarafından kontrol edilen tür paylaşılan işaretçi.

*Ty2* sağ tarafından kontrol edilen tür paylaşılan işaretçi.

## <a name="op_lt_lt"></a>  İşleci&lt;&lt;

Paylaşılan işaretçi akışa yazar.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametreler

*Elem* akış öğesinin türü.

*Tr* türü akış öğesi özellikleri.

*Ty* paylaşılan işaretçiyle kontrol edilen tür.

*Çıkış* çıkış akışı.

*SP* paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevinin döndürdüğü `out << sp.get()`.

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
