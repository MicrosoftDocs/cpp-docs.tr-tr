---
title: CSession Sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CSession class
- Abort method
- Close method
- Commit method
- GetTransactionInfo method
- Open method
- StartTransaction method
ms.assetid: 83cd798f-b45d-4f11-a23c-29183390450c
ms.openlocfilehash: 72797411b100480a06e27b71b000264070e57e32
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211139"
---
# <a name="csession-class"></a>CSession Sınıfı

Tek bir veritabanı erişim oturumunu temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class CSession
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Abort](#abort)|İşlemi iptal eder (sonlandırır).|
|[~Eksik](#close)|Oturumu kapatır.|
|[Uygulayın](#commit)|İşlemi kaydeder.|
|[GetTransactionInfo](#gettransactioninfo)|Bir işlemle ilgili bilgileri döndürür.|
|[Açın](#open)|Veri kaynağı nesnesi için yeni bir oturum açar.|
|[StartTransaction](#starttransaction)|Bu oturum için yeni bir işlem başlatır.|

## <a name="remarks"></a>Açıklamalar

Bir veya daha fazla oturum, bir [CDataSource](../../data/oledb/cdatasource-class.md) nesnesi tarafından temsil edilen her bir sağlayıcı bağlantısıyla (veri kaynağı) ilişkilendirilebilir. Bir `CDataSource`için yeni bir `CSession` oluşturmak için [CSession:: Open](../../data/oledb/csession-open.md)çağırın. Bir veritabanı işlemine başlamak için `CSession` `StartTransaction` yöntemi sağlar. Bir işlem başlatıldıktan sonra, `Commit` metodunu kullanarak bu işleme veya `Abort` metodunu kullanarak iptal edebilirsiniz.

## <a name="csessionabort"></a><a name="abort"></a>CSession:: Abort

İşlemi sonlandırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Abort(BOID* pboidReason = NULL,
   BOOL bRetaining = FALSE,
   BOOL bAsync = FALSE) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [ITransaction:: Abort](/previous-versions/windows/desktop/ms709833(v=vs.85)) .

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="csessionclose"></a><a name="close"></a>CSession:: Close

[CSession:: Open](../../data/oledb/csession-open.md)tarafından açılan oturumu kapatır.

### <a name="syntax"></a>Sözdizimi

```cpp
void Close() throw();
```

### <a name="remarks"></a>Açıklamalar

`m_spOpenRowset` işaretçisini serbest bırakır.

## <a name="csessioncommit"></a><a name="commit"></a>CSession:: COMMIT

İşlemi kaydeder.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Commit(BOOL bRetaining = FALSE,
   DWORD grfTC = XACTTC_SYNC,
   DWORD grfRM = 0) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ITransaction:: COMMIT](/previous-versions/windows/desktop/ms713008(v=vs.85)) öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [ITransaction:: COMMIT](/previous-versions/windows/desktop/ms713008(v=vs.85)).

## <a name="csessiongettransactioninfo"></a><a name="gettransactioninfo"></a>CSession:: GetTransactionInfo

Bir işlemle ilgili bilgileri döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ITransaction:: GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) bölümüne bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcı başvurusunda* [ITransaction:: GetTransactionInfo](/previous-versions/windows/desktop/ms714975(v=vs.85)) bölümüne bakın.

## <a name="csessionopen"></a><a name="open"></a>CSession:: Open

Veri kaynağı nesnesi için yeni bir oturum açar.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(const CDataSource& ds,
   DBPROPSET *pPropSet = NULL,
   ULONG ulPropSets = 0) throw();
```

#### <a name="parameters"></a>Parametreler

*FID*<br/>
'ndaki Oturumun açıldığı veri kaynağı.

*pPropSet*<br/>
'ndaki Ayarlanacak özellikleri ve değerleri içeren bir [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapıları dizisine yönelik bir işaretçi. Windows SDK *OLE DB Programcı başvurusu* Içindeki [özellik kümeleri ve özellik grupları](/previous-versions/windows/desktop/ms713696(v=vs.85)) bölümüne bakın.

*ulPropSets*<br/>
'ndaki *PPropset* bağımsız değişkeninde geçirilen [dbpropset](/previous-versions/windows/desktop/ms714367(v=vs.85)) yapılarının sayısı.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Veri kaynağı nesnesini `CSession::Open`geçirmeden önce [CDataSource:: Open](../../data/oledb/cdatasource-open.md) kullanarak açmanız gerekir.

## <a name="csessionstarttransaction"></a><a name="starttransaction"></a>CSession:: StartTransaction

Bu oturum için yeni bir işlem başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT StartTransaction(ISOLEVEL isoLevel = ISOLATIONLEVEL_READCOMMITTED,
   ULONG isoFlags = 0,
   ITransactionOptions* pOtherOptions = NULL,
   ULONG* pulTransactionLevel = NULL) const throw();
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [ıctionlocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, *OLE DB Programcı başvurusunda* [ıctionlocal:: StartTransaction](/previous-versions/windows/desktop/ms709786(v=vs.85)) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CatDB](../../overview/visual-cpp-samples.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
