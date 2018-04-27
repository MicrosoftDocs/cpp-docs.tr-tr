---
title: treat_as_floating_point yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::chrono::treat_as_floating_point
dev_langs:
- C++
ms.assetid: d0a2161c-bbb2-4924-8961-7568d5ad5434
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08ff7f0bf9d3bb1df6f81b617a83929338750444
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
