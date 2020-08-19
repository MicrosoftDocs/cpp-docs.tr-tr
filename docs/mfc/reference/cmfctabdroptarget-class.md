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
ms.openlocfilehash: d1a521f8ac0a33dbc59d789e506ac1dd9c906e3e
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88562057"
---
# <a name="cmfctabdroptarget-class"></a>CMFCTabDropTarget sınıfı

Sekme denetimi ve OLE kitaplıkları arasındaki iletişim mekanizmasını sağlar.

## <a name="syntax"></a>Syntax

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
|[CMFCTabDropTarget:: OnDragEnter](#ondragenter)|Kullanıcı bir nesneyi sekme penceresine sürüklediğinde Framework tarafından çağırılır. ( [COleDropTarget:: OnDragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter)geçersiz kılar.)|
|[CMFCTabDropTarget:: OnDragLeave](#ondragleave)|Kullanıcı odağı olan sekme penceresinin dışına bir nesneyi sürüklediğinde Framework tarafından çağırılır. ( [COleDropTarget:: OnDragLeave](../../mfc/reference/coledroptarget-class.md#ondragleave)geçersiz kılar.)|
|[CMFCTabDropTarget:: Ondragon](#ondragover)|Kullanıcı bir nesneyi odağı olan sekme penceresine sürüklediğinde Framework tarafından çağırılır. ( [COleDropTarget:: OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover)geçersiz kılar.)|
|[CMFCTabDropTarget:: OnDropEx](#ondropex)|Kullanıcı bir sürükleme işleminin sonundaki fare düğmesini bıraktığında Framework tarafından çağırılır. ( [COleDropTarget:: OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex)geçersiz kılar.)|
|[CMFCTabDropTarget:: yazmaç](#register)|Denetimi OLE sürükle ve bırak işleminin hedefi olabilecek bir tane olarak kaydeder.|

### <a name="remarks"></a>Açıklamalar

Bu sınıf, sınıfa sürükle ve bırak desteği sağlar `CMFCBaseTabCtrl` . Uygulamanız, [Afxoleinit](ole-initialization.md#afxoleinit) IŞLEVINI kullanarak OLE kitaplıklarını başlattığında, `CMFCBaseTabCtrl` nesneler sürükle ve bırak işlemleri için kendilerini kaydeder.

`CMFCTabDropTarget`Sınıf, bir sürükleme işlemi etkin olduğunda imlecin altında bulunan sekmeyi yaparak temel sınıfını genişletir. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için bkz. [OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCTabDropTarget` ve metodunu nasıl kullanacağınızı gösterir `Register` .

[!code-cpp[NVC_MFC_RibbonApp#39](../../mfc/reference/codesnippet/cpp/cmfctabdroptarget-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[COleDropTarget](../../mfc/reference/coledroptarget-class.md)

[CMFCTabDropTarget](../../mfc/reference/cmfctabdroptarget-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxbasetabctrl. h

## <a name="cmfctabdroptargetondragenter"></a><a name="ondragenter"></a> CMFCTabDropTarget:: OnDragEnter

Kullanıcı bir nesneyi sekme penceresine sürüklediğinde Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Kullanılmayan.

*pDataObject*\
'ndaki Kullanıcının sürüklediği nesneye yönelik bir işaretçi.

*dwKeyState*\
'ndaki Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*\
'ndaki İmlecin istemci koordinatlarındaki konumu.

### <a name="return-value"></a>Dönüş Değeri

Bırakma, *işaret*tarafından belirtilen konumda gerçekleşirse oluşur. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Araç çubuğu çerçevesi özelleştirme modunda değilse veya Pano veri biçimi kullanılamıyorsa, bu yöntem DROPEFFECT_NONE döndürür. Aksi halde, belirtilen parametrelerle çağırmanın sonucunu döndürür `CMFCBaseTabCtrl::OnDragEnter` .

Özelleştirme modu hakkında daha fazla bilgi için bkz. [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [Copadataobject:: IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondragleave"></a><a name="ondragleave"></a> CMFCTabDropTarget:: OnDragLeave

Kullanıcı odağı olan sekme penceresinin dışına bir nesneyi sürüklediğinde Framework tarafından çağırılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Kullanılmayan.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCBaseTabCtrl::OnDragLeave` sürükleme işlemini gerçekleştirmek için yöntemini çağırır.

## <a name="cmfctabdroptargetondragover"></a><a name="ondragover"></a> CMFCTabDropTarget:: Ondragon

Kullanıcı bir nesneyi odağı olan sekme penceresine sürüklediğinde Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Kullanılmayan.

*pDataObject*\
'ndaki Kullanıcının sürüklediği nesneye yönelik bir işaretçi.

*dwKeyState*\
'ndaki Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*\
'ndaki İstemci koordinatlarındaki fare işaretçisinin konumu.

### <a name="return-value"></a>Dönüş Değeri

Bırakma, *işaret*tarafından belirtilen konumda gerçekleşirse oluşur. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntem, bir sürükleme işlemi etkin olduğunda imlecin altında yer alan sekmeyi yapar. Araç çubuğu çerçevesi özelleştirme modunda değilse veya Pano veri biçimi kullanılamıyorsa DROPEFFECT_NONE döndürür. Aksi halde, belirtilen parametrelerle çağırmanın sonucunu döndürür `CMFCBaseTabCtrl::OnDragOver` .

Özelleştirme modu hakkında daha fazla bilgi için bkz. [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [Copadataobject:: IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetondropex"></a><a name="ondropex"></a> CMFCTabDropTarget:: OnDropEx

Kullanıcı bir sürükleme işleminin sonundaki fare düğmesini bıraktığında Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*\
'ndaki Kullanılmayan.

*pDataObject*\
'ndaki Kullanıcının sürüklediği nesneye yönelik bir işaretçi.

*dropEffect*\
'ndaki Varsayılan bırakma işlemi.

*Açılan liste*\
'ndaki Kullanılmayan.

*seçeneğinin*\
'ndaki İstemci koordinatlarındaki fare işaretçisinin konumu.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan bırakma efekti. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE

- DROPEFFECT_COPY

- DROPEFFECT_MOVE

- DROPEFFECT_LINK

- DROPEFFECT_SCROLL

### <a name="remarks"></a>Açıklamalar

Bu yöntem `CMFCBaseTabCtrl::OnDrop` , araç çubuğu çerçevesi özelleştirme modundaysa ve Pano veri biçimi kullanılabilir olduğunda çağırır. Çağrısı `CMFCBaseTabCtrl::OnDrop` sıfır dışında bir değer döndürürse, bu yöntem *DROPEFFECT*tarafından belirtilen varsayılan bırakma efektini döndürür. Aksi takdirde, bu yöntem DROPEFFECT_NONE döndürür. Bırakma efektleri hakkında daha fazla bilgi için bkz. [COleDropTarget:: OnDropEx](../../mfc/reference/coledroptarget-class.md#ondropex).

Özelleştirme modu hakkında daha fazla bilgi için bkz. [CMFCToolBar:: IsCustomizeMode](../../mfc/reference/cmfctoolbar-class.md#iscustomizemode). Pano veri biçimleri hakkında daha fazla bilgi için bkz. [Copadataobject:: IsDataAvailable](../../mfc/reference/coledataobject-class.md#isdataavailable).

## <a name="cmfctabdroptargetregister"></a><a name="register"></a> CMFCTabDropTarget:: yazmaç

Denetimi OLE sürükle ve bırak işleminin hedefi olabilecek bir tane olarak kaydeder.

```
BOOL Register(CMFCBaseTabCtrl *pOwner);
```

### <a name="parameters"></a>Parametreler

*pOwner*\
'ndaki Bırakma hedefi olarak kaydolmak için sekme denetimi.

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, sürükle ve bırak işlemleri için denetimi kaydetmek üzere [COleDropTarget:: Register](../../mfc/reference/coledroptarget-class.md#register) öğesini çağırır.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)
