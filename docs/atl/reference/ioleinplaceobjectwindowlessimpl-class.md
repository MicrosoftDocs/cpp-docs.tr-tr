---
title: IOleInPlaceObjectWindowlessImpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetDropTarget
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::GetWindow
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::OnWindowMessage
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::SetObjectRects
- ATLCTL/ATL::IOleInPlaceObjectWindowlessImpl::UIDeactivate
dev_langs:
- C++
helpviewer_keywords:
- IOleInPlaceObjectWindowless, ATL implementation
- activation [C++], ATL
- IOleInPlaceObjectWindowlessImpl class
- ActiveX controls [C++], communication between container and control
- controls [ATL], windowless
- deactivating ATL
ms.assetid: a2e0feb4-bc59-4adf-aab2-105457bbdbb4
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3f455172723be4f46751b45d244e74dda5fcacae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>IOleInPlaceObjectWindowlessImpl sınıfı
Bu sınıf uygulayan **IUnknown** ve pencere iletileri almak ve sürükle ve bırak işlemlerinde katılmak için penceresiz bir denetim sağlayan yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Sınıfınız, türetilen `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı Yardım sağlar. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Kaynakları `IDropTarget` destekler sürükle ve bırak bir yerinde etkin, penceresiz nesne için arabirim. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Bir pencere tanıtıcının alır.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Etkin bir yerinde denetim devre dışı bırakır.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Yerinde etkin penceresiz bir denetim kapsayıcısından ileti gönderir.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Daha önce devre dışı bırakılan bir denetim yeniden etkinleştirir. ATL uygulamasını döndürür **E_NOTIMPL**.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Yerinde denetim hangi kısmının görünür olduğunu gösterir.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Devre dışı bırakır ve yerinde etkinleştirme destekleyen kullanıcı arabirimini kaldırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) arabirimi yönetir yeniden etkinleştirme ve devre dışı bırakma, yerinde denetler ve denetimi ne kadarının görünür olması belirler. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) arabirimi pencere iletileri almak ve sürükle ve bırak işlemlerinde katılmak için penceresiz bir denetim sağlar. Sınıf `IOleInPlaceObjectWindowlessImpl` bir varsayılan uygulamayı sağlar `IOleInPlaceObject` ve `IOleInPlaceObjectWindowless` ve uygulayan **IUnknown** aygıt hata ayıklama dökümü bilgileri göndererek oluşturur.  
  
 **İlgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [bir ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 Döndürür **E_NOTIMPL**.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) Windows SDK.  
  
##  <a name="getdroptarget"></a>IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 Döndürür **E_NOTIMPL**.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) Windows SDK.  
  
##  <a name="getwindow"></a>IOleInPlaceObjectWindowlessImpl::GetWindow  
 Kapsayıcı denetimi pencere tanıtıcısı almak için bu işlevi çağırır.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bazı kapsayıcıları, şu anda pencereli olsa bile penceresiz, bir denetim ile çalışmaz. ATL'ın uygulamasında, Denetim sınıfın veri üyesi `m_bWasOnceWindowless` olan **TRUE**, işlevi döndürür **E_FAIL**. Aksi halde, eğer *phwnd* değil **NULL**, `GetWindow` ayarlar \* *phwnd* denetim sınıfın veri üyesi için `m_hWnd` ve döndürür`S_OK`.  
  
 Bkz: [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) Windows SDK.  
  
##  <a name="inplacedeactivate"></a>IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Yerinde etkin denetim devre dışı bırakmak için kapsayıcı tarafından çağrılır.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir tam veya kısmi devre dışı bırakma denetimin durum bilgisinin bağlı olarak gerçekleştirir. Gerekirse, denetimin kullanıcı arabirimini devre dışı bırakılır ve varsa, denetimin penceresi yok. Kapsayıcı denetimi artık yerinde etkin olduğunu bildirilir. **IOleInPlaceUIWindow** menüleri anlaşılacak ve alan kenarlık kapsayıcı tarafından kullanılan arabirimi yayımlanır.  
  
 Bkz: [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK.  
  
##  <a name="onwindowmessage"></a>IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Yerinde etkin penceresiz bir denetim için bir kapsayıcı gelen iletiyi gönderir.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) Windows SDK.  
  
##  <a name="reactivateandundo"></a>IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 Döndürür **E_NOTIMPL**.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) Windows SDK.  
  
##  <a name="setobjectrects"></a>IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Kendi boyutu ve/veya konumu değişti denetim bildirmek için kapsayıcı tarafından çağrılır.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimin güncelleştirmeleri `m_rcPos` veri üyesi ve denetim görüntüleme. Kırpma bölgesinin kesiştiğinden denetimi yalnızca bir parçasının görüntülenir. Denetimin görüntüleme önceden kırpılmış ancak kırpma kaldırıldı, bu işlev denetim tam görünümünü yeniden çizmek için çağrılabilir.  
  
 Bkz: [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) Windows SDK.  
  
##  <a name="uideactivate"></a>IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Devre dışı bırakır ve yerinde etkinleştirme destekleyen denetimin kullanıcı arabirimi kaldırır.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfın veri üyesi ayarlar `m_bUIActive` için **FALSE**. ATL uygulamasını bu işlev her zaman döndürür `S_OK`.  
  
 Bkz: [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
