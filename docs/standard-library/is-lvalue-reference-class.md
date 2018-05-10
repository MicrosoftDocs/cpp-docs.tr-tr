---
title: is_lvalue_reference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_lvalue_reference
dev_langs:
- C++
helpviewer_keywords:
- is_lvalue_reference class
- is_lvalue_reference
ms.assetid: 7f11896b-935c-4de1-9c87-9d0127f904e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 692c5243a7fe2984d43a1e70fc39616de5cbcc9c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="islvaluereference-class"></a>is_lvalue_reference Sınıfı

Testleri lvalue başvuru türüdür.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Ty>
struct is_lvalue_reference;
```

### <a name="parameters"></a>Parametreler

`Ty` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Bu türü koşulu örneği doğru tutan türü `Ty` başvurudur bir nesne ya da false tuttuğu işlevi, aksi takdirde. Unutmayın `Ty` rvalue başvuru olmayabilir. Rvalues hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
[Lvalues ve Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md)<br/>
