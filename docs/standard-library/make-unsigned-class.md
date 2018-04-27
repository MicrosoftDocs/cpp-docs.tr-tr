---
title: make_unsigned sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: aba0421ab55d5cf30b38f69e58123fbd4056d16f
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="makeunsigned-class"></a>make_unsigned Sınıfı

Yapar yazın veya en küçük imzasız büyük yazın veya yazın boyutunda eşit.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct make_unsigned;

template <class T>
using make_unsigned_t = typename make_unsigned<T>::type;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`T`|Değiştirilecek tür.|

## <a name="remarks"></a>Açıklamalar

Bir değişiklik-türü tür değiştiricisi örneğini tutan `T` varsa `is_unsigned<T>` geçerlidir. Aksi takdirde en küçük imzalı türü olan `ST` kendisi için `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
