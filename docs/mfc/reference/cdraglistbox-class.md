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
ms.openlocfilehash: b260d3a88fc8c3f2d341005c1e47cfd9ab668e1e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500355"
---
# <a name="cdraglistbox-class"></a>CDragListBox sınıfı

Sınıfı, bir Windows liste kutusunun işlevlerini sağlamaya ek olarak, `CDragListBox` kullanıcının dosya adları gibi liste kutusu öğelerini liste kutusunda taşımasına izin verir.

## <a name="syntax"></a>Sözdizimi

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CDragListBox:: CDragListBox](#cdraglistbox)|Bir `CDragListBox` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDragListBox:: BeginDrag](#begindrag)|Bir sürükleme işlemi başladığında Framework tarafından çağırılır.|
|[CDragListBox:: CancelDrag](#canceldrag)|Bir sürükleme işlemi iptal edildiğinde Framework tarafından çağırılır.|
|[CDragListBox::D oyleme](#dragging)|Sürükleme işlemi sırasında Framework tarafından çağırılır.|
|[CDragListBox::D oy](#drawinsert)|Sürükleme listesi kutusunun ekleme kılavuzunu çizer.|
|[CDragListBox::D](#dropped)|Öğe bırakıldıktan sonra Framework tarafından çağırılır.|
|[CDragListBox:: ıtemfrompt](#itemfrompt)|Sürüklediğiniz öğenin koordinatlarını döndürür.|

## <a name="remarks"></a>Açıklamalar

Bu özelliğe sahip liste kutuları, kullanıcıların bir listedeki öğeleri kendileri için en faydalı şekilde sipariş edebilmesini sağlar. Varsayılan olarak, liste kutusu öğeyi listedeki yeni konuma taşır. Ancak `CDragListBox` nesneler, öğeleri taşımak yerine kopyalamak için özelleştirilebilir.

Sınıfla ilişkili liste kutusu denetiminin `CDragListBox` lbs_sort veya LBS_MULTIPLESELECT stili olmamalıdır. Liste kutusu stillerinin açıklaması için bkz. [liste kutusu stilleri](../../mfc/reference/styles-used-by-mfc.md#list-box-styles).

Uygulamanızın varolan bir iletişim kutusunda bir Sürükle liste kutusu kullanmak için iletişim kutusu düzenleyicisini kullanarak iletişim şablonunuza bir liste kutusu denetimi ekleyin ve iletişim `Control` `CDragListBox` şablonunuzda liste kutusu denetimine karşılık gelen bir üye değişkeni (kategori ve değişken türü) atayın.

Üye değişkenlerine denetim atama hakkında daha fazla bilgi için bkz. [Iletişim kutusu denetimleri Için üye değişkenleri tanımlama kısayolu](../../windows/adding-editing-or-deleting-controls.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CListBox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcmn. h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a> CDragListBox:: BeginDrag

Sol fare düğmesine basmak gibi bir sürükleme işlemine başlayabileceğiniz bir olay gerçekleştiğinde Framework tarafından çağırılır.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Sürüklediğiniz öğenin koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Sürüklemeye izin veriliyorsa sıfır olmayan, değilse 0.

### <a name="remarks"></a>Açıklamalar

Bir sürükleme işlemi başladığında ne olacağını denetlemek istiyorsanız bu işlevi geçersiz kılın. Varsayılan uygulama, fareyi yakalar ve Kullanıcı farenin sol veya sağ düğmesine tıklamasına veya ESC tuşuna basana kadar, sürükleme işleminin iptal edildiği zamanda, sürükleme modunda kalır.

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a> CDragListBox:: CancelDrag

Bir sürükleme işlemi iptal edildiğinde Framework tarafından çağırılır.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Sürüklediğiniz öğenin koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Liste kutusu denetiminiz için özel bir işlemeyi işlemek üzere bu işlevi geçersiz kılın.

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a> CDragListBox:: CDragListBox

Bir `CDragListBox` nesnesi oluşturur.

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a> CDragListBox::D oyleme

Bir liste kutusu öğesi nesnenin içinde sürüklendiğinde Framework tarafından çağırılır `CDragListBox` .

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
İmlecin x ve y ekran koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Görüntülenecek imlecin kaynak KIMLIĞI. Aşağıdaki değerler olasıdır:

- DL_COPYCURSOR, öğenin kopyalanacağını belirtir.

- DL_MOVECURSOR öğenin taşınacağını gösterir.

- DL_STOPCURSOR, geçerli bırakma hedefinin kabul edilemez olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış DL_MOVECURSOR döndürür. Ek işlevsellik sağlamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a> CDragListBox::D oy

Belirtilen dizine sahip öğeden önce ekleme kılavuzunu çizmek için Framework tarafından çağırılır.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Ekleme noktasının sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

-1 değeri, ekleme kılavuzunu temizler. Ekleme kılavuzunun görünümünü veya davranışını değiştirmek için bu işlevi geçersiz kılın.

## <a name="cdraglistboxdropped"></a><a name="dropped"></a> CDragListBox::D

Bir öğe bir nesne içinde bırakıldığında Framework tarafından çağırılır `CDragListBox` .

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Nsrcındex*<br/>
Bırakılan dizenin sıfır tabanlı dizinini belirtir.

*yönergelerinin*<br/>
Bırakma sitesinin koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış, liste kutusu öğesini ve verilerini yeni konuma kopyalar ve ardından orijinal öğeyi siler. Liste kutusu öğelerinin kopyalarının listedeki diğer konumlara sürüklenip etkinleştirilmesi gibi varsayılan davranışı özelleştirmek için bu işlevi geçersiz kılın.

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a> CDragListBox:: ıtemfrompt

*PT*konumunda bulunan liste kutusu öğesinin sıfır tabanlı dizinini almak için bu işlevi çağırın.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Liste kutusu içindeki bir noktanın koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

*bAutoScroll*<br/>
Kaydırmaya izin veriliyorsa sıfır dışı, aksi durumda 0.

### <a name="return-value"></a>Dönüş Değeri

Sürükle liste kutusu öğesinin sıfır tabanlı dizini.

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListBox sınıfı](../../mfc/reference/clistbox-class.md)
