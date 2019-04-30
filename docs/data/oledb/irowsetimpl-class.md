---
title: IRowsetImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IRowsetImpl
- IRowsetImpl::AddRefRows
- AddRefRows
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
- IRowsetImpl
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
- ATL.IRowsetImpl.ReleaseRows
- ReleaseRows
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
ms.openlocfilehash: 47b03a542933c6223e098bc9d8fa8d45bf5e047b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62390756"
---
# <a name="irowsetimpl-class"></a>IRowsetImpl Sınıfı

Bir uygulamasını sağlar `IRowset` arabirimi.

## <a name="syntax"></a>Sözdizimi

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
Sınıfınız, türetilen `IRowsetImpl`.

*RowsetInterface*<br/>
Öğesinden türetilen bir sınıf `IRowsetImpl`.

*RowClass*<br/>
Depolama birimi için `HROW`.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm olan satır işleyicilerini depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddRefRows](#addrefrows)|Var olan bir satır işleyici için bir başvuru sayısı ekler.|
|[CreateRow](#createrow)|Çağıran [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) yeni ayrılacak `HROW`. Doğrudan kullanıcı tarafından çağrılır değil.|
|[GetData](#getdata)|Satır satır kümesinin kopyadan verileri alır.|
|[GetDBStatus](#getdbstatus)|Belirtilen alan durumunu döndürür.|
|[GetNextRows](#getnextrows)|Satırlar sıralı olarak, önceki konumdan hatırlamak getirir.|
|[Irowsetımpl](#irowsetimpl)|Oluşturucu. Doğrudan kullanıcı tarafından çağrılır değil.|
|[RefRows](#refrows)|Çağıran [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md). Doğrudan kullanıcı tarafından çağrılır değil.|
|[ReleaseRows](#releaserows)|Satır serbest bırakır.|
|[RestartPosition](#restartposition)|Sonraki getirme konumunu ilk konumuna yeniden konumlandırır; diğer bir deyişle, satır kümesi ilk kez yüklendiğinde konumuna oluşturuldu.|
|[SetDBStatus](#setdbstatus)|Belirtilen alan için durum bayraklarını ayarlar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_bCanFetchBack](#bcanfetchback)|Bir sağlayıcının geri getirme destekleyip desteklemediğini gösterir.|
|[m_bCanScrollBack](#bcanscrollback)|Bir sağlayıcı, imleç kaydırma geriye doğru sahip olup olmadığını gösterir.|
|[m_bReset](#breset)|Bir sağlayıcı İmleç konumuna sıfırladı olup olmadığını gösterir. Bu geriye doğru kaydırma veya geriye doğru içinde getirilirken özel anlama sahip [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|
|[m_iRowset](#irowset)|İmleç temsil eden satır kümesi için bir dizin.|
|[m_rgRowHandles](#rgrowhandles)|Satır işleyicilerini listesi.|

## <a name="remarks"></a>Açıklamalar

[IRowset](/previous-versions/windows/desktop/ms720986(v=vs.85)) temel satır kümesi arabirimidir.

## <a name="addrefrows"></a> Irowsetımpl::addrefrows

Var olan bir satır işleyici için bir başvuru sayısı ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(AddRefRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="createrow"></a> Irowsetımpl::createrow

Bir yardımcı yöntemi tarafından aranır [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) yeni ayrılacak `HROW`.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CreateRow(DBROWOFFSET lRowsOffset,
   DBCOUNTITEM& cRowsObtained,
   HROW* rgRows);
```

#### <a name="parameters"></a>Parametreler

*lRowsOffset*<br/>
Oluşturulan satır imleç konumu.

*cRowsObtained*<br/>
Oluşturulan satır sayısını gösteren kullanıcıya geri başvuru geçirildi.

*rgRows*<br/>
Bir dizi `HROW`s döndürülen yeni oluşturulan satır tutamaçları çağırana.

### <a name="remarks"></a>Açıklamalar

Satır varsa, bu yöntemin çağırdığı [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve döndürür. Aksi takdirde, yeni bir örneğini RowClass Şablon değişkeni ayırır ve bu gruba ekler [m_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md).

## <a name="getdata"></a> Irowsetımpl::GetData

Satır satır kümesinin kopyadan verileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pDstData);
```

#### <a name="parameters"></a>Parametreler

Bkz: ['yı](/previous-versions/windows/desktop/ms716988(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

Bazı parametreler karşılık *OLE DB Programcının Başvurusu* açıklanan farklı adlar parametrelerinin `IRowset::GetData`:

|OLE DB Şablon parametreleri|*OLE DB Programcının Başvurusu* parametreleri|
|--------------------------------|------------------------------------------------|
|*pDstData*|*pData*|

### <a name="remarks"></a>Açıklamalar

OLE DB veri dönüştürme DLL kullanarak veri dönüştürme da işler.

## <a name="getdbstatus"></a> Irowsetımpl::getdbstatus

Belirtilen alan için DBSTATUS durumu bayrakları döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual DBSTATUS GetDBStatus(RowClass* currentRow,
   ATLCOLUMNINFO* columnNames);
```

#### <a name="parameters"></a>Parametreler

*currentRow*<br/>
[in] Geçerli satır.

*columnNames*<br/>
[in] Sütun durumu istenmektedir.

### <a name="return-value"></a>Dönüş Değeri

[DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) sütunun bayrakları.

## <a name="getnextrows"></a> Irowsetımpl::GetNextRows

Satırlar sıralı olarak, önceki konumdan hatırlamak getirir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetNextRows )(HCHAPTER hReserved,
   DBROWOFFSET lRowsOffset,
   DBROWCOUNT cRows,
   DBCOUNTITEM* pcRowsObtained,
   HROW** prghRows);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowset::GetNextRows](/previous-versions/windows/desktop/ms709827(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="irowsetimpl"></a> Irowsetımpl::ırowsetımpl

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
IRowsetImpl();
```

### <a name="remarks"></a>Açıklamalar

Genellikle doğrudan bu yöntemi çağırmanız gerekmez.

## <a name="refrows"></a> Irowsetımpl::refrows

Çağıran [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) ve [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) artırın veya mevcut bir satırı işlemek için bir başvuru sayısı sürüm.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT RefRows(DBCOUNTITEM cRows,
   const HROWrghRows[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[],
   BOOL bAdd);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowset::AddRefRows](/previous-versions/windows/desktop/ms719619(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

## <a name="releaserows"></a> Irowsetımpl::releaserows

Satır serbest bırakır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(ReleaseRows )(DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWOPTIONS rgRowOptions[],
   DBREFCOUNT rgRefCounts[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowset::ReleaseRows](/previous-versions/windows/desktop/ms719771(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="restartposition"></a> Irowsetımpl::restartposition

Sonraki getirme konumunu ilk konumuna yeniden konumlandırır; diğer bir deyişle, satır kümesi ilk kez yüklendiğinde konumuna oluşturuldu.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(RestartPosition )(HCHAPTER /* hReserved */);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowset::RestartPosition](/previous-versions/windows/desktop/ms712877(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

### <a name="remarks"></a>Açıklamalar

Satır kümesi konumuna kadar tanımsızdır `GetNextRow` çağrılır. Çağırarak geriye dönük bir rowet taşıyabilirsiniz `RestartPosition` ve getirilirken veya geriye doğru kaydırma.

## <a name="setdbstatus"></a> Irowsetımpl::setdbstatus

Belirtilen alan için DBSTATUS durumu bayraklarını ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
virtual HRESULT SetDBStatus(DBSTATUS* statusFlags,
   RowClass* currentRow,
   ATLCOLUMNINFO* columnInfo);
```

#### <a name="parameters"></a>Parametreler

*statusFlags*<br/>
[DBSTATUS](/previous-versions/windows/desktop/ms722617(v=vs.85)) bayraklar için sütunu ayarlayın.

*currentRow*<br/>
Geçerli satır.

*ColumnInfo*<br/>
Sütun için durumu ayarlanıyor.

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT değerini.

### <a name="remarks"></a>Açıklamalar

Sağlayıcı DBSTATUS_S_ISNULL ve DBSTATUS_S_DEFAULT için özel işleme sağlamak için bu işlevi geçersiz kılar.

## <a name="bcanfetchback"></a> Irowsetımpl::m_bcanfetchback

Bir sağlayıcının geri getirme destekleyip desteklemediğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bCanFetchBack:1;
```

### <a name="remarks"></a>Açıklamalar

Bağlı `DBPROP_CANFETCHBACKWARDS` özelliğinde `DBPROPSET_ROWSET` grubu. Sağlayıcı desteklemelidir `DBPROP_CANFETCHBACKWARDS` için `m_bCanFetchBackwards` olmasını **true**.

## <a name="bcanscrollback"></a> Irowsetımpl::m_bcanscrollback

Bir sağlayıcı, imleç kaydırma geriye doğru sahip olup olmadığını gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned  m_bCanScrollBack:1;
```

### <a name="remarks"></a>Açıklamalar

Bağlı `DBPROP_CANSCROLLBACKWARDS` özelliğinde `DBPROPSET_ROWSET` grubu. Sağlayıcı desteklemelidir `DBPROP_CANSCROLLBACKWARDS` için `m_bCanFetchBackwards` olmasını **true**.

## <a name="breset"></a> Irowsetımpl::m_breset

İmleç konumu satır kümesinde tanımlı olup olmadığını belirlemek için kullanılan bir bit bayrağı.

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned m_bReset:1;
```

### <a name="remarks"></a>Açıklamalar

Tüketici çağırırsa [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) bir negatif `lOffset` veya *cRows* ve `m_bReset` true ise `GetNextRows` satır sonuna taşır. Varsa `m_bReset` yanlış tüketici uygunluk OLE DB belirtimi ile bir hata kodunu alır. `m_bReset` Bayrağı ayarlanmış **true** satır kümesi ilk oluşturulduğunda ve tüketici çağırdığında [Irowsetımpl::restartposition](../../data/oledb/irowsetimpl-restartposition.md). Ayarlayın **false** çağırdığınızda `GetNextRows`.

## <a name="irowset"></a> Irowsetımpl::m_irowset

İmleç temsil eden satır kümesi için bir dizin.

### <a name="syntax"></a>Sözdizimi

```cpp
DBROWOFFSET m_iRowset;
```

## <a name="rgrowhandles"></a> Irowsetımpl::m_rgrowhandles

Şu anda yanıt olarak sağlayıcısı tarafından bulunan satır işleyicilerini haritasını `GetNextRows`.

### <a name="syntax"></a>Sözdizimi

```cpp
MapClass m_rgRowHandles;
```

### <a name="remarks"></a>Açıklamalar

Satır işleyicilerini çağırarak kaldırılır `ReleaseRows`. Bkz: [Irowsetımpl genel bakış](../../data/oledb/irowsetimpl-class.md) tanımını *MapClass*.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[CSimpleRow Sınıfı](../../data/oledb/csimplerow-class.md)