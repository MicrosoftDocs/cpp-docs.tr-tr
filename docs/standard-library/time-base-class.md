---
description: 'Hakkında daha fazla bilgi edinin: time_base sınıfı'
title: time_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- locale/std::time_base
helpviewer_keywords:
- time_base class
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
ms.openlocfilehash: cad27546109cf8ed6d8314869a3306f238cc6528
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97289575"
---
# <a name="time_base-class"></a>time_base Sınıfı

Sınıfı, yalnızca numaralandırılmış türü `dateorder` ve bu türden birkaç sabiti tanımlayarak time_get sınıf şablonu modelleri için bir temel sınıf işlevi görür.

## <a name="syntax"></a>Syntax

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

- `dmy` 2 Aralık 1979 ' de olduğu gibi, ayı gün, ay ve yıl olarak belirtir.

- `mdy` 2 Aralık 1979 ' de olacak şekilde ayı, günü ve yılı belirtir.

- `ymd` 1979/12/2 içinde olduğu gibi sipariş yılını, ayı ve günü belirtir.

- `ydm` 1979:2 ' de olduğu gibi, gün ve ay olarak ayı belirtir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
