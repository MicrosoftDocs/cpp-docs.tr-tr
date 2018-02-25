---
title: "is_literal_type sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- type_traits/std::is_literal_type
dev_langs:
- C++
helpviewer_keywords:
- is_literal_type
ms.assetid: a03a4ebb-ee66-48d6-91bb-41cf72b2401f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 09a1531458df692be2b78a97a1723366f912d087
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="isliteraltype-class"></a>is_literal_type Class
Bir tür olarak kullanılabilir olup olmadığını sınar bir `constexpr` değişkeni veya oluşturulan, tarafından kullanılan veya döndürülen `constexpr` işlevleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
struct is_literal_type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` olan bir *değişmez değer türü*, aksi takdirde false tutar. Değişmez değer türü olan `void`, skaler bir tür, bir başvuru türü, bir dizi değişmez değer türü veya bir değişmez değer sınıfı türü. Değişmez değer sınıf türü Önemsiz yıkıcı sahip bir sınıf türü, bir toplama türü veya en az bir olmayan-move, copy olmayan sahip `constexpr` oluşturucu ve tüm temel sınıflar ve statik olmayan veri üyeleri olan geçici olmayan değişmez değer türleri. Değişmez değer türü değişmez değer türü her zaman olsa da, değişmez değer türü kavramı derleyici olarak değerlendirilmesi için herhangi bir şey içeren bir `constexpr` derleme zamanında.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



