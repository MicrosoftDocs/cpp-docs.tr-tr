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
ms.openlocfilehash: 280ce6a24e1de9d0e7206e7f9e5b0d896d8c6787
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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



