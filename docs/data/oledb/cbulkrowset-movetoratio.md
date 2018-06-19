---
title: CBulkRowset::MoveToRatio | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CBulkRowset.MoveToRatio
- ATL::CBulkRowset::MoveToRatio
- MoveToRatio
- CBulkRowset::MoveToRatio
- ATL.CBulkRowset<TAccessor>.MoveToRatio
- ATL::CBulkRowset<TAccessor>::MoveToRatio
- ATL.CBulkRowset.MoveToRatio
- CBulkRowset<TAccessor>::MoveToRatio
dev_langs:
- C++
helpviewer_keywords:
- MoveToRatio method
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0ab702781ed47a4520b53e9698319b5c245e2dfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33093366"
---
# <a name="cbulkrowsetmovetoratio"></a>CBulkRowset::MoveToRatio
Satır satır kümesindeki bir kesir konumundan başlayarak getirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
HRESULT MoveToRatio(DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator)throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `nNumerator`  
 [in] Veri getirme kesirli konumu belirlemek için kullanılan pay.  
  
 `nDenominator`  
 [in] Veri getirme kesirli konumu belirlemek için kullanılan payda.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 `MoveToRatio` aşağıdaki formülü göre kabaca satırlarını getirir:  
  
 `(nNumerator *  RowsetSize ) / nDenominator`  
  
 Burada `RowsetSize` satır ölçülen satır boyutu. Bu formülü doğruluğunu belirli sağlayıcısına bağlıdır. Ayrıntılar için bkz [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CBulkRowset Sınıfı](../../data/oledb/cbulkrowset-class.md)