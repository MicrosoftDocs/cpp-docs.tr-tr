---
title: CAccessorBase::ReleaseAccessors | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CAccessorBase::ReleaseAccessors
- CAccessorBase.ReleaseAccessors
- ReleaseAccessors
dev_langs: C++
helpviewer_keywords: ReleaseAccessors method
ms.assetid: f08bc88e-0552-4a9c-9c65-b4061094649a
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a46278b59803ffafbd0b9ee4db2b77249b425fa2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="caccessorbasereleaseaccessors"></a>CAccessorBase::ReleaseAccessors
Sınıfı tarafından oluşturulan erişimciler serbest bırakır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT ReleaseAccessors(  
   IUnknown* pUnk   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *pUnk*  
 [in] Bir işaretçi bir **IUnknown** erişimciler oluşturuldu COM nesnesi için arabirim.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Çağrılır [CAccessorRowset::Close](../../data/oledb/caccessorrowset-close.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAccessorBase Sınıfı](../../data/oledb/caccessorbase-class.md)