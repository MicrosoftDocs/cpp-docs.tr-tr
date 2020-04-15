---
title: COleDropTarget Sınıfı
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
ms.openlocfilehash: 01eb277da029d06ee44d8e048cf3244f4371a9ec
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375000"
---
# <a name="coledroptarget-class"></a>COleDropTarget Sınıfı

Bir pencere ve OLE kitaplıkları arasındaki iletişim mekanizmasını sağlar.

## <a name="syntax"></a>Sözdizimi

```
class COleDropTarget : public CCmdTarget
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[COleDropTarget::COleDropTarget](#coledroptarget)|Bir `COleDropTarget` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[COleDropTarget::OnDragEnter](#ondragenter)|İmleç pencereye ilk girdiğinde çağrılır.|
|[COleDropTarget::OnDragYorum](#ondragleave)|İmleç pencereden dışarı sürüklendiğinde çağrılır.|
|[COleDropTarget::OnDragOver](#ondragover)|İmleç pencerenin üzerinde sürüklendiğinde art arda çağrılır.|
|[COleDropTarget::OnDragScroll](#ondragscroll)|İmlecin pencerenin kaydırma bölgesine sürüklenip sürüklenmediğini belirlemek için çağrılır.|
|[COleDropTarget::OnDrop](#ondrop)|Veri pencereye bırakıldığında, varsayılan işleyici olarak adlandırılır.|
|[COleDropTarget::OnDropEx](#ondropex)|Veri pencereye bırakıldığında, ilk işleyici olarak adlandırılır.|
|[COleDropTarget::Kayıt ol](#register)|Pencereyi geçerli bir bırakma hedefi olarak kaydeder.|
|[COleDropTarget::İptal et](#revoke)|Pencerenin geçerli bir bırakma hedefi olmaktan olmasına neden olur.|

## <a name="remarks"></a>Açıklamalar

Bu sınıfın bir nesnesi oluşturmak, bir pencerenin OLE sürükle ve bırak mekanizması aracılığıyla verileri kabul etmesine olanak tanır.

Açılan komutları kabul etmek için bir pencere almak için, önce `COleDropTarget` sınıfın bir nesnesi oluşturmanız ve ardından yalnızca parametre olarak istenen `CWnd` nesneye işaretçiyle Kayıt [işlevi](#register) aramanız gerekir.

OLE kullanarak sürükle ve bırak işlemleri hakkında daha fazla bilgi [için, OLE sürükle ve bırak](../../mfc/drag-and-drop-ole.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

`COleDropTarget`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxole.h

## <a name="coledroptargetcoledroptarget"></a><a name="coledroptarget"></a>COleDropTarget::COleDropTarget

Sınıfın `COleDropTarget`bir nesnesini inşa eder.

```
COleDropTarget();
```

### <a name="remarks"></a>Açıklamalar

Bu nesneyi bir pencereyle ilişkilendirmek için [Kaydol'u](#register) arayın.

## <a name="coledroptargetondragenter"></a><a name="ondragenter"></a>COleDropTarget::OnDragEnter

İmleç ilk kez pencereye sürüklendiğinde çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin girdiği pencereyi işaret eder.

*pDataObject*<br/>
Bırakılabilen verileri içeren veri nesnesini işaret eder.

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
İmlecin istemci koordinatlarında geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir düşüş denenirse ortaya çıkan etki. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işlemi gelmek üzere veya hedefte meydana gelmek üzeredir.

### <a name="remarks"></a>Açıklamalar

Pencerede bırakma işlemlerinin gerçekleşmesine izin vermek için bu işlevi geçersiz kılın. Varsayılan uygulama [CView çağırır::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), hangi sadece varsayılan olarak DROPEFFECT_NONE döndürür.

Daha fazla bilgi için [Bkz. IDropTarget::DragEnter](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragenter) in Windows SDK.

## <a name="coledroptargetondragleave"></a><a name="ondragleave"></a>COleDropTarget::OnDragYorum

Sürükleme işlemi etkinken imleç pencereden ayrıldığında çerçeve tarafından çağrılır.

```
virtual void OnDragLeave(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin ayrıldığı pencereyi işaret eder.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemi belirtilen pencereden ayrıldığında özel davranış istiyorsanız bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulaması [CView çağırır::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).

Daha fazla bilgi için [Bkz. IDropTarget::DragWindows](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragleave) SDK'da bırakın.

## <a name="coledroptargetondragover"></a><a name="ondragover"></a>COleDropTarget::OnDragOver

İmleç pencerenin üzerinde sürüklendiğinde çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin bittiğini pencereye işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesini işaret edin.

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
İmlecin istemci koordinatlarında geçerli konumunu içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir düşüş denenirse ortaya çıkan etki. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işleminin gerçekleşmek üzere olduğunu veya hedefte meydana geldiğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu işlev, pencerede bırakma işlemlerinin gerçekleşmesine izin vermek için geçersiz kılınmalıdır. Bu işlevin varsayılan uygulaması, varsayılan olarak DROPEFFECT_NONE döndüren [CView:OnDragOver'ı](../../mfc/reference/cview-class.md#ondragover)çağırır. Bu işlev sürükle ve bırak işlemi sırasında sık sık çağrıldığı için, mümkün olduğunca en iyi duruma getirilmelidir.

Daha fazla bilgi için Windows SDK'daki [IDropTarget::DragOver'a](/windows/win32/api/oleidl/nf-oleidl-idroptarget-dragover) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]

