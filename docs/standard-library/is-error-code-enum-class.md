---
title: "is_error_code_enum sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::is_error_code_enum
dev_langs: C++
helpviewer_keywords: is_error_code_enum class
ms.assetid: cee5be2d-7c20-4cec-a352-1ab8b7d32601
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fdaddd95ac6abf6355e93db28f1770b93d7725d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="iserrorcodeenum-class"></a>is_error_code_enum Sınıfı
İçin test türü koşulu temsil eden [error_code](../standard-library/error-code-class.md) numaralandırması.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <_Enum>
class is_error_code_enum;
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bu örneği [türü koşulu](../standard-library/type-traits.md) ise true ayrı tutma türü `_Enum` bir numaralandırma değeri türünde bir nesne depolamak için uygun olan `error_code`.  
  
 Bu türü kullanıcı tanımlı türler için özelleştirmeleri eklemek için izin verilir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< type_traits >](../standard-library/type-traits.md)   
 [< system_error >](../standard-library/system-error.md)



