---
title: CTable::Open | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1b9edfb63c29298eb2805372cbb1303144a084f0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ctableopen"></a>CTable::Open
Tablo açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [in] Tablo açılan oturumu.  
  
 *wszTableName*  
 [in] Açmak için tablonun adını bir UNICODE dizesi geçirildi.  
  
 *szTableName*  
 [in] Açmak için tablonun adını ANSI dize olarak geçirildi.  
  
 *DBID*  
 [in] **DBID** açmak için tablonun.  
  
 *pPropSet*  
 [in] Bir dizi için bir işaretçi [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) özellikleri ve ayarlanacak değerleri içeren yapıları. Bkz: [özellik kümeleri ve özellik grupları](https://msdn.microsoft.com/en-us/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK. Varsayılan değer NULL olan hiçbir özellikleri belirtir.  
  
 `ulPropSets`  
 [in] Sayısı [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişkeni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT`.  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla ayrıntı için bkz: [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTable sınıfı](../../data/oledb/ctable-class.md)