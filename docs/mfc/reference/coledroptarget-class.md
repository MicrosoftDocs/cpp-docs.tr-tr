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
ms.openlocfilehash: f5f101ca2c505e1b7c6b50b21af7d5aeef4ae625
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127887"
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
|[COleDropTarget:: COleDropTarget](#coledroptarget)|`COleDropTarget` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[COleDropTarget:: OnDragEnter](#ondragenter)|İmleç ilk kez pencereye girdiğinde çağırılır.|
|[COleDropTarget:: OnDragLeave](#ondragleave)|İmleç pencerenin dışına sürüklendiğinde çağırılır.|
|[COleDropTarget:: Ondragon](#ondragover)|İmleç pencerenin üzerine sürüklendiğinde tekrar tekrar çağırılır.|
|[COleDropTarget:: OnDragScroll](#ondragscroll)|İmlecin pencerenin kaydırma bölgesine sürüklenip sürüklamayacağını anlamak için çağırılır.|
|[COleDropTarget:: OnDrop](#ondrop)|Veriler pencereye bırakıldığında çağırılır, varsayılan işleyici.|
|[COleDropTarget:: OnDropEx](#ondropex)|Veriler pencereye bırakıldığında çağırılır, ilk işleyici.|
|[COleDropTarget:: Register](#register)|Pencereyi geçerli bir bırakma hedefi olarak kaydeder.|
|[COleDropTarget:: Revoke](#revoke)|Pencerenin geçerli bir bırakma hedefi olarak kesilmesine neden olur.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın bir nesnesinin oluşturulması, bir pencerenin OLE sürükle ve bırak mekanizması aracılığıyla verileri kabul etmesine olanak tanır.

Bırakma komutlarının kabul edileceği bir pencere almak için, önce `COleDropTarget` sınıfının bir nesnesini oluşturmanız ve ardından [Kaydet](#register) işlevini yalnızca istenen `CWnd` nesnesine tek parametre olarak bir işaretçi ile çağırmanız gerekir.

OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi için [OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole. h

##  <a name="coledroptarget"></a>COleDropTarget:: COleDropTarget

`COleDropTarget`sınıfından bir nesne oluşturur.

```
COleDropTarget();
```

### <a name="remarks"></a>Açıklamalar

Bu nesneyi bir pencereyle ilişkilendirmek için [register](#register) çağrısı yapın.

##  <a name="ondragenter"></a>COleDropTarget:: OnDragEnter

İmleç pencereye ilk kez sürüklendiğinde Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmlecin girildiği pencereyi işaret eder.

*pDataObject*<br/>
Bırakılan verileri içeren veri nesnesine işaret eder.

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
İmlecin istemci koordinatlarındaki geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir bırakma denendiğinde ortaya bir sonuç verir. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- Bir sürükleme kaydırma işlemi DROPEFFECT_SCROLL gerçekleşmekte veya hedefte gerçekleşmekte.

### <a name="remarks"></a>Açıklamalar

Pencerede bırakma işlemlerinin oluşmasına izin vermek için bu işlevi geçersiz kılın. Varsayılan uygulama, yalnızca DROPEFFECT_NONE varsayılan olarak döndüren [CView:: OnDragEnter](../../mfc/reference/cview-class.md#ondragenter)çağırır.

Daha fazla bilgi için bkz. [IDropTarget::D Gengenter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) Windows SDK.

##  <a name="ondragleave"></a>COleDropTarget:: OnDragLeave

İmleç, bir sürükleme işlemi etkin durumdayken pencereden ayrıldığında, Framework tarafından çağırılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmlecin terk ettiği pencereyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemi belirtilen pencereyi terk ettiğinde özel bir davranış istiyorsanız bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulamasında [CView:: OnDragLeave](../../mfc/reference/cview-class.md#ondragleave)çağrılır.

Daha fazla bilgi için bkz. [IDropTarget::D ragLeave](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) Windows SDK.

##  <a name="ondragover"></a>COleDropTarget:: Ondragon

İmleç pencerenin üzerine sürüklendiğinde Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmlecin üzerinde bulunduğu pencereyi işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesine işaret eder.

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
İmlecin istemci koordinatlarındaki geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir bırakma denendiğinde ortaya bir sonuç verir. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin gerçekleşmekte olduğunu veya hedefte meydana geldiğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, bırakma işlemlerinin pencerede oluşmasına izin vermek için geçersiz kılınmalıdır. Bu işlevin varsayılan uygulanması, varsayılan olarak DROPEFFECT_NONE döndüren [CView:: OnDragOver](../../mfc/reference/cview-class.md#ondragover)' ı çağırır. Bu işlev bir sürükle ve bırak işlemi sırasında sık kullanıldığından, mümkün olduğunca en iyi duruma getirilmesi gerekir.

Daha fazla bilgi için, bkz. [IDropTarget::D ragOver](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

##  <a name="ondragscroll"></a>COleDropTarget:: OnDragScroll

*Noktanın* kaydırma bölgesinde olup olmadığını anlamak Için [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) çağrılmadan önce Framework tarafından çağırılır.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmlecin o anda üzerine bulunduğu pencereyi işaret eder.

*dwKeyState*<br/>
Değiştirici anahtarlarının durumunu içerir. Bu, aşağıdakilerden herhangi bir sayıda bir birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*seçeneğinin*<br/>
İmlecin, ekrana göre piksel cinsinden konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir bırakma denendiğinde ortaya bir sonuç verir. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin gerçekleşmekte olduğunu veya hedefte meydana geldiğini belirtir.

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulamasında [CView:: OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll)çağrılır. Bu, imleç pencerenin kenarlığının içindeki varsayılan kaydırma bölgesine sürüklendiğinde DROPEFFECT_NONE döndürür ve pencereyi kaydırır.

##  <a name="ondrop"></a>COleDropTarget:: OnDrop

Bir bırakma işlemi gerçekleştiğinde Framework tarafından çağırılır.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
İmlecin o anda üzerine bulunduğu pencereyi işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesine işaret eder.

*dropEffect*<br/>
Kullanıcının bırakma işlemi için seçtiği efekt. Aşağıdakilerden biri veya birkaçı olabilir:

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

*seçeneğinin*<br/>
İmlecin, ekrana göre piksel cinsinden konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

Bırakma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Framework ilk olarak [OnDropEx](#ondropex)öğesini çağırır. `OnDropEx` işlevi bırakmayı işlemezse, Framework bu üye işlevini çağırır `OnDrop`. Genellikle, uygulama sağ fare düğmesi sürükleyip bırakmayı işlemek için Görünüm sınıfındaki [OnDropEx](../../mfc/reference/cview-class.md#ondropex) öğesini geçersiz kılar. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak işlemek için kullanılır.

Varsayılan `COleDropTarget::OnDrop`, varsayılan olarak FALSE döndüren [CView:: OnDrop](../../mfc/reference/cview-class.md#ondrop)' ı çağırır.

Daha fazla bilgi için, Windows SDK içindeki [IDropTarget::D ROP](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) bölümüne bakın.

##  <a name="ondropex"></a>COleDropTarget:: OnDropEx

Bir bırakma işlemi gerçekleştiğinde Framework tarafından çağırılır.

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
İmlecin o anda üzerine bulunduğu pencereyi işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesine işaret eder.

*Varsayılan Drop*<br/>
Kullanıcının geçerli anahtar durumuna göre varsayılan bırakma işlemi için seçtiği efekt. DROPEFFECT_NONE olabilir. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

*Açılan liste*<br/>
Bırakma kaynağının desteklediği bırakma efektlerinin bir listesi. Bırakma efekti değerleri bit düzeyinde OR ( **&#124;** ) işlemi kullanılarak birleştirilebilir. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

*seçeneğinin*<br/>
İmlecin, ekrana göre piksel cinsinden konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*İşaret*tarafından belirtilen konumdaki bırakma denemesinden kaynaklanan bırakma etkisi. Bırakma etkileri, açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Framework ilk olarak bu işlevi çağırır. Bırakma işlemezse, çerçeve [OnDrop](#ondrop)'ı çağırır. Genellikle, sağ fare düğmesi sürükleyip bırakmayı desteklemek için Görünüm sınıfındaki [OnDropEx](../../mfc/reference/cview-class.md#ondropex) öğesini geçersiz kılacaksınız. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) , basit sürükle ve bırak desteğinin durumunu işlemek için kullanılır.

`COleDropTarget::OnDropEx` varsayılan uygulanması [CView:: OnDropEx](../../mfc/reference/cview-class.md#ondropex)çağırır. Varsayılan olarak, [CView:: OnDropEx](../../mfc/reference/cview-class.md#ondropex) yalnızca bir kukla değer döndürür ve [OnDrop](#ondrop) üye işlevinin çağrılması gerektiğini gösterir.

Bırakma etkileri, bir bırakma işlemiyle ilişkili eylemi anlatmaktadır. Aşağıdaki bırakma etkileri listesine bakın:

- DROPEFFECT_NONE bırakmaya izin verilmez.

- Kopyalama işlemi DROPEFFECT_COPY gerçekleştirilir.

- DROPEFFECT_MOVE bir taşıma işlemi gerçekleştirilecek.

- Bırakılan verilerden özgün verilere bir bağlantı DROPEFFECT_LINK oluşturulur.

- DROPEFFECT_SCROLL, bir sürükleme kaydırma işleminin gerçekleşmekte olduğunu veya hedefte meydana geldiğini belirtir.

Daha fazla bilgi için, Windows SDK içindeki [IDropTarget::D ROP](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) bölümüne bakın.

##  <a name="register"></a>COleDropTarget:: Register

Geçerli bir bırakma hedefi olarak pencerenizi OLE dll 'Leri ile kaydetmek için bu işlevi çağırın.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*pWnd*<br/>
Bırakma hedefi olarak kaydedilecek pencereyi işaret eder.

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bırakma işlemlerinin kabul edilmesi için bu işlevin çağrılması gerekir.

Daha fazla bilgi için, Windows SDK [RegisterDragDrop](/windows/win32/api/ole2/nf-ole2-registerdragdrop) bölümüne bakın.

##  <a name="revoke"></a>COleDropTarget:: Revoke

Bırakma hedefleri listesinden kaldırmak için [yazmaç](#register) çağrısıyla bir bırakma hedefi olarak kaydedilmiş herhangi bir pencereyi yok etmeden önce bu işlevi çağırın.

```
virtual void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, kayıtlı pencerenin [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) işleyicisinden otomatik olarak çağrılır, bu yüzden genellikle bu işlevi açıkça çağırmak gerekli değildir.

Daha fazla bilgi için bkz. Windows SDK [iptal](/windows/win32/api/ole2/nf-ole2-revokedragdrop) edin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource Sınıfı](../../mfc/reference/coledropsource-class.md)
