---
description: 'Daha fazla bilgi edinin: IQuickActivateImpl sınıfı'
title: IQuickActivateImpl sınıfı
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
ms.openlocfilehash: 1e9dc2891351512ec3ebe54ebe6711ee9d4a3fa0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158133"
---
# <a name="iquickactivateimpl-class"></a>IQuickActivateImpl sınıfı

Bu sınıf, kapsayıcıların denetim başlatmasını tek bir çağrıda birleştirir.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IQuickActivateImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IQuickActivateImpl:: GetContentExtent](#getcontentextent)|Çalışan bir denetim için geçerli görüntüleme boyutunu alır.|
|[IQuickActivateImpl:: QuickActivate](#quickactivate)|Yüklenmekte olan denetimlerin hızlı başlatılmasını gerçekleştirir.|
|[IQuickActivateImpl:: SetContentExtent](#setcontentextent)|Kapsayıcının kendisine ne kadar alan gösterdiğine ilişkin denetimi bilgilendirir.|

## <a name="remarks"></a>Açıklamalar

[IQuickActivate](/windows/win32/api/ocidl/nn-ocidl-iquickactivate) arabirimi, tek bir çağrıda başlatmayı birleştirerek bir denetimin yüklenmesi sırasında kapsayıcıların gecikmelerden kaçınmanıza yardımcı olur. `QuickActivate`Yöntemi, kapsayıcının denetim ihtiyacı olan tüm arabirimlerin işaretçilerini tutan bir [Qacontainer](/windows/win32/api/ocidl/ns-ocidl-qacontainer) yapısına işaretçi geçmesine izin verir. Dönüş sırasında denetim, kapsayıcı tarafından kullanılan kendi arabirimine işaretçiler tutan bir [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) yapısına işaretçi geri geçirir. Sınıfı, `IQuickActivateImpl` `IQuickActivate` `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek varsayılan bir uygulamasını sağlar ve uygular.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="iquickactivateimplgetcontentextent"></a><a name="getcontentextent"></a> IQuickActivateImpl:: GetContentExtent

Çalışan bir denetim için geçerli görüntüleme boyutunu alır.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Boyut, denetimin tam olarak işlenmesi içindir ve HIMETRIK birimlerde belirtilir.

Windows SDK [IQuickActivate:: GetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) bölümüne bakın.

## <a name="iquickactivateimplquickactivate"></a><a name="quickactivate"></a> IQuickActivateImpl:: QuickActivate

Yüklenmekte olan denetimlerin hızlı başlatılmasını gerçekleştirir.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Açıklamalar

Yapı, denetim için gereken arabirimlerin ve bazı çevresel özelliklerin değerlerinin işaretçilerini içerir. Geri dönüş sırasında denetim, kapsayıcının gerektirdiği kendi arayüzlerinin işaretçilerini ve ek durum bilgilerini içeren bir [qacontrol](/windows/win32/api/ocidl/ns-ocidl-qacontrol) yapısına işaretçi geçirir.

Windows SDK [IQuickActivate:: QuickActivate](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-quickactivate) ' a bakın.

## <a name="iquickactivateimplsetcontentextent"></a><a name="setcontentextent"></a> IQuickActivateImpl:: SetContentExtent

Kapsayıcının kendisine ne kadar alan gösterdiğine ilişkin denetimi bilgilendirir.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Boyut, HIMETRIK birimlerde belirtilir.

Windows SDK [IQuickActivate:: SetContentExtent](/windows/win32/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
