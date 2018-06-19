---
title: alignment_of sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::alignment_of
dev_langs:
- C++
helpviewer_keywords:
- alignment_of class
- alignment_of
ms.assetid: 4141c59a-f94e-41c4-93fd-9ea578b27387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7d9ba59d7f1539f690d7b04c70139c263490368
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33850697"
---
# <a name="alignmentof-class"></a>alignment_of Sınıfı

Belirtilen tür hizalamasını alır. Bu yapı cinsinden uygulanan [alignof](../cpp/alignof-and-alignas-cpp.md). Kullanım `alignof` doğrudan yalnızca gerektiğinde bir hizalama değeri sorgulanamıyor. Etiket gönderme yaparken örneğin bir tamsayı sabiti gerektiğinde alignment_of kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü bir sorgu değerini tutan türü hizalamasını `Ty`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage Sınıfı](../standard-library/aligned-storage-class.md)<br/>
