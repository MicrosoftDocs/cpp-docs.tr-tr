---
title: CTable sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CTable
- ATL.CTable
- CTable
- ATL.CTable.Open
- ATL::CTable::Open
- CTable::Open
- CTable.Open
dev_langs:
- C++
helpviewer_keywords:
- CTable class
- Open method
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7dc1383199b5e8167936d99d487bdfc3eb15bddb
ms.sourcegitcommit: b217daee32d3413cf33753d9b4dc35a0022b1bfa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2018
ms.locfileid: "39233496"
---
# <a name="ctable-class"></a>CTable Sınıfı
Bir basit satır kümesine (parametresi olmayan) doğrudan erişim için bir yol sağlar.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
template <class TAccessor = CNoAccessor, 
            template <typename T> class TRowset = CRowset>  
class CTable :  
   public CAccessorRowset <TAccessor, TRowset>  
```  
  
### <a name="parameters"></a>Parametreler  
 *TAccessor*  
 Bir erişimci sınıfı.  
  
 *CRowset*  
 Bir satır kümesi sınıfı.  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[açın](#open)|Tablo açılır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bkz: [CCommand](../../data/oledb/ccommand-class.md) bir satır kümesine erişmek için bir komutu nasıl çalıştıracağını hakkında bilgi için.  

## <a name="open"></a> CTable::Open
Tablo açılır.  
  
### <a name="syntax"></a>Sözdizimi  
  
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
 *Oturumu*  
 [in] Tablonun en iyi duruma açıldığında oturumu.  
  
 *wszTableName*  
 [in] Açmak için tablonun adını bir Unicode dize olarak geçirildi.  
  
 *szTableName*  
 [in] Açmak için tablonun adı bir ANSI dizesine geçirildi.  
  
 *dbid*  
 [in] `DBID` Açmak için tablo.  
  
 *pPropSet*  
 [in] Bir dizi işaretçi [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](https://msdn.microsoft.com/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde. Varsayılan değeri NULL özellik belirtir.  
  
 *ulPropSets*  
 [in] Sayısını [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla ayrıntı için [IOpenRowset::OpenRowset](https://msdn.microsoft.com/library/ms716724.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)   
