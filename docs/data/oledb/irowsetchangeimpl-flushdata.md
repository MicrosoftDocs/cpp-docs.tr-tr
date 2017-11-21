---
title: IRowsetChangeImpl::flushdata | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
dev_langs: C++
helpviewer_keywords: FlushData method
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 31555e1f8305a281955902b71fdc71fbcc5405e5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetchangeimplflushdata"></a>IRowsetChangeImpl::FlushData
Verileri, depolama alanına kaydetmeye sağlayıcısı tarafından Overidden.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *hRowToFlush*  
 [in] Verileri satırlara işleyin. Bu satır türüne gelen belirlenir *RowClass* şablonu bağımsız değişkeni `IRowsetImpl` sınıfı (`CSimpleRow` varsayılan olarak).  
  
 *hAccessorToFlush*  
 [in] Bağlama bilgileri ve tür bilgileri içeren erişimcisi tanıtıcı kendi **PROVIDER_MAP** (bkz [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetChangeImpl sınıfı](../../data/oledb/irowsetchangeimpl-class.md)