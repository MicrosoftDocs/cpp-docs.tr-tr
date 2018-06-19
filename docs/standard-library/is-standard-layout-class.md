---
title: is_standard_layout sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d899d9c56ecc8b27b18498de225bbba6f0d110d2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852090"
---
# <a name="isstandardlayout-class"></a>is_standard_layout Sınıfı

Testleri standart bir yerleşim türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_standard_layout;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|`Ty`|Sorgu türü|

## <a name="remarks"></a>Açıklamalar

Bu türü koşulu örneği doğru tutan türü `Ty` false tuttuğu bellekte, aksi takdirde member nesnelerinde standart bir düzenine sahip bir sınıftır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
