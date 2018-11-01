---
title: Iquickactivateımpl sınıfı
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
ms.openlocfilehash: 5dacdd4986580ca665d2199568584faafa8d6699
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50560816"
---
# <a name="iquickactivateimpl-class"></a>Iquickactivateımpl sınıfı

Bu sınıf, kapsayıcılar denetimi başlatma tek bir çağrı halinde birleştirir.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class ATL_NO_VTABLE IQuickActivateImpl : public IQuickActivate
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IQuickActivateImpl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IQuickActivateImpl::GetContentExtent](#getcontentextent)|Çalışan bir denetim için geçerli görüntü boyutunu alır.|
|[IQuickActivateImpl::QuickActivate](#quickactivate)|Hızlı Başlatma yüklenen denetimleri gerçekleştirir.|
|[IQuickActivateImpl::SetContentExtent](#setcontentextent)|Kapsayıcı atanmış ne kadar görüntüleme alanı denetim bildirir.|

## <a name="remarks"></a>Açıklamalar

[IQuickActivate](/windows/desktop/api/ocidl/nn-ocidl-iquickactivate) arabirimi denetimleri, tek bir çağrı başlatma birleştirerek yüklenirken gecikmeleri önlemek kapsayıcıları yardımcı olur. `QuickActivate` Yöntemi sağlayan bir işaretçiyi kapsayıcıya bir [QACONTAINER](/windows/desktop/api/ocidl/ns-ocidl-tagqacontainer) tüm arabirimleri denetimi işaretçileri tutan yapı gerekiyor. Getirisi, denetim için bir işaretçi geri geçer bir [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) kapsayıcı tarafından kullanılan kendi arabirimlerine işaretçileri tutan yapı. Sınıf `IQuickActivateImpl` bir varsayılan uygulamayı sağlar `IQuickActivate` ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IQuickActivate`

`IQuickActivateImpl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="getcontentextent"></a>  IQuickActivateImpl::GetContentExtent

Çalışan bir denetim için geçerli görüntü boyutunu alır.

```
STDMETHOD(GetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Denetimin tam işleme için büyüklüğünde ve HIMETRIC birimleri cinsinden belirtilir.

Bkz: [IQuickActivate::GetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-getcontentextent) Windows SDK içinde.

##  <a name="quickactivate"></a>  IQuickActivateImpl::QuickActivate

Hızlı Başlatma yüklenen denetimleri gerçekleştirir.

```
STDMETHOD(QuickActivate)(
    QACONTAINER* pQACont,
    QACONTROL* pQACtrl);
```

### <a name="remarks"></a>Açıklamalar

Yapısı, Denetim ve ortam bazı özelliklerin değerlerini tarafından gerekli arabirim işaretçileri içerir. İade sırasında denetim için bir işaretçi geçirir. bir [QACONTROL](/windows/desktop/api/ocidl/ns-ocidl-tagqacontrol) kapsayıcı gerektiren kendi arabirimleri ve ek durum bilgilerini işaretçileri içeren yapısı.

Bkz: [IQuickActivate::QuickActivate](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-quickactivate) Windows SDK içinde.

##  <a name="setcontentextent"></a>  IQuickActivateImpl::SetContentExtent

Kapsayıcı atanmış ne kadar görüntüleme alanı denetim bildirir.

```
STDMETHOD(SetContentExtent)(LPSIZEL pSize);
```

### <a name="remarks"></a>Açıklamalar

Boyutunu HIMETRIC birimleri cinsinden belirtilir.

Bkz: [IQuickActivate::SetContentExtent](/windows/desktop/api/ocidl/nf-ocidl-iquickactivate-setcontentextent) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca Bkz.

[CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
