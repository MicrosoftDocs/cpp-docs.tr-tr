---
title: Ioleınplaceobjectwindowlessımpl sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c48670ca6e7dd38e94a2c57f0a0c0415f654f445
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37881496"
---
# <a name="ioleinplaceobjectwindowlessimpl-class"></a>Ioleınplaceobjectwindowlessımpl sınıfı
Bu sınıfın uyguladığı `IUnknown` ve pencere iletileri almak ve sürükle ve bırak işlemleri katılmak için penceresiz denetime olanak tanıyan yöntemler sağlar.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<class T>
class IOleInPlaceObjectWindowlessImpl
```  
  
#### <a name="parameters"></a>Parametreler  
 *T*  
 Sınıfınız, türetilen `IOleInPlaceObjectWindowlessImpl`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp](#contextsensitivehelp)|Bağlama duyarlı Yardım sağlar. ATL uygulamasını E_NOTIMPL döndürür.|  
|[IOleInPlaceObjectWindowlessImpl::GetDropTarget](#getdroptarget)|Kaynakları `IDropTarget` , sürükle ve bırak bir yerinde etkin, penceresiz nesne için arabirim. ATL uygulamasını E_NOTIMPL döndürür.|  
|[IOleInPlaceObjectWindowlessImpl::GetWindow](#getwindow)|Bir pencere tutucu alır.|  
|[IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate](#inplacedeactivate)|Etkin bir yerinde denetim devre dışı bırakır.|  
|[IOleInPlaceObjectWindowlessImpl::OnWindowMessage](#onwindowmessage)|Yerinde etkin bir penceresiz denetime kapsayıcısından bir ileti gönderir.|  
|[IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo](#reactivateandundo)|Daha önce devre dışı bırakılmış bir denetimi yeniden etkinleştirir. ATL uygulamasını E_NOTIMPL döndürür.|  
|[IOleInPlaceObjectWindowlessImpl::SetObjectRects](#setobjectrects)|Hangi kısmının yerinde denetimi görünür olduğunu gösterir.|  
|[IOleInPlaceObjectWindowlessImpl::UIDeactivate](#uideactivate)|Devre dışı bırakır ve yerinde etkinleştirme destekleyen kullanıcı arabirimini kaldırır.|  
  
## <a name="remarks"></a>Açıklamalar  
 [IOleInPlaceObject](http://msdn.microsoft.com/library/windows/desktop/ms692646) arabirimi yöneten etkinleştirme ve devre dışı bırakma yerinde denetler ve denetimin ne kadarının görünür olacağını belirler. [IOleInPlaceObjectWindowless](http://msdn.microsoft.com/library/windows/desktop/ms687304) penceresiz denetime pencere iletileri almak ve sürükle ve bırak işlemleri katılmak için arabirim sağlar. Sınıf `IOleInPlaceObjectWindowlessImpl` bir varsayılan uygulamayı sağlar `IOleInPlaceObject` ve `IOleInPlaceObjectWindowless` ve uygulayan `IUnknown` dökümünü almak için bilgi göndererek hata ayıklama cihazı oluşturur.  
  
 **İle ilgili makaleler** [ATL öğretici](../../atl/active-template-library-atl-tutorial.md), [ATL projesi oluşturma](../../atl/reference/creating-an-atl-project.md)  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IOleInPlaceObjectWindowless`  
  
 `IOleInPlaceObjectWindowlessImpl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlctl.h  
  
##  <a name="contextsensitivehelp"></a>  IOleInPlaceObjectWindowlessImpl::ContextSensitiveHelp  
 E_NOTIMPL döndürür.  
  
```
HRESULT ContextSensitiveHelp(BOOL fEnterMode);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleWindow::ContextSensitiveHelp](http://msdn.microsoft.com/library/windows/desktop/ms680059) Windows SDK içinde.  
  
##  <a name="getdroptarget"></a>  IOleInPlaceObjectWindowlessImpl::GetDropTarget  
 E_NOTIMPL döndürür.  
  
```
HRESULT GetDropTarget(IDropTarget** ppDropTarget);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObjectWindowless::GetDropTarget](http://msdn.microsoft.com/library/windows/desktop/ms678535) Windows SDK içinde.  
  
##  <a name="getwindow"></a>  IOleInPlaceObjectWindowlessImpl::GetWindow  
 Kapsayıcı denetim pencere tanıtıcısı almak için bu işlevi çağırır.  
  
```
HRESULT GetWindow(HWND* phwnd);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bazı kapsayıcıları, şu anda pencereli olsa bile penceresiz, bir denetim ile çalışmaz. ATL'nin uygulamasında, Denetim sınıfın veri üyesi `m_bWasOnceWindowless` doğru ise, işlev E_FAIL döndürür. Aksi takdirde *phwnd* NULL değil `GetWindow` ayarlar \* *phwnd* denetim sınıfın veri üyesinin `m_hWnd` ve S_OK döndürür.  
  
 Bkz: [IOleWindow::GetWindow](http://msdn.microsoft.com/library/windows/desktop/ms687282) Windows SDK içinde.  
  
##  <a name="inplacedeactivate"></a>  IOleInPlaceObjectWindowlessImpl::InPlaceDeactivate  
 Yerinde etkin denetim devre dışı bırakmak için kapsayıcı tarafından çağrılır.  
  
```
HRESULT InPlaceDeactivate(HWND* phwnd);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, bir tam veya kısmi devre dışı bırakma denetim durumuna bağlı olarak gerçekleştirir. Gerekirse, denetimin kullanıcı arabirimini devre dışı bırakılır ve varsa, denetimin penceresi yok. Kapsayıcı denetimi artık yerinde etkin olduğunu bildirilir. `IOleInPlaceUIWindow` Menüleri anlaşılacak ve alanı kenarlık kapsayıcı tarafından kullanılan arabirimi yayımlanır.  
  
 Bkz: [IOleInPlaceObject::InPlaceDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms679700) Windows SDK içinde.  
  
##  <a name="onwindowmessage"></a>  IOleInPlaceObjectWindowlessImpl::OnWindowMessage  
 Bir kapsayıcı yerinde etkin bir penceresiz denetime bir ileti gönderir.  
  
```
HRESULT OnWindowMessage(
    UINT msg,
    WPARAM WParam,
    LPARAM LParam,
    LRESULT plResultParam);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObjectWindowless::OnWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms693783) Windows SDK içinde.  
  
##  <a name="reactivateandundo"></a>  IOleInPlaceObjectWindowlessImpl::ReactivateAndUndo  
 E_NOTIMPL döndürür.  
  
```
HRESULT ReactivateAndUndo();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bkz: [IOleInPlaceObject::ReactivateAndUndo](http://msdn.microsoft.com/library/windows/desktop/ms691372) Windows SDK içinde.  
  
##  <a name="setobjectrects"></a>  IOleInPlaceObjectWindowlessImpl::SetObjectRects  
 Kendi boyutunun ve/veya konumu değişti denetim bildirmek için kapsayıcı tarafından çağrılır.  
  
```
HRESULT SetObjectRects(LPCRECT prcPos, LPCRECT prcClip);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetimin güncelleştirmeleri `m_rcPos` veri üyesi ve denetimi görüntüleme. Kırpma bölgesini kesişip denetimi yalnızca bir parçası olarak görüntülenir. Bir denetimin görüntü daha önce kırpılarak ancak kırpma kaldırıldı, tam bir denetimin görünümünü yeniden çizmek için bu işlev çağrılabilir.  
  
 Bkz: [IOleInPlaceObject::SetObjectRects](http://msdn.microsoft.com/library/windows/desktop/ms683767) Windows SDK içinde.  
  
##  <a name="uideactivate"></a>  IOleInPlaceObjectWindowlessImpl::UIDeactivate  
 Devre dışı bırakır ve yerinde etkinleştirme destekler denetimin kullanıcı arabirimi kaldırır.  
  
```
HRESULT UIDeactivate();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Denetim sınıfın veri üyesi ayarlar `m_bUIActive` false. Bu işlev ATL uygulamasını her zaman S_OK döndürür.  
  
 Bkz: [IOleInPlaceObject::UIDeactivate](http://msdn.microsoft.com/library/windows/desktop/ms693348) Windows SDK içinde.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComControl sınıfı](../../atl/reference/ccomcontrol-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
