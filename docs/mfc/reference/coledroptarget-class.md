---
title: COleDropTarget sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDropTarget
- AFXOLE/COleDropTarget
- AFXOLE/COleDropTarget::COleDropTarget
- AFXOLE/COleDropTarget::OnDragEnter
- AFXOLE/COleDropTarget::OnDragLeave
- AFXOLE/COleDropTarget::OnDragOver
- AFXOLE/COleDropTarget::OnDragScroll
- AFXOLE/COleDropTarget::OnDrop
- AFXOLE/COleDropTarget::OnDropEx
- AFXOLE/COleDropTarget::Register
- AFXOLE/COleDropTarget::Revoke
helpviewer_keywords:
- COleDropTarget [MFC], COleDropTarget
- COleDropTarget [MFC], OnDragEnter
- COleDropTarget [MFC], OnDragLeave
- COleDropTarget [MFC], OnDragOver
- COleDropTarget [MFC], OnDragScroll
- COleDropTarget [MFC], OnDrop
- COleDropTarget [MFC], OnDropEx
- COleDropTarget [MFC], Register
- COleDropTarget [MFC], Revoke
ms.assetid: a58c9a48-6a93-4357-b078-4594df258311
ms.openlocfilehash: 127245385ebd89e51a1cc77d1efaa16729d73fe7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57300134"
---
# <a name="coledroptarget-class"></a>COleDropTarget sınıfı

