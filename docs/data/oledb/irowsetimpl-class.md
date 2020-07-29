---
title: IRowsetImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- IRowsetImpl.AddRefRows
- ATL::IRowsetImpl::AddRefRows
- ATL.IRowsetImpl.AddRefRows
- IRowsetImpl.CreateRow
- ATL.IRowsetImpl.CreateRow
- ATL::IRowsetImpl::CreateRow
- CreateRow
- IRowsetImpl::CreateRow
- ATL.IRowsetImpl.GetData
- ATL::IRowsetImpl::GetData
- IRowsetImpl::GetData
- IRowsetImpl.GetData
- GetDBStatus
- IRowsetImpl.GetDBStatus
- IRowsetImpl::GetDBStatus
- GetNextRows
- ATL.IRowsetImpl.GetNextRows
- ATL::IRowsetImpl::GetNextRows
- IRowsetImpl::GetNextRows
- IRowsetImpl.GetNextRows
- IRowsetImpl.IRowsetImpl
- ATL::IRowsetImpl::IRowsetImpl
- ATL.IRowsetImpl.IRowsetImpl
- IRowsetImpl::IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- IRowsetImpl::ReleaseRows
- ATL::IRowsetImpl::ReleaseRows
- IRowsetImpl.ReleaseRows
- ATL.IRowsetImpl.RestartPosition
- IRowsetImpl::RestartPosition
- RestartPosition
- ATL::IRowsetImpl::RestartPosition
- IRowsetImpl.RestartPosition
- IRowsetImpl.SetDBStatus
- IRowsetImpl::SetDBStatus
- SetDBStatus
- ATL.IRowsetImpl.m_bCanFetchBack
- ATL::IRowsetImpl::m_bCanFetchBack
- IRowsetImpl.m_bCanFetchBack
- IRowsetImpl::m_bCanFetchBack
- m_bCanFetchBack
- IRowsetImpl::m_bCanScrollBack
- ATL::IRowsetImpl::m_bCanScrollBack
- IRowsetImpl.m_bCanScrollBack
- ATL.IRowsetImpl.m_bCanScrollBack
- m_bCanScrollBack
- ATL.IRowsetImpl.m_bReset
- IRowsetImpl.m_bReset
- m_bReset
- IRowsetImpl::m_bReset
- ATL::IRowsetImpl::m_bReset
- IRowsetImpl::m_iRowset
- IRowsetImpl.m_iRowset
- ATL::IRowsetImpl::m_iRowset
- ATL.IRowsetImpl.m_iRowset
- m_iRowset
- IRowsetImpl::m_rgRowHandles
- IRowsetImpl.m_rgRowHandles
- m_rgRowHandles
- ATL::IRowsetImpl::m_rgRowHandles
- ATL.IRowsetImpl.m_rgRowHandles
helpviewer_keywords:
- IRowsetImpl class
- AddRefRows method
- CreateRow method
- GetData method [OLE DB]
- GetDBStatus method
- GetNextRows method
- IRowsetImpl constructor
- RefRows method
- ReleaseRows method
- RestartPosition method
- SetDBStatus method
- m_bCanFetchBack
- m_bCanScrollBack
- m_bReset
- m_iRowset
- m_rgRowHandles
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
ms.openlocfilehash: f440bb891c30033962208c3e89648bd05ba3f81b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87232150"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl Sınıfı

Arabirimin bir uygulamasını sağlar `IRowset` .

## <a name="syntax"></a>Söz dizimi

```cpp
template <
   class T,
   class RowsetInterface,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <
      RowClass::KeyType,
      RowClass*>>
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IRowsetImpl` .

*RowsetInterface*<br/>
Sınıfından türetilmiş bir sınıf `IRowsetImpl` .

