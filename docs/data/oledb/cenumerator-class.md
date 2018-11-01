---
title: CEnumerator Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CEnumerator
- CEnumerator::Find
- ATL::CEnumerator::Find
- ATL.CEnumerator.Find
- CEnumerator.Find
- GetMoniker
- CEnumerator.GetMoniker
- CEnumerator::GetMoniker
- ATL.CEnumerator.GetMoniker
- ATL::CEnumerator::GetMoniker
- ATL.CEnumerator.Open
- CEnumerator::Open
- ATL::CEnumerator::Open
- CEnumerator.Open
helpviewer_keywords:
- CEnumerator class
- Find method
- GetMoniker method
- Open method
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
ms.openlocfilehash: c148bdb0a897e19bc3f3aeb7ed40e905073336b2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428609"
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı

Kullanıma sunan bir OLE DB sabit listesi nesnesi kullanan [ISourcesRowset](/previous-versions/windows/desktop/ms715969) tüm veri kaynaklarını ve numaralandırıcıları açıklayan bir satır kümesi döndürmek için arabirim.

## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumerator : 
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldbcli.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Bul](#find)|Belirtilen ada sahip bir arayan yok sağlayıcıları (veri kaynakları) arar.|
|[GetMoniker](#getmoniker)|Alır `IMoniker` geçerli kayıt için arabirim.|
|[açın](#open)|Numaralandırıcı açılır.|

## <a name="remarks"></a>Açıklamalar

Alabileceğiniz `ISourcesRowset` dolaylı olarak bu sınıftaki veri.

## <a name="find"></a> CEnumerator::Find

Belirtilen bir adı yok sağlayıcıları arasında arar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>Parametreler

*szSearchName*<br/>
[in] Aranacak ad.

### <a name="return-value"></a>Dönüş Değeri

**doğru** adı bulunursa. Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu ad eşlendiği `SOURCES_NAME` üyesi [ISourcesRowset](/previous-versions/windows/desktop/ms715969) arabirimi.

## <a name="getmoniker"></a> CEnumerator::GetMoniker

Görünen ad, bilinen adı dönüştürülebilir dize bileşeninin ayıklanacağı ayrıştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker, 
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>Parametreler

*ppMoniker*<br/>
[out] Adı görünen adı ayrıştırıldı ([CEnumeratorAccessor::m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) geçerli satır.

*lpszDisplayName*<br/>
[in] Ayrıştırılacak görünen adı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="open"></a> CEnumerator::Open

Bir belirtilir ve ardından çağırarak satır kümesi için bir numaralandırıcı alır, numaralandırıcı için bilinen ad bağlar [ISourcesRowset::GetSourcesRowset](/previous-versions/windows/desktop/ms711200).

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>Parametreler

*pMoniker*<br/>
[in] Bir işaretçi için bir numaralandırıcı için bir bilinen ad.

*pClsid*<br/>
[in] Bir işaretçi `CLSID` Numaralayıcı.

*Numaralandırıcı*<br/>
[in] Bir başvuru için bir numaralandırıcı.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="see-also"></a>Ayrıca Bkz.

[DBViewer](../../visual-cpp-samples.md)<br/>
[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)