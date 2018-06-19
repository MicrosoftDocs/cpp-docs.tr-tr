---
title: add_rvalue_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- add_rvalue_reference Class
ms.assetid: 76b0cb7c-1031-45d0-b409-f03ab0297580
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1cceec4e7d954e07e1d776042f311dfa1a386300
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850762"
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference Sınıfı

Bir şablon parametresi rvalue başvuru türünde bir nesne veya işlev türü ise oluşturur. Aksi takdirde, daraltma başvuru semantiği nedeniyle, şablon parametresi ile aynı türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

T türü değiştirmek için.

## <a name="remarks"></a>Açıklamalar

`add_rvalue_reference` Sınıf adında bir üyeye sahip `type`, şablon parametresi için bir rvalue başvuru türü için bir diğer ad olduğu `T`. Daraltma başvuru semantiği, nesne olmayan ve işlev olmayan türleri için kapsıyor `T`, `T&&` olan bir `T`. Örneğin, `T` bir lvalue başvuru türü `add_rvalue_reference<T>::type` lvalue başvuru rvalue başvuru türüdür.

Kolaylık sağlamak için \<type_traits > yardımcı şablonu tanımlar `add_rvalue_reference_t`, bu diğer adları `type` üyesi `add_rvalue_reference`.

## <a name="example"></a>Örnek

Bu kod örneği, nasıl rvalue başvuru türleri kullanılarak oluşturulan göstermek için static_assert kullanır. `add_rvalue_reference` ve `add_rvalue_reference_t`ve nasıl sonucu `add_rvalue_reference` lvalue başvuru türü rvalue başvuru değil, ancak lvalue başvuru türüne daraltır.

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

Başlık: < type_traits > Namespace: std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_lvalue_reference Sınıfı](../standard-library/add-lvalue-reference-class.md)<br/>
[is_rvalue_reference Sınıfı](../standard-library/is-rvalue-reference-class.md)<br/>
