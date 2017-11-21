---
title: "is_error_condition_enum sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::is_error_condition_enum
dev_langs: C++
helpviewer_keywords: is_error_condition_enum class
ms.assetid: 752bb87a-c61c-4304-9254-5aaf228b59c0
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d26913c9767f35c131605a8f7abee87396e753a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iserrorconditionenum-class"></a>is_error_condition_enum Sınıfı
İçin test türü koşulu temsil eden [error_condition](../standard-library/error-condition-class.md) numaralandırması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <_Enum>
class is_error_condition_enum;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu örneği [türü koşulu](../standard-library/type-traits.md) ise true ayrı tutma türü `_Enum` bir numaralandırma değeri türünde bir nesne depolamak için uygun olan `error_condition`.  
  
 Bu türü kullanıcı tanımlı türler için özelleştirmeleri eklemek için izin verilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [< system_error >](../standard-library/system-error.md)



