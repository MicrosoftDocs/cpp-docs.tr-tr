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
ms.openlocfilehash: 6b9830ac2b6f1eacedd1b59184292f2148087093
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80210875"
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl Sınıfı

[IAccessor](/previous-versions/windows/desktop/ms719672(v=vs.85)) arabiriminin bir uygulamasını sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class T,
   class BindType = ATLBINDINGS,
   class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>
```

### <a name="parameters"></a>Parametreler

*Şı*<br/>
Satır kümesi veya komut nesne sınıfınız.

*BindType*<br/>
Bağlama bilgileri için depolama birimi. Varsayılan değer `ATLBINDINGS` yapısıdır (bkz. Atldb. h).

*BindingVector*<br/>
Sütun bilgileri için depolama birimi. Varsayılan değer, anahtar öğesinin bir HACCESSOR değeri olduğu ve value öğesinin bir `BindType` yapısına yönelik bir işaretçi olduğu [CAtlMap](../../atl/reference/catlmap-class.md) 'dir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Atldb. h

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[IAccessorImpl](#iaccessorimpl)|Oluşturucu.|

### <a name="interface-methods"></a>Arabirim yöntemleri

|||
|-|-|
|[AddRefAccessor](#addrefaccessor)|Varolan bir erişimciye bir başvuru sayısı ekler.|
|[CreateAccessor](#createaccessor)|Bir bağlama kümesinden erişimci oluşturur.|
|[GetBindings](#getbindings)|Bir erişimcinin bağlamalarını döndürür.|
|[ReleaseAccessor](#releaseaccessor)|Bir erişimci yayınlar.|

## <a name="remarks"></a>Açıklamalar

Bu, satır kümelerinde ve komutlarda zorunludur. OLE DB, sağlayıcıların bir [Dbbinding](/previous-versions/windows/desktop/ms716845(v=vs.85)) yapıları dizisine bir etiket olan BIR HACCESSOR uygulaması olmasını gerektirir. `IAccessorImpl` tarafından sunulan Herişimcileri `BindType` yapıların adresleridir. Varsayılan olarak `BindType`, `IAccessorImpl`şablon tanımında bir `ATLBINDINGS` olarak tanımlanır. `BindType`, `DBBINDING` dizisindeki öğelerin sayısını ve bir başvuru sayısı ve erişimci bayraklarını izlemek için `IAccessorImpl` tarafından kullanılan bir mekanizma sağlar.

## <a name="iaccessorimpliaccessorimpl"></a><a name="iaccessorimpl"></a>IAccessorImpl:: IAccessorImpl

Oluşturucu.

### <a name="syntax"></a>Sözdizimi

```cpp
IAccessorImpl();
```

## <a name="iaccessorimpladdrefaccessor"></a><a name="addrefaccessor"></a>IAccessorImpl:: AddRefAccessor

Varolan bir erişimciye bir başvuru sayısı ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(AddRefAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: AddRefAccessor](/previous-versions/windows/desktop/ms714978(v=vs.85)) öğesine bakın.

## <a name="iaccessorimplcreateaccessor"></a><a name="createaccessor"></a>IAccessorImpl:: CreateAccessor

Bir bağlama kümesinden erişimci oluşturur.

### <a name="syntax"></a>Sözdizimi

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

## <a name="iaccessorimplgetbindings"></a><a name="getbindings"></a>IAccessorImpl:: GetBindings

Bir erişimcideki tüketiciden temel sütun bağlamalarını döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(GetBindings)(HACCESSOR hAccessor,
   DBACCESSORFLAGS* pdwAccessorFlags,
   DBCOUNTITEM* pcBindings,
   DBBINDING** prgBindings);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: GetBindings](/previous-versions/windows/desktop/ms721253(v=vs.85)) öğesine bakın.

## <a name="iaccessorimplreleaseaccessor"></a><a name="releaseaccessor"></a>IAccessorImpl:: ReleaseAccessor

Bir erişimci yayınlar.

### <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(ReleaseAccessor)(HACCESSOR hAccessor,
   DBREFCOUNT* pcRefCount);
```

#### <a name="parameters"></a>Parametreler

*OLE DB Programcı başvurusunda* [IAccessor:: ReleaseAccessor](/previous-versions/windows/desktop/ms719717(v=vs.85)) öğesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB sağlayıcı şablonları](../../data/oledb/ole-db-provider-templates-cpp.md)<br/>
[OLE DB Sağlayıcı Şablonu Mimarisi](../../data/oledb/ole-db-provider-template-architecture.md)
