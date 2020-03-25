---
title: CSimpleRow Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleRow
- ATL::CSimpleRow
- ATL.CSimpleRow
- CSimpleRow::AddRefRow
- AddRefRow
- ATL.CSimpleRow.AddRefRow
- ATL::CSimpleRow::AddRefRow
- CSimpleRow.AddRefRow
- CSimpleRow.Compare
- CSimpleRow::Compare
- ATL::CSimpleRow::CSimpleRow
- CSimpleRow.CSimpleRow
- ATL.CSimpleRow.CSimpleRow
- CSimpleRow::CSimpleRow
- ATL::CSimpleRow::ReleaseRow
- CSimpleRow::ReleaseRow
- ReleaseRow
- CSimpleRow.ReleaseRow
- ATL.CSimpleRow.ReleaseRow
- CSimpleRow.m_dwRef
- CSimpleRow::m_dwRef
- CSimpleRow::m_iRowset
- CSimpleRow.m_iRowset
helpviewer_keywords:
- CSimpleRow class
- AddRefRow method
- Compare method
- CSimpleRow class, constructor
- ReleaseRow method
- m_dwRef
- m_iRowset
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
ms.openlocfilehash: 2b08e0e8f3b5b43f79019c70e3fe32ae9064dee9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211126"
---
# <a name="csimplerow-class"></a>CSimpleRow Sınıfı

, [IRowsetImpl](../../data/oledb/irowsetimpl-class.md) sınıfında kullanılan satır tanıtıcısı için varsayılan bir uygulama sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
class CSimpleRow
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddRefRow](#addrefrow)|Varolan bir satır tanıtıcısına bir başvuru sayısı ekler.|
|[Compare](#compare)|Aynı satır örneğine başvurduklarında iki satırı karşılaştırır.|
|[CSimpleRow](#csimplerow)|Oluşturucu.|
|[ReleaseRow](#releaserow)|Satırları yayınlar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_dwRef](#dwref)|Varolan bir satır tanıtıcısına başvuru sayısı.|
|[m_iRowset](#irowset)|İmleci temsil eden satır kümesi dizini.|

## <a name="remarks"></a>Açıklamalar

Satır tanıtıcısı, bir sonuç satırı için mantıksal olarak benzersiz bir etikettir. `IRowsetImpl` [IRowsetImpl:: GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)içinde istenen her satır için yeni bir `CSimpleRow` oluşturur. `CSimpleRow`, `IRowsetImpl`bir varsayılan şablon bağımsız değişkeni olduğundan, kendi satır tanıtıcı uygulamanız ile de değiştirilebilir. Bu sınıfı değiştirme gereksinimi, değiştirme sınıfının **Long**türünde tek bir parametre kabul eden bir Oluşturucu sağlamasını sağlamaktır.

## <a name="csimplerowaddrefrow"></a><a name="addrefrow"></a>CSimpleRow:: AddRefRow

Bir başvuru sayısını, iş parçacığı güvenli bir şekilde var olan bir satır tanıtıcısına ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
DWORD AddRefRow();
```

## <a name="csimplerowcompare"></a><a name="compare"></a>CSimpleRow:: Compare

Aynı satır örneğine başvurduklarında iki satırı karşılaştırır.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT Compare(CSimpleRow* pRow);
```

#### <a name="parameters"></a>Parametreler

*pRow*<br/>
`CSimpleRow` nesnesine yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Genellikle S_OK, iki satır aynı satır örneği veya S_FALSE iki satırı farklı olduğunu belirten bir HRESULT değeri. *OLE DB Programcı 'nın* diğer olası dönüş değerleri için başvurusu Içindeki [IRowsetIdentity:: IsSameRow](/previous-versions/windows/desktop/ms719629(v=vs.85)) bölümüne bakın.

## <a name="csimplerowcsimplerow"></a><a name="csimplerow"></a>CSimpleRow:: CSimpleRow

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
CSimpleRow(DBCOUNTITEM iRowsetCur);
```

#### <a name="parameters"></a>Parametreler

*ırowsetcur*<br/>
'ndaki Geçerli satır kümesinin dizini.

### <a name="remarks"></a>Açıklamalar

[M_iRowset](../../data/oledb/csimplerow-m-irowset.md) , *ırowsetcur*olarak ayarlar.

## <a name="csimplerowreleaserow"></a><a name="releaserow"></a>CSimpleRow:: ReleaseRow

Satırları iş parçacığı güvenli bir şekilde yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
DWORD ReleaseRow();
```

## <a name="csimplerowm_dwref"></a><a name="dwref"></a>CSimpleRow:: m_dwRef

Varolan bir satır tanıtıcısına başvuru sayısı.

### <a name="syntax"></a>Sözdizimi

```cpp
DWORD m_dwRef;
```

## <a name="csimplerowm_irowset"></a><a name="irowset"></a>CSimpleRow:: m_iRowset

İmleci temsil eden satır kümesi dizini.

### <a name="syntax"></a>Sözdizimi

```cpp
KeyType m_iRowset;
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[IRowsetImpl Sınıfı](../../data/oledb/irowsetimpl-class.md)
