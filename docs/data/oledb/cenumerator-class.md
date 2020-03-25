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
ms.openlocfilehash: d0fa5f381dba4f67934007d59dbdaf4450bcfb60
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211802"
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı

Tüm veri kaynaklarını ve numaralandırıcıları açıklayan bir satır kümesi döndürmek için [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) arabirimini kullanıma sunan OLE DB Numaralandırıcı nesnesini kullanır.

## <a name="syntax"></a>Sözdizimi

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Bul](#find)|Belirtilen ada sahip bir tane arayan kullanılabilir sağlayıcılarda (veri kaynakları) arar.|
|[GetMoniker](#getmoniker)|Geçerli kayıt için `IMoniker` arabirimini alır.|
|[Açın](#open)|Numaralandırıcı öğesini açar.|

## <a name="remarks"></a>Açıklamalar

`ISourcesRowset` verilerini bu sınıftan dolaylı olarak alabilirsiniz.

## <a name="cenumeratorfind"></a><a name="find"></a>CEnumerator:: Find

Kullanılabilir sağlayıcılar arasında belirtilen adı arar.

### <a name="syntax"></a>Sözdizimi

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>Parametreler

*szSearchName*<br/>
'ndaki Aranacak ad.

### <a name="return-value"></a>Dönüş Değeri

ad bulunursa **true** . Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu ad, [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) arabiriminin `SOURCES_NAME` üyesine eşlenir.

## <a name="cenumeratorgetmoniker"></a><a name="getmoniker"></a>CEnumerator:: Getbilinen ad

Bir ada dönüştürülebileceği dizenin bileşenini ayıklamak için görünen adı ayrıştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT GetMoniker(LPMONIKER* ppMoniker) const throw();

HRESULT GetMoniker(LPMONIKER* ppMoniker,
   LPCTSTR lpszDisplayName) const throw();
```

#### <a name="parameters"></a>Parametreler

*Ppbilinen adı*<br/>
dışı Bilinen ad, geçerli satırın görünen adından ([CEnumeratorAccessor:: m_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)) ayrıştırıldı.

*lpszDisplayName*<br/>
'ndaki Ayrıştırılacak görünen ad.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="cenumeratoropen"></a><a name="open"></a>CEnumerator:: Open

, Bir tane belirtilmişse, Numaralandırıcı için bilinen adı bağlar, ardından [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85))öğesini çağırarak Numaralandırıcı için satır kümesini alır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>Parametreler

*Pbilinen*<br/>
'ndaki Numaralandırıcı için bilinen ad işaretçisi.

*pCLSID*<br/>
'ndaki Numaralandırıcı `CLSID` için bir işaretçi.

*sının*<br/>
'ndaki Bir Numaralandırıcı başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="see-also"></a>Ayrıca bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB Tüketici Şablonları Başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
