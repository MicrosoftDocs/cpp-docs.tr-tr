---
title: is_standard_layout sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_standard_layout
dev_langs:
- C++
helpviewer_keywords:
- is_standard_layout class
- is_standard_layout
ms.assetid: 15ccf111-f537-45ef-b552-59152a7ba312
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97ed762b390152794a078b6f439a76babe66f54c
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
