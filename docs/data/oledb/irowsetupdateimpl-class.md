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
ms.openlocfilehash: 6347a42b9065239f768c6b50c430946393358df1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370743"
---
# <a name="irowsetupdateimpl-class"></a>IRowsetUpdateImpl Sınıfı

[IRowsetUpdate](/previous-versions/windows/desktop/ms714401(v=vs.85)) arabiriminin OLE DB Şablonları uygulaması.

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

*T*<br/>
'den `IRowsetUpdateImpl`türetilen bir sınıf.

*Depolama*<br/>
Kullanıcı kaydı.

*UpdateArray*<br/>
Rowset'i güncelleştirmek için önbelleğe alınmış verileri içeren bir dizi.

*Rowclass*<br/>
Depolama `HROW`birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods-used-with-irowsetchange"></a>Arayüz Yöntemleri (IRowsetChange ile birlikte kullanılır)

|||
|-|-|
|[Setdata](#setdata)|Veri değerlerini bir veya daha fazla sütunda ayarlar.|

### <a name="interface-methods-used-with-irowsetupdate"></a>Arayüz Yöntemleri (IRowsetUpdate ile birlikte kullanılır)

|||
|-|-|
|[Orijinal Verileri Alın](#getoriginaldata)|Bekleyen değişiklikleri yoksayarak, en son veri kaynağına aktarılan veya veri kaynağından elde edilen verileri alır.|
|[GetPendingRows](#getpendingrows)|Bekleyen değişikliklerle birlikte satırların listesini döndürür.|
|[GetRowStatus](#getrowstatus)|Belirtilen satırların durumunu verir.|
|[Geri al](#undo)|Son getirme veya güncelleştirmeden bu yana satırda yapılan değişiklikleri geri alır.|
|[Güncelleştir](#update)|Son getirme veya güncelleştirmeden bu yana satırda yapılan değişiklikleri iletir.|

### <a name="implementation-methods-callback"></a>Uygulama Yöntemleri (Geri Arama)

|||
|-|-|
|[IsUpdateAllowed](#isupdateallowed)|Güncelleştirmelere izin vermeden önce güvenlik, bütünlük ve benzeri denetimleri denetlemek için kullanılır.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[m_mapCachedData](#mapcacheddata)|Ertelenmiş işlemin özgün verilerini içerir.|

## <a name="remarks"></a>Açıklamalar

İlk okumalı ve [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))için belgeleri anlamak , orada açıklanan her şey de burada geçerlidir çünkü. Ayrıca, veri ayarı konusunda *OLE DB Programcı Başvurusu'nun* 6.

`IRowsetUpdateImpl`tüketicilerin veri kaynağına `IRowsetUpdate` yapılan `IRowsetChange` değişikliklerin iletimini geciktirmesini ve iletimden önce değişiklikleri geri almalarını sağlayan OLE DB arabirimini uygular.

> [!IMPORTANT]
> Sağlayıcınızı uygulamaya çalışmadan önce aşağıdaki belgeleri okumanız önerilir:

- [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB Programcı Referans* Bölüm 6

- Ayrıca, [Sınıfın UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneğinde nasıl kullanıldığını da görün `RUpdateRowset`

## <a name="irowsetupdateimplsetdata"></a><a name="setdata"></a>IRowsetUpdateImpl::SetData

Veri değerlerini bir veya daha fazla sütunda ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parametreler

Bkz. [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) *OLE DB Programcı'nın Referans*.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [IRowsetChangeImpl geçersiz kılar::SetData](../../data/oledb/irowsetchangeimpl-setdata.md) yöntemi, işlemin hemen veya ertelenmiş işleme izin vermek için orijinal verilerin önbelleğe alma içerir.

## <a name="irowsetupdateimplgetoriginaldata"></a><a name="getoriginaldata"></a>IRowsetUpdateImpl::GetOriginalData

Bekleyen değişiklikleri yoksayarak, en son veri kaynağına aktarılan veya veri kaynağından elde edilen verileri alır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetOriginalData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pData);
```

#### <a name="parameters"></a>Parametreler

Bkz. [IRowsetUpdate::GetOriginalData](/previous-versions/windows/desktop/ms709947(v=vs.85)) in the *OLE DB Programcı'nın Referansı*.

## <a name="irowsetupdateimplgetpendingrows"></a><a name="getpendingrows"></a>IRowsetUpdateImpl::GetPendingRows

Bekleyen değişikliklerle birlikte satırların listesini döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetPendingRows )(HCHAPTER /* hReserved */,
   DBPENDINGSTATUS dwRowStatus,
   DBCOUNTITEM* pcPendingRows,
   HROW** prgPendingRows,
   DBPENDINGSTATUS** prgPendingStatus);
```

#### <a name="parameters"></a>Parametreler

*hAyrılmış*<br/>
[içinde] IRowsetUpdate *hChapter* parametre karşılık [gelir::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)).

Diğer parametreler için, [Bkz. IRowsetUpdate::GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) in the *OLE DB Programcı'nın Referansı.*

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için, [IRowsetUpdate bakın:: GetPendingRows](/previous-versions/windows/desktop/ms719626(v=vs.85)) *OLE DB Programcı's Referans*.

## <a name="irowsetupdateimplgetrowstatus"></a><a name="getrowstatus"></a>IRowsetUpdateImpl::GetRowStatus

Belirtilen satırların durumunu verir.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (GetRowStatus )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBPENDINGSTATUS rgPendingStatus[]);
```

#### <a name="parameters"></a>Parametreler

*hAyrılmış*<br/>
[içinde] IRowsetUpdate *hChapter* parametre karşılık [gelir::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)).

Diğer parametreler için, [bkz: IRowsetUpdate::GetRowStatus](/previous-versions/windows/desktop/ms724377(v=vs.85)) *OLE DB Programcı's Reference*.

## <a name="irowsetupdateimplundo"></a><a name="undo"></a>IRowsetUpdateImpl::Geri

Son getirme veya güncelleştirmeden bu yana satırda yapılan değişiklikleri geri alır.

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

*hAyrılmış*<br/>
[içinde] IRowsetUpdate *hChapter* parametre karşılık [gelir::Geri .](/previous-versions/windows/desktop/ms719655(v=vs.85))

*pcRowsUndone*<br/>
[çıkış] IRowsetUpdate *pcRows* parametre karşılık [gelir::Geri .](/previous-versions/windows/desktop/ms719655(v=vs.85))

*prgRowsUndone*<br/>
[içinde] IRowsetUpdate *prgRows* parametre karşılık [gelir::Geri .](/previous-versions/windows/desktop/ms719655(v=vs.85))

Diğer parametreler için, [bkz: IRowsetUpdate::OLE](/previous-versions/windows/desktop/ms719655(v=vs.85)) *DB Programcı'nın Referansını*Geri Al.

## <a name="irowsetupdateimplupdate"></a><a name="update"></a>IRowsetUpdateImpl::Güncelleme

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

*hAyrılmış*<br/>
[içinde] IRowsetUpdate *hChapter* parametre karşılık [gelir::Güncelleme](/previous-versions/windows/desktop/ms719709(v=vs.85)).

Diğer parametreler için, [Bkz. IRowsetUpdate::OLE](/previous-versions/windows/desktop/ms719709(v=vs.85)) *DB Programcısının Referansında*güncelleştirme.

### <a name="remarks"></a>Açıklamalar

Değişiklikler [IRowsetChangeImpl::FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)çağırarak iletilir. TüketicicRowset aramak [gerekir::Değişikliklerin](../../data/oledb/crowset-update.md) etkili olması için güncelleştirme. *PrgRowstatus'u,* *OLE DB Programcısının Referansında* [Satır Durumlarında](/previous-versions/windows/desktop/ms722752(v=vs.85)) açıklandığı gibi uygun bir değere ayarlayın.

## <a name="irowsetupdateimplisupdateallowed"></a><a name="isupdateallowed"></a>IRowsetUpdateImpl::IsUpdateAllowed

Güncelleştirmeden önce güvenlik, bütünlük ve benzeri denetler için bu yöntemi geçersiz kılın.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT IsUpdateAllowed(DBPENDINGSTATUS /* [in] */ /* status */,
   HROW /* [in] */ /* hRowUpdate */,
   DBROWSTATUS* /* [out] */ /* pRowStatus */);
```

#### <a name="parameters"></a>Parametreler

*Durum*<br/>
[içinde] Satırlarda bekleyen işlemlerin durumu.

*hRowUpdate*<br/>
[içinde] Kullanıcının güncelleştirmek istediği satırları işleme.

*pRowStatus*<br/>
[çıkış] Durum kullanıcıya döndürülür.

### <a name="remarks"></a>Açıklamalar

Bir güncelleştirmeye izin verilmesi gerektiğini belirlerseniz, S_OK döndürür; aksi takdirde E_FAIL döndürür. Bir güncelleştirmeye izin verirseniz, `DBROWSTATUS` [iRowsetUpdateImpl'de](../../data/oledb/irowsetupdateimpl-update.md) de ayarlamanız gerekir::Uygun bir [satır durumuna](/previous-versions/windows/desktop/ms722752(v=vs.85))güncelleme.

## <a name="irowsetupdateimplm_mapcacheddata"></a><a name="mapcacheddata"></a>IRowsetUpdateImpl::m_mapCachedData

Ertelenmiş işlemin özgün verilerini içeren bir harita.

### <a name="syntax"></a>Sözdizimi

```cpp
CAtlMap<
   HROW hRow,
   Storage* pData
>
m_mapCachedData;
```

#### <a name="parameters"></a>Parametreler

*Hrow*<br/>
Veriler için satırları işle.

*Pdata*<br/>
Önbelleğe alınacak verilere işaretçi. Veriler tür *Depolama* (kullanıcı kayıt sınıfı) olduğunu. [IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md) *Sınıfındadepolama* şablonu bağımsız değişkenine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablon Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)<br/>
[Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)
