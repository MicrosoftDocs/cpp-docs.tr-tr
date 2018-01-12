---
title: "future_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: future/std::future_error
dev_langs: C++
ms.assetid: 6071c545-ac2a-49ef-9967-07b0125da861
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1fc5ba9a34ee5c1a29892e4ba6ebc25366e408be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="futureerror-class"></a>future_error Sınıfı
Yönetme türleri yöntemleri ile oluşturulan bir özel durum nesnesi tanımlar [gelecekteki](../standard-library/future-class.md) nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class future_error : public logic_error {
public:
    future_error(error_code code);

const error_code& code() const throw();

const char *what() const throw();

};
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<gelecekteki >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [logic_error sınıfı](../standard-library/logic-error-class.md)   
 [error_code Sınıfı](../standard-library/error-code-class.md)
