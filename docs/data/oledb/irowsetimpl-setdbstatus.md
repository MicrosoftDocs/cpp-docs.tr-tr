---
title: "Irowsetımpl::setdbstatus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs: C++
helpviewer_keywords: SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dcc6783ce210c434e58814bcee8654ddd9111b52
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Ayarlar `DBSTATUS` durumu bayrakları belirtilen alan için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `statusFlags`  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) sütunu için ayarlamak için bayrak.  
  
 `currentRow`  
 Geçerli satır.  
  
 *ColumnInfo*  
 Durum ayarlanan sütun.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
## <a name="remarks"></a>Açıklamalar  
 Sağlayıcı için özel işlem sağlamak için bu işlevi geçersiz kılmaları **DBSTATUS_S_ISNULL** ve **DBSTATUS_S_DEFAULT**.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Irowsetımpl sınıfı](../../data/oledb/irowsetimpl-class.md)