---
title: "Activationfactory::QueryInterface yöntemi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::ActivationFactory::QueryInterface
dev_langs: C++
helpviewer_keywords: QueryInterface method
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: efd94727fb49d7673f8f16a6ee427640be79d6e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactoryqueryinterface-method"></a>ActivationFactory::QueryInterface Yöntemi
Belirtilen arabirim için bir işaretçi alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `riid`  
 Bir arabirim kimliği  
  
 `ppvObject`  
 Bu işlem tamamlandığında, parametresi tarafından belirtilen arabirimi için bir işaretçi `riid`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa S_OK; Aksi takdirde, HRESULT hata açıklar.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ActivationFactory Sınıfı](../windows/activationfactory-class.md)