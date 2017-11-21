---
title: "FtmBase::DisconnectObject yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: ftm/Microsoft::WRL::FtmBase::DisconnectObject
dev_langs: C++
helpviewer_keywords: DisconnectObject method
ms.assetid: 33253eec-3a65-4e72-8525-0249245a4790
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 618590f28dcb82be0bcb9c4407c9aa4eaa2432ce
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ftmbasedisconnectobject-method"></a>FtmBase::DisconnectObject Yöntemi
Zorla nesneye tüm dış bağlantıları serbest bırakır. Nesnenin sunucu nesnenin uyarlamasını kapatmadan önce bu yöntemi çağırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHODIMP DisconnectObject(  
   __in DWORD dwReserved  
) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dwReserved`  
 Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata gösterir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [FtmBase sınıfı](../windows/ftmbase-class.md)