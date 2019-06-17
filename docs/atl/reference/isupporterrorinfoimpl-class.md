---
title: Isupporterrorınfoımpl sınıfı
ms.date: 06/13/2019
f1_keywords:
- ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl
- ATLCOM/ATL::ISupportErrorInfoImpl::InterfaceSupportsErrorInfo
helpviewer_keywords:
- ISupportErrorInfo ATL implementation
- ISupportErrorInfoImpl class
- error information, ATL
ms.assetid: e33a4b11-a123-41cf-bcea-7b19743902af
ms.openlocfilehash: 650d90c9ec98754e11586f63e0871b70ebbe34f3
ms.sourcegitcommit: e79188287189b76b34eb7e8fb1bfe646bdb586bc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/14/2019
ms.locfileid: "67141698"
---
# <a name="isupporterrorinfoimpl-class"></a>Isupporterrorınfoımpl sınıfı

Bu sınıfın bir varsayılan uygulamayı sağlar [ISupportErrorInfo arabirimi](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

> [!IMPORTANT]
> Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Parametreler

*piid*<br/>
Laboratuvardaki destekleyen bir arabirim işaretçisi [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo).

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekler [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) arabirimi.|

## <a name="remarks"></a>Açıklamalar

[ISupportErrorInfo arabirimi](/windows/desktop/api/oaidl/nn-oaidl-isupporterrorinfo) hata bilgilerini istemciye döndürdüğünü sağlar. Nesneleri kullanan `IErrorInfo` uygulamalıdır `ISupportErrorInfo`.

Sınıf `ISupportErrorInfoImpl` bir varsayılan uygulamayı sağlar `ISupportErrorInfo` ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir. Örneğin:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="interfacesupportserrorinfo"></a>  ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Arabirim tarafından tanımlanan olup olmadığını gösteren `riid` destekler [IErrorInfo](/windows/desktop/api/oaidl/nn-oaidl-ierrorinfo) arabirimi.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Açıklamalar

Bkz: [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/desktop/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
