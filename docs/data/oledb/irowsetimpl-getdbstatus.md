---
title: "Irowsetımpl::getdbstatus | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs: C++
helpviewer_keywords: GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bcfa368eaac89c1b7f0a094c139fc2434691e143
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
Döndürür `DBSTATUS` durumu bayrakları belirtilen alan için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      virtual DBSTATUS GetDBStatus(  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`currentRow`  
 Geçerli satır.  
  
 [in]`columnNames`  
 Durum istenmektedir sütun.  
  
## <a name="return-value"></a>Dönüş Değeri  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) sütun için bayrak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Irowsetımpl sınıfı](../../data/oledb/irowsetimpl-class.md)