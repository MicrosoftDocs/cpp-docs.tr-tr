---
title: COleDropSource Sınıfı
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
ms.openlocfilehash: 324c4b7273f021b43c319fb0a494ac843856c78a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375019"
---
# <a name="coledropsource-class"></a>COleDropSource Sınıfı

Verilerin bırakma hedefine sürüklenmesine izin verir.

## <a name="syntax"></a>Sözdizimi

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDropSource::COleDropSource](#coledropsource)|Bir `COleDropSource` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDropSource::GiveFeedback](#givefeedback)|Sürükle ve bırak işlemi sırasında imleci değiştirir.|
|[COleDropSource::OnBeginDrag](#onbegindrag)|Sürükle ve bırak işlemi sırasında fare yakalama yı işler.|
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Sürüklemenin devam edip etmeyeceğini denetler.|

## <a name="remarks"></a>Açıklamalar

[COleDropTarget](../../mfc/reference/coledroptarget-class.md) sınıfı sürükle ve bırak işleminin alıcı kısmını işler. Nesne, `COleDropSource` sürükleme işleminin ne zaman başlayacağını belirlemek, sürükleme işlemi sırasında geri bildirim sağlamak ve sürükleme işleminin ne zaman sona erdirileni belirlemekten sorumludur.

Bir `COleDropSource` nesneyi kullanmak için oluşturucuyu aramaniz gereken bir nesnedir. Bu, fare tıklaması gibi hangi olayların [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), veya [COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) işlevini kullanarak sürükleme işlemine başlama işlemini belirleme işlemini kolaylaştırır. Bu işlevler `COleDropSource` sizin için bir nesne oluşturur. Geçersiz kılınabilir işlevlerin varsayılan `COleDropSource` davranışını değiştirmek isteyebilirsiniz. Bu üye işlevler çerçeve tarafından uygun zamanlarda çağrılacaktır.

OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi [için, OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

Daha fazla bilgi için Windows SDK'daki [IDropSource'a](/windows/win32/api/oleidl/nn-oleidl-idropsource) bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledropsourcecoledropsource"></a><a name="coledropsource"></a>COleDropSource::COleDropSource

Bir `COleDropSource` nesne inşa eder.

```
COleDropSource();
```

## <a name="coledropsourcegivefeedback"></a><a name="givefeedback"></a>COleDropSource::GiveFeedback

COleDropTarget aradıktan sonra çerçeve tarafından [çağrılan::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) veya [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Parametreler

*dropEffect*<br/>
Kullanıcıya görüntülemek istediğiniz efekt, genellikle seçili verilerle bu noktada bir düşüş meydana gelirse ne olacağını gösterir. Genellikle bu değer, CView'e yapılan en son çağrıyla döndürülen [değerdir::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) veya [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işlemi gelmek üzere veya hedefte meydana gelmek üzeredir.

### <a name="return-value"></a>Dönüş Değeri

Sürükleme devam ediyorsa DRAGDROP_S_USEDEFAULTCURSORS döndürür, değilse NOERROR.

### <a name="remarks"></a>Açıklamalar

Bu noktada bir düşüş meydana gelirse ne olacağı hakkında kullanıcıya geri bildirim sağlamak için bu işlevi geçersiz kılın. Varsayılan uygulama OLE varsayılan imleçleri kullanır. OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi [için, OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

Daha fazla bilgi için, [Bkz. IDropSource::GiveFeedback](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [IDropTarget::DragOver](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover), ve [IDropTarget::DragEnter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK.'ya.

## <a name="coledropsourceonbegindrag"></a><a name="onbegindrag"></a>COleDropSource::OnBeginDrag

Sol fare düğmesine basmak gibi sürükleme işlemine başlabilen bir olay gerçekleştiğinde çerçeve tarafından çağrılır.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Seçili verileri içeren pencereyi işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Sürüklemeye izin veriliyorsa sıfır yok, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işleminin başlatılma biçimini değiştirmek istiyorsanız bu işlevi geçersiz kılın. Varsayılan uygulama fareyi yakalar ve kullanıcı sol veya sağ fare düğmesini tıklatana veya ESC'ye ulaşana kadar sürükleme modunda kalır ve fareyi serbest bırakır.

## <a name="coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a>COleDropSource::QueryContinueDrag

Sürükleme başladıktan sonra, sürükleme işlemi iptal edilene veya tamamlanana kadar bu işlev çerçeve tarafından tekrar tekrar çağrılır.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Parametreler

*bEscapePressed*<br/>
SON çağrıdan bu yana ESC tuşuna `COleDropSource::QueryContinueDrag`basılıp basılmayacağını belirtir.

*dwKeyState*<br/>
Klavyedeki değiştirici tuşlarının durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

### <a name="return-value"></a>Dönüş Değeri

DRAGDROP_S_CANCEL ESC tuşuna veya sağ tuşuna basıldığında veya sürükleme başlamadan önce sol düğmeye basılırsa. bir bırakma işlemi meydana gelirse DRAGDROP_S_DROP. Aksi takdirde S_OK.

### <a name="remarks"></a>Açıklamalar

Sürüklemenin iptal edildiği veya bir düşüş oluştuğu noktayı değiştirmek istiyorsanız bu işlevi geçersiz kılın.

Varsayılan uygulama bırakma başlatır veya aşağıdaki gibi sürükleme iptal eder. ESC tuşuna veya sağ fare düğmesine basıldığında sürükleme işlemini iptal eder. Sürükleme başladıktan sonra sol fare düğmesi yükseltildiğinde bir bırakma işlemi başlatır. Aksi takdirde, S_OK döndürür ve başka işlem gerçekleştirmez.

Bu işlev sık çağrıldığı için, mümkün olduğunca en iyi duruma getirilmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)
