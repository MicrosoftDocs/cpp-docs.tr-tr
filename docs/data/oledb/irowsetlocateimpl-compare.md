---
title: IRowsetLocateImpl::COMPARE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.IRowsetLocateImpl.Compare
- IRowsetLocateImpl::Compare
- IRowsetLocateImpl.Compare
- ATL::IRowsetLocateImpl::Compare
dev_langs: C++
helpviewer_keywords: Compare method
ms.assetid: 6f84052c-c68c-480a-982f-03748faa7d5d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2dba219ef2b2e0747d800d45950217e220ab1449
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="irowsetlocateimplcompare"></a>IRowsetLocateImpl::Compare
İki yer işaretleri karşılaştırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      STDMETHOD ( Compare )(  
   HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmark1,  
   const BYTE* pBookmark1,  
   DBBKMARK cbBookmark2,  
   const BYTE* pBookmark2,  
   DBCOMPARE* pComparison   
);  
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
 [IRowsetLocateImpl sınıfı](../../data/oledb/irowsetlocateimpl-class.md)