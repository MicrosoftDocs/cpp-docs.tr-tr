---
title: IPropertyPage2Impl Sınıfı
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
ms.openlocfilehash: d112a2411a9debbf2eb77e6b851f4500e8d32ab8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329586"
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl Sınıfı

Bu sınıf `IUnknown` [iPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)varsayılan uygulama uygular ve devralır.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<class T>
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Sınıfınızdan `IPropertyPage2Impl`türetilmiştir.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[IPropertyPage2Impl::EditProperty](#editproperty)|Özellik sayfası etkinleştirildiğinde hangi özellik denetiminin odağı alacağını belirtir. ATL uygulaması E_NOTIMPL döndürür.|

## <a name="remarks"></a>Açıklamalar

[IPropertyPage2](/windows/win32/api/ocidl/nn-ocidl-ipropertypage2) arabirimi `EditProperty` yöntemi ekleyerek [IPropertyPage](/windows/win32/api/ocidl/nn-ocidl-ipropertypage) genişletir. Bu yöntem, istemcinin bir özellik sayfası nesnesinde belirli bir özelliği seçmesine olanak tanır.

Sınıf `IPropertyPage2Impl` sadece E_NOTIMPL `IPropertyPage2::EditProperty`için döndürür. Ancak, [iPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) varsayılan uygulama devralır ve `IUnknown` hata ayıklama oluşturur damlama aygıtına bilgi göndererek uygular.

Bir özellik sayfası oluşturduğunuzda, sınıfınız `IPropertyPageImpl`genellikle .'den türetilir. Ek destek `IPropertyPage2`sağlamak için sınıf tanımınızı değiştirin `EditProperty` ve yöntemi geçersiz kılın.

**İlgili Makaleler** [ATL Tutorial](../../atl/active-template-library-atl-tutorial.md), [ATL Projesi Oluşturma](../../atl/reference/creating-an-atl-project.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IPropertyPage`

[IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)

`IPropertyPage2Impl`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlctl.h

## <a name="ipropertypage2impleditproperty"></a><a name="editproperty"></a>IPropertyPage2Impl::EditProperty

Özellik sayfası etkinleştirildiğinde hangi özellik denetiminin odağı alacağını belirtir.

```
HRESULT EditProperty(DISPID dispID);
```

### <a name="return-value"></a>Dönüş Değeri

E_NOTIMPL döndürür.

### <a name="remarks"></a>Açıklamalar

Bkz. [IPropertyPage2::Windows](/windows/win32/api/ocidl/nf-ocidl-ipropertypage2-editproperty) SDK'daki Emlak'ı editProperty.

## <a name="see-also"></a>Ayrıca bkz.

[IPerPropertyBrowsingImpl Sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)<br/>
[ISpecifyPropertyPagesImpl Sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
