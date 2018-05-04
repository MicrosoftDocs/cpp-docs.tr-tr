---
title: IPerPropertyBrowsingImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetDisplayString
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedStrings
- ATLCTL/ATL::IPerPropertyBrowsingImpl::GetPredefinedValue
- ATLCTL/ATL::IPerPropertyBrowsingImpl::MapPropertyToPage
dev_langs:
- C++
helpviewer_keywords:
- IPerPropertyBrowsingImpl class
- property pages, accessing information
- IPerPropertyBrowsing, ATL implementation
ms.assetid: 0b1a9be3-d242-4767-be69-663a21e4b728
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2d9fffd6151405eaf53e99f770281139d7664b01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="iperpropertybrowsingimpl-class"></a>IPerPropertyBrowsingImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir istemcinin bir nesnenin özellik sayfaları bilgilerinde erişmesine olanak tanır.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```

template <class T>
class ATL_NO_VTABLE IPerPropertyBrowsingImpl :
    public IPerPropertyBrowsing
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPerPropertyBrowsingImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPerPropertyBrowsingImpl::GetDisplayString](#getdisplaystring)|Belirli bir özelliğe tanımlayan bir dize alır.|  
|[IPerPropertyBrowsingImpl::GetPredefinedStrings](#getpredefinedstrings)|Bir özelliğe kabul edebileceği değerlere karşılık gelen bir dizeler dizisi alır.|  
|[IPerPropertyBrowsingImpl::GetPredefinedValue](#getpredefinedvalue)|Alır bir **değişken** verilen DISPID tarafından tanımlanan bir özellik değerini içeren. Kaynağından alınan dize adı ile DISPID ilişkilendirilen `GetPredefinedStrings`. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IPerPropertyBrowsingImpl::MapPropertyToPage](#mappropertytopage)|Belirli bir özellik ile ilişkilendirilmiş özellik sayfası CLSID alır.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPerPropertyBrowsing](http://msdn.microsoft.com/library/windows/desktop/ms678432) arabirimi nesnenin özellik sayfaları bilgilerinde erişmek için bir istemci izin verir. Sınıf `IPerPropertyBrowsingImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
> [!NOTE]
>  Microsoft Access kapsayıcı uygulaması olarak kullanıyorsanız, sınıfından türetilmelidir `IPerPropertyBrowsingImpl`. Aksi takdirde, erişim denetim yüklemez.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPerPropertyBrowsing`  
  
 `IPerPropertyBrowsingImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="getdisplaystring"></a>  IPerPropertyBrowsingImpl::GetDisplayString  
 Belirli bir özelliğe tanımlayan bir dize alır.  
  
```
STDMETHOD(GetDisplayString)(
    DISPID dispID,
    BSTR* pBstr);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPerPropertyBrowsing::GetDisplayString](http://msdn.microsoft.com/library/windows/desktop/ms688734) Windows SDK.  
  
##  <a name="getpredefinedstrings"></a>  IPerPropertyBrowsingImpl::GetPredefinedStrings  
 Her dizi sıfır öğe ile doldurur.  
  
```
STDMETHOD(GetPredefinedStrings)(
    DISPID dispID,
    CALPOLESTR* pCaStringsOut,
    CADWORD* pCaCookiesOut);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ATL'ın uyarlamasını [GetPredefinedValue](#getpredefinedvalue) döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPerPropertyBrowsing::GetPredefinedStrings öğesini](http://msdn.microsoft.com/library/windows/desktop/ms679724) Windows SDK.  
  
##  <a name="getpredefinedvalue"></a>  IPerPropertyBrowsingImpl::GetPredefinedValue  
 Alır bir **değişken** verilen DISPID tarafından tanımlanan bir özellik değerini içeren. Kaynağından alınan dize adı ile DISPID ilişkilendirilen `GetPredefinedStrings`.  
  
```
STDMETHOD(GetPredefinedValue)(
    DISPID dispID,
    DWORD dwCookie,
    VARIANT* pVarOut);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 ATL'ın uyarlamasını [GetPredefinedStrings](#getpredefinedstrings) karşılık gelen hiçbir dizeleri alır.  
  
 Bkz: [IPerPropertyBrowsing::GetPredefinedValue](http://msdn.microsoft.com/library/windows/desktop/ms690401) Windows SDK.  
  
##  <a name="mappropertytopage"></a>  IPerPropertyBrowsingImpl::MapPropertyToPage  
 Belirtilen özellik ile ilişkilendirilmiş özellik sayfası CLSID alır.  
  
```
STDMETHOD(MapPropertyToPage)(
    DISPID dispID,
    CLSID* pClsid);
```  
  
### <a name="remarks"></a>Açıklamalar  
 ATL nesnenin özellik eşlemesi bu bilgileri almak için kullanır.  
  
 Bkz: [IPerPropertyBrowsing::MapPropertyToPage](http://msdn.microsoft.com/library/windows/desktop/ms694476) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyPageImpl sınıfı](../../atl/reference/ipropertypageimpl-class.md)   
 [ISpecifyPropertyPagesImpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
