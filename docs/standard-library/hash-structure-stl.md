---
title: "hash yapısı (Standart C++ Kitaplığı) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: thread/std::hash
dev_langs: C++
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3ced015fec2e581748bd4309f6c7e1569cc2a7d1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="hash-structure-c-standard-library"></a>hash yapısı (Standart C++ Kitaplığı)
Benzersiz olarak tarafından belirlenen bir değer döndüren bir üye işlevini tanımlar `Val`. Üye işlevini tanımlayan bir [karma](../standard-library/hash-class.md) eşleme türü değerleri için uygun işlevi `thread::id` dizin değerlerin bir dağıtım.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<iş parçacığı >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [\<iş parçacığı >](../standard-library/thread.md)   
 [unary_function yapısı](../standard-library/unary-function-struct.md)
