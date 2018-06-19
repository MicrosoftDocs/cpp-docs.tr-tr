---
title: CAxWindow2T sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAxWindow2T
- ATLWIN/ATL::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::CAxWindow2T
- ATLWIN/ATL::CAxWindow2T::Create
- ATLWIN/ATL::CAxWindow2T::CreateControlLic
- ATLWIN/ATL::CAxWindow2T::CreateControlLicEx
- ATLWIN/ATL::CAxWindow2T::GetWndClassName
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 077ecfe36e1ddf6c319f02bdabb89d660a5f22d8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360764"
---
# <a name="caxwindow2t-class"></a>CAxWindow2T sınıfı
Bu sınıf bir ActiveX denetimini barındırır ve ayrıca Lisanslı ActiveX denetimlerini barındırma desteği olan bir pencere düzenleme için yöntemleri sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Parametreler  
 *TBase*  
 Sınıfından `CAxWindowT` türetilir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Oluşturan bir `CAxWindow2T` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Bir konak pencere oluşturur.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır, belirtilen penceresinde barındıran ve bir arabirim işaretçisi (veya işaretçileri) denetimden alır.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Pencere sınıfı adını alır statik yöntem.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Atayan bir `HWND` varolan bir `CAxWindow2T` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAxWindow2T` ActiveX denetimi barındıran bir pencere düzenleme için yöntemleri sağlar. `CAxWindow2T` Lisanslı ActiveX denetimlerini barındırma desteği de vardır. Barındırma tarafından sağlanan " **AtlAxWinLic80**", tarafından Sarmalanan `CAxWindow2T`.  
  
 Sınıf `CAxWindow2` uzmanlaşması uygulanan `CAxWindow2T` sınıfı. Bu uzmanlık olarak bildirilmiş:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT` üyeleri altında belgelenmiştir [CAxWindow](../../atl/reference/caxwindow-class.md).  
  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) bu sınıfın üyeleri kullanan bir örnek için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlwin.h  
  
##  <a name="caxwindow2t"></a>  CAxWindow2T::CAxWindow2T  
 Oluşturan bir `CAxWindow2T` nesnesi.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Varolan bir pencere tanıtıcısı.  
  
##  <a name="create"></a>  CAxWindow2T::Create  
 Bir konak pencere oluşturur.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CAxWindow2T::Create` çağrıları [CWindow::Create](../../atl/reference/cwindow-class.md#create) ile `LPCTSTR lpstrWndClass` parametre denetimi barındırma sağlar pencere sınıfı ( **AtlAxWinLic80**).  
  
 Bkz: `CWindow::Create` parametreler ve dönüş değeri açıklaması.  
  
 **Not** 0 değeri olarak kullanılıyorsa, `MenuOrID` parametresi 0U belirtilmelidir (Derleyici Hatası önlemek için varsayılan değer).  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::Create`.  
  
##  <a name="createcontrollic"></a>  CAxWindow2T::CreateControlLic  
 Lisanslı bir ActiveX denetimi oluşturur, onu başlatır ve belirtilen pencerede barındırır.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrLicKey`  
 Denetim için lisans anahtarı; Nonlicensed denetimi oluşturma yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) kalan parametreler ve dönüş değeri açıklaması.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::CreateControlLic`.  
  
##  <a name="createcontrollicex"></a>  CAxWindow2T::CreateControlLicEx  
 Lisanslı bir ActiveX denetimi oluşturur, bunu başlatır, belirtilen penceresinde barındıran ve bir arabirim işaretçisi (veya işaretçileri) denetimden alır.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `bstrLicKey`  
 Denetim için lisans anahtarı; Nonlicensed denetimi oluşturma yoksa NULL.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) kalan parametreler ve dönüş değeri açıklaması.  
  
### <a name="example"></a>Örnek  
 Bkz: [ActiveX denetimlerini kullanarak ATL AXHost barındırma](../../atl/hosting-activex-controls-using-atl-axhost.md) kullanan bir örnek için `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="getwndclassname"></a>  CAxWindow2T::GetWndClassName  
 Pencere sınıfı adını alır.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Pencere sınıfı adını içeren bir dize için bir işaretçi ( **AtlAxWinLic80**) lisanslı ve nonlicensed ActiveX denetimlerini barındırabilir.  
  
##  <a name="operator_eq"></a>  CAxWindow2T::operator =  
 Atayan bir `HWND` varolan bir `CAxWindow2T` nesnesi.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `hWnd`  
 Varolan bir pencere tanıtıcısı.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Denetim kapsamı SSS](../../atl/atl-control-containment-faq.md)
