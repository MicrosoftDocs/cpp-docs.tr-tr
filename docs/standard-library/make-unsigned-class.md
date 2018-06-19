---
title: make_unsigned sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::make_unsigned
dev_langs:
- C++
helpviewer_keywords:
- make_unsigned class
- make_unsigned
ms.assetid: 7a6a3c4f-1a4c-47e8-9ee2-ac1f7b669353
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 37f121912a13d6e4dac1692d2dab1b5ffd34bd6d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855568"
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
