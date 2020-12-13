---
description: 'Şu konuda daha fazla bilgi edinin: ıupporterrorınfoımpl sınıfı'
title: Iupporterrorınfoımpl sınıfı
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
ms.openlocfilehash: 182f55f7d7c288e4c8679c3e8cc1df7bb5cd79bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139145"
---
# <a name="isupporterrorinfoimpl-class"></a>Iupporterrorınfoımpl sınıfı

Bu sınıf, [ıupporterrorınfo arabiriminin](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) varsayılan bir uygulamasını sağlar ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```cpp
template<const IID* piid>
class ATL_NO_VTABLE ISupportErrorInfoImpl
   : public ISupportErrorInfo
```

### <a name="parameters"></a>Parametreler

*piıd*<br/>
[IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)destekleyen BIR arabirimin IID 'sine yönelik bir işaretçi.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Iupporterrorınfoımpl:: InterfaceSupportsErrorInfo](#interfacesupportserrorinfo)|Tarafından tanımlanan arabirimin `riid` [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) arabirimini destekleyip desteklemediğini gösterir.|

## <a name="remarks"></a>Açıklamalar

[Iupporterrorınfo arabirimi](/windows/win32/api/oaidl/nn-oaidl-isupporterrorinfo) istemciye hata bilgilerini geri dönebilmesini sağlar. Kullanan nesneler `IErrorInfo` uygulamalıdır `ISupportErrorInfo` .

Sınıfı `ISupportErrorInfoImpl` varsayılan bir uygulaması sağlar `ISupportErrorInfo` ve yalnızca tek bir arabirim bir nesne üzerinde hata oluşturduğunda kullanılabilir. Örneğin:

[!code-cpp[NVC_ATL_COM#48](../../atl/codesnippet/cpp/isupporterrorinfoimpl-class_1.h)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISupportErrorInfo`

`ISupportErrorInfoImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="isupporterrorinfoimplinterfacesupportserrorinfo"></a><a name="interfacesupportserrorinfo"></a> Iupporterrorınfoımpl:: InterfaceSupportsErrorInfo

Tarafından tanımlanan arabirimin `riid` [IErrorInfo](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo) arabirimini destekleyip desteklemediğini gösterir.

```cpp
STDMETHOD(InterfaceSupportsErrorInfo)(REFIID riid);
```

### <a name="remarks"></a>Açıklamalar

Windows SDK [ıupporterrorınfo:: InterfaceSupportsErrorInfo](/windows/win32/api/oaidl/nf-oaidl-isupporterrorinfo-interfacesupportserrorinfo) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
