---
title: "is_destructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: type_traits/std::is_destructible
dev_langs: C++
helpviewer_keywords: is_destructible
ms.assetid: 3bb9b718-1ad5-49ae-93cc-92b93b546b4d
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b673ae9c46479723684a22205853229f913573d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="isdestructible-class"></a>is_destructible sınıfı
Türü destructible olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
struct is_destructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sorgulanacak tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Türü koşulu örneği doğru tutan türü `T` false tuttuğu destructible, aksi takdirde türüdür. Destructible türleridir başvuru türleri, nesne türleri ve türleri burada bazı türü için `U` eşit `remove_all_extents_t<T>` değerlendirilmeyecek işleneni `std::declval<U&>.~U()` doğru oluşturulmamış. Eksik türler dahil olmak üzere diğer türleri `void`ve işlev türleri, destructible türleri değildir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



