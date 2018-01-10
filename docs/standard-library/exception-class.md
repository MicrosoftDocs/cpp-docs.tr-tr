---
title: "özel durum sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception
dev_langs: C++
helpviewer_keywords: exception class
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33e6d0ed3153b31c231790610de1a7c4da1a94ab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exception-class"></a>exception Class
Sınıfı, belirli ifadeleri ve C++ Standart Kitaplığı tarafından oluşturulan tüm özel durumlar için temel sınıf olarak görev yapar.  
  
## <a name="syntax"></a>Sözdizimi  
```  
class exception {
   public:
   exception();
   exception(const char* const &message);
   exception(const char* const &message, int);
   exception(const exception &right);
   exception& operator=(const exception &right);
   virtual ~exception();
   virtual const char *what() const;
   };  
``` 
## <a name="remarks"></a>Açıklamalar  
 Özellikle, bu taban sınıf içinde tanımlanan standart özel durum sınıfları köküdür [ \<stdexcept >](../standard-library/stdexcept.md). C dize tarafından döndürülen değeri `what` varsayılan oluşturucu tarafından belirtilmezse, ancak belirli türetilen sınıflar için oluşturucular tarafından uygulama tanımlı C dize olarak tanımlanabilir. Üye işlevleri hiçbiri tüm özel durumlar oluşturma.  
  
 `int` Parametresi bellek ayrılması gereken belirtmenize olanak verir. Değeri `int` göz ardı edilir.  
  
> [!NOTE]
>  Oluşturucular `exception(const char* const &message)` ve `exception(const char* const &message, int)` C++ Standart Kitaplığı için Microsoft uzantıları.  
  
## <a name="example"></a>Örnek  
 Devralınan standart özel durum sınıfları kullanım örnekleri için `exception` sınıfı, tanımlanan sınıflarından herhangi biriyle bkz [ \<stdexcept >](../standard-library/stdexcept.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<özel durum >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



