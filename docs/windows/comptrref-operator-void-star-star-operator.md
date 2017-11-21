---
title: "ComPtrRef::operator void ** işleci | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs: C++
helpviewer_keywords: operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6f961328444d49bb282b87b4d4670aeab7fe7997
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="comptrrefoperator-void-operator"></a>ComPtrRef::operator void** İşleci
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
operator void**() const;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Geçerli ComPtrRef nesneyi siler, ComPtrRef nesnesiyle bir işaretçi--pointer-için temsil edilen arabirimi işaretçisine bıraktığı `void`ve atama işaretçi döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** client.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ComPtrRef sınıfı](../windows/comptrref-class.md)   
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)