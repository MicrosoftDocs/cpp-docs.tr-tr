---
title: "AsyncBase::get_ErrorCode yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::get_ErrorCode
dev_langs: C++
helpviewer_keywords: get_ErrorCode method
ms.assetid: 50b4f8a2-9a21-4ea0-bb5d-7ff524d62aea
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cec834638af5b718b5a1dd11e8c580eac014ee53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasegeterrorcode-method"></a>AsyncBase::get_ErrorCode Metodu
Geçerli zaman uyumsuz işlemi için hata kodunu alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   get_ErrorCode  
)(HRESULT* errorCode) override;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `errorCode`  
 Geçerli hata kodu depolandığı konum.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde geçerli zaman uyumsuz işlemi kapalıysa E_ILLEGAL_METHOD_CALL.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** async.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [AsyncBase Sınıfı](../windows/asyncbase-class.md)