---
title: CTable::Open | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- Open method
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: d727af84dfeae77ab08e57f2f3a11120f9f88631
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ctableopen"></a>CTable::Open
Tablo açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  


HRESULT Open(const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  


HRESULT Open(const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0) throw ();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `session`  
 [in] Tablo açılan oturumu.  
  
 *wszTableName*  
 [in] Açmak için tablonun adını bir UNICODE dizesi geçirildi.  
  
 *szTableName*  
 [in] Açmak için tablonun adını ANSI dize olarak geçirildi.  
  
 *dbid*  
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
 [CTable Sınıfı](../../data/oledb/ctable-class.md)