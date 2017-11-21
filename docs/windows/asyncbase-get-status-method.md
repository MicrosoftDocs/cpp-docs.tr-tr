---
title: "AsyncBase::get_Status yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::get_Status
dev_langs: C++
helpviewer_keywords: get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f7ac7e7a42d0cde4507f812a270548acfb5a69e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbasegetstatus-method"></a>AsyncBase::get_Status Metodu
Zaman uyumsuz işlemin durumunu gösteren bir değer alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `status`  
 Durum depolanması bulunduğu konum. Daha fazla bilgi için bkz: Windows::Foundation::AsyncStatus numaralandırması.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yöntem IAsyncInfo::get_Status uygular.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase sınıfı](../windows/asyncbase-class.md)