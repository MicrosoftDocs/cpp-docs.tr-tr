---
title: time_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: ddaf9905e859c062031940d35adfa2a3393dbb5a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72685782"
---
# <a name="time_base-class"></a>time_base Sınıfı

Sınıfı, yalnızca numaralandırılmış tür `dateorder` ve bu türden birkaç sabiti tanımlayarak, sınıf şablonu time_get modelleri için bir temel sınıf işlevi görür.

## <a name="syntax"></a>Sözdizimi

```cpp
class time_base : public locale::facet {
public:
    enum dateorder {
        no_order,
        dmy,
        mdy,
        ymd,
        ydm
    };
    time_base(size_t _Refs = 0)
    ~time_base();
};
```

## <a name="remarks"></a>Açıklamalar

Her sabit, bir tarihin bileşenlerini sıralamayı farklı bir şekilde gösterir. Sabitler şunlardır:

- `no_order` belirli bir sıra belirtir.

- `dmy`, 2 Aralık 1979 ' de olduğu gibi Order Day, month ve Year yılını belirtir.

- `mdy`, 2 Aralık 1979 ' de olduğu gibi, gün ve sonra yılın sırasını belirtir.

- `ymd`, 1979/12/2 içinde olduğu gibi sipariş yılını, ayı ve günü belirtir.

- `ydm` 1979:2 ' de olduğu gibi, 1. gün, günü ve ayı belirtir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
