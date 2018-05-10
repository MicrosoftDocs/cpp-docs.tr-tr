---
title: is_move_assignable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_assignable
dev_langs:
- C++
helpviewer_keywords:
- is_move_assignable
ms.assetid: f33137f2-0639-4912-8745-bc0f9fd18d28
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: adda28e4c6cc2a7ba7a387e125bd873b2107b687
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="ismoveassignable-class"></a>is_move_assignable sınıfı

Türü olabiliyorsa, testleri atanan taşıyın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Bir türü taşıma atanabilir ise rvalue başvuru türüne bir başvuru türüne atanabilir. Türü koşulu eşdeğerdir `is_assignable<T&, T&&>`. Atanabilir türleri önerilebilir skaler türler ve taşıma atama işleçleri derleyicinin ürettiği veya kullanıcı tanımlı olan sınıf türünü taşıyın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
