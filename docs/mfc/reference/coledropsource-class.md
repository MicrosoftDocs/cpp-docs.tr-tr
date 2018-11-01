---
title: COleDropSource sınıfı
ms.date: 11/04/2016
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
ms.openlocfilehash: 51d524054b67a5cecc5aa7791b0aeea0cc076813
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50457791"
---
# <a name="coledropsource-class"></a>COleDropSource sınıfı

Bir bırakma hedefine sürüklenmesi veri sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDropSource::COleDropSource](#coledropsource)|Oluşturur bir `COleDropSource` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDropSource::GiveFeedback](#givefeedback)|İmleç bir Sürükle ve bırak işlemi sırasında değiştirir.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|Bir Sürükle ve bırak işlemi sırasında fare yakalamayı işler.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Sürükleme olup olmadığını görmek için denetimleri devam etmelidir.|

## <a name="remarks"></a>Açıklamalar

[COleDropTarget](../../mfc/reference/coledroptarget-class.md) sınıfı sürükle ve bırak işlemi alıcı bölümünü işler. `COleDropSource` Nesne, belirlenmesi sürükleme işlemi başladığı, sürükleme işlemi sırasında geribildirim sağlama ve belirlenmesi sürükleme işlemi sona erdiğinde sorumludur.

Kullanılacak bir `COleDropSource` nesne, yalnızca oluşturucusunu çağırın. Bu bir fare tıklaması gibi hangi olayların bir sürükleme işlemi kullanmaya başlamak belirleme işlemini basitleştiren [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), veya [ COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) işlevi. Bu işlevler oluşturacak bir `COleDropSource` nesnesi. Varsayılan davranışını değiştirmek isteyebileceğiniz `COleDropSource` geçersiz kılınabilir işlevler. Bu üye işlevleri uygun zamanlarda çerçevesi tarafından çağrılır.

Sürükle ve bırak işlemleri hakkında daha fazla bilgi için OLE kullanarak makaleye bakın [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).

Daha fazla bilgi için [IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource) Windows SDK.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxole.h

##  <a name="coledropsource"></a>  COleDropSource::COleDropSource

Oluşturur bir `COleDropSource` nesne.

```
COleDropSource();
```

##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback

Çağırdıktan sonra framework tarafından çağırılır [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) veya [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Parametreler

*dropEffect*<br/>
Bu noktada seçilen verileri içeren bir açılan oluştu kullanıcıya göstermek istediğiniz etkisi, genellikle ne belirten gerçekleşir. Bu en son çağrı tarafından döndürülen değer genellikle [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) veya [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Bir veya daha fazlasını olabilir:

- DROPEFFECT_NONE bırakma izin.

- DROPEFFECT_COPY bir kopyalama işlemi gerçekleştirilmesi.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilmesi.

- Özgün veriler bırakılan verilerden DROPEFFECT_LINK bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL bir sürükleme kaydırma işlemi gerçekleşmek üzere olduğunu veya hedef gerçekleşiyor.

### <a name="return-value"></a>Dönüş Değeri

Sürükleme, DRAGDROP_S_USEDEFAULTCURSORS değilse NOERROR devam ediyor döndürür.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir açılan bu noktada oluştuysa ne olacağını hakkında geri bildirim sağlamak için bu işlevi geçersiz kılar. Varsayılan uygulama OLE varsayılan işaretçiler kullanır. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için OLE kullanarak makaleye bakın [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).

Daha fazla bilgi için [IDropSource::GiveFeedback](/windows/desktop/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::DragOver](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragover), ve [IDropTarget::DragEnter](/windows/desktop/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK.

##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag

Çağıran bir olay oluştuğunda framework sol fare tuşuna basmak gibi bir sürükleme işlemi gelebilecek.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Seçili verileri içeren bir pencere işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sürükleyerek izin veriliyorsa, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemi başlatılmadan biçimini değiştirmek istiyorsanız, bu işlev geçersiz kılar. Varsayılan uygulama, fare yakalar ve kullanıcı sol veya sağ fare düğmesine tıklar veya isteğe bağlı olarak, aynı zamanda fare sürümleri, ESC İsabetleri kadar sürükleyin modda kalır.

##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag

Sürüklemeye sonra sürükleme işlemi ya da iptal tamamlandı veya sonlandırılana kadar bu işlev art arda framework tarafından çağırılır.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Parametreler

*bEscapePressed*<br/>
ESC tuşuna son çağrısından sonra basıldığını olup olmadığını belirten `COleDropSource::QueryContinueDrag`.

*dwKeyState*<br/>
Değiştirici tuşlarını durumunu içerir. Bu, aşağıdaki herhangi bir sayıda oluşur: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

### <a name="return-value"></a>Dönüş Değeri

Sağ düğme ve ESC tuşuna basılı ya da sol düğme DRAGDROP_S_CANCEL başlatır sürüklemeden önce ortaya çıkar. Bir bırakma işlemi gerçekleşirse DRAGDROP_S_DROP. Aksi S_OK.

### <a name="remarks"></a>Açıklamalar

Bu işlev, hangi sürükleyerek noktası değiştirmek istiyorsanız İptal geçersiz kılma veya bırakma oluşur.

Varsayılan uygulama açılır başlatır veya sürükleme şu şekilde iptal eder. ESC tuşunu veya sağ fare düğmesine basıldığında bir sürükleme işlemi iptal eder. Farenin sol düğmesine sürükleyerek başlatıldıktan sonra ortaya çıktığında bir bırakma işlemi başlatır. Aksi takdirde S_OK döndürür ve başka işlem gerçekleştirir.

Bu işlev sık çağrıldığından, mümkün olduğunca hale getirilmiştir.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek HIERSVR](../../visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)

