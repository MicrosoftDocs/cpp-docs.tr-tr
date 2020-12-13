---
description: 'Daha fazla bilgi edinin: IPropertyPage2Impl Class'
title: IPropertyPage2Impl sınıfı
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
ms.openlocfilehash: 8311746b03c4c680a040c0873ee58f936044dd9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139288"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl sınıfı

Bu sınıf `IUnknown` , [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)'nin varsayılan uygulamasını uygular ve devralır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınız, öğesinden türetilir `IPropertyPage2Impl` .

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPage2Impl:: EditProperty](#editproperty)|Özellik sayfası etkinleştirildiğinde, odağı hangi Özellik denetiminin alacağını belirtir. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) arabirimi, yöntemini ekleyerek [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 'i genişletir `EditProperty` . Bu yöntem, bir istemcinin bir özellik sayfası nesnesi içinde belirli bir özelliği seçmesine olanak sağlar.

Sınıfı `IPropertyPage2Impl` yalnızca E_NOTIMPL döndürür `IPropertyPage2::EditProperty` . Ancak, [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 'nin varsayılan uygulamasını devralır ve `IUnknown` hata ayıklama yapılarında döküm cihazına bilgi göndererek uygular.

Bir özellik sayfası oluşturduğunuzda, sınıfınız genellikle öğesinden türetilir `IPropertyPageImpl` . ' Nin ek desteğini sağlamak için `IPropertyPage2` , sınıf tanımınızı değiştirin ve yöntemi geçersiz kılın `EditProperty` .

**Ilgili makaleler** [ATL öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a> IPropertyPage2Impl:: EditProperty

Özellik sayfası etkinleştirildiğinde, odağı hangi Özellik denetiminin alacağını belirtir.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IPropertyPage2:: EditProperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) .

## <a name="see-also"></a>Ayrıca bkz.

[Iperpropertybrowsingimpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[Idiifyıpropertypagesimpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
