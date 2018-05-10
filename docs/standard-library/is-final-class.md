---
title: is_final sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_final
dev_langs:
- C++
helpviewer_keywords:
- is_final
ms.assetid: 9dbad82f-6685-4909-94e8-98e4a93994b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0b3d2c37b73d79619aeb16e7b1b81ad71819b09b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="isfinal-class"></a>is_final sınıfı

Türü işaretli bir sınıf türü olup olmadığını sınar `final`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_final;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` bir sınıf türü olarak işaretlenmiş `final`, aksi takdirde false tutar. Varsa `T` bir sınıf türü tam bir tür olması gerekir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[final Tanımlayıcısı](../cpp/final-specifier.md)<br/>
