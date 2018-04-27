---
title: is_rvalue_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- type_traits/std::is_rvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_rvalue_reference class
- is_rvalue_reference
ms.assetid: 40a97072-7b5c-4274-9154-298d3dcf064a
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 63c4cc79dd08742d6c7e594df6a8fb20468d3382
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="isrvaluereference-class"></a>is_rvalue_reference Sınıfı

Testleri bir rvalue başvuru türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_rvalue_reference;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Bu türü koşulu örneği doğru tutan türü `Ty` olan bir [rvalue başvuru](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
