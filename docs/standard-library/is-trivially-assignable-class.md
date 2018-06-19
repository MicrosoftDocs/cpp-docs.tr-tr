---
title: is_trivially_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_trivially_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_assignable
ms.assetid: 1284a8f7-4093-426d-9c9a-dabb46f90d6d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b604a4c9a2fc11a9c7274d0e29ab98acfd260907
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33912660"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable sınıfı

Bir değeri olup olmadığını sınar `From` türü trivially atanabilen `To` türü

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Parametreler

Atamayı alan nesnesi türü için.

Nesne türünden değer sağlar.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` doğru biçimlendirilmiş olması gerekir ve derleyici hiçbir Önemsiz olmayan işlemleri gerektirecek şekilde bilinmelidir. Her ikisi de `From` ve `To` tam tür `void`, veya bilinmeyen bağlı dizileri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
