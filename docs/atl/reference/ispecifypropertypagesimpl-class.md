---
description: 'Şu konuda daha fazla bilgi edinin: ıdiifypropertypagesimpl sınıfı'
title: Idiifyıpropertypagesimpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
ms.openlocfilehash: 528fafa0473a4aa803e1c1d17a24b2d27584c33a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158055"
---
# <a name="ispecifypropertypagesimpl-class"></a>Idiifyıpropertypagesimpl sınıfı

Bu sınıf `IUnknown` , [ıdiifıpropertypages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) arabiriminin varsayılan bir uygulamasını uygular ve sunar.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl
   : public ISpecifyPropertyPages
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `ISpecifyPropertyPagesImpl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Idiifypropertypagesimpl:: GetPages](#getpages)|Bir UUID değerlerinin sayılan dizisini doldurur. Her UUID, nesnenin özellik sayfasında görüntülenebilen Özellik sayfalarından birinin CLSID 'sine karşılık gelir.|

## <a name="remarks"></a>Açıklamalar

[Idiifıpropertypages](/windows/win32/api/ocidl/nn-ocidl-ispecifypropertypages) arabirimi, bir istemcinin bir nesne tarafından desteklenen özellik sayfaları için CLSID listesi almasına izin verir. Sınıfı, `ISpecifyPropertyPagesImpl` Bu arabirimin varsayılan bir uygulamasını sağlar ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

> [!NOTE]
> `ISpecifyPropertyPages`Nesneniz özellik sayfalarını desteklemiyorsa arabirimi kullanıma sunmayın.

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`ISpecifyPropertyPages`

`ISpecifyPropertyPagesImpl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ispecifypropertypagesimplgetpages"></a><a name="getpages"></a> Idiifypropertypagesimpl:: GetPages

[Cauuid](/windows/win32/api/ocidl/ns-ocidl-cauuid) yapısındaki diziyi, nesnenin özellik sayfasında görüntülenebilen Özellik sayfaları için CLSID 'ler ile doldurur.

```
STDMETHOD(GetPages)(CAUUID* pPages);
```

### <a name="remarks"></a>Açıklamalar

ATL her bir CLSID 'yi almak için nesnenin özellik eşlemesini kullanır.

Windows SDK [ıdiifypropertypages:: GetPages](/windows/win32/api/ocidl/nf-ocidl-ispecifypropertypages-getpages) bölümüne bakın.

## <a name="see-also"></a>Ayrıca bkz.

[IPropertyPageImpl sınıfı](../../atl/reference/ipropertypageimpl-class.md)<br/>
[Iperpropertybrowsingimpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
