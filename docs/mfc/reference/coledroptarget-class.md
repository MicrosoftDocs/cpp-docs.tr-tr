---
title: COleDropTarget sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fec20d8bb960d48392f2d174dab9ee6497738c80
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039608"
---
# <a name="coledroptarget-class"></a>COleDropTarget sınıfı
Bir pencere OLE kitaplıklarının arasındaki iletişim mekanizması sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDropTarget : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDropTarget::COleDropTarget](#coledroptarget)|Oluşturan bir `COleDropTarget` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDropTarget::OnDragEnter](#ondragenter)|İmleç ilk penceresi girdiğinde çağrılır.|  
|[COleDropTarget::OnDragLeave](#ondragleave)|İmleç penceresi dışında sürüklendiğinde çağrılır.|  
|[COleDropTarget::OnDragOver](#ondragover)|Art arda imleci pencere üzerinde ne zaman sürüklenen çağrılır.|  
|[COleDropTarget::OnDragScroll](#ondragscroll)|İmleç kaydırma bölgeye penceresinin sürüklenen olup olmadığını belirlemek için çağrılır.|  
|[COleDropTarget::OnDrop](#ondrop)|Veri penceresinde, varsayılan işleyici kesildiğinde çağrılır.|  
|[COleDropTarget::OnDropEx](#ondropex)|Veri penceresinde, ilk işleyici kesildiğinde çağrılır.|  
|[COleDropTarget::Register](#register)|Pencerenin geçerli bırakma hedefi olarak kaydeder.|  
|[COleDropTarget::Revoke](#revoke)|Pencerenin geçerli bırakma hedefi olan sona neden olur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın bir nesnesi oluşturma OLE sürükle ve bırak mekanizma verileri kabul etmek bir pencere sağlar.  
  
 Açılan komutları kabul etmek için bir pencere almak için önce bir nesneyi oluşturmanız gerekir `COleDropTarget` sınıfı ve ardından arama [kaydetmek](#register) gösteren bir işaretçi istenen işleviyle `CWnd` nesnesi tek parametre olarak.  
  
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
 Çağrı [kaydetmek](#register) bu nesne bir pencere ile ilişkilendirmek için.  
  
##  <a name="ondragenter"></a>  COleDropTarget::OnDragEnter  
 İmleç ilk penceresine sürüklendiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragEnter(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç girme noktaları penceresine.  
  
 *pDataObject*  
 İşaret eder bırakılabilir verileri içeren veri nesnesi.  
  
 *dwKeyState*  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 *Noktası*  
 İstemci koordinatları imleci geçerli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir açılan tarafından belirtilen konumda girişiminde bulunuldu, ortaya çıkabilecek etkisi *noktası*. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere olduğu veya hedef gerçekleştirilmektedir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bırakma işlemleri penceresinde oluşmasına izin vermek için bu işlevi geçersiz kılar. Varsayılan Uygulama çağrıları [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter), yalnızca döndüren `DROPEFFECT_NONE` varsayılan olarak.  
  
 Daha fazla bilgi için bkz: [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) Windows SDK'sındaki.  
  
##  <a name="ondragleave"></a>  COleDropTarget::OnDragLeave  
 İmleç penceresi ayrıldığında bir sürükleme işlemi etkinken çerçevesi tarafından çağrılır.  
  
```  
virtual void OnDragLeave(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç bırakarak noktaları penceresine.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükleme işlemi belirtilen pencere ayrıldığında özel davranış istiyorsanız, bu işlev geçersiz kılar. Bu işlev varsayılan uygulamasını çağıran [CView::OnDragLeave](../../mfc/reference/cview-class.md#ondragleave).  
  
 Daha fazla bilgi için bkz: [IDropTarget::DragLeave](http://msdn.microsoft.com/library/windows/desktop/ms680110) Windows SDK'sındaki.  
  
##  <a name="ondragover"></a>  COleDropTarget::OnDragOver  
 İmleç penceresi sürüklendiğinde çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDragOver(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç üzerinden penceresi noktalarına.  
  
 *pDataObject*  
 Kesilmesini istediğiniz verileri içeren veri nesnesi noktalarına.  
  
 *dwKeyState*  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 *Noktası*  
 İstemci koordinatları imleci geçerli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir açılan tarafından belirtilen konumda girişiminde bulunuldu, ortaya çıkabilecek etkisi *noktası*. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere veya hedef oluştuğunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, bırakma işlemleri penceresinde oluşmasına izin vermek için kılınmalıdır. Bu işlev varsayılan uygulamasını çağıran [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover), döndüren `DROPEFFECT_NONE` varsayılan olarak. Bu işlev bir Sürükle ve bırak işlemi sırasında sık çağrıldığı için mümkün olduğunca hale getirilmiştir.  
  
 Daha fazla bilgi için bkz: [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#21](../../mfc/codesnippet/cpp/coledroptarget-class_1.cpp)]  
  
##  <a name="ondragscroll"></a>  COleDropTarget::OnDragScroll  
 Çağırmadan önce framework tarafından çağrılan [OnDragEnter](#ondragenter) veya [OnDragOver](#ondragover) belirlemek için olup olmadığını *noktası* kaydırma bölgede değil.  
  
```  
virtual DROPEFFECT OnDragScroll(
    CWnd* pWnd,  
    DWORD dwKeyState,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç penceresine noktaları şu anda üzerinden.  
  
 *dwKeyState*  
 Değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
 *Noktası*  
 İmleç, piksel cinsinden ekran göreli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir açılan tarafından belirtilen konumda girişiminde bulunuldu, ortaya çıkabilecek etkisi *noktası*. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere veya hedef oluştuğunu gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu olay için özel davranışı sağlamak istediğinizde bu işlevi geçersiz kılar. Bu işlev varsayılan uygulamasını çağıran [CView::OnDragScroll](../../mfc/reference/cview-class.md#ondragscroll), döndüren `DROPEFFECT_NONE` ve imleci varsayılan kaydırma bölgesi iç kenarlık penceresinin içine sürüklendiğinde penceresi birlikte kayar.  
  
##  <a name="ondrop"></a>  COleDropTarget::OnDrop  
 Bırakma işlemi oluştuğu sırada çerçevesi tarafından çağrılır.  
  
```  
virtual BOOL OnDrop(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropEffect,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç penceresine noktaları şu anda üzerinden.  
  
 *pDataObject*  
 Kesilmesini istediğiniz verileri içeren veri nesnesi noktalarına.  
  
 *dropEffect*  
 Bırakma işlemi için kullanıcının seçtiği etkisi. Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
 *Noktası*  
 İmleç, piksel cinsinden ekran göreli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Açılan başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework ilk çağrıları [OnDropEx](#ondropex). Varsa `OnDropEx` işlevi açılır işlemiyor, framework daha sonra bu üye işlevi çağırır `OnDrop`. Genellikle, uygulama geçersiz kılmaları [OnDropEx](../../mfc/reference/cview-class.md#ondropex) sağ fare düğmesini işlemek için view sınıfı sürükle ve bırak. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak işlemek için kullanılır.  
  
 Varsayılan uygulaması `COleDropTarget::OnDrop` çağrıları [CView::OnDrop](../../mfc/reference/cview-class.md#ondrop), yalnızca döndüren **FALSE** varsayılan olarak.  
  
 Daha fazla bilgi için bkz: [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) Windows SDK'sındaki.  
  
##  <a name="ondropex"></a>  COleDropTarget::OnDropEx  
 Bırakma işlemi oluştuğu sırada çerçevesi tarafından çağrılır.  
  
```  
virtual DROPEFFECT OnDropEx(
    CWnd* pWnd,  
    COleDataObject* pDataObject,  
    DROPEFFECT dropDefault,  
    DROPEFFECT dropList,  
    CPoint point);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 İmleç penceresine noktaları şu anda üzerinden.  
  
 *pDataObject*  
 Kesilmesini istediğiniz verileri içeren veri nesnesi noktalarına.  
  
 *dropDefault*  
 Geçerli anahtar durumuna göre varsayılan bırakma işlemi için kullanıcının seçtiği etkisi. Bu olabilir `DROPEFFECT_NONE`. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
 *Listeyi*  
 Bırakma kaynağı destekleyen açılan etkilerini listesi. Bit düzeyinde OR kullanarak doğrudan etkisi değerleri birleştirilebilir ( **&#124;**) işlemi. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
 *Noktası*  
 İmleç, piksel cinsinden ekran göreli konumunu içerir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen konumda bırak girişimi kullanmasından kaynaklanan açılan etkisi *noktası*. Açılan efektler açıklamalar bölümünde ele alınmıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Framework önce bu işlevi çağırır. Açılan işlemez, framework sonra çağırması [OnDrop](#ondrop). Genellikle, geçersiz kılar [OnDropEx](../../mfc/reference/cview-class.md#ondropex) sağ fare düğmesini desteklemek için view sınıfı sürükle ve bırak. Genellikle, görünüm sınıfı [OnDrop](../../mfc/reference/cview-class.md#ondrop) basit sürükle ve bırak desteği durumu işlemek için kullanılır.  
  
 Varsayılan uygulaması `COleDropTarget::OnDropEx` çağrıları [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex). Varsayılan olarak, [CView::OnDropEx](../../mfc/reference/cview-class.md#ondropex) basitçe belirtmek için bir kukla değer verir [OnDrop](#ondrop) üye işlevi çağrılabilir.  
  
 Açılan etkileri açılan işlemle ilişkili eylemi açıklar. Açılan etkileri aşağıdaki listeye bakın:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere veya hedef oluştuğunu gösterir.  
  
 Daha fazla bilgi için bkz: [IDropTarget::Drop](http://msdn.microsoft.com/library/windows/desktop/ms687242) Windows SDK'sındaki.  
  
##  <a name="register"></a>  COleDropTarget::Register  
 OLE DLL'ler olarak geçerli bırakma hedefi ile pencerenizi kaydettirmek için bu işlevini çağırın.  
  
```  
BOOL Register(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 *pWnd*  
 Bırakma hedefi olarak kaydedilmesi için pencereyi noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kayıt başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev bırakma işlemleri kabul edilmesi çağrılmalıdır.  
  
 Daha fazla bilgi için bkz: [RegisterDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms678405) Windows SDK'sındaki.  
  
##  <a name="revoke"></a>  COleDropTarget::Revoke  
 Bir çağrı aracılığıyla bir bırakma hedefi olarak kayıtlı pencere yok etme önce bu işlevi çağırmak [kaydetmek](#register) bırakma hedeflerini listesinden kaldırmak için.  
  
```  
virtual void Revoke();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev otomatik olarak çağrılır [OnDestroy](../../mfc/reference/cwnd-class.md#ondestroy) genellikle açıkça bu işlevi çağırmak gerekli değildir, kayıtlı penceresi için işleyici.  
  
 Daha fazla bilgi için bkz: [RevokeDragDrop](http://msdn.microsoft.com/library/windows/desktop/ms692643) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [COleDropSource Sınıfı](../../mfc/reference/coledropsource-class.md)
