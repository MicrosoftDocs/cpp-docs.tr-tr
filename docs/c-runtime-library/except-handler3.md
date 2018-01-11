---
title: _except_handler3 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _except_handler3
apilocation:
- msvcrt.dll
- msvcr90.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr100.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- _except_handler3
- except_handler3
dev_langs: C++
helpviewer_keywords:
- _except_handler3 function
- except_handler3 function
ms.assetid: b0c64898-0ae5-48b7-9724-80135a0813e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b4fe280562d4f1278d74ae118712c9167de4b54d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="excepthandler3"></a>_except_handler3
İç CRT işlevi. Geçerli özel durumu işlemek için uygun özel durum işleyicisi bulmak için bir framework tarafından kullanıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _except_handler3(  
   PEXCEPTION_RECORD exception_record,  
   PEXCEPTION_REGISTRATION registration,  
   PCONTEXT context,  
   PEXCEPTION_REGISTRATION dispatcher  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`exception_record`  
 Bir özel durum hakkında bilgi sağlar.  
  
 [in]`registration`  
 Hangi kapsam tablo gösterir kaydı, özel durum işleyici bulmak için kullanılmalıdır.  
  
 [in]`context`  
 Ayrılmış.  
  
 [in]`dispatcher`  
 Ayrılmış.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir özel durum kapatıldığında, döndürür `DISPOSITION_DISMISS`. Kapsülleyerek özel durum işleyicileri için özel bir düzey yukarı iletilmesi gereken ise döndürür `DISPOSITION_CONTINUE_SEARCH`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem uygun özel durum işleyicisi bulursa, işleyicinin özel durum geçirir. Bu durumda, bu yöntem adlı kodu döndürmüyor ve dönüş değeri önemli değildir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Alfabetik İşlev Başvurusu](../c-runtime-library/reference/crt-alphabetical-function-reference.md)