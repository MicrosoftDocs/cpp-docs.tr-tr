---
title: IAccessorImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IAccessorImpl
- ATL.IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::IAccessorImpl
- IAccessorImpl::IAccessorImpl
- IAccessorImpl.IAccessorImpl
- ATL::IAccessorImpl::AddRefAccessor
- AddRefAccessor
- IAccessorImpl::AddRefAccessor
- IAccessorImpl.AddRefAccessor
- ATL.IAccessorImpl.AddRefAccessor
- IAccessorImpl::CreateAccessor
- CreateAccessor
- ATL::IAccessorImpl::CreateAccessor
- IAccessorImpl.CreateAccessor
- ATL.IAccessorImpl.CreateAccessor
- IAccessorImpl.GetBindings
- ATL::IAccessorImpl::GetBindings
- IAccessorImpl::GetBindings
- GetBindings
- ATL.IAccessorImpl.GetBindings
- ReleaseAccessor
- IAccessorImpl::ReleaseAccessor
- ATL.IAccessorImpl.ReleaseAccessor
- ATL::IAccessorImpl::ReleaseAccessor
- IAccessorImpl.ReleaseAccessor
helpviewer_keywords:
- IAccessorImpl class
- IAccessorImpl class, constructor
- IAccessorImpl constructor
- AddRefAccessor method
- CreateAccessor method
- GetBindings method
- ReleaseAccessor method
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
ms.openlocfilehash: 356278b316912bdb81f1c43bbf2034f00ec3d785
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845620"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl Sınıfı

[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Satır kümesi veya komut nesne sınıfınız.

*BindType*<br/>
Bağlama bilgileri için depolama birimi. Varsayılan, `ATLBINDINGS` yapısıdır (bkz. Atldb. h).

*BindingVector*<br/>
Sütun bilgileri için depolama birimi. Varsayılan değer, anahtar öğesinin bir HACCESSOR değeri olduğu ve value öğesinin bir yapı işaretçisi olduğu [CAtlMap](../../atl/reference/catlmap-class.md) 'dir `BindType` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

| Ad | Açıklama |
|-|-|
|[IAccessorImpl](#iaccessorimpl)|Oluşturucu.|

### <a name="interface-methods"></a>Arabirim yöntemleri

| Ad | Açıklama |
|-|-|
|[AddRefAccessor](#addrefaccessor)|Varolan bir erişimciye bir başvuru sayısı ekler.|
|[CreateAccessor](#createaccessor)|Bir bağlama kümesinden erişimci oluşturur.|
|[GetBindings](#getbindings)|Bir erişimcinin bağlamalarını döndürür.|
|[ReleaseAccessor](#releaseaccessor)|Bir erişimci yayınlar.|

## <a name="remarks"></a>Açıklamalar

Bu, satır kümelerinde ve komutlarda zorunludur. OLE DB, sağlayıcıların bir [Dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) yapıları dizisine bir etiket olan BIR HACCESSOR uygulaması olmasını gerektirir. Tarafından sunulan Herişimcileri `IAccessorImpl` yapıların adresleridir `BindType` . Varsayılan olarak, `BindType` `ATLBINDINGS` `IAccessorImpl` uygulamasının şablon tanımı olarak tanımlanmıştır. `BindType``IAccessorImpl`, dizi içindeki öğe sayısını `DBBINDING` ve başvuru sayısını ve erişimci bayraklarını izlemek için tarafından kullanılan bir mekanizma sağlar.

## <a name="iaccessorimpliaccessorimpl"></a><a name="iaccessorimpl"></a> IAccessorImpl:: IAccessorImpl

Oluşturucu.

### <a name="syntax"></a>Syntax

```cpp
IAccessorImpl();
```

## <a name="iaccessorimpladdrefaccessor"></a><a name="addrefaccessor"></a> IAccessorImpl:: AddRefAccessor

Varolan bir erişimciye bir başvuru sayısı ekler.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: AddRefAccessor](/previous-versions/windows/desktop/ms714978(v=vs.85)) öğesine bakın.

## <a name="iaccessorimplcreateaccessor"></a><a name="createaccessor"></a> IAccessorImpl:: CreateAccessor

Bir bağlama kümesinden erişimci oluşturur.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(CreateAccessor)(DBACCESSORFLAGS dwAccessorFlags,
   DBCOUNTITEM cBindings,
   const DBBINDING rgBindings[],
   DBLENGTH cbRowSize,
   HACCESSOR* phAccessor,
   DBBINDSTATUS rgStatus[]);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: CreateAccessor](/previous-versions/windows/desktop/ms720969(v=vs.85)) öğesine bakın.

## <a name="iaccessorimplgetbindings"></a><a name="getbindings"></a> IAccessorImpl:: GetBindings

Bir erişimcideki tüketiciden temel sütun bağlamalarını döndürür.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: GetBindings](/previous-versions/windows/desktop/ms721253(v=vs.85)) öğesine bakın.

## <a name="iaccessorimplreleaseaccessor"></a><a name="releaseaccessor"></a> IAccessorImpl:: ReleaseAccessor

Bir erişimci yayınlar.

### <a name="syntax"></a>Söz dizimi

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: ReleaseAccessor](/previous-versions/windows/desktop/ms719717(v=vs.85)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB sağlayıcı şablonu mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
