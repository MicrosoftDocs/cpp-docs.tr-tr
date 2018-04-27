---
title: is_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9e8ee756ce98e1476f10c04c10da1c6bce486513
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isassignable-class"></a>is_assignable sınıfı

Bir değeri olup olmadığını sınar `From` türü atanabilen bir `To` türü.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

Atamayı alan nesnesi türü için.

Nesne türünden değer sağlar.

## <a name="remarks"></a>Açıklamalar

Değerlendirilmeyecek ifade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
