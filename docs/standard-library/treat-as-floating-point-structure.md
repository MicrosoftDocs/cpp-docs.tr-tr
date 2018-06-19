---
title: treat_as_floating_point yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96687959ce4fdd7b5431611a64b878cf05f855ab
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33853306"
---
# <a name="treatasfloatingpoint-structure"></a>treat_as_floating_point Yapısı

Belirtir olup olmadığını `Rep` kayan noktalı bir tür olarak kabul.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Rep>
struct treat_as_floating_point : is_floating_point<Rep>;
```

## <a name="remarks"></a>Açıklamalar

`Rep` kayan nokta bir tür olarak kabul yalnızca uzmanlık `treat_as_floating_point<Rep>` türetildiği [true_type](../standard-library/type-traits-typedefs.md#true_type). Şablon sınıfı için bir kullanıcı tanımlı tür özelleştirilmiş.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std::chrono

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono >](../standard-library/chrono.md)<br/>
