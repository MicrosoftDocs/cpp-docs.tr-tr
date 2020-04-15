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
ms.openlocfilehash: ae4ceea53ec91cc3f9593dd3789fcf61e0702274
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376940"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl Sınıfı

OLE DB belirtiminde [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) arabiriminin OLE DB Şablonları uygulaması.

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
'den `IRowsetChangeImpl`türetilen bir sınıf.

*Depolama*<br/>
Kullanıcı kaydı.

*BaseInterface*<br/>
Arabirim için taban sınıf, `IRowsetChange`örneğin.

*Rowclass*<br/>
Satır tutamacı için depolama birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atldb.h

## <a name="members"></a>Üyeler

### <a name="interface-methods-used-with-irowsetchange"></a>Arayüz Yöntemleri (IRowsetChange ile birlikte kullanılır)

|||
|-|-|
|[Deleterows](#deleterows)|Satır kümesinden satırları siler.|
|[ınsertrow](#insertrow)|Satır kümesine bir satır ekler.|
|[Setdata](#setdata)|Veri değerlerini bir veya daha fazla sütunda ayarlar.|

### <a name="implementation-method-callback"></a>Uygulama Yöntemi (Geri Arama)

|||
|-|-|
|[FlushData](#flushdata)|Sağlayıcı tarafından depoya veri işlemek için geçersiz kılınmış.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, bir veri deposuna anında yazma işlemişlemlerini sorumludur. "Hemen", son kullanıcı (tüketiciyi kullanan kişi) herhangi bir değişiklik yaptığında, bu değişikliklerin hemen veri deposuna iletildiği (ve geri alınamayacağı) anlamına gelir.

`IRowsetChangeImpl`varolan satırlarda sütun `IRowsetChange` değerlerinin güncelleştirilmesini, satırları silmesini ve yeni satırlar eklenmesini sağlayan OLE DB arabirimini uygular.

OLE DB Şablonları uygulaması tüm temel`SetData` `InsertRow`yöntemleri `DeleteRows`destekler ( , , ve).

> [!IMPORTANT]
> Sağlayıcınızı uygulamaya çalışmadan önce aşağıdaki belgeleri okumanız önerilir:

- [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB Programcı Referans* Bölüm 6

- Ayrıca, [Sınıfın UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneğinde nasıl kullanıldığını da görün. `RUpdateRowset`

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>IRowsetChangeImpl::DeleteRows

Satır kümesinden satırları siler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

Bkz. [IRowsetChange::DOLE](/previous-versions/windows/desktop/ms724362(v=vs.85)) *DB Programcı Referansında*eleler.

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>IRowsetChangeImpl::InsertRow

Satır kümesinde yeni bir satır oluşturur ve başharfe başlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Parametreler

Bkz. [IRowsetChange::OLE](/previous-versions/windows/desktop/ms716921(v=vs.85)) *DB Programcısının Referansında*Ekleme Satırını .

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>IRowsetChangeImpl::SetData

Veri değerlerini bir veya daha fazla sütunda ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parametreler

Bkz. [IRowsetChange::SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) *OLE DB Programcı'nın Referans*.

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>IRowsetChangeImpl::FlushData

Sağlayıcı tarafından depoya veri işlemek için geçersiz kılınmış.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Parametreler

*hRowToFlush*<br/>
[içinde] Veriler için satırları işle. Bu satırın türü `IRowsetImpl` sınıfın *RowClass* şablon uyşundan (varsayılan`CSimpleRow` olarak) belirlenir.

*hAccessorToFlush*<br/>
[içinde] Bağlayıcı bilgiler ve tür bilgileri `PROVIDER_MAP` içeren erişimciye işle (bkz. [IAccessorImpl).](../../data/oledb/iaccessorimpl-class.md)

### <a name="return-value"></a>Dönüş Değeri

Standart bir HRESULT.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Sağlayıcı Şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablon Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
