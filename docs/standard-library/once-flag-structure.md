---
title: "once_flag yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- mutex/std::once_flag
dev_langs:
- C++
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 482ef221338651ef3e6f6ec272c1a48984d40912
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="onceflag-structure"></a>once_flag Yapısı
Temsil eden bir `struct` şablonu işleviyle kullanılan [call_once](../standard-library/mutex-functions.md#call_once) başlatmanın emin olmak için kod bile birden çok iş parçacığı yürütme varlığında yalnızca bir kez çağrılır.  
  
## <a name="syntax"></a>Sözdizimi  
  
Yapı once_flag {constexpr once_flag() noexcept; once_flag(const once_flag&); once_flag & işleci =(const once_flag&);};  
  
## <a name="remarks"></a>Açıklamalar  
 `once_flag` `struct` Yalnızca bir varsayılan oluşturucusu vardır.  
  
 Nesne türü `once_flag` oluşturulabilir, ancak bunlar kopyalanamaz.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<mutex >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



