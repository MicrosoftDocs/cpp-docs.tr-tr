---
title: "IPropertyPageImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::IPropertyPageImpl
- ATLCTL/ATL::IPropertyPageImpl::Activate
- ATLCTL/ATL::IPropertyPageImpl::Apply
- ATLCTL/ATL::IPropertyPageImpl::Deactivate
- ATLCTL/ATL::IPropertyPageImpl::GetPageInfo
- ATLCTL/ATL::IPropertyPageImpl::Help
- ATLCTL/ATL::IPropertyPageImpl::IsPageDirty
- ATLCTL/ATL::IPropertyPageImpl::Move
- ATLCTL/ATL::IPropertyPageImpl::SetDirty
- ATLCTL/ATL::IPropertyPageImpl::SetObjects
- ATLCTL/ATL::IPropertyPageImpl::SetPageSite
- ATLCTL/ATL::IPropertyPageImpl::Show
- ATLCTL/ATL::IPropertyPageImpl::TranslateAccelerator
- ATLCTL/ATL::IPropertyPageImpl::m_bDirty
- ATLCTL/ATL::IPropertyPageImpl::m_dwDocString
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpContext
- ATLCTL/ATL::IPropertyPageImpl::m_dwHelpFile
- ATLCTL/ATL::IPropertyPageImpl::m_dwTitle
- ATLCTL/ATL::IPropertyPageImpl::m_nObjects
- ATLCTL/ATL::IPropertyPageImpl::m_pPageSite
- ATLCTL/ATL::IPropertyPageImpl::m_ppUnk
- ATLCTL/ATL::IPropertyPageImpl::m_size
dev_langs: C++
helpviewer_keywords:
- property pages
- IPropertyPage ATL implementation
- IPropertyPageImpl class
ms.assetid: f9b7c8b1-7a04-4eab-aa63-63efddb740fa
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fbc62bd72ee5a639e8df0ada365cd7baac7d0c31
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ipropertypageimpl-class"></a>IPropertyPageImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve bir varsayılan uygulamayı sağlar [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) arabirimi.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>  
class IPropertyPageImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IPropertyPageImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPropertyPageImpl::IPropertyPageImpl](#ipropertypageimpl)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPropertyPageImpl::Activate](#activate)|Özellik sayfası için iletişim kutusu pencere oluşturur.|  
|[IPropertyPageImpl::Apply](#apply)|Geçerli özellik sayfası değerleri aracılığıyla belirtilen temel nesnelere uygulanır `SetObjects`. ATL uygulamasını döndürür `S_OK`.|  
|[IPropertyPageImpl::Deactivate](#deactivate)|İle oluşturulan pencerenin bozar **etkinleştirme**.|  
|[IPropertyPageImpl::GetPageInfo](#getpageinfo)|Özellik sayfasında ilgili bilgileri alır.|  
|[IPropertyPageImpl::Help](#help)|Özellik sayfası Windows yardımını çağırır.|  
|[IPropertyPageImpl::IsPageDirty](#ispagedirty)|Özellik sayfasını, etkinleştirilmesinden sonra değişip değişmediğini gösterir.|  
|[IPropertyPageImpl::Move](#move)|Yerleştirir ve özellik sayfası iletişim kutusu yeniden boyutlandırır.|  
|[IPropertyPageImpl::SetDirty](#setdirty)|Özellik sayfanın durumu değiştirilmiş veya değişmemiş olarak işaretler.|  
|[IPropertyPageImpl::SetObjects](#setobjects)|Bir dizi sağlar **IUnknown** özellik sayfası ile ilişkili nesneleri işaretçileri. Bu nesneler çağrısıyla geçerli özellik sayfası değerleri alma **Uygula**.|  
|[IPropertyPageImpl::SetPageSite](#setpagesite)|Özellik sayfasıyla sağlayan bir `IPropertyPageSite` üzerinden özellik sayfası iletişim kurar özelliği çerçeve işaretçisi.|  
|[IPropertyPageImpl::Show](#show)|Özellik sayfası iletişim kutusu görünür veya görünmez kılar.|  
|[IPropertyPageImpl::TranslateAccelerator](#translateaccelerator)|Belirtilen bir tuş vuruşu işler.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IPropertyPageImpl::m_bDirty](#m_bdirty)|Özellik sayfanın durumu değişip değişmediğini belirtir.|  
|[IPropertyPageImpl::m_dwDocString](#m_dwdocstring)|Özellik sayfası açıklayan metin dizesi ile ilişkili olan kaynak kimliğini depolar.|  
|[IPropertyPageImpl::m_dwHelpContext](#m_dwhelpcontext)|Özellik sayfası ile ilişkili Yardım konusu içerik tanımlayıcısını depolar.|  
|[IPropertyPageImpl::m_dwHelpFile](#m_dwhelpfile)|Özellik sayfası açıklayan Yardım dosyası adı ile ilişkili olan kaynak kimliğini depolar.|  
|[IPropertyPageImpl::m_dwTitle](#m_dwtitle)|Özellik Sayfası sekmesinde görüntülenen metin dizesi ile ilişkili olan kaynak kimliğini depolar.|  
|[IPropertyPageImpl::m_nObjects](#m_nobjects)|Özellik sayfası ile ilişkili nesne sayısı depolar.|  
|[IPropertyPageImpl::m_pPageSite](#m_ppagesite)|İşaret `IPropertyPageSite` üzerinden özellik sayfası iletişim kurar özelliği çerçevesiyle arabirimi.|  
|[IPropertyPageImpl::m_ppUnk](#m_ppunk)|Noktaları için bir dizi **IUnknown** özellik sayfası ile ilişkili nesne işaretçileri.|  
|[IPropertyPageImpl::m_size](#m_size)|Özellik sayfasının iletişim kutusunun genişliği ve yüksekliği piksel cinsinden depolar.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) arabirimi sağlayan bir özellik sayfası belirli özellik sayfasında yönetmek bir nesne. Sınıf `IPropertyPageImpl` bu arabirimin varsayılan uygulamasını sağlar ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IPropertyPage`  
  
 `IPropertyPageImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="activate"></a>IPropertyPageImpl::Activate  
 Özellik sayfası için iletişim kutusu pencere oluşturur.  
  
```
HRESULT Activate(  
    HWND hWndParent,
    LPCRECT pRect,
    BOOL bModal);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, iletişim kutusu her zaman değeri bağımsız olarak kalıcı olmayan *bModal* parametresi.  
  
 Bkz: [IPropertyPage::Activate](http://msdn.microsoft.com/library/windows/desktop/ms682250) Windows SDK.  
  
##  <a name="apply"></a>IPropertyPageImpl::Apply  
 Geçerli özellik sayfası değerleri aracılığıyla belirtilen temel nesnelere uygulanır `SetObjects`.  
  
```
HRESULT Apply();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::Apply](http://msdn.microsoft.com/library/windows/desktop/ms691284) Windows SDK.  
  
##  <a name="deactivate"></a>IPropertyPageImpl::Deactivate  
 İle oluşturulan iletişim kutusunun penceresi yok eder [etkinleştirme](#activate).  
  
```
HRESULT Deactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::Deactivate](http://msdn.microsoft.com/library/windows/desktop/ms682504) Windows SDK.  
  
##  <a name="getpageinfo"></a>IPropertyPageImpl::GetPageInfo  
 Doldurur *pPageInfo* veri üyeleri bilgilerle yapısı.  
  
```
HRESULT GetPageInfo(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 `GetPageInfo`ile ilişkili dize kaynaklarını yükler [m_dwDocString](#m_dwdocstring), [m_dwHelpFile](#m_dwhelpfile), ve [m_dwTitle](#m_dwtitle).  
  
 Bkz: [IPropertyPage::GetPageInfo](http://msdn.microsoft.com/library/windows/desktop/ms680714) Windows SDK.  
  
##  <a name="help"></a>IPropertyPageImpl::Help  
 Özellik sayfası Windows yardımını çağırır.  
  
```
HRESULT Help(PROPPAGEINFO* pPageInfo);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::Help](http://msdn.microsoft.com/library/windows/desktop/ms691504) Windows SDK.  
  
##  <a name="ipropertypageimpl"></a>IPropertyPageImpl::IPropertyPageImpl  
 Oluşturucu.  
  
```
IPropertyPageImpl();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm veri üyeleri başlatır.  
  
##  <a name="ispagedirty"></a>IPropertyPageImpl::IsPageDirty  
 Özellik sayfasını, etkinleştirilmesinden sonra değişip değişmediğini gösterir.  
  
```
HRESULT IsPageDirty(void);
```  
  
### <a name="remarks"></a>Açıklamalar  
 `IsPageDirty`döndürür `S_OK` onu etkinleştirilmesinden sonra sayfanın değiştirilmesi durumunda.  
  
##  <a name="m_bdirty"></a>IPropertyPageImpl::m_bDirty  
 Özellik sayfanın durumu değişip değişmediğini belirtir.  
  
```
BOOL m_bDirty;
```  
  
##  <a name="m_nobjects"></a>IPropertyPageImpl::m_nObjects  
 Özellik sayfası ile ilişkili nesne sayısı depolar.  
  
```
ULONG m_nObjects;
```  
  
##  <a name="m_dwhelpcontext"></a>IPropertyPageImpl::m_dwHelpContext  
 Özellik sayfası ile ilişkili Yardım konusu içerik tanımlayıcısını depolar.  
  
```
DWORD m_dwHelpContext;
```  
  
##  <a name="m_dwdocstring"></a>IPropertyPageImpl::m_dwDocString  
 Özellik sayfası açıklayan metin dizesi ile ilişkili olan kaynak kimliğini depolar.  
  
```
UINT m_dwDocString;
```  
  
##  <a name="m_dwhelpfile"></a>IPropertyPageImpl::m_dwHelpFile  
 Özellik sayfası açıklayan Yardım dosyası adı ile ilişkili olan kaynak kimliğini depolar.  
  
```
UINT m_dwHelpFile;
```  
  
##  <a name="m_dwtitle"></a>IPropertyPageImpl::m_dwTitle  
 Özellik Sayfası sekmesinde görüntülenen metin dizesi ile ilişkili olan kaynak kimliğini depolar.  
  
```
UINT m_dwTitle;
```  
  
##  <a name="m_ppagesite"></a>IPropertyPageImpl::m_pPageSite  
 İşaret [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) üzerinden özellik sayfası iletişim kurar özelliği çerçevesiyle arabirimi.  
  
```
IPropertyPageSite* m_pPageSite;
```  
  
##  <a name="m_ppunk"></a>IPropertyPageImpl::m_ppUnk  
 Noktaları için bir dizi **IUnknown** özellik sayfası ile ilişkili nesne işaretçileri.  
  
```
IUnknown** m_ppUnk;
```  
  
##  <a name="m_size"></a>IPropertyPageImpl::m_size  
 Özellik sayfasının iletişim kutusunun genişliği ve yüksekliği piksel cinsinden depolar.  
  
```
SIZE m_size;
```  
  
##  <a name="move"></a>IPropertyPageImpl::Move  
 Yerleştirir ve özellik sayfası iletişim kutusu yeniden boyutlandırır.  
  
```
HRESULT Move(LPCRECT pRect);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::Move](http://msdn.microsoft.com/library/windows/desktop/ms680118) Windows SDK.  
  
##  <a name="setdirty"></a>IPropertyPageImpl::SetDirty  
 Değiştirilmiş veya değişmemiş değerine bağlı olarak farklı özellik sayfanın durumu bayrakları `bDirty`.  
  
```
void SetDirty(BOOL bDirty);
```  
  
### <a name="parameters"></a>Parametreler  
 `bDirty`  
 [in] Varsa **doğru**, özellik sayfanın durumu değişmiş olarak işaretlenir. Aksi takdirde, işaretlenmiş olarak değişmez.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, `SetDirty` özellik sayfası değişti çerçeve bildirir.  
  
##  <a name="setobjects"></a>IPropertyPageImpl::SetObjects  
 Bir dizi sağlar **IUnknown** özellik sayfası ile ilişkili nesneleri işaretçileri.  
  
```
HRESULT SetObjects(ULONG nObjects, IUnknown** ppUnk);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::SetObjects](http://msdn.microsoft.com/library/windows/desktop/ms678529) Windows SDK.  
  
##  <a name="setpagesite"></a>IPropertyPageImpl::SetPageSite  
 Özellik sayfasıyla sağlayan bir [IPropertyPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690583) üzerinden özellik sayfası iletişim kurar özelliği çerçeve işaretçisi.  
  
```
HRESULT SetPageSite(IPropertyPageSite* pPageSite);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::SetPageSite](http://msdn.microsoft.com/library/windows/desktop/ms690413) Windows SDK.  
  
##  <a name="show"></a>IPropertyPageImpl::Show  
 Özellik sayfası iletişim kutusu görünür veya görünmez kılar.  
  
```
HRESULT Show(UINT nCmdShow);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::Show](http://msdn.microsoft.com/library/windows/desktop/ms694467) Windows SDK.  
  
##  <a name="translateaccelerator"></a>IPropertyPageImpl::TranslateAccelerator  
 Belirtilen tuş vuruşu işler `pMsg`.  
  
```
HRESULT TranslateAccelerator(MSG* pMsg);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IPropertyPage::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms686603) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IPropertyPage2Impl sınıfı](../../atl/reference/ipropertypage2impl-class.md)   
 [IPerPropertyBrowsingImpl sınıfı](../../atl/reference/iperpropertybrowsingimpl-class.md)   
 [ISpecifyPropertyPagesImpl sınıfı](../../atl/reference/ispecifypropertypagesimpl-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
