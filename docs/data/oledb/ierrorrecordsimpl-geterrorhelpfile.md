---
title: "Ierrorrecordsımpl::geterrorhelpfile | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IErrorRecordsImpl::GetErrorHelpFile
- GetErrorHelpFile
- IErrorRecordsImpl.GetErrorHelpFile
dev_langs:
- C++
helpviewer_keywords:
- GetErrorHelpFile method
ms.assetid: ad198f76-5bdf-4b8d-9f1a-3d38f72f31ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7cbb28592a054e524601b91503b98bb08b7415f1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="ierrorrecordsimplgeterrorhelpfile"></a>IErrorRecordsImpl::GetErrorHelpFile
Yardım dosyasının yol adı bir hata kayıttan alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      LPOLESTR GetErrorHelpFile(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rCurError`  
 Bir `ERRORINFO` kaydında bir **IErrorInfo** arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hata için Yardım dosyasına yol adını içeren bir dize işaretçi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IErrorRecordsImpl Sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)