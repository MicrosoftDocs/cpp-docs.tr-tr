---
title: ISupportErrorInfoImpl Sınıfı
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
ms.openlocfilehash: 4c60b58ba697f00b146077a2cdecd727fe2cac02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326375"
---
# <a name="isupporterrorinfoimpl-class"></a>ISupportErrorInfoImpl Sınıfı

Bu [sınıf, iSupportErrorInfo Arabiriminin](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) varsayılan uygulamasını sağlar ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Parametreler

*piid*<br/>
[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)destekleyen bir arabirimin IID için bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[ISupportErrorInfoImpl::InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Tanımlanan `riid` arabirimin [iErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) arabirimini destekleyip desteklemediğini gösterir.|

## <a name="remarks"></a>Açıklamalar

[ISupportErrorInfo Arabirimi,](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) hata bilgilerinin istemciye döndürülmesini sağlar. Kullanan `IErrorInfo` nesneler uygulanmalıdır. `ISupportErrorInfo`

Sınıf `ISupportErrorInfoImpl` varsayılan bir `ISupportErrorInfo` uygulama sağlar ve yalnızca tek bir arabirim bir nesne üzerinde hata lar oluşturduğunda kullanılabilir. Örneğin:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a>ISupportErrorInfoImpl::InterfaceSupportsErrorInfo

Tanımlanan `riid` arabirimin [iErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) arabirimini destekleyip desteklemediğini gösterir.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Açıklamalar

Bkz. [ISupportErrorInfo::InterfaceSupportsErrorInfo](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
