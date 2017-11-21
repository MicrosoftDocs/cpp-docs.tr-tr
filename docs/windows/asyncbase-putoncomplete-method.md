---
title: "AsyncBase::PutOnComplete yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::PutOnComplete
dev_langs: C++
helpviewer_keywords: PutOnComplete method
ms.assetid: 1c469ff9-b2df-4637-bf05-01a617043149
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6eeddf1f94d72407b90b9f99c4755b6e0a865ec5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseputoncomplete-method"></a>AsyncBase::PutOnComplete Yöntemi
Tamamlama olay işleyicisi adresini belirtilen değere ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   PutOnComplete  
)(TComplete* completeHandler);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `completeHandler`  
 Tamamlama olay işleyici ayarlamayı adresi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)