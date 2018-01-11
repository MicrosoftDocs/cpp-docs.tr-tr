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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0dc57bb342f6a9625c968e918b67a7b5e1bbb668
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [FtmBase Sınıfı](../windows/ftmbase-class.md)