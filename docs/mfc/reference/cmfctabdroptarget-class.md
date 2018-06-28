---
title: CMFCTabDropTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
dev_langs:
- C++
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68d78e221b9bcdbffbfc80ba26c6106498c4fa41
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040993"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget sınıfı
Sekme denetimi OLE kitaplıklarının arasındaki iletişim mekanizması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMFCTabDropTarget : public COleDropTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|||  
|-|-|  
|Ad|Açıklama|  
|`CMFCTabDropTarget::CMFCTabDropTarget`|Varsayılan Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|||  
|-|-|  
|Ad|Açıklama|  
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Kullanıcı bir sekme penceresine nesneyi sürüklendiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|  
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Kullanıcı bir nesne odaklı sekmesi penceresi dışında sürüklendiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|  
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Kullanıcı bir nesne odaklı sekmesi penceresi sürüklendiğinde çerçevesi tarafından çağrılır. (Geçersiz kılmaları [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|  
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Kullanıcı bir sürükleme işlemi sonunda fare düğmesini bıraktığında çerçevesi tarafından çağrılır. (Geçersiz kılmaları [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|  
|[CMFCTabDropTarget::Register](#register)|Denetim bir OLE sürükle ve bırak işlemi hedefi olan tek olarak kaydeder.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf için sürükle ve bırak desteği sağlar `CMFCBaseTabCtrl` sınıfı. OLE kitaplıklarının kullanarak uygulamanızı başlatır, [Afxoleınit](ole-initialization.md#afxoleinit) işlevi, `CMFCBaseTabCtrl` nesnelerini kaydetmek kendileri için sürükle ve bırak işlemleri.  
  
 `CMFCTabDropTarget` Sınıfı bir sürükleme işlemi etkin olduğunda, imleç altında sekmesini yaparak devralınabilir. taban sınıf genişletir. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için bkz: [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl oluşturulacağını gösteren bir `CMFCTabDropTarget` nesne ve kullanmak, `Register` yöntemi.  
  
 [!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md)  
  
 [CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxbasetabctrl.h  
  
##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter  
 Kullanıcı bir sekme penceresine nesneyi sürüklendiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pWnd*|Kullanılmayan.|  
|[in] *pDataObject*|Kullanıcının sürüklediği nesnesine bir işaretçi.|  
|[in] *dwKeyState*|Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, ve `MK_RBUTTON`.|  
|[in] *noktası*|İstemci koordinatları imleç konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan tarafından belirtilen konumda oluşursa sonuçları etkisi *noktası*. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem `DROPEFFECT_NONE` araç framework özelleştirme modunda değilse veya Pano verileri biçimi kullanılamaz. Aksi takdirde, arama sonucu döndürür `CMFCBaseTabCtrl::OnDragEnter` sağlanan parametrelere sahip.  
  
 Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz: [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave  
 Kullanıcı bir nesne odaklı sekmesi penceresi dışında sürüklendiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pWnd*|Kullanılmayan.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır `CMFCBaseTabCtrl::OnDragLeave` sürükleme işlemi gerçekleştirmek için yöntem.  
  
##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver  
 Kullanıcı bir nesne odaklı sekmesi penceresi sürüklendiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pWnd*|Kullanılmayan.|  
|[in] *pDataObject*|Kullanıcının sürüklediği nesnesine bir işaretçi.|  
|[in] *dwKeyState*|Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: `MK_CONTROL`, `MK_SHIFT`, `MK_ALT`, `MK_LBUTTON`, `MK_MBUTTON`, ve `MK_RBUTTON`.|  
|[in] *noktası*|İstemci koordinatları fare işaretçisini konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan tarafından belirtilen konumda oluşursa sonuçları etkisi *noktası*. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem bir sürükleme işlemi etkin olduğunda, imleç altında sekme yapar. Döndürdüğü `DROPEFFECT_NONE` araç framework özelleştirme modunda değilse veya Pano verileri biçimi kullanılamaz. Aksi takdirde, arama sonucu döndürür `CMFCBaseTabCtrl::OnDragOver` sağlanan parametrelere sahip.  
  
 Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz: [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx  
 Kullanıcı bir sürükleme işlemi sonunda fare düğmesini bıraktığında çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pWnd*|Kullanılmayan.|  
|[in] *pDataObject*|Kullanıcının sürüklediği nesnesine bir işaretçi.|  
|[in] *dropEffect*|Varsayılan bırakma işlemi.|  
|[in] *listeyi*|Kullanılmayan.|  
|[in] *noktası*|İstemci koordinatları fare işaretçisini konumu.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonuçta elde edilen açılan etkisi. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE`  
  
- `DROPEFFECT_COPY`  
  
- `DROPEFFECT_MOVE`  
  
- `DROPEFFECT_LINK`  
  
- `DROPEFFECT_SCROLL`  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır `CMFCBaseTabCtrl::OnDrop` araç framework özelleştirme modda ise ve Pano verileri biçimi kullanılabilir. Varsa çağrısı `CMFCBaseTabCtrl::OnDrop` sıfır olmayan bir değer, bu yöntem tarafından belirtilen varsayılan açılan etkisi döndürür döndürür *dropEffect*. Aksi takdirde, bu yöntemi döndürür `DROPEFFECT_NONE`. Açılan etkileri hakkında daha fazla bilgi için bkz: [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).  
  
 Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz: [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).  
  
##  <a name="register"></a>  CMFCTabDropTarget::Register  
 Denetim bir OLE sürükle ve bırak işlemi hedefi olan tek olarak kaydeder.  
  
```  
BOOL Register(CMFCBaseTabCtrl *pOwner);
```  
  
### <a name="parameters"></a>Parametreler  
  
|||  
|-|-|  
|Parametre|Açıklama|  
|[in] *pOwner*|Bırakma hedefi olarak kaydetmek için sekme denetimi.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) sürükle ve bırak işlemleri için Denetim kaydetmek için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Sınıfları](../../mfc/reference/mfc-classes.md)   
 [Sürükleme ve Bırakma (OLE)](../../mfc/drag-and-drop-ole.md)



