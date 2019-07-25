---
title: time_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: 85565dc0c0ec904551eb8dd981cfacc9a2e1f256
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460035"
---
# <a name="timebase-class"></a>time_base Sınıfı

Sınıfı, yalnızca numaralandırılmış türü `dateorder` ve bu türden birkaç sabiti tanımlayarak time_get şablon sınıfı modelleri için bir temel sınıf görevi görür.

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

- `no_order`belirli bir sıra belirtir.

- `dmy`2 Aralık 1979 ' de olduğu gibi, ayı gün, ay ve yıl olarak belirtir.

- `mdy`2 Aralık 1979 ' de olacak şekilde ayı, günü ve yılı belirtir.

- `ymd`1979/12/2 içinde olduğu gibi sipariş yılını, ayı ve günü belirtir.

- `ydm`1979 ' de olduğu gibi, gün ve sonra ay yılını belirtir: 2 Dec.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
