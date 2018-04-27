---
title: is_nothrow_constructible sınıfı | Microsoft Docs
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
- type_traits/std::is_nothrow_constructible
dev_langs:
- C++
helpviewer_keywords:
- is_nothrow_constructible
ms.assetid: 8be3f927-283e-4d67-95a5-8bf5dc4e7a3d
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 38c334524cc5965f187d5ec76f698e9ed275f8b0
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
