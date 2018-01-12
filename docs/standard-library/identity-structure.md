---
title: "identity yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: utility/std::identity
dev_langs: C++
helpviewer_keywords:
- identity class
- identity structure
ms.assetid: 990756fd-7969-4b39-ad7e-0878e8dac8fd
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c9166383cbe79835cc3790826fc2e617eca22484
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="identity-structure"></a>identity Yapısı
Şablon parametresi olarak bir tür tanımı sağlar yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
```  
struct identity {
   typedef Type type;
   Type operator()(const Type& left) const;
   };  
```  
#### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Tanımlamak için değer.|  
  
## <a name="remarks"></a>Açıklamalar  
 Sınıfı ortak türü tanımını içeren `type`, şablon parametre türü ile aynı olduğu. Şablon işlevi ile birlikte kullanılan [İleri](../standard-library/utility-functions.md#forward) bir işlev parametresi da istenen türe sahip olduğundan emin olmak için.  
  
 Eski kod ile uyumluluk için sınıfı ayrıca IDENTITY işlevi tanımlayan `operator()` bağımsız değişkeni döndürür `left`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yardımcı programı >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yardımcı programı >](../standard-library/utility.md)



