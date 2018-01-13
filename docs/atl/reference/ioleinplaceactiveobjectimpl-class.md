---
title: "IOleInPlaceActiveObjectImpl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::EnableModeless
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnDocWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::OnFrameWindowActivate
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::ResizeBorder
- ATLCTL/ATL::IOleInPlaceActiveObjectImpl::TranslateAccelerator
dev_langs: C++
helpviewer_keywords:
- IOleInPlaceActiveObjectImpl class
- ActiveX controls [C++], communication between container and control
- IOleInPlaceActiveObject, ATL implementation
ms.assetid: 44e6cc6d-a2dc-4187-98e3-73cf0320dea9
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6d88f85e83a88b0a1ce2bd4566e3ca479dddc1af
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ioleinplaceactiveobjectimpl-class"></a>IOleInPlaceActiveObjectImpl sınıfı
Bu sınıf, bir yerinde denetimi kapsayıcısı arasındaki iletişimi yardımcı yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class IOleInPlaceActiveObjectImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IOleInPlaceActiveObjectImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IOleInPlaceActiveObjectImpl::ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı Yardım sağlar. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleInPlaceActiveObjectImpl::EnableModeless](#enablemodeless)|Kalıcı olmayan iletişim kutuları sağlar. ATL uygulamasını döndürür `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::GetWindow](#getwindow)|Bir pencere tanıtıcının alır.|  
|[IOleInPlaceActiveObjectImpl::OnDocWindowActivate](#ondocwindowactivate)|Kapsayıcının belge penceresine etkinleştirilmiş veya devre dışı olduğunda denetim bildirir. ATL uygulamasını döndürür `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::OnFrameWindowActivate](#onframewindowactivate)|Kapsayıcının en üst düzey çerçeve penceresi etkin veya devre dışı olduğunda denetim bildirir. ATL uygulamasını döndürür|  
|[IOleInPlaceActiveObjectImpl::ResizeBorder](#resizeborder)|Kenarlıkları yeniden boyutlandırmak gereken denetim bildirir. ATL uygulamasını döndürür `S_OK`.|  
|[IOleInPlaceActiveObjectImpl::TranslateAccelerator](#translateaccelerator)|Menü kısayol tuşu iletileri kapsayıcısından işler. ATL uygulamasını döndürür **E_NOTIMPL**.|  
  
  
## <a name="remarks"></a>Açıklamalar  
 [IOleInPlaceActiveObject](http://msdn.microsoft.com/library/windows/desktop/ms691299) arabirimi bir yerinde denetimi kapsayıcısı arasındaki iletişimi yardımcı olur; Örneğin, Denetim ve kapsayıcı etkin durumunu iletişim ve denetim bildiren, yeniden boyutlandırmak için gerekli kendisi. Sınıf `IOleInPlaceActiveObjectImpl` bir varsayılan uygulamayı sağlar `IOleInPlaceActiveObject` ve destekleyen **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IOleInPlaceActiveObject`  
  
 `IOleInPlaceActiveObjectImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceActiveObjectImpl::ContextSensitiveHelp  
 Bağlama duyarlı Yardım sağlar.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **E_NOTIMPL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) Windows SDK.  
  
##  <a name="enablemodeless"></a>IOleInPlaceActiveObjectImpl::EnableModeless  
 Kalıcı olmayan iletişim kutuları sağlar.  
  
```
HRESULT EnableModeless(BOOL fEnable);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceActiveObject::EnableModeless](http://msdn.microsoft.com/library/windows/desktop/ms680115) Windows SDK.  
  
##  <a name="getwindow"></a>IOleInPlaceActiveObjectImpl::GetWindow  
 Kapsayıcı denetimi pencere tanıtıcısı almak için bu işlevi çağırır.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bazı kapsayıcıları, şu anda pencereli olsa bile penceresiz, bir denetim ile çalışmaz. ATL'ın uygulamasında varsa **CComControl::m_bWasOnceWindowless** veri üyesi olduğu **TRUE**, işlevi döndürür **E_FAIL**. Aksi halde, eğer \* *phwnd* değil **NULL**, `GetWindow` atar *phwnd* denetim sınıfın veri üyesi için `m_hWnd` ve döndürür`S_OK`.  
  
 Bkz: [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) Windows SDK.  
  
##  <a name="ondocwindowactivate"></a>IOleInPlaceActiveObjectImpl::OnDocWindowActivate  
 Kapsayıcının belge penceresine etkinleştirilmiş veya devre dışı olduğunda denetim bildirir.  
  
```
HRESULT OnDocWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceActiveObject::OnDocWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms687281) Windows SDK.  
  
##  <a name="onframewindowactivate"></a>IOleInPlaceActiveObjectImpl::OnFrameWindowActivate  
 Kapsayıcının en üst düzey çerçeve penceresi etkin veya devre dışı olduğunda denetim bildirir.  
  
```
HRESULT OnFrameWindowActivate(BOOL fActivate);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceActiveObject::OnFrameWindowActivate](http://msdn.microsoft.com/library/windows/desktop/ms683969) Windows SDK.  
  
##  <a name="resizeborder"></a>IOleInPlaceActiveObjectImpl::ResizeBorder  
 Kenarlıkları yeniden boyutlandırmak gereken denetim bildirir.  
  
```
HRESULT ResizeBorder(
    LPRECT prcBorder,
    IOleInPlaceUIWindow* pUIWindow,
    BOOL fFrameWindow);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceActiveObject::ResizeBorder](http://msdn.microsoft.com/library/windows/desktop/ms680053) Windows SDK.  
  
##  <a name="translateaccelerator"></a>IOleInPlaceActiveObjectImpl::TranslateAccelerator  
 Menü kısayol tuşu iletileri kapsayıcısından işler.  
  
```
HRESULT TranslateAccelerator(LPMSG lpmsg);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu yöntem aşağıdaki dönüş değerlerini destekler.  
  
 `S_OK`İletiyi başarıyla çevrilen durumunda.  
  
 **S_FALSE** ileti değil çevrilmiş.  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceActiveObject::TranslateAccelerator](http://msdn.microsoft.com/library/windows/desktop/ms693360) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl Sınıfı](../../atl/reference/ccomcontrol-class.md)  
 [Arabirimleri ActiveX denetimleri](http://msdn.microsoft.com/library/windows/desktop/ms692724)  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
