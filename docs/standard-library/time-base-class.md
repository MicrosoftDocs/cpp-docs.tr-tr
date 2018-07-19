---
title: time_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- locale/std::time_base
dev_langs:
- C++
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e1111ede44edc36e5399d82b3c4e088b20cc1c9
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957304"
---
# <a name="timebase-class"></a>time_base Sınıfı

Sınıfı yalnızca bir listeden seçimli türü tanımlayan Şablon sınıfı time_get modelleri için temel bir sınıf olarak hizmet verir `dateorder` ve bu türdeki çeşitli sabit.

## <a name="syntax"></a>Sözdizimi

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {no_order,
    dmy,
 mdy,
    ymd,
 ydm};
    time_base(
 size_t _Refs = 0)
 ~time_base();

};
```

## <a name="remarks"></a>Açıklamalar

Her sabit tarih bileşenlerinin sıralamak için farklı bir şekilde çalışmayan belirtir. Sabittir:

- `no_order` belirli bir sırada belirtir.

- `dmy` sipariş günü, ay ve yıl, 2 aralık 1979 olduğu gibi belirtir.

- `mdy` sıra ay, gün ve yıl, 2 aralık 1979 olduğu gibi belirtir.

- `ymd` Sipariş yılı, ayı ve ardından 1979/12/2 olduğu gibi günlük belirtir.

- `ydm` Sipariş yılı, gün, ay, 1979:2 Ara olduğu gibi belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
