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
ms.openlocfilehash: fd0a8bbffd3a6e0f03635b659dd3743e12c9f077
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700771"
---
# <a name="istriviallyassignable-class"></a>is_trivially_assignable sınıfı

Bir değeri olup olmadığını test `From` türü basit bir şekilde atanabilen `To` türü

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_trivially_assignable;
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Atamayı alan nesnenin türü.

*Kaynak*<br/>
Değer sağlayan bir nesne türü.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır ve derleyici için Önemsiz olmayan bir işlem istemek için bilinmesi gerekir. Her ikisi de `From` ve `To` tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
