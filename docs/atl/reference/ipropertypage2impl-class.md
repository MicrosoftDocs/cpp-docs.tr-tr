---
title: "IPropertyPage2Impl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17773bdd07d4ae25b33bc104d46d607b5069f78d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ipropertypage2impl-class"></a>IPropertyPage2Impl sınıfı
Bu sınıf uygulayan **IUnknown** ve varsayılan uygulaması devralır [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md).  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class IPropertyPage2Impl : public IPropertyPageImpl<T>
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPropertyPage2Impl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPropertyPage2Impl::EditProperty](#editproperty)|Özellik sayfası etkinleştirildiğinde özelliğini denetleyen odak alacağını belirtir. ATL uygulamasını döndürür **E_NOTIMPL**.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) arabirimi genişletiyor [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) ekleyerek `EditProperty` yöntemi. Bu yöntem, belirli bir özelliği bir özellik sayfası nesnesinde seçmek bir istemci sağlar.  
  
 Sınıf `IPropertyPage2Impl` yalnızca döndürür **E_NOTIMPL** için **IPropertyPage2::EditProperty**. Ancak, varsayılan uygulaması devralır [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md) ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 Özellik sayfası oluşturduğunuzda, sınıfınız genellikle türetildiği `IPropertyPageImpl`. Ek desteği sağlamak için **IPropertyPage2**, sınıf tanımını değiştirin ve geçersiz kılma `EditProperty` yöntemi.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPropertyPage`  
  
 [IPropertyPageImpl](../../atl/reference/ipropertypageimpl-class.md)  
  
 `IPropertyPage2Impl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="editproperty"></a>IPropertyPage2Impl::EditProperty  
 Özellik sayfası etkinleştirildiğinde özelliğini denetleyen odak alacağını belirtir.  
  
```
HRESULT EditProperty(DISPID dispID);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage2::EditProperty](http://msdn.microsoft.com/library/windows/desktop/ms690353) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPerPropertyBrowsingImpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
