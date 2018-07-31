---
title: CSession sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession
- ATL::CSession
- ATL.CSession
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
- CSession::Close
- ATL.CSession.Close
- CSession.Close
- ATL::CSession::Close
- CSession.Commit
- ATL.CSession.Commit
- ATL::CSession::Commit
- CSession::Commit
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
- ATL::CSession::Open
- CSession::Open
- CSession.Open
- ATL.CSession.Open
- CSession::StartTransaction
- StartTransaction
- ATL.CSession.StartTransaction
- CSession.StartTransaction
- ATL::CSession::StartTransaction
dev_langs:
- C++
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 72ac1a5be4f2e114e5b90b65542b09733c43d174
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39338869"
---
# <a name="csession-class"></a>CSession Sınıfı
Bir tek veritabanı erişim oturumu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi

```cpp
class CSession  
```  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atldbcli.h  
  
## <a name="members"></a>Üyeler  
  
### <a name="methods"></a>Yöntemler  
  
|||  
|-|-|  
|[Durdurma](#abort)|İptal (sonlandırır) işlem.|  
|[Kapat](#close)|Bir oturumu kapatır.|  
|[İşleme](#commit)|hareketi tamamlar.|  
|[GetTransactionInfo](#gettransactioninfo)|Bir işlem ile ilgili bilgileri döndürür.|  
|[açın](#open)|Veri kaynağı nesnesi için yeni bir oturum açar.|  
|[StartTransaction](#starttransaction)|Bu oturum için yeni bir işlem başlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir veya daha fazla oturum ilişkilendirilebilir tarafından temsil edilen her sağlayıcı bağlantısı (veri kaynağı) ile bir [CDataSource](../../data/oledb/cdatasource-class.md) nesne. Yeni bir `CSession` için bir `CDataSource`, çağrı [CSession::Open](../../data/oledb/csession-open.md). Bir veritabanı işlemi başlatamadığı için `CSession` sağlar `StartTransaction` yöntemi. Bir işlem başlatıldıktan sonra onu kullanarak yürütülemez `Commit` yöntemi kullanarak iptal `Abort` yöntemi.  
  
## <a name="abort"></a> CSession::Abort
İşlem sona erer.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Abort(BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [Iİşlem::Durdur](https://msdn.microsoft.com/library/ms709833.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT. 

## <a name="close"></a> CSession::Close
Tarafından açılmış oturumu [CSession::Open](../../data/oledb/csession-open.md).  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
void Close() throw();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yayınları `m_spOpenRowset` işaretçi.  

## <a name="commit"></a> CSession::Commit
hareketi tamamlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Commit(BOOL bRetaining = FALSE,   
   DWORD grfTC = XACTTC_SYNC,   
   DWORD grfRM = 0) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [ITransaction::Commit](https://msdn.microsoft.com/library/ms713008.aspx).  

## <a name="gettransactioninfo"></a> CSession::gettransactionınfo
Bir işlem ile ilgili bilgileri döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/library/ms714975.aspx) içinde *OLE DB Programcının Başvurusu*. 

## <a name="open"></a> CSession::Open
Veri kaynağı nesnesi için yeni bir oturum açar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT Open(const CDataSource& ds,  
   DBPROPSET *pPropSet = NULL,  
   ULONG ulPropSets = 0) throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 *DS*  
 [in] Oturum açılacak olan veri kaynağı.  
  
 *pPropSet*  
 [in] Bir dizi işaretçi [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) özelliklerini ve değerlerini ayarlamak için içeren yapılar. Bkz: [özellik kümeleri ve özellik gruplarını](https://msdn.microsoft.com/library/ms713696.aspx) içinde *OLE DB Programcının Başvurusu* Windows SDK içinde.  
  
 *ulPropSets*  
 [in] Sayısını [DBPROPSET](https://msdn.microsoft.com/library/ms714367.aspx) yapıları geçirilen *pPropSet* bağımsız değişken.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  
 Veri kaynağı nesnesi kullanılarak açmalısınız [CDataSource::Open](../../data/oledb/cdatasource-open.md) öğesine iletmeden önce `CSession::Open`.  

## <a name="starttransaction"></a> CSession::StartTransaction
Bu oturum için yeni bir işlem başlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,  
   ULONG isoFlags = 0,  
   ITransactionOptions* pOtherOptions = NULL,  
   ULONG* pulTransactionLevel = NULL) const throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 Bkz: [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir HRESULT.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için [ITransactionLocal::StartTransaction](https://msdn.microsoft.com/library/ms709786.aspx) içinde *OLE DB Programcının Başvurusu*. 
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CatDB](../../visual-cpp-samples.md)   
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)