---
title: IRowsetLocateImpl::COMPARE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 57cef167c76d3cfe2396684ddb4ba5959ef38e5c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
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