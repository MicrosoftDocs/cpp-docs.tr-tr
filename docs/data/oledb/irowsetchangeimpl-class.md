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
ms.openlocfilehash: b069cd08814855a0528806ac6d19ed8f5beb6f37
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210463"
---
# <a name="irowsetchangeimpl-class"></a>IRowsetChangeImpl Sınıfı

OLE DB belirtiminde [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) arabiriminin OLE DB Şablonları uygulamasıdır.

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

*Şı*<br/>
`IRowsetChangeImpl`türetilen bir sınıf.

*Depolama*<br/>
Kullanıcı kaydı.

*BaseInterface*<br/>
`IRowsetChange`gibi arabirim için temel sınıf.

*RowClass*<br/>
Satır tanıtıcısı için depolama birimi.

*MapClass*<br/>
Sağlayıcı tarafından tutulan tüm satır tutamaçları için depolama birimi.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="interface-methods-used-with-irowsetchange"></a>Arabirim yöntemleri (IRowsetChange ile kullanılır)

|||
|-|-|
|[DeleteRows](#deleterows)|Satır kümesinden satır siler.|
|[InsertRow](#insertrow)|Satır kümesine bir satır ekler.|
|[SetData](#setdata)|Veri değerlerini bir veya daha fazla sütunda ayarlar.|

### <a name="implementation-method-callback"></a>Uygulama yöntemi (geri çağırma)

|||
|-|-|
|[FlushData](#flushdata)|Veri deposuna verileri yürütmek için sağlayıcı tarafından geçersiz kılındı.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, bir veri deposuna anında yazma işlemlerinden sorumludur. "Hemen", Son Kullanıcı (tüketiciyi kullanan kişi) herhangi bir değişiklik yaptığında, bu değişikliklerin hemen veri deposuna aktarılmasıdır (ve geri alınamaz).

`IRowsetChangeImpl`, mevcut satırlardaki sütunların değerlerinin güncelleştirilmesini sağlayan, satırları silen ve yeni satırlar eklenen OLE DB `IRowsetChange` arabirimini uygular.

OLE DB şablonları uygulamasında tüm temel Yöntemler (`SetData`, `InsertRow`ve `DeleteRows`) desteklenir.

> [!IMPORTANT]
>  Sağlayıcınızı uygulamayı denemeden önce aşağıdaki belgeleri okumanız kesinlikle önerilir:

- [Güncelleştirilebilir Sağlayıcı Oluşturma](../../data/oledb/creating-an-updatable-provider.md)

- *OLE DB Programcı başvurusunun* 6. bölümü

- Ayrıca, `RUpdateRowset` sınıfının [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) örneğinde nasıl kullanıldığını görün.

## <a name="irowsetchangeimpldeleterows"></a><a name="deleterows"></a>IRowsetChangeImpl::D eleteRows

Satır kümesinden satır siler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (DeleteRows )(HCHAPTER /* hReserved */,
   DBCOUNTITEM cRows,
   const HROW rghRows[],
   DBROWSTATUS rgRowStatus[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [ırowsetchange::D eleterows](/previous-versions/windows/desktop/ms724362(v=vs.85)) .

## <a name="irowsetchangeimplinsertrow"></a><a name="insertrow"></a>IRowsetChangeImpl:: InsertRow

Satır kümesinde yeni bir satır oluşturur ve başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (InsertRow )(HCHAPTER /* hReserved */,
   HACCESSOR hAccessor,
   void* pData,
   HROW* phRow);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetChange:: InsertRow](/previous-versions/windows/desktop/ms716921(v=vs.85)) .

## <a name="irowsetchangeimplsetdata"></a><a name="setdata"></a>IRowsetChangeImpl:: SetData

Veri değerlerini bir veya daha fazla sütunda ayarlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD (SetData )(HROW hRow,
   HACCESSOR hAccessor,
   void* pSrcData);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda*bkz. [IRowsetChange:: SetData](/previous-versions/windows/desktop/ms721232(v=vs.85)) .

## <a name="irowsetchangeimplflushdata"></a><a name="flushdata"></a>IRowsetChangeImpl:: FlushData

Veri deposuna verileri yürütmek için sağlayıcı tarafından geçersiz kılındı.

### <a name="syntax"></a>Sözdizimi

```cpp
HRESULT FlushData(HROW hRowToFlush,
   HACCESSOR hAccessorToFlush);
```

#### <a name="parameters"></a>Parametreler

*hRowToFlush*<br/>
'ndaki Verilerin satırları için tanıtıcı. Bu satırın türü `IRowsetImpl` sınıfın *RowClass* şablonu bağımsız değişkeninden belirlenir (varsayılan olarak`CSimpleRow`).

*hAccessorToFlush*<br/>
'ndaki `PROVIDER_MAP` bağlama bilgilerini ve tür bilgilerini içeren erişimci için tanıtıcı (bkz. [IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)).

### <a name="return-value"></a>Dönüş Değeri

Standart HRESULT.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
