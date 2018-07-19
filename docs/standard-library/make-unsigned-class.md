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
ms.openlocfilehash: f379500f9455ed9ad9a581966e0f8ed7bfed13f7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38953920"
---
# <a name="makeunsigned-class"></a>make_unsigned Sınıfı

Yapar yazın veya en küçük işaretsiz büyük yazın veya boyutu türü için eşittir.

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
|*T*|Değiştirilecek tür.|

## <a name="remarks"></a>Açıklamalar

Tür değiştiricinin bir örneği bir değişiklik-tür tutar *T* varsa `is_unsigned<T>` geçerlidir. Aksi takdirde, en küçük imzalı türdür `ST` hangi `sizeof (T) <= sizeof (ST)`.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
