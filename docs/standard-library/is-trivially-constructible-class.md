---
title: is_trivially_constructible sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- type_traits/std::is_trivially_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_trivially_constructible
ms.assetid: 3fa918c1-e66f-4d0e-a11b-be1fb2c02e7b
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f564ae5970f56690f493e26cbefebbdc34cfec61
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="istriviallyconstructible-class"></a>is_trivially_constructible sınıfı

Belirtilen bağımsız değişken türleri kullanıldığında bir türü trivially oluşturulabilir olup olmadığını test eder.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T, class... Args>
struct is_trivially_constructible;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

`Args` Bir oluşturucuda eşleştirmek için bağımsız değişken türleri `T`.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` bağımsız değişken türleri trivially oluşturulabilir kullanmaktır `Args`, aksi takdirde false tutar. Tür `T` trivially oluşturulabilir olduğundan, değişken tanımını `T t(std::declval<Args>()...);` doğru biçimlendirildiğinden ve önemsiz olmayan bir işlem çağırmak için bilinen. Her ikisi de `T` ve içindeki tüm türler `Args` tam tür `void`, veya bilinmeyen bağlı dizileri.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
