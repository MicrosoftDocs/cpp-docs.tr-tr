---
title: CDynamicParameterAccessor::SetParamStatus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDynamicParameterAccessor::SetParamStatus
- ATL.CDynamicParameterAccessor.SetParamStatus
- ATL::CDynamicParameterAccessor::SetParamStatus
- CDynamicParameterAccessor.SetParamStatus
- SetParamStatus
dev_langs: C++
helpviewer_keywords: SetParamStatus method
ms.assetid: 0c2271f6-457d-46ca-88b7-4590aadb20d7
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8b239000efa761ee30aa44fb8285fa96992e0b0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicparameteraccessorsetparamstatus"></a>CDynamicParameterAccessor::SetParamStatus
Arabellekte depolanan belirtilen parametre durumunu ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      bool SetParamStatus(  
   DBORDINAL nParam,  
   DBSTATUS status  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nParam`  
 [in] Parametre numarası (1 uzaklığı). Parametre 0 dönüş değerleri için ayrılmıştır. Numaralı parametre SQL veya saklı yordam çağrısı, sırayla göre parametre dizinidir. Bkz: [SetParam](../../data/oledb/cdynamicparameteraccessor-setparam.md) bir örnek.  
  
 *durumu*  
 [in] `DBSTATUS` Belirtilen parametre durumu. Hakkında bilgi için `DBSTATUS` değerler, bakın [durum](https://msdn.microsoft.com/en-us/library/ms722617.aspx) içinde *OLE DB Programcının Başvurusu*, veya arama `DBSTATUS` biçim içinde.  
  
## <a name="remarks"></a>Açıklamalar  
 Döndürür **true** başarı veya **false** hatasında.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CDynamicParameterAccessor sınıfı](../../data/oledb/cdynamicparameteraccessor-class.md)