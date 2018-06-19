---
title: CSimpleRow::Compare | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSimpleRow.Compare
- CSimpleRow::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 0bb65f09-c7bc-449b-aa4e-c828cac13510
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 75d79e753f1f4af630c26ef07fbb7241576535ce
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33098971"
---
# <a name="csimplerowcompare"></a>CSimpleRow::Compare
Aynı satır örneğine bakın görmek için iki satır karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Compare(CSimpleRow* pRow);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `pRow`  
 Bir işaretçi bir `CSimpleRow` nesnesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `HRESULT` değeri, genellikle `S_OK`, iki satır aynı satır örneğini belirterek veya **S_FALSE**, iki satır belirten farklıdır. Bkz: [IRowsetIdentity::IsSameRow](https://msdn.microsoft.com/en-us/library/ms719629.aspx) içinde *OLE DB Programcının Başvurusu* diğer olası dönüş değerleri.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSimpleRow sınıfı](../../data/oledb/csimplerow-class.md)   
 [CSimpleRow::ReleaseRow](../../data/oledb/csimplerow-releaserow.md)   
 [IRowsetImpl::RefRows](../../data/oledb/irowsetimpl-refrows.md)