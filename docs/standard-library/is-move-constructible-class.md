---
title: "is_move_constructible sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::is_move_constructible
dev_langs: C++
helpviewer_keywords: is_move_constructible
ms.assetid: becdf076-7419-488d-a335-78adf2478b9b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0bd58dc985a96a334192ea0e84232ccbcfaa986f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ismoveconstructible-class"></a>is_move_constructible sınıfı
Bir taşıma oluşturucusuna türüne sahip olup olmadığını sınar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>  
struct is_move_constructible;
```  
  
#### <a name="parameters"></a>Parametreler  
 T  
 Değerlendirilecek türü  
  
## <a name="remarks"></a>Açıklamalar  
 Türü ise true olarak değerlendirilir türü koşulu `T` bir taşıma işlemi kullanılarak oluşturulabilir. Bu koşul eşdeğerdir `is_constructible<T, T&&>`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)



