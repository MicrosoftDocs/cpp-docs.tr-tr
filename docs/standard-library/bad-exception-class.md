---
title: "bad_exception sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3a322ce0ed9621e1413009092b0afb9572196a9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="badexception-class"></a>bad_exception Class
Beklenmeyen bir işleyicisinden oluşturulan bir özel durum sınıfı tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>Açıklamalar  
 [Beklenmeyen](../standard-library/exception-functions.md#unexpected) özel durum oluşturacak bir `bad_exception` sonlandırma yerine veya ile belirtilen başka bir işlevi çağırmak yerine [set_unexpected](../standard-library/exception-functions.md#set_unexpected) varsa `bad_exception` işlevi throw listesinde yer.  
  
 Tarafından döndürülen değer **ne** bir uygulama tanımlı C dize. Üye işlevleri hiçbiri tüm özel durumlar oluşturma.  
  
 Tarafından devralınan üyelerin listesi için `bad_exception` sınıfı için bkz: [özel durum sınıfı](../standard-library/exception-class.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [set_unexpected](../standard-library/exception-functions.md#set_unexpected) kullanımına ilişkin bir örnek [beklenmeyen](../standard-library/exception-functions.md#unexpected) atma bir `bad_exception`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<özel durum >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[özel durum sınıfı](../standard-library/exception-class.md) [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

