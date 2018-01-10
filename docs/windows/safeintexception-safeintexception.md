---
title: "Safeıntexception::safeıntexception | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs: C++
helpviewer_keywords: SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
caps.latest.revision: "6"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85bf6bae5ba07154bdeb807171dd2d3df61d0774
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException
Oluşturur bir `SafeIntException` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`code`  
 Oluşan hatayı açıklayan bir numaralandırılmış veri değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Olası değerler için `code` Safeint.h dosyasında tanımlanır. Kolaylık sağlamak için olası değerler da burada listelenir.  
  
-   `SafeIntNoError`  
  
-   `SafeIntArithmeticOverflow`  
  
-   `SafeIntDivideByZero`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** safeint.h  
  
 **Namespace:** msl::utilities  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SafeInt Kitaplığı](../windows/safeint-library.md)   
 [Safeıntexception sınıfı](../windows/safeintexception-class.md)   
 [SafeInt Sınıfı](../windows/safeint-class.md)