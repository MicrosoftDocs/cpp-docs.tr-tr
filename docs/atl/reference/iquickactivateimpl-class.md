---
title: IQuickActivateImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl
- ATLCTL/ATL::IQuickActivateImpl::GetContentExtent
- ATLCTL/ATL::IQuickActivateImpl::QuickActivate
- ATLCTL/ATL::IQuickActivateImpl::SetContentExtent
helpviewer_keywords:
- activating ATL controls
- controls [ATL], activating
- IQuickActivateImpl class
- IQuickActivate ATL implementation
ms.assetid: aa80c056-1041-494e-b21d-2acca7dc27ea
ms.openlocfilehash: 7e1984249caf66e2986341f9c9f7a939d7039125
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329549"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl Sınıfı

Bu sınıf, kapsayıcıların denetim başlatmasını tek bir çağrıda birleştirir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IQuickActivateImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Çalışan bir denetim için geçerli ekran boyutunu alır.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Yüklenen denetimlerin hızlı bir şekilde başlatılmasını gerçekleştirir.|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Kapsayıcının kendisine ne kadar görüntü alanı atadığının denetimini bildirir.|

## <a name="remarks"></a>Açıklamalar

[IQuickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) arabirimi, tek bir çağrıda başlatmayı birleştirerek denetimleri yüklerken kapsayıcıların gecikmeleri önlemelerine yardımcı olur. Yöntem, `QuickActivate` kapsayıcının bir işaretçiyi denetimin ihtiyacı olan tüm arabirimlere işaretçiler tutan [bir QACONTAINER](/windows/win32/api/ocidl/ns-ocidl-qacontainer) yapısına geçirmesini sağlar. İade de, denetim, işaretçileri kapsayıcı tarafından kullanılan kendi arabirimlerine tutan bir [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) yapısına geri geçirir. Sınıf `IQuickActivateImpl` varsayılan bir `IQuickActivate` uygulama sağlar `IUnknown` ve hata ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a>IQuickActivateImpl::GetContentExtent

Çalışan bir denetim için geçerli ekran boyutunu alır.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Boyutu kontrolün tam bir render içindir ve HIMETRIC birimlerinde belirtilir.

Bkz. [IQuickActivate::Windows](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) SDK'da GetContentExtent.

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a>IQuickActivateImpl::QuickActivate

Yüklenen denetimlerin hızlı bir şekilde başlatılmasını gerçekleştirir.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Açıklamalar

Yapı, denetim in gerektirdiği arabirimlere işaretçiler ve bazı ortam özelliklerinin değerlerini içerir. Döndükten sonra, denetim kapsayıcı nın gerektirdiği kendi arabirimlerine işaretçiler ve ek durum bilgileri içeren bir [QACONTROL](/windows/win32/api/ocidl/ns-ocidl-qacontrol) yapısına geçer.

Bkz. [IQuickActivate::QuickActivate](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) Windows SDK içinde.

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a>IQuickActivateImpl::SetContentExtent

Kapsayıcının kendisine ne kadar görüntü alanı atadığının denetimini bildirir.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Boyut HIMETRIC birimlerinde belirtilir.

Bkz. [IQuickActivate::SetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
