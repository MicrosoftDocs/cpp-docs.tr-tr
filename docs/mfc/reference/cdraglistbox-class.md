---
title: CDragListBox Sınıfı
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
ms.openlocfilehash: 0d1ae94948e1143a5bac17985423c4bd1bfbaf65
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374040"
---
# <a name="cdraglistbox-class"></a>CDragListBox Sınıfı

`CDragListBox` Sınıf, windows liste kutusunun işlevselliğini sağlamanın yanı sıra, kullanıcının liste kutusu içinde dosya adları gibi liste kutusu öğelerini taşımasına olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
class CDragListBox : public CListBox
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CDragListBox::CDragListBox](#cdraglistbox)|Bir `CDragListBox` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDragListBox::BeginDrag](#begindrag)|Sürükleme işlemi başladığında çerçeve tarafından çağrılır.|
|[CDragListBox::İptalSürükley](#canceldrag)|Sürükleme işlemi iptal edildiğinde çerçeve tarafından çağrılır.|
|[CDragListBox::Dragging](#dragging)|Sürükleme işlemi sırasında çerçeve tarafından çağrılır.|
|[CDragListBox::DrawInsert](#drawinsert)|Sürükle listesi kutusunun ekleme kılavuzunu çizer.|
|[CDragListBox::Dropped](#dropped)|Öğe düşürüldükten sonra çerçeve tarafından çağrılır.|
|[CdraglistBox::ItemFromPt](#itemfrompt)|Sürüklenen öğenin koordinatlarını verir.|

## <a name="remarks"></a>Açıklamalar

Bu özelme sahip liste kutuları, kullanıcıların öğeleri bir listedeki öğeleri kendileri için en yararlı şekilde sipariş etmelerine olanak sağlar. Varsayılan olarak, liste kutusu öğeyi listedeki yeni konuma taşır. Ancak, `CDragListBox` nesneleri taşımak yerine öğeleri kopyalamak için özelleştirilebilir.

`CDragListBox` Sınıfla ilişkili liste kutusu denetimi, LBS_SORT veya LBS_MULTIPLESELECT stiline sahip olmamalıdır. Liste kutusu stillerinin açıklaması için [Liste Kutusu Stilleri'ne](../../mfc/reference/styles-used-by-mfc.md#list-box-styles)bakın.

Uygulamanızın varolan bir iletişim kutusunda sürükle listesi kutusu kullanmak için, iletişim düzenleyicisini kullanarak iletişim şablonunuza bir liste `Control` kutusu denetimi `CDragListBox`ekleyin ve ardından iletişim şablonunuzda liste kutusu denetimine karşılık gelen bir üye değişken (Kategori ve Değişken Türü) atayın.

Üye değişkenlere denetim atama hakkında daha fazla bilgi için, [İletişim Denetimleri için Üye Değişkenleri Tanımlama için Kısayol'a](../../windows/defining-member-variables-for-dialog-controls.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

[Clistbox](../../mfc/reference/clistbox-class.md)

`CDragListBox`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcmn.h

## <a name="cdraglistboxbegindrag"></a><a name="begindrag"></a>CDragListBox::BeginDrag

Sol fare düğmesine basmak gibi sürükleme işlemine başlabilen bir olay gerçekleştiğinde çerçeve tarafından çağrılır.

```
virtual BOOL BeginDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Sürüklenen öğenin koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Sürüklemeye izin veriliyorsa sıfır yok, aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Sürükleme işlemi başladığında ne olacağını denetlemek istiyorsanız bu işlevi geçersiz kılın. Varsayılan uygulama fareyi yakalar ve kullanıcı sol veya sağ fare düğmesini tıklatana veya ESC tuşuna basana ve bu sırada sürükleme işlemi iptal edilene kadar sürükleme modunda kalır.

## <a name="cdraglistboxcanceldrag"></a><a name="canceldrag"></a>CDragListBox::İptalSürükley

Sürükleme işlemi iptal edildiğinde çerçeve tarafından çağrılır.

```
virtual void CancelDrag(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Sürüklenen öğenin koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Liste kutu denetiminiz için herhangi bir özel işleme işlemek için bu işlevi geçersiz kılın.

## <a name="cdraglistboxcdraglistbox"></a><a name="cdraglistbox"></a>CDragListBox::CDragListBox

Bir `CDragListBox` nesne inşa eder.

```
CDragListBox();
```

## <a name="cdraglistboxdragging"></a><a name="dragging"></a>CDragListBox::Dragging

Bir liste kutusu öğesi `CDragListBox` nesne içinde sürüklenirken çerçeve tarafından çağrılır.

```
virtual UINT Dragging(CPoint pt);
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
İmlecin x ve y ekran koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="return-value"></a>Dönüş Değeri

İmlecin görüntülenecek kaynak kimliği. Aşağıdaki değerler mümkündür:

- DL_COPYCURSOR Öğenin kopyalanacağını gösterir.

- DL_MOVECURSOR Maddenin taşınacağını gösterir.

- DL_STOPCURSOR Geçerli bırakma hedefinin kabul edilemez olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış DL_MOVECURSOR döndürür. Ek işlevsellik sağlamak istiyorsanız bu işlevi geçersiz kılın.

## <a name="cdraglistboxdrawinsert"></a><a name="drawinsert"></a>CDragListBox::DrawInsert

Belirtilen dizin ile öğenin önce ekleme kılavuzu çizmek için çerçeve tarafından çağrılır.

```
virtual void DrawInsert(int nItem);
```

### <a name="parameters"></a>Parametreler

*nÖğe*<br/>
Ekleme noktasının sıfır tabanlı dizin.

### <a name="remarks"></a>Açıklamalar

- 1 değeri ekleme kılavuzunu temizler. Ekleme kılavuzunun görünümünü veya davranışını değiştirmek için bu işlevi geçersiz kılın.

## <a name="cdraglistboxdropped"></a><a name="dropped"></a>CDragListBox::Dropped

Bir öğe nesnenin içine `CDragListBox` bırakıldığında çerçeve tarafından çağrılır.

```
virtual void Dropped(
    int nSrcIndex,
    CPoint pt);
```

### <a name="parameters"></a>Parametreler

*nSrcIndex*<br/>
Bırakılan dizenin sıfır tabanlı dizinini belirtir.

*Pt*<br/>
Bırakma alanının koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

### <a name="remarks"></a>Açıklamalar

Varsayılan davranış, liste kutusu öğesini ve verilerini yeni konuma kopyalar ve özgün öğeyi siler. Liste kutusu öğelerinin kopyalarının listedeki diğer konumlara sürüklenmesini etkinleştirmek gibi varsayılan davranışı özelleştirmek için bu işlevi geçersiz kılın.

## <a name="cdraglistboxitemfrompt"></a><a name="itemfrompt"></a>CdraglistBox::ItemFromPt

*Pt'de*bulunan liste kutusu öğesinin sıfır tabanlı dizinini almak için bu işlevi arayın.

```
int ItemFromPt(
    CPoint pt,
    BOOL bAutoScroll = TRUE) const;
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Liste kutusundaki bir noktanın koordinatlarını içeren bir [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.

*bAutoScroll*<br/>
Kaydırma izin verilirse nonzero, aksi takdirde 0.

### <a name="return-value"></a>Dönüş Değeri

Sürükle listesi kutusu öğesinin sıfır tabanlı dizin.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TSTCON](../../overview/visual-cpp-samples.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)
