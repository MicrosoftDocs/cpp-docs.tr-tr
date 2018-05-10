---
title: is_literal_type sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp
- devlang-cpp
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b123144643fd50b019853d21e4140ba2d931f7c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="isliteraltype-class"></a>is_literal_type sınıfı

Bir tür olarak kullanılabilir olup olmadığını sınar bir `constexpr` değişkeni veya oluşturulan, tarafından kullanılan veya döndürülen `constexpr` işlevleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametreler

`T` Sorgulanacak türü.

## <a name="remarks"></a>Açıklamalar

Türü koşulu örneği doğru tutan türü `T` olan bir *değişmez değer türü*, aksi takdirde false tutar. Değişmez değer türü olan `void`, skaler bir tür, bir başvuru türü, bir dizi değişmez değer türü veya bir değişmez değer sınıfı türü. Değişmez değer sınıf türü Önemsiz yıkıcı sahip bir sınıf türü, bir toplama türü veya en az bir olmayan-move, copy olmayan sahip `constexpr` oluşturucu ve tüm temel sınıflar ve statik olmayan veri üyeleri olan geçici olmayan değişmez değer türleri. Değişmez değer türü değişmez değer türü her zaman olsa da, değişmez değer türü kavramı derleyici olarak değerlendirilmesi için herhangi bir şey içeren bir `constexpr` derleme zamanında.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
