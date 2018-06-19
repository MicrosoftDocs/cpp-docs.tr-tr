---
title: underlying_type sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::underlying_type
dev_langs:
- C++
helpviewer_keywords:
- underlying_type
ms.assetid: 691ddce3-2677-4480-bd35-d933fab85d3e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4f45af807b37294b87920b6fabac18647f170025
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853228"
---
# <a name="underlyingtype-class"></a>underlying_type sınıfı

Bir numaralandırma türü için temel alınan tam sayı tür üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct underlying_type;
```

### <a name="parameters"></a>Parametreler

`T` Değişiklik türü.

## <a name="remarks"></a>Açıklamalar

`type` Şablon sınıfının üye typedef adları temel tam sayı türü `T`, `T` bir numaralandırma türü olan aksi hiçbir üye typedef yoktur `type`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
