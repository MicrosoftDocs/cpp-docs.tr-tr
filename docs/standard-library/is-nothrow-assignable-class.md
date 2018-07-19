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
ms.openlocfilehash: 424fcf5b960182326dc1192d8d60f168ead59d98
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965421"
---
# <a name="isnothrowassignable-class"></a>is_nothrow_assignable sınıfı

Bir değeri olup olmadığını test *gelen* türüne atanabilen *için* türü ve atama değil atmasına bilinir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class To, class From>
struct is_nothrow_assignable;
```

### <a name="parameters"></a>Parametreler

*İçin* atamayı alan nesnenin türü.

*Gelen* değer sağlayan bir nesne türü.

## <a name="remarks"></a>Açıklamalar

İfade `declval<To>() = declval<From>()` iyi biçimlendirilmiş olmalıdır ve derleyiciye değil atmak için bilinmesi gerekir. Her ikisi de *gelen* ve *için* tam türler olmalıdır **void**, veya bilinmeyen bağlı bir dizi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
