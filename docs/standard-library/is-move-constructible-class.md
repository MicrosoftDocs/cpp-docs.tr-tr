---
title: is_move_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_move_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d87eac720b205560993a7d6995be8a8fe6ad6194
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33843528"
---
# <a name="ismoveconstructible-class"></a>is_move_constructible sınıfı

Bir taşıma oluşturucusuna türüne sahip olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>Parametreler

Değerlendirilecek T türü

## <a name="remarks"></a>Açıklamalar

Türü ise true olarak değerlendirilir türü koşulu `T` bir taşıma işlemi kullanılarak oluşturulabilir. Bu koşul eşdeğerdir `is_constructible<T, T&&>`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
