---
title: ISpecifyPropertyPagesImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl
- ATLCOM/ATL::ISpecifyPropertyPagesImpl::GetPages
dev_langs:
- C++
helpviewer_keywords:
- property pages, CLSIDs associated with
- ISpecifyPropertyPages
- ISpecifyPropertyPagesImpl class
ms.assetid: 4e4b9795-b656-4d56-9b8c-85941e7731f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 74f10684c32cc5b1b4b07ac30406520c9ba41ddd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ispecifypropertypagesimpl-class"></a>ISpecifyPropertyPagesImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir varsayılan uygulamayı sağlar [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class ATL_NO_VTABLE ISpecifyPropertyPagesImpl 
   : public ISpecifyPropertyPages
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `ISpecifyPropertyPagesImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ISpecifyPropertyPagesImpl::GetPages](#getpages)|Bir dizi UUID, sayılan değerleri doldurur. Her UUID CLSID nesnenin özellik sayfasında görüntülenen özellik sayfaları birine karşılık gelir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [ISpecifyPropertyPages](http://msdn.microsoft.com/library/windows/desktop/ms695217) arabirimi bir nesne tarafından desteklenen özellik sayfaları için CLSID listesini almak bir istemci izin verir. Sınıf `ISpecifyPropertyPagesImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
> [!NOTE]
>  Değil kullanıma **ISpecifyPropertyPages** nesnenizin özellik sayfaları desteklemiyorsa arabirim.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ISpecifyPropertyPages`  
  
 `ISpecifyPropertyPagesImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
##  <a name="getpages"></a>  ISpecifyPropertyPagesImpl::GetPages  
 Dizi doldurur [CAUUID](http://msdn.microsoft.com/library/windows/desktop/ms680048) nesnenin özellik sayfasında görüntülenen özellik sayfaları CLSID yapısıyla.  
  
```
STDMETHOD(GetPages)(CAUUID* pPages);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi her CLSID almak için kullanır.  
  
 Bkz: [ISpecifyPropertyPages::GetPages](http://msdn.microsoft.com/library/windows/desktop/ms687276) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyPageImpl sınıfı](../../atl/reference/ipropertypageimpl-class.md)   
 [IPerPropertyBrowsingImpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
