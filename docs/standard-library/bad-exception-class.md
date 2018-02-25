---
title: "bad_exception sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- exception/std::bad_exception
dev_langs:
- C++
helpviewer_keywords:
- bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 44c42ece609f971910ac8f13f96416626a6c74f9
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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

