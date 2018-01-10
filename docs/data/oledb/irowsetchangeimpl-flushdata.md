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
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 565b971b53ddb0a50b276d76aaaf62e9f7fa39f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
 [IRowsetChangeImpl Sınıfı](../../data/oledb/irowsetchangeimpl-class.md)