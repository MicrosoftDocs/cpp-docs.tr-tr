---
title: IRowsetUpdateImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IRowsetUpdateImpl
- ATL.IRowsetUpdateImpl
- ATL::IRowsetUpdateImpl
- IRowsetUpdateImpl::SetData
- IRowsetUpdateImpl.SetData
- ATL::IRowsetUpdateImpl::SetData
- ATL.IRowsetUpdateImpl.SetData
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetPendingRows
- GetPendingRows
- IRowsetUpdateImpl.GetPendingRows
- ATL::IRowsetUpdateImpl::GetPendingRows
- ATL.IRowsetUpdateImpl.GetPendingRows
- ATL.IRowsetUpdateImpl.GetRowStatus
- IRowsetUpdateImpl::GetRowStatus
- IRowsetUpdateImpl.GetRowStatus
- ATL::IRowsetUpdateImpl::GetRowStatus
- ATL.IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl::Undo
- IRowsetUpdateImpl.Undo
- ATL::IRowsetUpdateImpl::Update
- IRowsetUpdateImpl::Update
- IRowsetUpdateImpl.Update
- ATL.IRowsetUpdateImpl.Update
- IRowsetUpdateImpl::IsUpdateAllowed
- IRowsetUpdateImpl.IsUpdateAllowed
- IsUpdateAllowed
- IRowsetUpdateImpl.m_mapCachedData
- IRowsetUpdateImpl::m_mapCachedData
- m_mapCachedData
helpviewer_keywords:
- providers, updatable
- IRowsetUpdateImpl class
- updatable providers, deferred update
- SetData method
- GetOriginalData method
- GetPendingRows method
- GetRowStatus method
- Undo method
- Update method
- IsUpdateAllowed method
- m_mapCachedData
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
ms.openlocfilehash: 79d85e7d1c849bcaa7c2aa1b3f6d9d50a20d1b2a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210320"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl Sınıfı

[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) arabiriminin OLE DB Şablonları uygulamasıdır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   class T,
   class Storage,
   class UpdateArray = CAtlArray<Storage>,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>
>

class IRowsetUpdateImpl : public IRowsetChangeImpl<
   T,
   Storage,
   IRowsetUpdate,
   RowClass,
   MapClass>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
`IRowsetUpdateImpl`türetilen bir sınıf.

*Depolama*<br/>
Kullanıcı kaydı.

*UpdateArray*<br/>
Satır kümesini güncelleştirmek için önbelleğe alınmış verileri içeren bir dizi.

*RowClass*<br/>
`HROW`için depolama birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)

|||
|-|-|
|[SetData](#setdata)|Veri değerlerini bir veya daha fazla sütunda ayarlar.|

### <a name="interface-methods-used-with-irowsetupdate"></a>Arabirim yöntemleri (IRowsetUpdate ile kullanılır)

|||
|-|-|
|[GetOriginalData](#getoriginaldata)|Bekleyen değişiklikleri yoksayarak veri kaynağından en son iletilen veya alınan verileri alır.|
|[GetPendingRows](#getpendingrows)|Bekleyen değişiklikleri olan satırların bir listesini döndürür.|
|[GetRowStatus](#getrowstatus)|Belirtilen satırların durumunu döndürür.|
|[Komutunu](#undo)|Son getirme veya güncelleştirmeden sonra satırdaki değişiklikleri geri alır.|
|[Güncelleştirme](#update)|Son getirme veya güncelleştirmeden bu yana satırda yapılan değişiklikleri iletir.|

### <a name="implementation-methods-callback"></a>Uygulama yöntemleri (geri çağırma)

|||
|-|-|
|[Isupdateallowed](#isupdateallowed)|Güncelleştirmelere izin vermeden önce güvenlik, bütünlük ve benzerlerini denetlemek için kullanılır.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|Ertelenmiş işlem için özgün verileri içerir.|

## <a name="remarks"></a>Açıklamalar

Burada açıklanan her şey burada da geçerli olduğundan, [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))belgelerini okumanız ve anlamanız gerekir. Ayrıca, ayar verilerinde *OLE DB Programcı başvurusunun* Bölüm 6 ' yı da okumalısınız.

`IRowsetUpdateImpl`, OLE DB `IRowsetUpdate` arabirimini uygular ve bu da tüketicilerin veri kaynağına `IRowsetChange` yapılan değişikliklerin aktarımını geciktirmesini ve iletimden önce değişiklikleri geri almasını sağlar.

> [!IMPORTANT]
>  Sağlayıcınızı uygulamayı denemeden önce aşağıdaki belgeleri okumanız kesinlikle önerilir:

- [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB Programcı başvurusunun* 6. bölümü

- Ayrıca, `RUpdateRowset` sınıfının [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneğinde nasıl kullanıldığını görün

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowsetUpdateImpl:: SetData

Veri değerlerini bir veya daha fazla sütunda ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, [IRowsetChangeImpl:: SetData](../../data/oledb/irowsetchangeimpl-setdata.md) metodunu geçersiz kılar, ancak işlemin anında veya ertelenmiş işlemesini sağlamak için özgün verilerin önbelleğe alınmasını içerir.

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>IRowsetUpdateImpl:: GetOriginalData

Bekleyen değişiklikleri yoksayarak veri kaynağından en son iletilen veya alınan verileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetUpdate:: GetOriginalData](/previous-versions/windows/desktop/ms709947(v=vs.85)) .

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowsetUpdateImpl:: GetPendingRows

Bekleyen değişiklikleri olan satırların bir listesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,
   DBPENDINGSTATUS dwRowStatus,
   DBCOUNTITEM* pcPendingRows,
   HROW** prgPendingRows,
   DBPENDINGSTATUS** prgPendingStatus);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetUpdate:: GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85))Içindeki *hbölüm* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda* [IRowsetUpdate:: GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için *OLE DB Programcı başvurusunda* [IRowsetUpdate:: GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) bölümüne bakın.

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>IRowsetUpdateImpl:: GetRowStatus

Belirtilen satırların durumunu döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetUpdate:: GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85))Içindeki *hbölüm* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda*bkz. [IRowsetUpdate:: GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)) .

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowsetUpdateImpl:: Undo

Son getirme veya güncelleştirmeden sonra satırdaki değişiklikleri geri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (Undo )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[ ],
   DBCOUNTITEM* pcRowsUndone,
   HROW** prgRowsUndone,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))Içindeki *hbölüm* parametresine karşılık gelir.

