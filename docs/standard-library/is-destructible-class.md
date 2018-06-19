---
title: is_destructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_destructible
dev_langs:
- C++
helpviewer_keywords:
- is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 41a5da108c082dc4199a216d36f51d41e1748ada
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33844295"
---
# <a name="isdestructible-class"></a>is_destructible sınıfı

Türü destructible olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_destructible;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` false tuttuğu destructible, aksi takdirde türüdür. Destructible türleridir başvuru türleri, nesne türleri ve türleri burada bazı türü için `U` eşit `remove_all_extents_t<T>` değerlendirilmeyecek işleneni `std::declval<U&>.~U()` doğru oluşturulmamış. Eksik türler dahil olmak üzere diğer türleri `void`ve işlev türleri, destructible türleri değildir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
