---
title: "Ierrorrecordsımpl::geterrorguıd | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
dev_langs: C++
helpviewer_keywords: GetErrorGUID method
ms.assetid: 42c00755-50e5-401a-8246-adef9de5ced2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a2b1ec6a783bc5b289a024be2b64917b064e581e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ierrorrecordsimplgeterrorguid"></a>IErrorRecordsImpl::GetErrorGUID
GUID hata bir hata kayıttan alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      REFGUID GetErrorGUID(  
   ERRORINFO& rCurError   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rCurError`  
 Bir `ERRORINFO` kaydında bir **IErrorInfo** arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hata için bir GUID referansı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Ierrorrecordsımpl sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)