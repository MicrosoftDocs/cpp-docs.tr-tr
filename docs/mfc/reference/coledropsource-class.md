---
title: COleDropSource sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- COleDropSource
- AFXOLE/COleDropSource
- AFXOLE/COleDropSource::COleDropSource
- AFXOLE/COleDropSource::GiveFeedback
- AFXOLE/COleDropSource::OnBeginDrag
- AFXOLE/COleDropSource::QueryContinueDrag
dev_langs:
- C++
helpviewer_keywords:
- COleDropSource [MFC], COleDropSource
- COleDropSource [MFC], GiveFeedback
- COleDropSource [MFC], OnBeginDrag
- COleDropSource [MFC], QueryContinueDrag
ms.assetid: d3eecc5f-a70b-4a01-b705-7d2c098ebe17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e510811fcaac81aa54699250ef37f48ffe1f40e2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="coledropsource-class"></a>COleDropSource sınıfı
Verilerin bir bırakma hedefi sürüklenen olanak tanır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleDropSource : public CCmdTarget  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDropSource::COleDropSource](#coledropsource)|Oluşturan bir `COleDropSource` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleDropSource::GiveFeedback](#givefeedback)|İmleç bir Sürükle ve bırak işlemi sırasında değiştirir.|  
|[COleDropSource::OnBeginDrag](#onbegindrag)|Fare yakalama bir Sürükle ve bırak işlemi sırasında işler.|  
|[COleDropSource::QueryContinueDrag](#querycontinuedrag)|Sürükleme olup olmadığını görmek için denetimleri devam etmelidir.|  
  
## <a name="remarks"></a>Açıklamalar  
 [COleDropTarget](../../mfc/reference/coledroptarget-class.md) sınıfı sürükle ve bırak işlemi alıcı bölümünü işler. `COleDropSource` Nesnesi olan bir sürükleme işlemi başladığı belirleme, sürükleme işlemi sırasında geribildirim sağlama ve sürükleme işlemi sona erdiğinde belirleme sorumlu.  
  
 Kullanılacak bir `COleDropSource` nesne, yalnızca Oluşturucusu çağırın. Fare tıklatma gibi hangi olayların bir sürükleme işlemi kullanmaya başlamak belirleme işlemi basitleştirir [COleDataSource::DoDragDrop](../../mfc/reference/coledatasource-class.md#dodragdrop), [COleClientItem::DoDragDrop](../../mfc/reference/coleclientitem-class.md#dodragdrop), veya [ COleServerItem::DoDragDrop](../../mfc/reference/coleserveritem-class.md#dodragdrop) işlevi. Bu işlevler oluşturacak bir `COleDropSource` nesnesi. Varsayılan davranışını değiştirmek isteyebilirsiniz `COleDropSource` geçersiz kılınabilir işlevler. Bu üye işlevleri uygun zamanlarda çerçevesi tarafından çağrılır.  
  
 Sürükle ve bırak işlemleri hakkında daha fazla bilgi için OLE kullanarak makaleye bakın [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Daha fazla bilgi için bkz: [IDropSource](http://msdn.microsoft.com/library/windows/desktop/ms690071) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `COleDropSource`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="coledropsource"></a>  COleDropSource::COleDropSource  
 Oluşturan bir `COleDropSource` nesnesi.  
  
```  
COleDropSource();
```  
  
##  <a name="givefeedback"></a>  COleDropSource::GiveFeedback  
 Çağrıldıktan sonra çerçevesi tarafından çağrılır [COleDropTarget::OnDragOver](../../mfc/reference/coledroptarget-class.md#ondragover) veya [COleDropTarget::DragEnter](../../mfc/reference/coledroptarget-class.md#ondragenter).  
  
```  
virtual SCODE GiveFeedback(DROPEFFECT dropEffect);
```  
  
### <a name="parameters"></a>Parametreler  
 `dropEffect`  
 Seçili verileri ile bu noktada bir açılan oluştu kullanıcıya görüntülemek istediğiniz etkisi, genellikle ne belirten gerçekleşir. Genellikle, en son çağrı tarafından döndürülen değer budur [CView::OnDragEnter](../../mfc/reference/cview-class.md#ondragenter) veya [CView::OnDragOver](../../mfc/reference/cview-class.md#ondragover). Aşağıdakilerden birini veya birkaçını olabilir:  
  
- `DROPEFFECT_NONE` Bir açılan izin verilmez.  
  
- `DROPEFFECT_COPY` Bir kopyalama işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_MOVE` Bir taşıma işlemi gerçekleştirilmesi.  
  
- `DROPEFFECT_LINK` Özgün veriler bırakılan verilerden bir bağlantı kurulamıyor.  
  
- `DROPEFFECT_SCROLL` Sürükleme kaydırma işlemi gerçekleşmek üzere olduğu veya hedef gerçekleştirilmektedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **DRAGDROP_S_USEDEFAULTCURSORS** sürükleyerek, sürüyorsa **NOERROR** değilse.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanıcı bir açılan bu noktada ortaya çıktıysa ne olacağını hakkında geri bildirim sağlamak için bu işlevi geçersiz kılar. Varsayılan uygulama OLE varsayılan imleçler kullanır. Sürükle ve bırak işlemleri hakkında daha fazla bilgi için OLE kullanarak makaleye bakın [sürükleme ve bırakma (OLE)](../../mfc/drag-and-drop-ole.md).  
  
 Daha fazla bilgi için bkz: [IDropSource::GiveFeedback](http://msdn.microsoft.com/library/windows/desktop/ms693723), [IDropTarget::DragOver](http://msdn.microsoft.com/library/windows/desktop/ms680129), ve [IDropTarget::DragEnter](http://msdn.microsoft.com/library/windows/desktop/ms680106) Windows SDK'sındaki.  
  
##  <a name="onbegindrag"></a>  COleDropSource::OnBeginDrag  
 Çağıran bir olay gerçekleştiğinde framework sol fare düğmesine basarak gibi bir sürükleme işlemi başlamadan.  
  
```  
virtual BOOL OnBeginDrag(CWnd* pWnd);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWnd`  
 Seçili verileri içeren bir pencere noktalarına.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürükleme izin veriliyorsa, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükleme işlemi başlatıldı yolu değiştirmek istiyorsanız, bu işlev geçersiz kılar. Varsayılan uygulama fare yakalar ve kullanıcı sola veya sağa fare düğmesini tıklattığında veya isteğe bağlı olarak hangi zaman fare serbest ESC isabetler kadar Sürükle modunda kalır.  
  
##  <a name="querycontinuedrag"></a>  COleDropSource::QueryContinueDrag  
 Sürükleme başladıktan sonra sürükleme işlemi iptal tamamlandı ya da kadar bu işlev art arda çerçevesi tarafından çağrılır.  
  
```  
virtual SCODE QueryContinueDrag(
    BOOL bEscapePressed, 
    DWORD dwKeyState);
```  
  
### <a name="parameters"></a>Parametreler  
 *bEscapePressed*  
 Son çağrısından sonra ESC tuşuna basılı olup olmadığını belirten `COleDropSource::QueryContinueDrag`.  
  
 `dwKeyState`  
 Klavyedeki değiştirici tuşları durumunu içerir. Bu aşağıdaki herhangi bir sayıda birleşiminden oluşur: **MK_CONTROL**, **MK_SHIFT**, **MK_ALT**, **MK_LBUTTON**, **MK_ MBUTTON**, ve **MK_RBUTTON**.  
  
### <a name="return-value"></a>Dönüş Değeri  
 **DRAGDROP_S_CANCEL** ESC tuşuna veya sağ düğmesine basıldığında veya sol düğme başlatır sürükleyerek önce oluşturulur. **DRAGDROP_S_DROP** bırakma işlemi oluşursa. Aksi takdirde `S_OK`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev, hangi sürükleyerek adresindeki noktasını değiştirmek istiyorsanız İptal geçersiz kılma veya bir açılan oluşur.  
  
 Varsayılan uygulama açılır başlatır veya sürükle aşağıdaki gibi iptal eder. ESC tuşuna veya farenin sağ düğmesiyle basıldığında sürükleme işlemi iptal eder. Sürükleme başlatıldıktan sonra sol fare düğmesini oluştuğunda bırakma işlemi başlatır. Aksi takdirde, döndürür `S_OK` ve başka hiçbir işlem gerçekleştirir.  
  
 Bu işlev sık çağrıldığı için mümkün olduğunca hale getirilmiştir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek HIERSVR](../../visual-cpp-samples.md)   
 [MFC örnek OCLIENT](../../visual-cpp-samples.md)   
 [CCmdTarget sınıfı](../../mfc/reference/ccmdtarget-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



