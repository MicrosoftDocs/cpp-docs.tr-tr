---
title: add_rvalue_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 64694f2428c1dd536df4d242a17f3f011cfb290c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456545"
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference Sınıfı

Bir nesne veya işlev türü ise, şablon parametresinin bir rvalue başvuru türünü oluşturur. Aksi takdirde, başvuru daraltma semantiklerinden dolayı tür, şablon parametresiyle aynıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*ŞI*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

Sınıfı adlı `type`bir üyeye sahiptir ve bu, T Şablon parametresine bir rvalue başvurusu türü için diğer addır.  `add_rvalue_reference` Başvuru daraltma semantiğinin anlamı, nesne olmayan ve işlev olmayan tür *t* `T&&` için bir *t*. Örneğin, *T* bir lvalue başvuru türü olduğunda, `add_rvalue_reference<T>::type` bir rvalue başvurusu değil, lvalue başvuru türüdür.

Kolaylık sağlaması \<için, type_traits >, öğesinin `type` `add_rvalue_reference`üyesi olan `add_rvalue_reference_t`bir yardımcı şablonu tanımlar.

## <a name="example"></a>Örnek

Bu kod örneği, rvalue başvuru türlerinin ve `add_rvalue_reference` `add_rvalue_reference_t`kullanılarak nasıl oluşturulduğunu `add_rvalue_reference` ve bir lvalue başvuru türü üzerindeki sonucunun bir rvalue başvurusu değil, lvalue başvuru türüne ne kadar daraltılaabileceğini göstermek için static_assert kullanır.

```cpp
// ex_add_rvalue_reference.cpp
// Build by using: cl /EHsc /W4 ex_add_rvalue_reference.cpp
#include <type_traits>
#include <iostream>
#include <string>

using namespace std;
int main()
{
    static_assert(is_same<add_rvalue_reference<string>::type, string&&>::value,
        "Expected add_rvalue_reference_t<string> to be string&&");
    static_assert(is_same<add_rvalue_reference_t<string*>, string*&&>::value,
        "Expected add_rvalue_reference_t<string*> to be string*&&");
    static_assert(is_same<add_rvalue_reference<string&>::type, string&>::value,
        "Expected add_rvalue_reference_t<string&> to be string&");
    static_assert(is_same<add_rvalue_reference_t<string&&>, string&&>::value,
        "Expected add_rvalue_reference_t<string&&> to be string&&");
    cout << "All static_assert tests of add_rvalue_reference passed." << endl;
    return 0;
}

/*Output:
All static_assert tests of add_rvalue_reference passed.
*/
```

## <a name="requirements"></a>Gereksinimler

Üst bilgi \<: type_traits >

Ad alanı: std

## <a name="see-also"></a>Ayrıca bkz.

[< type_traits >](../standard-library/type-traits.md)\
[add_lvalue_reference sınıfı](../standard-library/add-lvalue-reference-class.md)\
[is_rvalue_reference Sınıfı](../standard-library/is-rvalue-reference-class.md)