## <a name="coledroptargetondragscroll"></a><a name="ondragscroll"></a>COleDropTarget::OnDragScroll

*Kaydırma* bölgesinde nokta olup olmadığını belirlemek için [OnDragEnter](#ondragenter) veya [OnDragOver'ı](#ondragover) aramadan önce çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,
    DWORD dwKeyState,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin şu anda üzerinde olduğu pencereye işaret eder.

*dwKeyState*<br/>
Değiştirici anahtarların durumunu içerir. Bu, aşağıdakilerden herhangi birinin birleşimidir: MK_CONTROL, MK_SHIFT, MK_ALT, MK_LBUTTON, MK_MBUTTON ve MK_RBUTTON.

*Nokta*<br/>
İmlecin konumunu, ekrana göre piksel olarak içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*ile belirtilen konumda bir düşüş denenirse ortaya çıkan etki. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işleminin gerçekleşmek üzere olduğunu veya hedefte meydana geldiğini gösterir.

### <a name="remarks"></a>Açıklamalar

Bu olay için özel davranış sağlamak istediğinizde bu işlevi geçersiz kılın. Bu işlevin varsayılan uygulaması [CView çağırır::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), DROPEFFECT_NONE döndürür ve imleç pencerenin kenarlığı içinde varsayılan kaydırma bölgesine sürüklendiğinde pencere kaydırır.

## <a name="coledroptargetondrop"></a><a name="ondrop"></a>COleDropTarget::OnDrop

Bir bırakma işlemi gerçekleşirken çerçeve tarafından çağrılır.

```
virtual BOOL OnDrop(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropEffect,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin şu anda üzerinde olduğu pencereye işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesini işaret edin.

*dropEffect*<br/>
Kullanıcının bırakma işlemi için seçtiği etki. Aşağıdakilerden biri veya birkaçı olabilir:

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

*Nokta*<br/>
İmlecin konumunu, ekrana göre piksel olarak içerir.

### <a name="return-value"></a>Dönüş Değeri

Damla başarılı olursa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Çerçeve ilk [OnDropEx](#ondropex)çağırır. `OnDropEx` İşlev düşüşü işlemiyorsa, çerçeve bu üye `OnDrop`işlevi çağırır. Genellikle, uygulama sağ fare düğmesi sürükle ve bırak işlemek için görünüm sınıfında [OnDropEx](../../mfc/reference/cview-class.md#ondropex) geçersiz kılar. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak işlemek için kullanılır.

`COleDropTarget::OnDrop` [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), varsayılan olarak FALSE döndürür çağrıları varsayılan uygulaması.

Daha fazla bilgi için Windows SDK'daki [IDropTarget::Drop'](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) a bakın.

## <a name="coledroptargetondropex"></a><a name="ondropex"></a>COleDropTarget::OnDropEx

Bir bırakma işlemi gerçekleşirken çerçeve tarafından çağrılır.

```
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,
    COleDataObject* pDataObject,
    DROPEFFECT dropDefault,
    DROPEFFECT dropList,
    CPoint point);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
