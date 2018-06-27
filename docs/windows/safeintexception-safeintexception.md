---
title: Safeıntexception::safeıntexception | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- SafeIntException
- SafeIntException.SafeIntException
- SafeIntException::SafeIntException
dev_langs:
- C++
helpviewer_keywords:
- SafeIntException, constructor
ms.assetid: 8e5a0c24-a56b-4c80-9ee8-876604b1e7dc
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ef3c1d11c0f814699ca1492f7ec1fb49c43c3d76
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892182"
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
 [in] `code`  
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