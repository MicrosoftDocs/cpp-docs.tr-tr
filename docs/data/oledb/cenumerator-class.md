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
ms.openlocfilehash: f3e3a61028768144cbef17912952622f19ad0242
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838158"
---
# <a name="cenumerator-class"></a>CEnumerator Sınıfı

Tüm veri kaynaklarını ve numaralandırıcıları açıklayan bir satır kümesi döndürmek için [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) arabirimini kullanıma sunan OLE DB Numaralandırıcı nesnesini kullanır.

## <a name="syntax"></a>Syntax

```cpp
class CEnumerator :
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atldbclı. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[Bilgi](#find)|Belirtilen ada sahip bir tane arayan kullanılabilir sağlayıcılarda (veri kaynakları) arar.|
|[GetMoniker](#getmoniker)|`IMoniker`Geçerli kayıt için arabirimi alır.|
|[Aç](#open)|Numaralandırıcı öğesini açar.|

## <a name="remarks"></a>Açıklamalar

`ISourcesRowset`Bu sınıftan verileri dolaylı olarak alabilirsiniz.

## <a name="cenumeratorfind"></a><a name="find"></a> CEnumerator:: Find

Kullanılabilir sağlayıcılar arasında belirtilen adı arar.

### <a name="syntax"></a>Söz dizimi

```cpp
bool Find(TCHAR* szSearchName) throw();
```

#### <a name="parameters"></a>Parametreler

*szSearchName*<br/>
'ndaki Aranacak ad.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ad bulunursa. Aksi takdirde, **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu ad `SOURCES_NAME` , [ISourcesRowset](/previous-versions/windows/desktop/ms715969(v=vs.85)) arabiriminin üyesine eşlenir.

## <a name="cenumeratorgetmoniker"></a><a name="getmoniker"></a> CEnumerator:: Getbilinen ad

Bir ada dönüştürülebileceği dizenin bileşenini ayıklamak için görünen adı ayrıştırır.

### <a name="syntax"></a>Söz dizimi

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

## <a name="cenumeratoropen"></a><a name="open"></a> CEnumerator:: Open

, Bir tane belirtilmişse, Numaralandırıcı için bilinen adı bağlar, ardından [ISourcesRowset:: GetSourcesRowset](/previous-versions/windows/desktop/ms711200(v=vs.85))öğesini çağırarak Numaralandırıcı için satır kümesini alır.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT Open(LPMONIKER pMoniker) throw();

HRESULT Open(const CLSID* pClsid = & CLSID_OLEDB_ENUMERATOR) throw();

HRESULT Open(const CEnumerator& enumerator) throw();
```

#### <a name="parameters"></a>Parametreler

*Pbilinen*<br/>
'ndaki Numaralandırıcı için bilinen ad işaretçisi.

*pCLSID*<br/>
'ndaki Numaralandırıcı için bir işaretçi `CLSID` .

*sının*<br/>
'ndaki Bir Numaralandırıcı başvurusu.

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="see-also"></a>Ayrıca bkz.

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB tüketici şablonları başvurusu](../../data/oledb/ole-db-consumer-templates-reference.md)
