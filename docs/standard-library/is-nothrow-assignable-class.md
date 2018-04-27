---
title: is_nothrow_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_nothrow_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_assignable
ms.assetid: aa3aca92-308b-4b1d-b3f3-c54216c48fe7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f9b162ad4f0ff932314bcc8cb01183eb12a55f0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
