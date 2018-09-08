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
ms.openlocfilehash: a20a637872c8c26433920da313d4e6c001736d06
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44105763"
---
# <a name="addrvaluereference-class"></a>add_rvalue_reference Sınıfı

Bir nesne veya işlev türü ise, bir şablon parametresi rvalue başvuru türünü oluşturur. Aksi takdirde, başvuru daraltma semantiği, şablon parametresi ile aynı türdür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct add_rvalue_reference;

template <class T>
using add_rvalue_reference_t = typename add_rvalue_reference<T>::type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Değiştirilecek tür.

## <a name="remarks"></a>Açıklamalar

`add_rvalue_reference` Sınıfında adında bir üye `type`, şablon parametresi için bir rvalue başvuru türü için bir diğer ad olduğu *T*. Nesne olmayan ve işlev olmayan türler için başvuru daraltma semantiği anlamına *T*, `T&&` olduğu bir *T*. Örneğin, *T* bir lvalue başvuru türü `add_rvalue_reference<T>::type` bir rvalue başvurusunu lvalue başvuru türü.

Kolaylık sağlamak için \<type_traits > Yardımcısı şablon tanımlayan `add_rvalue_reference_t`, bu diğer adları `type` üyesi `add_rvalue_reference`.

## <a name="example"></a>Örnek

Bu kod örneği static_assert, rvalue başvuru türleri kullanılarak nasıl oluşturulduğunu göstermek için kullanır `add_rvalue_reference` ve `add_rvalue_reference_t`ve nasıl sonucunu `add_rvalue_reference` bir lvalue başvuru türü bir rvalue başvurusu değil, ancak lvalue başvuru türüne daraltır.

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

Başlık: \<type_traits >  
Namespace: std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[add_lvalue_reference Sınıfı](../standard-library/add-lvalue-reference-class.md)<br/>
[is_rvalue_reference Sınıfı](../standard-library/is-rvalue-reference-class.md)<br/>
