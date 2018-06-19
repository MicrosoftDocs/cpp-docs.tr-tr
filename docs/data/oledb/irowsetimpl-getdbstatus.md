---
title: Irowsetımpl::getdbstatus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- GetDBStatus method
ms.assetid: e51d8ee2-fc0c-4909-861c-026c94fb0dfc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ebebbc2d1392e4f3c863ce366e8d19cfad3b7162
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33106537"
---
# <a name="irowsetimplgetdbstatus"></a>IRowsetImpl::GetDBStatus
Döndürür `DBSTATUS` durumu bayrakları belirtilen alan için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      virtual DBSTATUS GetDBStatus(RowClass* currentRow,  
   ATLCOLUMNINFO* columnNames);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `currentRow`  
 Geçerli satır.  
  
 [in] `columnNames`  
 Durum istenmektedir sütun.  
  
## <a name="return-value"></a>Dönüş Değeri  
 [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) sütun için bayrak.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)