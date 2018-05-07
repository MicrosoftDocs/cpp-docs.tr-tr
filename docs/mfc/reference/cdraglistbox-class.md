---
title: CDragListBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDragListBox
- AFXCMN/CDragListBox
- AFXCMN/CDragListBox::CDragListBox
- AFXCMN/CDragListBox::BeginDrag
- AFXCMN/CDragListBox::CancelDrag
- AFXCMN/CDragListBox::Dragging
- AFXCMN/CDragListBox::DrawInsert
- AFXCMN/CDragListBox::Dropped
- AFXCMN/CDragListBox::ItemFromPt
dev_langs:
- C++
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 34655c244f13cb721693208fa93353582de452e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdraglistbox-class"></a>CDragListBox sınıfı
Bir Windows liste kutusu işlevselliğini sağlayan yanı sıra `CDragListBox` sınıfı içinde liste kutusu gibi dosya adları, liste kutusu öğeleri taşımak kullanıcı verir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CDragListBox : public CListBox  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDragListBox::CDragListBox](#cdraglistbox)|Oluşturan bir `CDragListBox` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CDragListBox::BeginDrag](#begindrag)|Sürükleme işlemi başlatıldığında çerçevesi tarafından çağrılır.|  
|[CDragListBox::CancelDrag](#canceldrag)|Sürükleme işlemi iptal ettiğinizde çerçevesi tarafından çağrılır.|  
|[CDragListBox::Dragging](#dragging)|Sürükleme işlemi sırasında çerçevesi tarafından çağrılır.|  
|[CDragListBox::DrawInsert](#drawinsert)|Sürükleme liste kutusu ekleme Kılavuzu çizer.|  
|[CDragListBox::Dropped](#dropped)|Öğesi bırakıldı sonra çerçevesi tarafından çağrılır.|  
|[CDragListBox::ItemFromPt](#itemfrompt)|Sürüklenen öğenin koordinat döndürür.|  
  
## <a name="remarks"></a>Açıklamalar  
 Liste kutuları ile bu özellik, kullanıcıların herhangi bir şekilde kendilerine en yararlı bir listesinde öğeleri sipariş izin verin. Varsayılan olarak, liste kutusu öğesi listede yeni bir konuma taşır. Ancak, `CDragListBox` nesneleri, onları taşıyarak yerine öğeleri kopyalamak için özelleştirilebilir.  
  
 Liste kutusu denetimini ilişkili `CDragListBox` sınıfı değil olmalıdır **LBS_SORT** veya **LBS_MULTIPLESELECT** stili. Liste kutusu stilleri açıklaması için bkz: [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).  
  
 Sürükleme liste kutusu, uygulamanızın bir iletişim kutusunda kullanmak için iletişim kutusu Düzenleyicisi'ni kullanarak iletişim şablonunuza bir liste kutusu denetimini eklemek ve bir üye değişkenine atayın (kategorisinin `Control` ve değişken türü `CDragListBox`) karşılık gelen liste kutusu iletişim şablonunuzda denetler.  
  
 Denetimler için üye değişkenleri atama hakkında daha fazla bilgi için bkz: [iletişim kutusu denetimleri için üye değişkenleri tanımlama için kısayol](../../windows/defining-member-variables-for-dialog-controls.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CListBox](../../mfc/reference/clistbox-class.md)  
  
 `CDragListBox`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="begindrag"></a>  CDragListBox::BeginDrag  
 Çağıran bir olay gerçekleştiğinde framework sol fare düğmesine basarak gibi bir sürükleme işlemi başlamadan.  
  
```  
virtual BOOL BeginDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) sürüklenen öğenin koordinatları içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürükleme izin veriliyorsa, aksi takdirde 0 sıfır olmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Sürükleme işlemi başladığında ne olacağını denetlemek istiyorsanız, bu işlev geçersiz kılar. Varsayılan uygulama fare yakalar ve kullanıcı sola veya sağa fare düğmesini tıklattığında veya sürükleme işlemi aynı zamanda İptal ESC tuşuna bastığında kadar Sürükle modunda kalır.  
  
##  <a name="canceldrag"></a>  CDragListBox::CancelDrag  
 Sürükleme işlemi iptal ettiğinizde çerçevesi tarafından çağrılır.  
  
```  
virtual void CancelDrag(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) sürüklenen öğenin koordinatları içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste kutusu denetimi için hiçbir özel işlem işlemek için bu işlev geçersiz kılar.  
  
##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox  
 Oluşturan bir `CDragListBox` nesnesi.  
  
```  
CDragListBox();
```  
  
##  <a name="dragging"></a>  CDragListBox::Dragging  
 Liste kutusu öğesi içinde sürüklenen çerçevesi tarafından çağrılır `CDragListBox` nesnesi.  
  
```  
virtual UINT Dragging(CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) x ve y içeren nesne ekran İmleç koordinatları.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Görüntülenecek kaynak kimliği imleci. Aşağıdaki olası değerler:  
  
- `DL_COPYCURSOR` Öğenin kopyalanacağı gösterir.  
  
- `DL_MOVECURSOR` Öğe taşınacağını gösterir.  
  
- `DL_STOPCURSOR` Geçerli bırakma hedefi kabul edilebilir değil gösterir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan davranış döndürür `DL_MOVECURSOR`. Ek işlevsellik sağlamak istiyorsanız, bu işlev geçersiz kılar.  
  
##  <a name="drawinsert"></a>  CDragListBox::DrawInsert  
 Belirtilen dizinle öğeyi önce ekleme Kılavuzu çizmek için çerçevesi tarafından çağrılır.  
  
```  
virtual void DrawInsert(int nItem);
```  
  
### <a name="parameters"></a>Parametreler  
 `nItem`  
 Ekleme noktasını sıfır tabanlı dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Değeri, - 1 ekleme Kılavuzu temizler. Bu işlev görünüm veya ekleme Kılavuzu davranışını değiştirmek için geçersiz kılar.  
  
##  <a name="dropped"></a>  CDragListBox::Dropped  
 Bir öğe içinde bırakıldığında çerçevesi tarafından çağrılır bir `CDragListBox` nesnesi.  
  
```  
virtual void Dropped(
    int nSrcIndex,  
    CPoint pt);
```  
  
### <a name="parameters"></a>Parametreler  
 *nSrcIndex*  
 Bırakılan dize sıfır tabanlı dizini belirtir.  
  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) açılan site koordinatlarını içeren nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsayılan davranış, liste kutusu öğesi ve kendi veri yeni konuma kopyalar ve özgün öğeyi siler. Liste kutusu öğeleri listesi içindeki başka konumlara sürüklenebilir için kopyalarını etkinleştirme gibi varsayılan davranışını özelleştirmek için bu işlevi geçersiz kılar.  
  
##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt  
 Liste kutusu öğesi sıfır tabanlı dizini almak için bu işlevi bulunan çağrı `pt`.  
  
```  
int ItemFromPt(
    CPoint pt,  
    BOOL bAutoScroll = TRUE) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) liste kutusu içinde bir noktayı koordinatlarını içeren nesne.  
  
 *bAutoScroll*  
 Kaydırma izin veriliyorsa, aksi takdirde 0 sıfır olmayan.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sürükleme liste kutusu öğesi sıfır tabanlı dizini.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek TSTCON](../../visual-cpp-samples.md)   
 [CListBox sınıfı](../../mfc/reference/clistbox-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
