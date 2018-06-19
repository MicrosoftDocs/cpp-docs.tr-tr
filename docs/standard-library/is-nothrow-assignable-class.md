---
title: is_nothrow_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f11e1ce8b016ab8c6e8af04e351e80307b2189e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843450"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable sınıfı

Değeri olup olmadığını sınar `From` türü atanabilen `To` türü ve atama değil atmak için bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parametreler

Atamayı alan nesnesi türü için.

Nesne türünden değer sağlar.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir ve derleyiciye değil throw bilinmesi gerekir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
