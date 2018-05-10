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
ms.openlocfilehash: 4c13cd76f5d353cf91997406c8e7f74b5383cf8e
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="timebase-class"></a>time_base Sınıfı

Sınıf şablonu sınıfı time_get yalnızca numaralandırılmış türünü tanımlamak, modelleri için temel bir sınıf olarak hizmet veren **dateorder** ve bu tür birkaç sabitleri.

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

Her sabit bir tarih bileşenlerinin sıralamak için farklı bir şekilde belirtir. Sabitler şunlardır:

- **no_order** belirli bir sırada belirtir.

- **GAY** sipariş gün, ay ve yıl, 2 aralık 1979 olduğu gibi belirtir.

- **AGY** sipariş ay, gün sonra 2 aralık 1979 olduğu gibi yıl belirtir.

- **YAG'dir** sipariş yıl, ay, ardından 1979/12/2 gibi gün belirtir.

- **ydm** sipariş yıl, gün, ay, 1979:2 Ara olduğu gibi belirtir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
