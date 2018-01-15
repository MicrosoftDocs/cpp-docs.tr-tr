---
title: "make_signed sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: type_traits/std::make_signed
dev_langs: C++
helpviewer_keywords:
- make_signed class
- make_signed
ms.assetid: 686247c0-247c-496b-9b1b-ba9dcd633621
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9b811f585370a19be47b0140adf74495b6d9019
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="makesigned-class"></a>make_signed Sınıfı
Yapar yazın veya en küçük imzalı büyük yazın veya yazın boyutunda eşit.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class T>
struct make_signed;

template <class T>
using make_signed_t = typename make_signed<T>::type;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Değiştirilecek tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir değişiklik-türü tür değiştiricisi örneğini tutan `T` varsa `is_signed<T>` geçerlidir. Aksi takdirde en küçük imzasız türü olan `UT` kendisi için `sizeof (T) <= sizeof (UT)`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<type_traits >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<type_traits>](../standard-library/type-traits.md)



