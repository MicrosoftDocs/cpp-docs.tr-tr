---
title: IPointerInactiveImpl Sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl
- ATLCTL/ATL::IPointerInactiveImpl::GetActivationPolicy
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveMouseMove
- ATLCTL/ATL::IPointerInactiveImpl::OnInactiveSetCursor
helpviewer_keywords:
- IPointerInactive ATL implementation
- inactive objects
- IPointerInactiveImpl class
ms.assetid: e1fe9ea6-d38a-4527-9112-eb344771e0b7
ms.openlocfilehash: 229b8c6803aa7b3817cb3d95474bde0502829f8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326446"
---
# <a name="ipointerinactiveimpl-class"></a>IPointerInactiveImpl Sınıfı

Bu sınıf `IUnknown` uygular ve [IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) arabirim yöntemleri.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPointerInactiveImpl
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPointerInactiveImpl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPointerInactiveImpl::GetActivationPolicy](#getactivationpolicy)|Nesne için geçerli etkinleştirme ilkesini alır. ATL uygulaması E_NOTIMPL döndürür.|
|[IPointerInactiveImpl::OnInactiveMouseMove](#oninactivemousemove)|Fare işaretçisinin üzerinde hareket ettiğini ve nesnenin fare olaylarını ateşleyebiliri belirten nesneyi belirtir. ATL uygulaması E_NOTIMPL döndürür.|
|[IPointerInactiveImpl::OnInactiveSetCursor](#oninactivesetcursor)|Etkin olmayan nesne için fare işaretçisini ayarlar. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

Etkin olmayan nesne, yalnızca yüklenen veya çalışan bir nesnedir. Etkin bir nesnenin aksine, etkin olmayan bir nesne Windows fare ve klavye iletileri alamaz. Böylece, etkin olmayan nesneler daha az kaynak kullanır ve genellikle daha verimlidir.

[IPointerInactive](/windows/win32/api/ocidl/nn-ocidl-ipointerinactive) arabirimi, bir nesnenin etkin olmayan bir şekilde kalırken fare etkileşiminin en az düzeyini desteklemesine olanak tanır. Bu işlevsellik özellikle denetimler için yararlıdır.

Sınıf `IPointerInactiveImpl` yöntemleri `IPointerInactive` sadece E_NOTIMPL döndürerek uygular. Ancak, hata `IUnknown` ayıklama oluştururda dökümü aygıtına bilgi göndererek uygular.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPointerInactive`

`IPointerInactiveImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ipointerinactiveimplgetactivationpolicy"></a><a name="getactivationpolicy"></a>IPointerInactiveImpl::GetActivationPolicy

Nesne için geçerli etkinleştirme ilkesini alır.

```
HRESULT GetActivationPolicy(DWORD* pdwPolicy);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPointerInactive::Windows](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-getactivationpolicy) SDK'da GetActivationPolicy.

## <a name="ipointerinactiveimploninactivemousemove"></a><a name="oninactivemousemove"></a>IPointerInactiveImpl::OnInactiveMouseMove

Fare işaretçisinin üzerinde hareket ettiğini ve nesnenin fare olaylarını ateşleyebiliri belirten nesneyi belirtir.

```
HRESULT OnInactiveMouseMove(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPointerInactive::OnInactiveMouseMove](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivemousemove) Windows SDK içinde.

## <a name="ipointerinactiveimploninactivesetcursor"></a><a name="oninactivesetcursor"></a>IPointerInactiveImpl::OnInactiveSetCursor

Etkin olmayan nesne için fare işaretçisini ayarlar.

```
HRESULT OnInactiveSetCursor(
    LPCRECT pRectBounds,
    long x,
    long y,
    DWORD dwMouseMsg,
    BOOL fSetAlways);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPointerInactive::Windows SDK'da OnInactiveSetCursor.](/windows/win32/api/ocidl/nf-ocidl-ipointerinactive-oninactivesetcursor)

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
