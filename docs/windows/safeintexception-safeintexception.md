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
ms.openlocfilehash: 393c424feb2a84fff85ba0efb5de7cbcaf54737c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2018
ms.locfileid: "40016765"
---
# <a name="safeintexceptionsafeintexception"></a>SafeIntException::SafeIntException
Oluşturur bir **Safeıntexception** nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
SafeIntException();  
  
SafeIntException(  
   SafeIntError code  
);  
```  
  
### <a name="parameters"></a>Parametreler  
 [in] *kod*  
 Oluşan hatayı açıklayan bir numaralandırılmış veri değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Olası değerler için *kod* Safeint.h dosyasında tanımlanır. Kolaylık olması için olası değerler de burada listelenir.  
  
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