*RowClass*<br/>
İçin depolama birimi `HROW` .

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddRefRows](#addrefrows)|Varolan bir satır tanıtıcısına bir başvuru sayısı ekler.|
|[CreateRow](#createrow)|Yeni bir ayırmak için [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) tarafından çağırılır `HROW` . Doğrudan Kullanıcı tarafından çağrılmaz.|
|[GetData](#getdata)|Satır kümesinin satır kopyasından verileri alır.|
|[GetDBStatus](#getdbstatus)|Belirtilen alanın durumunu döndürür.|
|[GetNextRows](#getnextrows)|Önceki konumu hatırlayıp, satırları sırayla getirir.|
|[IRowsetImpl](#irowsetimpl)|Oluşturucu. Doğrudan Kullanıcı tarafından çağrılmaz.|
|[RefRows](#refrows)|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)tarafından çağırılır. Doğrudan Kullanıcı tarafından çağrılmaz.|
|[ReleaseRows](#releaserows)|Satırları yayınlar.|
|[RestartPosition](#restartposition)|Sonraki getirme konumunu ilk konumuna konumlandırır; diğer bir deyişle, satır kümesi ilk oluşturulduğunda konumu.|
|[SetDBStatus](#setdbstatus)|Belirtilen alanın durum bayraklarını ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|Bir sağlayıcının geri getirmeyi destekleyip desteklemediğini gösterir.|
|[m_bCanScrollBack](#bcanscrollback)|Bir sağlayıcının imlece geriye doğru kayıp gidemeyeceğini gösterir.|
|[m_bReset](#breset)|Bir sağlayıcının imleç konumunu sıfırlayıp sıfırmadığını gösterir. Bu, geriye doğru kaydırma yaparken veya [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)içinde geri getirilirken özel bir anlam içerir.|
|[m_iRowset](#irowset)|İmleci temsil eden satır kümesi dizini.|
|[m_rgRowHandles](#rgrowhandles)|Satır tanıtıcılarının listesi.|

## <a name="remarks"></a>Açıklamalar

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) , temel satır kümesi arabirimidir.

## <a name="irowsetimpladdrefrows"></a><a name="addrefrows"></a>IRowsetImpl:: AddRefRows

Varolan bir satır tanıtıcısına bir başvuru sayısı ekler.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) öğesine bakın.

## <a name="irowsetimplcreaterow"></a><a name="createrow"></a>IRowsetImpl:: CreateRow

[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) tarafından yeni bir ayırma için çağrılan bir yardımcı yöntem `HROW` .

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>Parametreler

*lRowsOffset*<br/>
Oluşturulan satırın imleç konumu.

*cRowsObtained*<br/>
Oluşturulan satır sayısını gösteren bir başvuru, kullanıcıya geri geçirildi.

*Rbüyüdükçe*<br/>
`HROW`Yeni oluşturulan satır tanıtıcılarını kullanarak çağırana döndürülen bir dizisi.

### <a name="remarks"></a>Açıklamalar

Satır varsa, bu yöntem [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) çağırır ve döndürür. Aksi takdirde, RowClass şablon değişkeninin yeni bir örneğini ayırır ve [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)ekler.

## <a name="irowsetimplgetdata"></a><a name="getdata"></a>IRowsetImpl:: GetData

Satır kümesinin satır kopyasından verileri alır.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: GetData](/previous-versions/windows/desktop/ms716988(v=vs.85)) ' na bakın.

Bazı parametreler, ' de açıklanan farklı adların *OLE DB Programcı Başvuru* parametrelerine karşılık gelir `IRowset::GetData` :

|OLE DB şablon parametreleri|*OLE DB Programcı Başvuru* parametreleri|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>Açıklamalar

Ayrıca OLE DB veri dönüştürme DLL 'sini kullanarak veri dönüştürmeyi işler.

## <a name="irowsetimplgetdbstatus"></a><a name="getdbstatus"></a>IRowsetImpl:: GetDBStatus

Belirtilen alan için DBSTATUS durum bayraklarını döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>Parametreler

*currentRow*<br/>
'ndaki Geçerli satır.

*columnNames*<br/>
'ndaki Durumu istenen sütun.

### <a name="return-value"></a>Dönüş Değeri

Sütun için [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) bayrakları.

## <a name="irowsetimplgetnextrows"></a><a name="getnextrows"></a>IRowsetImpl:: GetNextRows

Önceki konumu hatırlayıp, satırları sırayla getirir.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: GetNextRows](/previous-versions/windows/desktop/ms709827(v=vs.85)) bakın.

## <a name="irowsetimplirowsetimpl"></a><a name="irowsetimpl"></a>IRowsetImpl:: IRowsetImpl

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>Açıklamalar

Genellikle bu yöntemi doğrudan çağırmanız gerekmez.

## <a name="irowsetimplrefrows"></a><a name="refrows"></a>IRowsetImpl:: RefRows

Bir başvuru sayısını var olan bir satır tanıtıcısına artırmak veya serbest bırakmak için [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) tarafından çağırılır.

### <a name="syntax"></a>Söz dizimi

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) öğesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

## <a name="irowsetimplreleaserows"></a><a name="releaserows"></a>IRowsetImpl:: ReleaseRows

Satırları yayınlar.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) bakın.

## <a name="irowsetimplrestartposition"></a><a name="restartposition"></a>IRowsetImpl:: RestartPosition

Sonraki getirme konumunu ilk konumuna konumlandırır; diğer bir deyişle, satır kümesi ilk oluşturulduğunda konumu.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IRowset:: RestartPosition](/previous-versions/windows/desktop/ms712877(v=vs.85)) bakın.

### <a name="remarks"></a>Açıklamalar

Satır kümesi konumu çağrılana kadar tanımsızdır `GetNextRow` . Çağırarak ve sonra geri alarak veya kaydırarak bir rowet içinde geriye doğru taşıyabilirsiniz `RestartPosition` .

## <a name="irowsetimplsetdbstatus"></a><a name="setdbstatus"></a>IRowsetImpl:: SetDBStatus

Belirtilen alan için DBSTATUS durum bayraklarını ayarlar.

### <a name="syntax"></a>Söz dizimi

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>Parametreler

*statusFlags*<br/>
Sütun için ayarlanacak [DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) bayrakları.

*currentRow*<br/>
Geçerli satır.

*ColumnInfo*<br/>
Durumun ayarlandığı sütun.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

Sağlayıcı, DBSTATUS_S_ISNULL ve DBSTATUS_S_DEFAULT için özel işlem sağlamak üzere bu işlevi geçersiz kılar.

## <a name="irowsetimplm_bcanfetchback"></a><a name="bcanfetchback"></a>IRowsetImpl:: m_bCanFetchBack

Bir sağlayıcının geri getirmeyi destekleyip desteklemediğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>Açıklamalar

`DBPROP_CANFETCHBACKWARDS`Gruptaki özelliği ile bağlantılı `DBPROPSET_ROWSET` . Sağlayıcının olması için desteği `DBPROP_CANFETCHBACKWARDS` olmalıdır `m_bCanFetchBackwards` **`true`** .

## <a name="irowsetimplm_bcanscrollback"></a><a name="bcanscrollback"></a>IRowsetImpl:: m_bCanScrollBack

Bir sağlayıcının imlece geriye doğru kayıp gidemeyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>Açıklamalar

`DBPROP_CANSCROLLBACKWARDS`Gruptaki özelliği ile bağlantılı `DBPROPSET_ROWSET` . Sağlayıcının olması için desteği `DBPROP_CANSCROLLBACKWARDS` olmalıdır `m_bCanFetchBackwards` **`true`** .

## <a name="irowsetimplm_breset"></a><a name="breset"></a>IRowsetImpl:: m_bReset

İmleç konumunun satır kümesinde tanımlanıp tanımlanmadığını belirlemede kullanılan bir bit bayrağı.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>Açıklamalar

Tüketici negatif [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) `lOffset` veya *Crow* ile GetNextRows öğesini çağırırsa ve `m_bReset` true ise, `GetNextRows` satır kümesinin sonuna gider. `m_bReset`Yanlış ise, tüketici OLE DB belirtimine uyum olarak bir hata kodu alır. `m_bReset`Bayrak, **`true`** satır kümesi ilk oluşturulduğunda ve tüketici [IRowsetImpl:: RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)öğesini çağırdığında olarak ayarlanır. ' İ çağırdığınızda olarak ayarlanır **`false`** `GetNextRows` .

## <a name="irowsetimplm_irowset"></a><a name="irowset"></a>IRowsetImpl:: m_iRowset

İmleci temsil eden satır kümesi dizini.

### <a name="syntax"></a>Sözdizimi

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="irowsetimplm_rgrowhandles"></a><a name="rgrowhandles"></a>IRowsetImpl:: m_rgRowHandles

Şu anda sağlayıcı tarafından yanıt olarak bulunan satır tanıtıcılarının Haritası `GetNextRows` .

### <a name="syntax"></a>Sözdizimi

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>Açıklamalar

Satır tutamaçları çağırarak kaldırılır `ReleaseRows` . *MapClass*tanımı Için [IRowsetImpl 'ya genel bakış ' a](../../data/oledb/irowsetimpl-class.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow sınıfı](../../data/oledb/csimplerow-class.md)
