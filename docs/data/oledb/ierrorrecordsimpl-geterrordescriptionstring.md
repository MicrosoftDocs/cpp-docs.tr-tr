---
title: "Ierrorrecordsımpl::geterrordescriptionstring | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorDescriptionString
- IErrorRecordsImpl.GetErrorDescriptionString
- IErrorRecordsImpl::GetErrorDescriptionString
dev_langs: C++
helpviewer_keywords: GetErrorDescriptionString method
ms.assetid: 8bc71c45-ca9f-4632-bb02-1aa9ed8086c4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: bbbb3e620c519a3f320c3cd7929bd2d4a91e3e0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ierrorrecordsimplgeterrordescriptionstring"></a>IErrorRecordsImpl::GetErrorDescriptionString
Hata açıklama dizesi bir hata kayıttan alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      LPOLESTR GetErrorDescriptionString(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rCurError`  
 Bir `ERRORINFO` kaydında bir **IErrorInfo** arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hatayı açıklayan bir dize için bir işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IErrorRecordsImpl Sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)