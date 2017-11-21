---
title: "system_error sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: system_error/std::system_error
dev_langs: C++
helpviewer_keywords: system_error class
ms.assetid: 2eeaacbb-8a4a-4ad7-943a-997901a77f32
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 975fcf228191695e419df2b04bd5578e15924f6b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="systemerror-class"></a>system_error Sınıfı
Bir alt düzey sistem hatası rapor için oluşturulan tüm özel durumlar için temel sınıfı temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class system_error : public runtime_error {  
public:  
    explicit system_error(error_code _Errcode,
    const string& _Message = "");

    system_error(error_code _Errcode,
    const char *_Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const string& _Message);

    system_error(error_code::value_type _Errval,  
    const error_category& _Errcat,
    const char *_Message);
const error_code& code() const throw();
const error_code& code() const throw();

 };  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tarafından döndürülen değer `what` sınıfında [özel durum](../standard-library/exception-class.md) gelen oluşturulan `_Message` ve saklı nesne türünün [error_code](../standard-library/error-code-class.md) (ya da `code` veya `error_code(_Errval, _Errcat)`).  
  
 Üye işlevini `code` saklı döndürür [error_code](../standard-library/error-code-class.md) nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<system_error >  
  
 **Namespace:** std  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< system_error >](../standard-library/system-error.md)