Bir pencere ve OLE kitaplıkları arasındaki iletişim mekanizmasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDropTarget::COleDropTarget](#coledroptarget)|Oluşturur bir `COleDropTarget` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDropTarget::OnDragEnter](#ondragenter)|İmleç ilk kez pencereye girdiğinde çağırılır.|
|[COleDropTarget::OnDragLeave](#ondragleave)|İmleç pencerenin dışında sürüklendiğinde çağırılır.|
|[COleDropTarget::OnDragOver](#ondragover)|İmleç pencerenin üstünden ne zaman sürüklediğiniz art arda çağrılır.|
|[COleDropTarget::OnDragScroll](#ondragscroll)|İmleç pencerenin kaydırma bölgeye sürüklediğiniz olup olmadığını belirlemek için çağrılır.|
|[COleDropTarget::OnDrop](#ondrop)|Pencereye, varsayılan işleyici veri kesildiğinde çağrılır.|
|[COleDropTarget::OnDropEx](#ondropex)|Pencereye, ilk işleyici veri kesildiğinde çağrılır.|
|[COleDropTarget::Register](#register)|Pencerenin geçerli bırakma hedefi olarak kaydeder.|
|[COleDropTarget::Revoke](#revoke)|Pencerenin geçerli bırakma hedefi olan durdurmasına neden olur.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın bir nesnesi oluşturulurken OLE sürükle ve bırak mekanizma aracılığıyla verileri kabul etmek bir pencere sağlar.

DROP komutu kabul etmek için bir pencere elde etmek için önce bir nesne oluşturmanız gerekir `COleDropTarget` sınıfı ve sonra çağrı [kaydetme](#register) istenen işaretçisi işleviyle `CWnd` tek parametre olarak nesne.

Sürükle ve bırak işlemleri hakkında daha fazla bilgi için OLE kullanarak makaleye bakın [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="coledroptarget"></a>  COleDropTarget::COleDropTarget

Sınıfın bir nesnesi oluşturur `COleDropTarget`.

```
COleDropTarget();
```

### <a name="remarks"></a>Açıklamalar

Çağrı [kaydetme](#register) bu nesne bir pencere ile ilişkilendirmek için.

##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter

İmleç ilk kez pencereye sürüklendiğinde framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmleç pencerenin noktalarına girdiğinden.

*pDataObject*<br/>
Bırakılabilir verileri içeren veri nesnesi işaret eder.

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
İstemci koordinatları imleç geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bir bırakma bulunulması durumunda ortaya çıkabilecek etkisi *noktası*. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL bir sürükleme kaydırma işlemi gerçekleşmek üzere olduğunu veya hedef gerçekleşiyor.

### <a name="remarks"></a>Açıklamalar

Bırakma işlemleri penceresinde gerçekleşecek şekilde izin vermek için bu işlevi geçersiz kılar. Varsayılan Uygulama çağrıları [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), yalnızca döndüren DROPEFFECT_NONE varsayılan olarak.

Daha fazla bilgi için [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK.

##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave

İmleç pencerenin ayrılırken bir sürükleme işlemi etkin durumdayken framework tarafından çağırılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Pencerenin işaret imleç ayrılıyor.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemi belirtilen pencere ayrıldığında özel davranış istiyorsanız bu işlev yok sayın. Bu işlev varsayılan uygulamasını çağırır [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).

Daha fazla bilgi için [IDropTarget::DragLeave](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragleave) Windows SDK.

##  <a name="ondragover"></a>  COleDropTarget::OnDragOver

İmleç pencerenin üstünden sürüklendiğinde framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmleç üzerinden penceresi işaret eder.

*pDataObject*<br/>
Bırakılmasına verileri içeren veri nesneyi işaret eder.

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
İstemci koordinatları imleç geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bir bırakma bulunulması durumunda ortaya çıkabilecek etkisi *noktası*. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi gerçekleşmek üzere olan veya hedef oluştuğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev penceresinde gerçekleşecek şekilde bırakma işlemleri izin vermek için geçersiz. Bu işlev varsayılan uygulamasını çağırır [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), varsayılan olarak DROPEFFECT_NONE döndürür. Bu işlev, bir Sürükle ve bırak işlemi sırasında sık çağrıldığından, mümkün olduğunca hale getirilmiştir.

Daha fazla bilgi için [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll

Çağırmadan önce framework tarafından çağırılır [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) belirlemek için olup olmadığını *noktası* kaydırma alanında olup.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmleç o sırada üzerinde olduğu penceresi işaret eder.

*dwKeyState*<br/>
Değiştirici tuşları durumunu içerir. Bu, aşağıdaki herhangi bir sayıda birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Noktası*<br/>
İmleç, piksel cinsinden ekranına göre konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bir bırakma bulunulması durumunda ortaya çıkabilecek etkisi *noktası*. Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi gerçekleşmek üzere olan veya hedef oluştuğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlev geçersiz kılar. Bu işlev varsayılan uygulamasını çağırır [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), DROPEFFECT_NONE döndürür ve imleç varsayılan kaydırma bölgesi içinde kenarlık penceresinin içine sürüklendiğinde pencereye kaydırır.

##  <a name="ondrop"></a>  COleDropTarget::OnDrop

Bir bırakma işlemi meydana geldiğinde framework tarafından çağırılır.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmleç o sırada üzerinde olduğu penceresi işaret eder.

*pDataObject*<br/>
Bırakılmasına verileri içeren veri nesneyi işaret eder.

*dropEffect*<br/>
Bırakma işlemi için kullanıcının seçtiği efekti. Bir veya daha fazlasını olabilir:

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

*Noktası*<br/>
İmleç, piksel cinsinden ekranına göre konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Açılan başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Framework ilk çağrı [OnDropEx](#ondropex). Varsa `OnDropEx` işlevi açılan işlemez, framework daha sonra bu üye işlevini çağırır `OnDrop`. Genellikle, uygulama geçersiz kılmalar [OnDropEx](../../mfc/reference/cview-class.md#ondropex) sağ fare düğmesi işlemek için view sınıfı, sürükle ve bırak. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak işlemek için kullanılır.

Varsayılan uygulaması `COleDropTarget::OnDrop` çağrıları [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), yalnızca döndüren FALSE varsayılan olarak.

Daha fazla bilgi için [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK.

##  <a name="ondropex"></a>  COleDropTarget::OnDropEx

Bir bırakma işlemi meydana geldiğinde framework tarafından çağırılır.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmleç o sırada üzerinde olduğu penceresi işaret eder.

*pDataObject*<br/>
Bırakılmasına verileri içeren veri nesneyi işaret eder.

*dropDefault*<br/>
Geçerli anahtar durumunu temel alan varsayılan bırakma işlemi için kullanıcının seçtiği efekti. DROPEFFECT_NONE olabilir. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

*Listeyi*<br/>
Bırakma kaynağı destekleyen bırakma etkileri listesi. Bit düzeyinde OR kullanarak doğrudan etkisi değerleri birleştirilebilir (**&#124;**) işlemi. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

*Noktası*<br/>
İmleç, piksel cinsinden ekranına göre konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen konumda bırakma denemesi kullanmasından bırakma etkisi *noktası*. Bırakma etkileri açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Framework, önce bu işlevi çağırır. Açılan işlemez, framework sonra çağıran [OnDrop](#ondrop). Genellikle, kılar [OnDropEx](../../mfc/reference/cview-class.md#ondropex) sağ fare düğmesi desteklemek için view sınıfı, sürükle ve bırak. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak desteği durumu işlemek için kullanılır.

Varsayılan uygulaması `COleDropTarget::OnDropEx` çağrıları [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). Varsayılan olarak, [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) basitçe belirtmek için bir kukla değer döndürür [OnDrop](#ondrop) üye işlevi çağrılabilir.

Bir bırakma işlemi ile ilişkili eylemi açılan etkileri açıklanmaktadır. Bırakma etkileri aşağıdaki listeye bakın:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL sürükleme kaydırma işlemi gerçekleşmek üzere olan veya hedef oluştuğunu gösterir.

Daha fazla bilgi için [IDropTarget::Drop](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-drop) Windows SDK.

##  <a name="register"></a>  COleDropTarget::Register

OLE DLL'leri geçerli bırakma hedefi olarak pencerenizi kaydetmek için bu işlevi çağırın.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bir bırakma hedefi kaydedilecek olan pencerenin işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu işlev, kabul edilmesi bırakma işlemleri için çağrılmalıdır.

Daha fazla bilgi için [RegisterDragDrop](/windows/desktop/api/ole2/nf-ole2-registerdragdrop) Windows SDK.

##  <a name="revoke"></a>  COleDropTarget::Revoke

Bir çağrı yoluyla bir bırakma hedefi olarak kayıtlı herhangi bir pencere yok etme öncesinde bu işlevi çağırın [kaydetme](#register) bırakma hedefleri listesinden kaldırmak için.

```
virtual void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev otomatik olarak çağrılır [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) genellikle bu işlevi açıkça çağırmak gerekli değildir, kaydedildiği pencere işleyicisi.

Daha fazla bilgi için [RevokeDragDrop](/windows/desktop/api/ole2/nf-ole2-revokedragdrop) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource Sınıfı](../../mfc/reference/coledropsource-class.md)
