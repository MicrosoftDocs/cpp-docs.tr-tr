---
title: "AsyncBase::FireProgress yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs: C++
helpviewer_keywords: FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dd7aa1d66697058d711edd38b3c2eb0679b73c07
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasefireprogress-method"></a>AsyncBase::FireProgress Yöntemi
Geçerli ilerleme olay işleyiciyi çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `arg`  
 Çağrılacak olay işleyicisi yöntemi.  
  
## <a name="remarks"></a>Açıklamalar  
 `ProgressTraits`türetilmiş [ArgTraitsHelper yapısı](../windows/argtraitshelper-structure.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)