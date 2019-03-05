---
title: Ipropertypage2ımpl sınıfı
ms.date: 11/04/2016
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
ms.openlocfilehash: bf76182242f7b76e3a2c18f85b72674e88afa737
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287511"
---
# <a name="ipropertypage2impl-class"></a>Ipropertypage2ımpl sınıfı

Bu sınıfın uyguladığı `IUnknown` ve varsayılan uygulamasını devralan [Ipropertypageımpl](../../atl/reference/ipropertypageimpl-class.md).

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, türetilen `IPropertyPage2Impl`.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Özellik sayfasını etkinleştirildiğinde özelliğini denetleyen odak alacağını belirtir. ATL uygulamasını E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage2](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage2) arabirimini genişletir [IPropertyPage](/windows/desktop/api/ocidl/nn-ocidl-ipropertypage) ekleyerek `EditProperty` yöntemi. Bu yöntem, özellik sayfa nesnesi içinde belirli bir özelliği seçmek bir istemci sağlar.

Sınıf `IPropertyPage2Impl` E_NOTIMPL için basitçe döndürür `IPropertyPage2::EditProperty`. Bununla birlikte, varsayılan uygulamasını devralır [Ipropertypageımpl](../../atl/reference/ipropertypageimpl-class.md) ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.

Özellik sayfası oluşturduğunuzda, kendi sınıfınızı genellikle türetilir `IPropertyPageImpl`. Ek destek sağlamak üzere `IPropertyPage2`, sınıf tanımına değiştirmek ve geçersiz kılma `EditProperty` yöntemi.

**İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

[Ipropertypageımpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlctl.h

##  <a name="editproperty"></a>  IPropertyPage2Impl::EditProperty

Özellik sayfasını etkinleştirildiğinde özelliğini denetleyen odak alacağını belirtir.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Dönüş Değeri

Returns E_NOTIMPL.

### <a name="remarks"></a>Açıklamalar

Bkz: [IPropertyPage2::EditProperty](/windows/desktop/api/ocidl/nf-ocidl-ipropertypage2-editproperty) Windows SDK içinde.

## <a name="see-also"></a>Ayrıca bkz.

[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
