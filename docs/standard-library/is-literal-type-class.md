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
ms.openlocfilehash: fd4481be124cbcbba04f6b45b4c5a08beb34f04d
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44103311"
---
# <a name="isliteraltype-class"></a>is_literal_type sınıfı

Bir tür olarak kullanılabilir olup olmadığını test bir `constexpr` değişkeni veya oluşturulan, tarafından kullanılan veya döndürüldüğü `constexpr` işlevleri.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T>
struct is_literal_type;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sorgulanacak tür.

## <a name="remarks"></a>Açıklamalar

Karşılaştırmasının bir örneği true tutan türü *T* olduğu bir *değişmez değer türü*, aksi takdirde false tutar. Değişmez değer türü geçerli **void**, skaler bir tür, bir başvuru türü, bir dizi değişmez değer türü veya sınıf değişmez değer türü. Bir değişmez değer sınıfı türü önemsiz bir yok Edicisi olan bir sınıf türü, bir toplama türü veya en az bir olmayan-taşıma, kopyalama olmayan sahip `constexpr` oluşturucusu ve tüm temel sınıflar ve statik olmayan veri üyesi geçici olmayan sabit değer türleri olan. Bir sabit değer türü sabit değer türündeki her zaman olsa da, derleyici olarak değerlendirilmesi için herhangi bir şey değişmez değer türü kavramını içerir bir `constexpr` derleme zamanında.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<type_traits >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[<type_traits>](../standard-library/type-traits.md)<br/>
