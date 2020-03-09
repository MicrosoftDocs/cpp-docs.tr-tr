---
title: '&lt;bellek&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- memory/std::operator!=
- memory/std::operator>
- memory/std::operator>=
- memory/std::operator<
- memory/std::operator<=
- memory/std::operator<<
- memory/std::operator==
ms.assetid: 257e3ba9-c4c2-4ae8-9b11-b156ba9c28de
ms.openlocfilehash: 661f1bb4c0f5734d88dd23f73c69b362f59a76c2
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78884085"
---
# <a name="ltmemorygt-operators"></a>&lt;bellek&gt; işleçleri

## <a name="op_neq"></a>işleç! =

Nesneler arasında eşitsizlik için testler.

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

*sol*\
Eşitsizlik için test edilecek nesnelerden biri.

*sağ*\
Eşitsizlik için test edilecek nesnelerden biri.

*Ty1*\
Sol paylaşılan işaretçi tarafından denetlenen tür.

*Ty2*\
Doğru paylaşılan işaretçi tarafından denetlenen tür.

### <a name="return-value"></a>Dönüş Değeri

Nesneler eşit değilse **true** ; nesneler eşitse **false** .

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci false döndürür. (Varsayılan ayrıcılar eşittir.)

İkinci ve üçüncü şablon işleçleri `!(left == right)`döndürür.

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

## <a name="op_eq_eq"></a>işleç = =

Nesneler arasındaki eşitlik için testler.

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

*sol*\
Eşitlik için test edilecek nesnelerden biri.

*sağ*\
Eşitlik için test edilecek nesnelerden biri.

*Ty1*\
Sol paylaşılan işaretçi tarafından denetlenen tür.

*Ty2*\
Doğru paylaşılan işaretçi tarafından denetlenen tür.

### <a name="return-value"></a>Dönüş Değeri

nesneler eşitse **true** , nesneler eşitse **false** .

### <a name="remarks"></a>Açıklamalar

İlk şablon işleci true döndürür. (Varsayılan ayrıcılar eşittir.)

İkinci ve üçüncü şablon işleçleri `left.get() ==  right.get()`döndürür.

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

## <a name="op_gt_eq"></a>işleç&gt;=

Bir nesne için ikinci bir nesneden büyük veya ona eşit olan testler.

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

*sol*\
Karşılaştırılacak nesnelerden biri.

*sağ*\
Karşılaştırılacak nesnelerden biri.

*Ty1*\
Sol paylaşılan işaretçi tarafından denetlenen tür.

*Ty2*\
Doğru paylaşılan işaretçi tarafından denetlenen tür.

### <a name="remarks"></a>Açıklamalar

Şablon işleçleri `left.get() >= right.get()`döndürür.

## <a name="op_lt"></a>işleç&lt;

Bir nesne için ikinci bir nesneden daha az olan testler.

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

*sol*\
Karşılaştırılacak nesnelerden biri.

*sağ*\
Karşılaştırılacak nesnelerden biri.

*Ty1*\
Sol işaretçiye göre denetlenen tür.

*Ty2*\
Sağ işaretçiye göre denetlenen tür.

## <a name="op_lt_eq"></a>işleç&lt;=

Bir nesne için ikinci bir nesneden daha az veya eşit olan testler.

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

*sol*\
Karşılaştırılacak nesnelerden biri.

*sağ*\
Karşılaştırılacak nesnelerden biri.

*Ty1*\
Sol paylaşılan işaretçi tarafından denetlenen tür.

*Ty2*\
Doğru paylaşılan işaretçi tarafından denetlenen tür.

### <a name="remarks"></a>Açıklamalar

Şablon işleçleri `left.get() <= right.get()` döndürür

## <a name="op_gt"></a>işleç&gt;

Bir nesne için ikinci bir nesneden daha büyük olan testler.

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

*sol*\
Karşılaştırılacak nesnelerden biri.

*sağ*\
Karşılaştırılacak nesnelerden biri.

*Ty1*\
Sol paylaşılan işaretçi tarafından denetlenen tür.

*Ty2*\
Doğru paylaşılan işaretçi tarafından denetlenen tür.

## <a name="op_lt_lt"></a>işleç&lt;&lt;

Paylaşılan işaretçiyi akışa yazar.

```cpp
template <class Elem, class Tr, class Ty>
std::basic_ostream<Elem, Tr>& operator<<(std::basic_ostream<Elem, Tr>& out,
    shared_ptr<Ty>& sp);
```

### <a name="parameters"></a>Parametreler

*Eled*\
Stream öğesinin türü.

*Tr*\
Stream öğesi nitelikleri yazın.

*Ty*\
Paylaşılan işaretçi tarafından denetlenen tür.

*out*\
Çıkış akışı.

*sp*\
Paylaşılan işaretçi.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `out << sp.get()`döndürür.

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
