---
title: CDragListBox sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CDragListBox [MFC], CDragListBox
- CDragListBox [MFC], BeginDrag
- CDragListBox [MFC], CancelDrag
- CDragListBox [MFC], Dragging
- CDragListBox [MFC], DrawInsert
- CDragListBox [MFC], Dropped
- CDragListBox [MFC], ItemFromPt
ms.assetid: fee20b42-60ae-4aa9-83f9-5a3d9b96e33b
ms.openlocfilehash: 6574ffaf8c4b8c0414c00ef2f4a31f6ed74ebe9e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57294947"
---
# <a name="cdraglistbox-class"></a>CDragListBox sınıfı

Windows liste kutusu işlevselliği sağlayan yanı sıra `CDragListBox` sınıfı kullanıcının liste dosya adları gibi liste kutusu öğelerini taşımasına izin verir.

## <a name="syntax"></a>Sözdizimi

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDragListBox::CDragListBox](#cdraglistbox)|Oluşturur bir `CDragListBox` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDragListBox::BeginDrag](#begindrag)|Bir sürükleme işlemi başladığında framework tarafından çağırılır.|
|[CDragListBox::CancelDrag](#canceldrag)|Bir sürükleme işlemi iptal edildiğinde framework tarafından çağırılır.|
|[CDragListBox::Dragging](#dragging)|Bir sürükleme işlemi sırasında framework tarafından çağırılır.|
|[CDragListBox::DrawInsert](#drawinsert)|Sürükleme liste kutusu ekleme klavuzunu çizer.|
|[CDragListBox::Dropped](#dropped)|Öğe bırakıldıktan sonra framework tarafından çağırılır.|
|[CDragListBox::ItemFromPt](#itemfrompt)|Sürüklenen öğenin koordinatlarını döndürür.|

## <a name="remarks"></a>Açıklamalar

Liste kutuları ile bu özellik kullanıcıların bir listedeki herhangi bir şekilde kendisine en kullanışlı olduğunu öğelerinizi sıraya sokmanızı sağlar. Varsayılan olarak, liste kutusu, öğe listesinde yeni konumuna taşınır. Ancak, `CDragListBox` nesneleri taşımak yerine öğeleri kopyalamak için özelleştirilebilir.

Liste kutusu denetimini ilişkili `CDragListBox` sınıfı LBS_SORT veya LBS_MULTIPLESELECT stili değil olmalıdır. Liste kutusu stilleri açıklaması için bkz: [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Bir sürükleme liste kutusu, uygulamanızın bir iletişim kutusunda kullanmak için bir liste kutusu denetimini iletişim kutusu düzenleyicisini kullanma iletişim şablonunuza eklemek ve ardından bir üye değişkenine atayın (kategorisinin `Control` ve değişken türü `CDragListBox`) liste kutusuna karşılık gelen iletişim şablonunuzda denetler.

Denetimleri için üye değişkenleri atama hakkında daha fazla bilgi için bkz. [iletişim kutusu denetimleri için üye değişkenleri tanımlama için kısayol](../../windows/defining-member-variables-for-dialog-controls.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

##  <a name="begindrag"></a>  CDragListBox::BeginDrag

Çağıran bir olay oluştuğunda framework sol fare tuşuna basmak gibi bir sürükleme işlemi gelebilecek.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) sürüklenen öğenin koordinatlarını içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Sıfır sürükleyerek izin veriliyorsa, aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bir sürükleme işlemi başladığında ne olacağını denetlemek istiyorsanız, bu işlev geçersiz kılar. Varsayılan uygulama, fare yakalar ve kullanıcı sol veya sağ fare düğmesine tıklar veya aynı zamanda sürükleme işlemi iptal edildi, ESC tuşuna bastığında kadar sürükleyin modda kalır.

##  <a name="canceldrag"></a>  CDragListBox::CancelDrag

Bir sürükleme işlemi iptal edildiğinde framework tarafından çağırılır.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) sürüklenen öğenin koordinatlarını içeren nesne.

### <a name="remarks"></a>Açıklamalar

Bu işlev, liste kutusu denetimi için herhangi bir özel işlemi işlemek için geçersiz kılın.

##  <a name="cdraglistbox"></a>  CDragListBox::CDragListBox

Oluşturur bir `CDragListBox` nesne.

```
CDragListBox();
```

##  <a name="dragging"></a>  CDragListBox::Dragging

Liste kutusu öğesi içinde sürüklenen framework tarafından çağırılır `CDragListBox` nesne.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) x ve y içeren nesne İmleç koordinatlarını ekran.

### <a name="return-value"></a>Dönüş Değeri

Görüntülenecek kaynak kimliği imleç. Aşağıdaki değerleri desteklenir:

- DL_COPYCURSOR öğe kopyalanır belirtir.

- DL_MOVECURSOR öğesi taşınacağını gösterir.

- DL_STOPCURSOR geçerli bırakma hedefi kabul edilebilir olmadığını gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış DL_MOVECURSOR döndürür. Ek işlevler sağlamak istiyorsanız, bu işlev geçersiz kılar.

##  <a name="drawinsert"></a>  CDragListBox::DrawInsert

Belirtilen dizin ile öğeyi çizmeden önce ekleme klavuzunu çizmek için framework tarafından çağırılır.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Parametreler

*nItem*<br/>
Ekleme noktasını sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Değeri - 1 klavuzunu temizler. Bu işlev ekleme klavuzunu davranışını ve görünümünü değiştirmek için geçersiz kılın.

##  <a name="dropped"></a>  CDragListBox::Dropped

Bir öğe içinde bırakıldığında framework tarafından çağırılır. bir `CDragListBox` nesne.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Parametreler

*nSrcIndex*<br/>
Bırakılan dize sıfır tabanlı dizini belirtir.

*PT*<br/>
A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) bırakma site koordinatları içeren nesne.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranışı, liste kutusu öğesini ve kendi verilerini yeni bir konuma kopyalar ve ardından özgün öğeyi siler. Liste kutusu öğeleri listesi içindeki diğer konumlara sürüklenmesi için kopyalarını etkinleştirme gibi varsayılan davranışını özelleştirmek için bu işlevi geçersiz kılar.

##  <a name="itemfrompt"></a>  CDragListBox::ItemFromPt

Liste kutusu öğesinin sıfır tabanlı dizini almak için bu işlevi bulunan çağrı *pt*.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
A [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) liste kutusunun içinde bir nokta koordinatları içeren nesne.

*bAutoScroll*<br/>
Kaydırma izin veriliyorsa, aksi durumda 0 sıfır.

### <a name="return-value"></a>Dönüş Değeri

Sürükleme liste kutusu öğesinin sıfır tabanlı dizini.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek TSTCON](../../visual-cpp-samples.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
