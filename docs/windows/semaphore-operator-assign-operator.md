---
title: "Semaphore::operator = işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Semaphore::operator=
dev_langs: C++
helpviewer_keywords: operator= operator
ms.assetid: ea19839f-91f0-4b00-a35b-5728fcba4981
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb5d5145df5df5e55b12f2928f43b8ac78b5d884
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="semaphoreoperator-operator"></a>Semaphore::operator= İşleci
Belirtilen tanıtıcı geçerli semafor nesnesine bir semafor nesneden taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
Semaphore& operator=(  
   _Inout_ Semaphore&& h  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `h`  
 Rvalue başvuru semafor nesnesine.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Geçerli semafor nesneye başvuru.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** corewrappers.h  
  
 **Namespace:** Microsoft::wrl:: Wrappers
 
 ## <a name="see-also"></a>Ayrıca Bkz.
 [Semafor sınıfı](../windows/semaphore-class.md)