---
title: add_rvalue_reference Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_rvalue_reference
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
ms.openlocfilehash: 6d7cc1d45ed3b963de0a0a004c1696ddbf0af440
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623926"
---
# <a name="add_rvalue_reference-class"></a>add_rvalue_reference Sınıfı

Bir nesne veya işlev türü ise, şablon parametresinin bir rvalue başvuru türünü oluşturur. Aksi takdirde, başvuru daraltma semantiklerinden dolayı tür, şablon parametresiyle aynıdır.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*Şı*\
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`add_rvalue_reference`Sınıfı adlı bir üyeye sahiptir `type` ve bu, *T*Şablon parametresine bir rvalue başvurusu türü için diğer addır. Başvuru daraltma semantiğinin anlamı, nesne olmayan ve işlev olmayan tür *t*Için `T&&` bir *t*. Örneğin, *T* bir lvalue başvuru türü olduğunda, `add_rvalue_reference<T>::type` bir rvalue başvurusu değil, lvalue başvuru türüdür.

Kolaylık olması için, \<type_traits> `add_rvalue_reference_t` öğesinin üyesi olan bir yardımcı şablonu tanımlar `type` `add_rvalue_reference` .

## <a name="example"></a>Örnek

Bu kod örneği, rvalue başvuru türlerinin ve kullanılarak nasıl oluşturulduğunu `add_rvalue_reference` `add_rvalue_reference_t` ve `add_rvalue_reference` bir lvalue başvuru türü üzerindeki sonucunun bir rvalue başvurusu değil, lvalue başvuru türüne ne kadar daraltılaabileceğini göstermek için static_assert kullanır.

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

Üst bilgi\<type_traits>

Ad alanı: std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](type-traits.md)\
[add_lvalue_reference sınıfı](add-lvalue-reference-class.md)\
[is_rvalue_reference sınıfı](is-rvalue-reference-class.md)
