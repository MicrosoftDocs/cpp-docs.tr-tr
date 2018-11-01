---
title: is_standard_layout Sınıfı
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_standard_layout
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
ms.openlocfilehash: 75691c1b09b71580474cc22cdc8382bff55a5e29
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50500288"
---
# <a name="isstandardlayout-class"></a>is_standard_layout Sınıfı

Standart Düzen türü olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Ty*|Sorgulanacak tür|

## <a name="remarks"></a>Açıklamalar

Bu tür koşulu örneği true tutan türü *Ty* üye nesneleri standart düzeni false tuttuğu bellekte, aksi takdirde sahip bir sınıftır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