*Pcrowsunbitti*<br/>
dışı [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))Içindeki *pcRows* parametresine karşılık gelir.

*prgRowsUndone*<br/>
'ndaki [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85))Içindeki *prbüyüdükçe* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda*bkz. [IRowsetUpdate:: Undo](/previous-versions/windows/desktop/ms719655(v=vs.85)) .

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowsetUpdateImpl:: Update

Son getirme veya güncelleştirmeden bu yana satırda yapılan değişiklikleri iletir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (Update )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBCOUNTITEM* pcRows,
   HROW** prgRows,
   DBROWSTATUS** prgRowStatus);
```

#### <a name="parameters"></a>Parametreler

*Hayrılmış*<br/>
'ndaki [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85))Içindeki *hbölüm* parametresine karşılık gelir.

Diğer parametreler için *OLE DB Programcı başvurusunda* [IRowsetUpdate:: Update](/previous-versions/windows/desktop/ms719709(v=vs.85)) bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Değişiklikler [IRowsetChangeImpl:: FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)çağırarak iletilir. Değişikliklerin etkili olması için tüketiciden [CRowset:: Update](../../data/oledb/crowset-update.md) çağrısı yapılmalıdır. *PrgRowstatus* *programcı başvurusunda satır ole db* [durumları](/previous-versions/windows/desktop/ms722752(v=vs.85)) bölümünde açıklandığı gibi uygun bir değere ayarlayın.

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowsetUpdateImpl:: ısupdateallowed

Güncelleştirmelerden önce güvenlik, bütünlük ve benzerlerini denetlemek için bu yöntemi geçersiz kılın.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
'ndaki Satırlarda bekleyen işlemlerin durumu.

*hRowUpdate*<br/>
'ndaki Kullanıcının güncelleştirmek istediği satırlara yönelik tanıtıcı.

*pRowStatus*<br/>
dışı Kullanıcıya döndürülen durum.

### <a name="remarks"></a>Açıklamalar

Bir güncelleştirmenin izin verileceğini belirlerseniz, S_OK döndürür; Aksi takdirde E_FAIL döndürür. Bir güncelleştirmeye izin verirseniz, [IRowsetUpdateImpl:: Update](../../data/oledb/irowsetupdateimpl-update.md) içindeki `DBROWSTATUS` uygun bir [satır durumuna](/previous-versions/windows/desktop/ms722752(v=vs.85))ayarlamanız gerekir.

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowsetUpdateImpl:: m_mapCachedData

Ertelenmiş işlem için özgün verileri içeren bir harita.

### <a name="syntax"></a>Sözdizimi

```cpp
CAtlMap<
   HROW hRow,
   Storage* pData
>
m_mapCachedData;
```

#### <a name="parameters"></a>Parametreler

*hRow*<br/>
Verilerin satırları için tanıtıcı.

*pData*<br/>
Önbelleğe alınacak verilere yönelik bir işaretçi. Veri *depolama* türüdür (Kullanıcı kayıt sınıfı). [IRowsetUpdateImpl sınıfında](../../data/oledb/irowsetupdateimpl-class.md) *depolama* şablonu bağımsız değişkenine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)
