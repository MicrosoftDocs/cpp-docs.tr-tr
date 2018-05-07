---
title: IRowsetLocateImpl::COMPARE | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs:
- C++
helpviewer_keywords:
- Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 208f912e92045daec36066e1dcc06fc38b5a8ed2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
İki yer işaretleri karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
      STDMETHOD (Compare )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison);  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="remarks"></a>Açıklamalar  
 Aşağıdakilerden birini yer işaretleri standart olabilir OLE DB tanımlanan [standart yer işareti](https://msdn.microsoft.com/en-us/library/ms712954.aspx) (**DBBMK_FIRST**, **DBBMK_LAST**, veya **DBBMK_INVALID**). Döndürülen değerin `pComparison` iki yer işaretleri arasındaki ilişkiyi gösterir:  
  
-   **DBCOMPARE_LT** (`cbBookmark1` önce `cbBookmark2`.)  
  
-   **DBCOMPARE_EQ** (`cbBookmark1` eşittir `cbBookmark2`.)  
  
-   **DBCOMPARE_GT** (`cbBookmark1` sonra `cbBookmark2`.)  
  
-   **DBCOMPARE_NE** (yer işaretleri eşit ve sıralı değil.)  
  
-   **DBCOMPARE_NOTCOMPARABLE** (yer işaretleri karşılaştırılamaz.)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldb.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IRowsetLocateImpl Sınıfı](../../data/oledb/irowsetlocateimpl-class.md)