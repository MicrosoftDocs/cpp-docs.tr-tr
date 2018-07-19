---
title: is_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_assignable
ms.assetid: 53444287-c8be-4ad2-9487-a85c066a4f84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5666aca2d6a855b64af26d38a1ae834fecec5d6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958471"
---
# <a name="isassignable-class"></a>is_assignable sınıfı

Bir değeri olup olmadığını test `From` türüne atanabilen bir `To` türü.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>Parametreler

Atamayı alan nesne türü için.

Değer sağlayan bir nesne türü.

## <a name="remarks"></a>Açıklamalar

Değerlendirilmemiş ifade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır. Her ikisi de `From` ve `To` tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
