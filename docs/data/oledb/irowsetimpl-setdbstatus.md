---
title: Irowsetımpl::setdbstatus | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
dev_langs:
- C++
helpviewer_keywords:
- SetDBStatus method
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7e6e07b6fe1a45a779c5ffe1e1afffaabdcb6d34
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33103908"
---
# <a name="irowsetimplsetdbstatus"></a>IRowsetImpl::SetDBStatus
Ayarlar `DBSTATUS` durumu bayrakları belirtilen alan için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo);  
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
 [IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)