İmlecin şu anda üzerinde olduğu pencereye işaret eder.

*pDataObject*<br/>
Bırakılacak verileri içeren veri nesnesini işaret edin.

*dropVarsayılan*<br/>
Geçerli anahtar durumuna göre kullanıcının varsayılan bırakma işlemi için seçtiği etki. DROPEFFECT_NONE olabilir. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

*dropList*<br/>
Bırakma kaynağının desteklediği bırakma efektlerinin listesi. Bırakma efekti değerleri bitwise OR** (&#124;**) işlemi kullanılarak birleştirilebilir. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

*Nokta*<br/>
İmlecin konumunu, ekrana göre piksel olarak içerir.

### <a name="return-value"></a>Dönüş Değeri

*Nokta*tarafından belirtilen konumdaki bırakma denemesinden kaynaklanan bırakma efekti. Damla efektleri Açıklamalar bölümünde ele alınmıştır.

### <a name="remarks"></a>Açıklamalar

Çerçeve ilk olarak bu işlevi çağırır. Bu damla işlemez, çerçeve sonra [OnDrop](#ondrop)çağırır. Genellikle, sağ fare tuşu sürükle ve bırak'ı desteklemek için görünüm sınıfında [OnDropEx'i](../../mfc/reference/cview-class.md#ondropex) geçersiz kılarsınız. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak için destek durumunu işlemek için kullanılır.

`COleDropTarget::OnDropEx` [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex)çağrılarının varsayılan uygulaması. Varsayılan olarak, [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) yalnızca [OnDrop](#ondrop) üye işlevinin çağrılması gerektiğini belirtmek için sahte bir değer döndürür.

Bırakma efektleri, bir bırakma işlemiyle ilişkili eylemi açıklar. Aşağıdaki bırakma efektleri listesine bakın:

- DROPEFFECT_NONE Bir damlaya izin verilmeyecekti.

- DROPEFFECT_COPY Bir kopyalama işlemi gerçekleştirilir.

- DROPEFFECT_MOVE Bir hareket işlemi gerçekleştirilir.

- DROPEFFECT_LINK Bırakılan verilerden özgün verilere bir bağlantı kurulabilir.

- DROPEFFECT_SCROLL Bir sürükleme kaydırma işleminin gerçekleşmek üzere olduğunu veya hedefte meydana geldiğini gösterir.

Daha fazla bilgi için Windows SDK'daki [IDropTarget::Drop'](/windows/win32/api/oleidl/nf-oleidl-idroptarget-drop) a bakın.

## <a name="coledroptargetregister"></a><a name="register"></a>COleDropTarget::Kayıt ol

Pencerenizi geçerli bir bırakma hedefi olarak OLE DLs'lere kaydetmek için bu işlevi arayın.

```
BOOL Register(CWnd* pWnd);
```

### <a name="parameters"></a>Parametreler

*Pwnd*<br/>
Açılan hedef olarak kaydedilecek pencereyi işaret ediyor.

### <a name="return-value"></a>Dönüş Değeri

Kayıt başarılı olursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bırakma işlemlerinin kabul edilemesi için bu işlev inden çağrılmalıdır.

Daha fazla bilgi için Windows SDK'daki [RegisterDragDrop'a](/windows/win32/api/ole2/nf-ole2-registerdragdrop) bakın.

## <a name="coledroptargetrevoke"></a><a name="revoke"></a>COleDropTarget::İptal et

Açılan hedefler listesinden kaldırmak için [Kaydolmak](#register) için yapılan bir çağrı aracılığıyla bırakma hedefi olarak kaydedilmiş herhangi bir pencereyi yok etmeden önce bu işlevi arayın.

```
virtual void Revoke();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, kayıtlı pencere için [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) işleyicisinden otomatik olarak çağrılır, bu nedenle genellikle bu işlevi açıkça çağırmak gerekmez.

Daha fazla bilgi için Windows SDK'daki [RevokeDragDrop'a](/windows/win32/api/ole2/nf-ole2-revokedragdrop) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek HIERSVR](../../overview/visual-cpp-samples.md)<br/>
[MFC Örnek OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[CCmdTarget Sınıfı](../../mfc/reference/ccmdtarget-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[COleDropSource Sınıfı](../../mfc/reference/coledropsource-class.md)
