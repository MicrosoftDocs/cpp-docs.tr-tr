---
title: CMFCTabDropTarget Sınıfı
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
ms.openlocfilehash: 83432fdb90fe28214fb1faaf843556deb2f44750
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367352"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget Sınıfı

Sekme denetimi ile OLE kitaplıkları arasındaki iletişim mekanizmasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CMFCTabDropTarget : public COleDropTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|||
|-|-|
|Adı|Açıklama|
|`CMFCTabDropTarget::CMFCTabDropTarget`|Varsayılan oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|||
|-|-|
|Adı|Açıklama|
|[CMFCTabDropTarget::Ondragenter](#ondragenter)|Kullanıcı bir nesneyi sekme penceresine sürüklediğinde çerçeve tarafından çağrılır. (Geçersiz kılar [COleDropTarget::OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).)|
|[CMFCTabDropTarget::OndragLeave](#ondragleave)|Kullanıcı, odağı olan sekme penceresinin dışına bir nesne sürüklediğinde çerçeve tarafından çağrılır. [(Overrides COleDropTarget::OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave).)|
|[CMFCTabDropTarget::Ondragover](#ondragover)|Kullanıcı bir nesneyi odağı olan sekme penceresine sürüklediğinde çerçeve tarafından çağrılır. (Geçersiz kılar [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover).)|
|[CMFCTabDropTarget::Ondropex](#ondropex)|Kullanıcı sürükleme işleminin sonunda fare düğmesini serbest bıraktığunda çerçeve tarafından çağrılır. [(Overrides COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).)|
|[CMFCTabDropTarget::Kayıt Ol](#register)|Denetimi, OLE sürükle ve bırak işleminin hedefi olabilecek bir denetim olarak kaydeder.|

### <a name="remarks"></a>Açıklamalar

Bu `CMFCBaseTabCtrl` sınıf, sınıfa sürükle ve bırak desteği sağlar. Uygulamanız [AfxOleInit](ole-initialization.md#afxoleinit) işlevini kullanarak OLE kitaplıklarını `CMFCBaseTabCtrl` başlatırsa, nesneler sürükle ve bırak işlemleri için kendilerini kaydeder.

Bir `CMFCTabDropTarget` sürükleme işlemi etkin olduğunda imlecin altındaki sekmeyi yaparak sınıf taban sınıfını genişletir. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için [OLE sürükle ve bırak'a](../../mfc/drag-and-drop-ole.md)bakın.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCTabDropTarget` nesnenin nasıl oluşturup yöntemini nasıl kullanılacağını `Register` gösterir.

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetabctrl.h

## <a name="cmfctabdroptargetondragenter"></a><a name="ondragenter"></a>CMFCTabDropTarget::Ondragenter

Kullanıcı bir nesneyi sekme penceresine sürüklediğinde çerçeve tarafından çağrılır.

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
|*Pwnd*|[içinde] Kullanılma -yan.|
|*pDataObject*|[içinde] Kullanıcının sürüklediği nesneye işaretçi.|
|*dwKeyState*|[içinde] Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.|
|*Nokta*|[içinde] İmlecin istemci koordinatlarında konumu.|

### <a name="return-value"></a>Dönüş Değeri

Damla *noktası*tarafından belirtilen yerde oluşursa sonuçları etkisi. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Araç çubuğu çerçevesi özelleştirme modunda değilse veya Pano veri biçimi kullanılamıyorsa, bu yöntem DROPEFFECT_NONE döndürür. Aksi takdirde, sağlanan parametreleri ile arama `CMFCBaseTabCtrl::OnDragEnter` sonucu döndürür.

Özelleştirme modu hakkında daha fazla bilgi için [CMFCToolBar::IsCustomizeMode'a](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)bakın. Pano veri biçimleri hakkında daha fazla bilgi için [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)' a bakın.

## <a name="cmfctabdroptargetondragleave"></a><a name="ondragleave"></a>CMFCTabDropTarget::OndragLeave

Kullanıcı, odağı olan sekme penceresinin dışına bir nesne sürüklediğinde çerçeve tarafından çağrılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*Pwnd*|[içinde] Kullanılma -yan.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCBaseTabCtrl::OnDragLeave` sürükleme işlemini gerçekleştirmek için yöntemi çağırır.

## <a name="cmfctabdroptargetondragover"></a><a name="ondragover"></a>CMFCTabDropTarget::Ondragover

Kullanıcı bir nesneyi odağı olan sekme penceresine sürüklediğinde çerçeve tarafından çağrılır.

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
|*Pwnd*|[içinde] Kullanılma -yan.|
|*pDataObject*|[içinde] Kullanıcının sürüklediği nesneye işaretçi.|
|*dwKeyState*|[içinde] Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.|
|*Nokta*|[içinde] İstemci koordinatlarında fare işaretçisinin konumu.|

### <a name="return-value"></a>Dönüş Değeri

Damla *noktası*tarafından belirtilen yerde oluşursa sonuçları etkisi. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir sürükleme işlemi etkin olduğunda imleç altında sekme yapar. Araç çubuğu çerçevesi özelleştirme modunda değilse veya Pano veri biçimi kullanılamıyorsa DROPEFFECT_NONE döndürür. Aksi takdirde, sağlanan parametreleri ile arama `CMFCBaseTabCtrl::OnDragOver` sonucu döndürür.

Özelleştirme modu hakkında daha fazla bilgi için [CMFCToolBar::IsCustomizeMode'a](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)bakın. Pano veri biçimleri hakkında daha fazla bilgi için [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)' a bakın.

## <a name="cmfctabdroptargetondropex"></a><a name="ondropex"></a>CMFCTabDropTarget::Ondropex

Kullanıcı sürükleme işleminin sonunda fare düğmesini serbest bıraktığunda çerçeve tarafından çağrılır.

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
|*Pwnd*|[içinde] Kullanılma -yan.|
|*pDataObject*|[içinde] Kullanıcının sürüklediği nesneye işaretçi.|
|*dropEffect*|[içinde] Varsayılan bırakma işlemi.|
|*dropList*|[içinde] Kullanılma -yan.|
|*Nokta*|[içinde] İstemci koordinatlarında fare işaretçisinin konumu.|

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan bırakma etkisi. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Araç çubuğu `CMFCBaseTabCtrl::OnDrop` çerçevesi özelleştirme modundaysa ve Pano veri biçimi kullanılabilirse, bu yöntem çağırır. Çağrı sıfır `CMFCBaseTabCtrl::OnDrop` olmayan bir değer döndürürse, bu yöntem dropEffect tarafından belirtilen varsayılan bırakma efektini *döndürür.* Aksi takdirde, bu yöntem DROPEFFECT_NONE döndürür. Damla efektleri hakkında daha fazla bilgi için [Bkz. COleDropTarget::OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).

Özelleştirme modu hakkında daha fazla bilgi için [CMFCToolBar::IsCustomizeMode'a](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode)bakın. Pano veri biçimleri hakkında daha fazla bilgi için [COleDataObject::IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable)' a bakın.

## <a name="cmfctabdroptargetregister"></a><a name="register"></a>CMFCTabDropTarget::Kayıt Ol

Denetimi, OLE sürükle ve bırak işleminin hedefi olabilecek bir denetim olarak kaydeder.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Parametreler

|||
|-|-|
|Parametre|Açıklama|
|*pSahibi*|[içinde] Açılan hedef olarak kaydolmak için sekme denetimi.|

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olduysa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem [COleDropTarget çağırır::Sürükle](../../mfc/reference/coledroptarget-class.md#register) ve bırak işlemleri için denetimi kaydetmek için kaydolun.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)
