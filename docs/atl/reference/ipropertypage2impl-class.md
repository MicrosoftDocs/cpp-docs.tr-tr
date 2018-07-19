---
title: Ipropertypage2ımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl
- ATLCTL/ATL::IPropertyPage2Impl::EditProperty
dev_langs:
- C++
helpviewer_keywords:
- property pages
- IPropertyPage2 ATL implementation
- IPropertyPage2Impl class
ms.assetid: e89fbe90-203a-47f0-a5de-23616697e1ce
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bf5cf9438d2fcecb434802dc99aaa5c692ba108f
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882903"
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
 *T*  
 Sınıfınız, türetilen `IPropertyPage2Impl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Özellik sayfasını etkinleştirildiğinde özelliğini denetleyen odak alacağını belirtir. ATL uygulamasını E_NOTIMPL döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) arabirimini genişletir [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) ekleyerek `EditProperty` yöntemi. Bu yöntem, özellik sayfa nesnesi içinde belirli bir özelliği seçmek bir istemci sağlar.  
  
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
 E_NOTIMPL döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Iperpropertybrowsingımpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Ispecifypropertypagesımpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
