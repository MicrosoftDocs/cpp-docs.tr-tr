---
title: CMFCTabDropTarget sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragEnter
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragLeave
- AFXBASETABCTRL/CMFCTabDropTarget::OnDragOver
- AFXBASETABCTRL/CMFCTabDropTarget::OnDropEx
- AFXBASETABCTRL/CMFCTabDropTarget::Register
helpviewer_keywords:
- CMFCTabDropTarget [MFC], OnDragEnter
- CMFCTabDropTarget [MFC], OnDragLeave
- CMFCTabDropTarget [MFC], OnDragOver
- CMFCTabDropTarget [MFC], OnDropEx
- CMFCTabDropTarget [MFC], Register
ms.assetid: 9777b7b6-10da-4c4b-b1d1-7ea795b0f1cb
ms.openlocfilehash: 8b24d7679edfaab4d4eeb6d59770f30cd4253580
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303943"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget sınıfı

Sekme denetimi ve OLE kitaplıkları arasındaki iletişim mekanizmasını sağlar.

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
|[CMFCTabDropTarget::OnDragEnter](#ondragenter)|Bir sekme penceresine kullanıcı nesneyi sürüklediğinde framework tarafından çağırılır. (Geçersiz kılmaları [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[CMFCTabDropTarget::OnDragLeave](#ondragleave)|Kullanıcı odaklı sekmesi penceresi dışında bir nesneyi sürüklediğinde framework tarafından çağırılır. (Geçersiz kılmaları [COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[CMFCTabDropTarget::OnDragOver](#ondragover)|Kullanıcı bir nesne odaklı sekmesi penceresi sürüklediğinde framework tarafından çağırılır. (Geçersiz kılmaları [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[CMFCTabDropTarget::OnDropEx](#ondropex)|Kullanıcı bir sürükleme işlemi sonunda fare düğmesini bıraktığında framework tarafından çağırılır. (Geçersiz kılmaları [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[CMFCTabDropTarget::Register](#register)|Denetim bir OLE sürükle ve bırak işlemi hedefi olan tek olarak kaydeder.|

### <a name="remarks"></a>Açıklamalar

Sürükle ve bırak desteği için bu sınıfın sağladığı `CMFCBaseTabCtrl` sınıfı. Uygulamanızı kullanarak OLE kitaplıklarının başlatır, [Afxoleınit](ole-initialization.md#afxoleinit) işlevi `CMFCBaseTabCtrl` nesneleri kendileri için sürükle ve bırak işlemleri kaydedin.

`CMFCTabDropTarget` Sınıfı bir sürükleme işlemi etkin olduğunda imlecin altındaki sekmesi yaparak onun temel sınıfından genişletir. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için bkz. [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCTabDropTarget` nesne ve kullanmak, `Register` yöntemi.

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxbasetabctrl.h

##  <a name="ondragenter"></a>  CMFCTabDropTarget::OnDragEnter

Bir sekme penceresine kullanıcı nesneyi sürüklediğinde framework tarafından çağırılır.

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
|*pWnd*|[in] Kullanılmayan.|
|*pDataObject*|[in] Kullanıcının sürüklediği nesneye bir işaretçi.|
|*dwKeyState*|[in] Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.|
|*Noktası*|[in] İstemci koordinatları imleç konumu.|

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bırak ortaya çıkarsa, etkili *noktası*. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntem, araç framework özelleştirme modunda değilse veya Pano verileri biçimi kullanılamaz DROPEFFECT_NONE döndürür. Aksi takdirde, çağrılması sonucunu döndürür `CMFCBaseTabCtrl::OnDragEnter` belirtilen parametrelere sahip.

Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="ondragleave"></a>  CMFCTabDropTarget::OnDragLeave

Kullanıcı odaklı sekmesi penceresi dışında bir nesneyi sürüklediğinde framework tarafından çağırılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pWnd*|[in] Kullanılmayan.|

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı `CMFCBaseTabCtrl::OnDragLeave` sürükleme işlemi gerçekleştirmek için yöntemi.

##  <a name="ondragover"></a>  CMFCTabDropTarget::OnDragOver

Kullanıcı bir nesne odaklı sekmesi penceresi sürüklediğinde framework tarafından çağırılır.

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
|*pWnd*|[in] Kullanılmayan.|
|*pDataObject*|[in] Kullanıcının sürüklediği nesneye bir işaretçi.|
|*dwKeyState*|[in] Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.|
|*Noktası*|[in] Fare işaretçisi istemci koordinatlarına göre konumu.|

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bırak ortaya çıkarsa, etkili *noktası*. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir sürükleme işlemi etkin olduğunda, imlecin altındaki sekme yapar. Araç çubuğu framework özelleştirme modunda değilse veya Pano verileri biçimi kullanılamaz DROPEFFECT_NONE döndürür. Aksi takdirde, çağrılması sonucunu döndürür `CMFCBaseTabCtrl::OnDragOver` belirtilen parametrelere sahip.

Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="ondropex"></a>  CMFCTabDropTarget::OnDropEx

Kullanıcı bir sürükleme işlemi sonunda fare düğmesini bıraktığında framework tarafından çağırılır.

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
|*pWnd*|[in] Kullanılmayan.|
|*pDataObject*|[in] Kullanıcının sürüklediği nesneye bir işaretçi.|
|*dropEffect*|[in] Varsayılan bırakma işlemi.|
|*Listeyi*|[in] Kullanılmayan.|
|*Noktası*|[in] Fare işaretçisi istemci koordinatlarına göre konumu.|

### <a name="return-value"></a>Dönüş Değeri

Sonuçta elde edilen bırakma efekti. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı `CMFCBaseTabCtrl::OnDrop` özelleştirme modu araç çubuğu çerçevesidir ve Pano verileri biçimi kullanılabilir. Çağrı `CMFCBaseTabCtrl::OnDrop` sıfır dışında bir değeri, bu yöntem tarafından belirtilen varsayılan bırakma etkisi döndürür döndürür *dropEffect*. Aksi takdirde, bu yöntem DROPEFFECT_NONE döndürür. Bırakma etkileri hakkında daha fazla bilgi için bkz. [COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).

Özelleştirme modu hakkında daha fazla bilgi için bkz: [CMFCToolBar::IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

##  <a name="register"></a>  CMFCTabDropTarget::Register

Denetim bir OLE sürükle ve bırak işlemi hedefi olan tek olarak kaydeder.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pOwner*|[in] Bir bırakma hedefi kaydetmek için sekmesinde denetimi.|

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağırdığı [COleDropTarget::Register](../../mfc/reference/coledroptarget-class.md#register) denetimi sürükle ve bırak işlemleri için kaydedilecek.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Sürükleme ve Bırakma (OLE)](../../mfc/drag-and-drop-ole.md)
