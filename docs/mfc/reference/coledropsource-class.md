---
description: 'Daha fazla bilgi edinin: COleDropSource sınıfı'
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
ms.openlocfilehash: 069c1b2a3cb46f0824da55bca8e97041e9b0b2e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227149"
---
# <a name="coledropsource-class"></a>COleDropSource sınıfı

Verilerin bırakma hedefine sürüklenip olmasını sağlar.

## <a name="syntax"></a>Syntax

```
class COleDropSource : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[COleDropSource:: COleDropSource](#coledropsource)|Bir `COleDropSource` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDropSource:: GiveFeedback](#givefeedback)|Sürükle ve bırak işlemi sırasında imleci değiştirir.|
|[COleDropSource:: OnBeginDrag](#onbegindrag)|Sürükle ve bırak işlemi sırasında fare yakalamayı işler.|
|[COleDropSource:: QueryContinueDrag](#querycontinuedrag)|Sürüklemeye devam edip etmediğini kontrol eder.|

## <a name="remarks"></a>Açıklamalar

[COleDropTarget](../../mfc/reference/coledroptarget-class.md) sınıfı, sürükle ve bırak işleminin alan kısmını işler. `COleDropSource`Nesne bir sürükleme işleminin ne zaman başladığını, sürükleme işlemi sırasında geri bildirim sağlamayı ve sürükleme işleminin ne zaman sona ereceğini belirlemeyi sağlamaktan sorumludur.

Bir nesnesi kullanmak için `COleDropSource` , oluşturucuyu çağırmanız yeterlidir. Bu, fare tıklaması gibi olayları belirleme sürecini basitleştirir; [Cotadatasource::D oDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [cotaclienentidıtem::D odragdrop](../../mfc/reference/coleclientitem-class.md#dodragdrop)veya [copaserverıtem::D odragdrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) işlevini kullanarak bir sürükleme işlemine başlar. Bu işlevler `COleDropSource` , sizin için bir nesnesi oluşturur. Geçersiz kılınabilir işlevlerin varsayılan davranışını değiştirmek isteyebilirsiniz `COleDropSource` . Bu üye işlevleri, Framework tarafından uygun zamanlarda çağrılacaktır.

OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi için [OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

Daha fazla bilgi için Windows SDK içindeki [IDropSource](/windows/win32/api/oleidl/nn-oleidl-idropsource) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropSource`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

## <a name="coledropsourcecoledropsource"></a><a name="coledropsource"></a> COleDropSource:: COleDropSource

Bir `COleDropSource` nesnesi oluşturur.

```
COleDropSource();
```

## <a name="coledropsourcegivefeedback"></a><a name="givefeedback"></a> COleDropSource:: GiveFeedback

[COleDropTarget:: OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) veya [coledroptarget::D oygenter](../../mfc/reference/coledroptarget-class.md#ondragenter)çağrıldıktan sonra Framework tarafından çağırılır.

```
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```

### <a name="parameters"></a>Parametreler

*dropEffect*<br/>
Bu noktada seçili verileri içeren bir bırakma gerçekleştiyse ne olacağını belirten kullanıcıya göstermek istediğiniz etki. Genellikle bu, [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) veya [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover)için en son çağrı tarafından döndürülen değerdir. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- Bir sürükleme kaydırma işlemi DROPEFFECT_SCROLL gerçekleşmekte veya hedefte gerçekleşmekte.

### <a name="return-value"></a>Dönüş Değeri

Sürükleme işlemi devam ediyorsa, NOERROR DRAGDROP_S_USEDEFAULTCURSORS döndürür.

### <a name="remarks"></a>Açıklamalar

Bu noktada bir bırakma gerçekleştiyse ne olacağı hakkında kullanıcıya geri bildirim sağlamak için bu işlevi geçersiz kılın. Varsayılan uygulama, OLE varsayılan imleçler kullanır. OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi için [OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

Daha fazla bilgi için, Windows SDK içindeki [IDropSource:: GiveFeedback](/windows/win32/api/oleidl/nf-oleidl-idropsource-givefeedback), [ıdroptarget::D Ragover](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover)ve [IDropTarget::D segenter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) ' a bakın.

## <a name="coledropsourceonbegindrag"></a><a name="onbegindrag"></a> COleDropSource:: OnBeginDrag

Sol fare düğmesine basmak gibi bir sürükleme işlemine başlayabileceğiniz bir olay gerçekleştiğinde Framework tarafından çağırılır.

```
virtual BOOL OnBeginDrag(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Seçili verileri içeren pencereye işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Sürüklemeye izin veriliyorsa sıfır olmayan, değilse 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işleminin başlatılma şeklini değiştirmek istiyorsanız bu işlevi geçersiz kılın. Varsayılan uygulama, fareyi yakalar ve Kullanıcı sol veya sağ fare düğmesine tıklaana veya ESC isabetlerine kadar fareyi yayınladığı sürece sürükleme modunda kalır.

## <a name="coledropsourcequerycontinuedrag"></a><a name="querycontinuedrag"></a> COleDropSource:: QueryContinueDrag

Sürüklemeye başladıktan sonra, sürükleme işlemi iptal edilene veya tamamlanana kadar bu işlev çerçeve tarafından tekrar tekrar çağırılır.

```
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed,
    DWORD dwKeyState);
```

### <a name="parameters"></a>Parametreler

*Bescapebasıldı*<br/>
Son çağrısından sonra ESC tuşuna basıldığını belirtir `COleDropSource::QueryContinueDrag` .

*dwKeyState*<br/>
Klavyedeki değiştirici tuşlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

### <a name="return-value"></a>Dönüş Değeri

ESC tuşu veya sağ düğmesine basıldığında veya sürüklemeye başlamadan önce sol düğme tetiklenir DRAGDROP_S_CANCEL. Bir bırakma işlemi gerçekleşmemelidir DRAGDROP_S_DROP. Aksi takdirde S_OK.

### <a name="remarks"></a>Açıklamalar

Sürükleme işleminin iptal edildiği veya bir bırakma işleminin gerçekleştiği noktayı değiştirmek istiyorsanız bu işlevi geçersiz kılın.

Varsayılan uygulama, bırakmayı başlatır veya aşağıdaki şekilde sürüklemeyi iptal eder. ESC tuşuna veya farenin sağ düğmesine basıldığında bir sürükleme işlemini iptal eder. Sürükleme başladıktan sonra sol fare düğmesi başlatıldığında bir bırakma işlemi başlatır. Aksi takdirde, S_OK döndürür ve başka işlemler gerçekleştirmez.

Bu işlev sıklıkla çağrıldığı için mümkün olduğunca en iyi duruma getirilmesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)
