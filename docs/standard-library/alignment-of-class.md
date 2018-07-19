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
ms.openlocfilehash: 8b679d4c8807a19c977cd7e59481dc1d78e67ba1
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956524"
---
# <a name="alignmentof-class"></a>alignment_of Sınıfı

Belirtilen tür hizalamasını alır. Bu struct açısından uygulanan [alignof](../cpp/alignof-and-alignas-cpp.md). Kullanım `alignof` doğrudan yalnızca gerektiğinde bir hizalama değeri sorgulanamıyor. Etiket dağıtım yaparken örneği için bir tamsayı sabiti gerektiğinde alignment_of kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct alignment_of;
```

### <a name="parameters"></a>Parametreler

*Ty* Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Türü bir sorgu değerini tutan türü hizalamasını *Ty*.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[aligned_storage Sınıfı](../standard-library/aligned-storage-class.md)<br/>
