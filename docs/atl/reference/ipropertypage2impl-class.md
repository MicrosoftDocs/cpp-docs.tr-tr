---
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
ms.openlocfilehash: 5ec6cb2f4fc6931a1bec429068b558bf7ac1906e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69495603"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl sınıfı

Bu sınıf, `IUnknown` [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)'nin varsayılan uygulamasını uygular ve devralır.

> [!IMPORTANT]
>  Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
Sınıfınız, öğesinden `IPropertyPage2Impl`türetilir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[IPropertyPage2Impl:: EditProperty](#editproperty)|Özellik sayfası etkinleştirildiğinde, odağı hangi Özellik denetiminin alacağını belirtir. ATL uygulama E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) arabirimi, `EditProperty` yöntemini ekleyerek [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) 'i genişletir. Bu yöntem, bir istemcinin bir özellik sayfası nesnesi içinde belirli bir özelliği seçmesine olanak sağlar.

Sınıf `IPropertyPage2Impl` , için `IPropertyPage2::EditProperty`yalnızca E_NOTIMPL döndürür. Ancak, [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) 'nin varsayılan uygulamasını devralır ve hata ayıklama yapılarında `IUnknown` döküm cihazına bilgi göndererek uygular.

Bir özellik sayfası oluşturduğunuzda, sınıfınız genellikle öğesinden `IPropertyPageImpl`türetilir. ' Nin `IPropertyPage2`ek desteğini sağlamak için, sınıf tanımınızı değiştirin ve `EditProperty` yöntemi geçersiz kılın.

**Ilgili makaleler** ATL [öğreticisi](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl. h

##  <a name="editproperty"></a>IPropertyPage2Impl:: EditProperty

Özellik sayfası etkinleştirildiğinde, odağı hangi Özellik denetiminin alacağını belirtir.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Windows SDK için bkz. [IPropertyPage2:: EditProperty](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) .

## <a name="see-also"></a>Ayrıca bkz.

[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
