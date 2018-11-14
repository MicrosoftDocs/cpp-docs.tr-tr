---
title: IRowsetChangeImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- ATL::IRowsetChangeImpl
- IRowsetChangeImpl
- ATL.IRowsetChangeImpl
- ATL.IRowsetChangeImpl.DeleteRows
- ATL::IRowsetChangeImpl::DeleteRows
- IRowsetChangeImpl.DeleteRows
- DeleteRows
- IRowsetChangeImpl::DeleteRows
- ATL.IRowsetChangeImpl.InsertRow
- InsertRow
- IRowsetChangeImpl.InsertRow
- ATL::IRowsetChangeImpl::InsertRow
- IRowsetChangeImpl::InsertRow
- SetData
- IRowsetChangeImpl::SetData
- ATL.IRowsetChangeImpl.SetData
- IRowsetChangeImpl.SetData
- ATL::IRowsetChangeImpl::SetData
- IRowsetChangeImpl::FlushData
- IRowsetChangeImpl.FlushData
- FlushData
helpviewer_keywords:
- providers, updatable
- updatable providers, immediate update
- IRowsetChangeImpl class
- DeleteRows method
- InsertRow method
- SetData method
- FlushData method
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
ms.openlocfilehash: dacf9de0835108ae946e7523472a0adf12e7e222
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556731"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl Sınıfı

OLE DB Şablonları uygulamasının [IRowsetChange](https://docs.microsoft.com/previous-versions/windows/desktop/ms715790(v=vs.85)) arabirimi OLE DB belirtimi.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   class T,
   class Storage,
   class BaseInterface = IRowsetChange,
   class RowClass = CSimpleRow,
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>>
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden türetilen bir sınıf `IRowsetChangeImpl`.

*Depolama*<br/>
Kullanıcı kayıt.

*BaseInterface*<br/>
Temel sınıf arabirim için gibi `IRowsetChange`.

*RowClass*<br/>
Satır tanıtıcısı depolama birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm olan satır işleyicilerini depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)

|||
|-|-|
|[DeleteRows](#deleterows)|Satır satır kümesinden siler.|
|[Insertrow](#insertrow)|Bir satır satır kümesine ekler.|
|[SetData](#setdata)|Bir veya daha fazla sütun veri değerlerini ayarlar.|

### <a name="implementation-method-callback"></a>Uygulama yöntemi (geri çağırma)

|||
|-|-|
|[FlushData](#flushdata)|Veri, depolama alanına kaydetmeye sağlayıcısı tarafından Overidden.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, bir veri deposuna anında yazma işlemleri sorumludur. "Mevcut" anlamına gelir (bir tüketici kullanarak kişi) son kullanıcıya herhangi bir değişiklik yaptığında, bu değişiklikleri hemen veri aktarılır depolayın (ve geri alınamaz).

`IRowsetChangeImpl` OLE DB uygulayan `IRowsetChange` var olan satır, satırları silme ve yeni satır ekleyerek sütunların değerlerinin güncelleştirme sağlayan arabirim.

OLE DB Şablonları uygulama temel tüm yöntemleri destekler (`SetData`, `InsertRow`, ve `DeleteRows`).

> [!IMPORTANT]
>  Sağlayıcınız uygulamak denemeden önce aşağıdaki belgeleri okumanız önemle tavsiye edilir:

- [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)

- Bölüm 6 *OLE DB Programcının Başvurusu*

- Ayrıca bkz: nasıl `RUpdateRowset` sınıfı kullanılan [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örnek.

## <a name="deleterows"></a> IRowsetChangeImpl::DeleteRows

Satır satır kümesinden siler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetChange::DeleteRows](https://docs.microsoft.com/previous-versions/windows/desktop/ms724362(v=vs.85)(v%3dvs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="insertrow"></a> IRowsetChangeImpl::ınsertrow

Oluşturur ve yeni bir satır kümesinde başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetChange::InsertRow](https://docs.microsoft.com/previous-versions/windows/desktop/ms716921(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="setdata"></a> IRowsetChangeImpl::SetData

Bir veya daha fazla sütun veri değerlerini ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parametreler

Bkz: [IRowsetChange::SetData](https://docs.microsoft.com/previous-versions/windows/desktop/ms721232(v=vs.85)) içinde *OLE DB Programcının Başvurusu*.

## <a name="flushdata"></a> IRowsetChangeImpl::flushdata

Veri, depolama alanına kaydetmeye sağlayıcısı tarafından Overidden.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Parametreler

*hRowToFlush*<br/>
[in] Veri satırları için işleyin. Bu satırın Türü alanından belirlenir *RowClass* şablon bağımsız değişkeni `IRowsetImpl` sınıfı (`CSimpleRow` varsayılan olarak).

*hAccessorToFlush*<br/>
[in] Bağlama bilgileri ve tür bilgilerini içeren erişimci tanıtıcı kendi `PROVIDER_MAP` (bkz [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)