---
title: is_nothrow_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 112da495673517f86a00437672ccc52429fbd251
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="isnothrowconstructible-class"></a>is_nothrow_constructible sınıfı

Bir türü oluşturulabilir ve belirtilen bağımsız değişken türleri kullanıldığında throw değil bilinen olup olmadığını sınar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_nothrow_constructible;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

`Args` Bir oluşturucuda eşleştirmek için bağımsız değişken türleri `T`.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` bağımsız değişken türleri oluşturulabilir kullanmaktır `Args`ve Oluşturucusu derleyici tarafından değil throw bilinen; Aksi halde false tutar. Tür `T` oluşturulabilir olduğundan, değişken tanımını `T t(std::declval<Args>()...);` doğru oluşturulmamış. Her ikisi de `T` ve içindeki tüm türler `Args` tam tür `void`, veya bilinmeyen bağlı dizileri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
