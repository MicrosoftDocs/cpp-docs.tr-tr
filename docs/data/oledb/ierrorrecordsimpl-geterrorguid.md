---
title: Ierrorrecordsımpl::geterrorguıd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetErrorGUID
- IErrorRecordsImpl.GetErrorGUID
- IErrorRecordsImpl::GetErrorGUID
dev_langs:
- C++
helpviewer_keywords:
- GetErrorGUID method
ms.assetid: 42c00755-50e5-401a-8246-adef9de5ced2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a17529b9132a322cf1610baa1463d921c313e118
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33100349"
---
# <a name="ierrorrecordsimplgeterrorguid"></a>IErrorRecordsImpl::GetErrorGUID
GUID hata bir hata kayıttan alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      REFGUID GetErrorGUID(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `rCurError`  
 Bir `ERRORINFO` kaydında bir **IErrorInfo** arabirimi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Hata için bir GUID referansı.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IErrorRecordsImpl Sınıfı](../../data/oledb/ierrorrecordsimpl-class.md)