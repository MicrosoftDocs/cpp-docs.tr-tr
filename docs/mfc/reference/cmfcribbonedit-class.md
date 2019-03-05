---
title: CMFCRibbonEdit sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CMFCRibbonEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::CanBeStretched
- AFXRIBBONEDIT/CMFCRibbonEdit::CopyFrom
- AFXRIBBONEDIT/CMFCRibbonEdit::CreateEdit
- AFXRIBBONEDIT/CMFCRibbonEdit::DestroyCtrl
- AFXRIBBONEDIT/CMFCRibbonEdit::DropDownList
- AFXRIBBONEDIT/CMFCRibbonEdit::EnableSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::GetCompactSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::GetIntermediateSize
- AFXRIBBONEDIT/CMFCRibbonEdit::GetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::GetWidth
- AFXRIBBONEDIT/CMFCRibbonEdit::HasCompactMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasFocus
- AFXRIBBONEDIT/CMFCRibbonEdit::HasLargeMode
- AFXRIBBONEDIT/CMFCRibbonEdit::HasSpinButtons
- AFXRIBBONEDIT/CMFCRibbonEdit::IsHighlighted
- AFXRIBBONEDIT/CMFCRibbonEdit::OnAfterChangeRect
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDraw
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawLabelAndImage
- AFXRIBBONEDIT/CMFCRibbonEdit::OnDrawOnList
- AFXRIBBONEDIT/CMFCRibbonEdit::OnEnable
- AFXRIBBONEDIT/CMFCRibbonEdit::OnHighlight
- AFXRIBBONEDIT/CMFCRibbonEdit::OnKey
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonDown
- AFXRIBBONEDIT/CMFCRibbonEdit::OnLButtonUp
- AFXRIBBONEDIT/CMFCRibbonEdit::OnRTLChanged
- AFXRIBBONEDIT/CMFCRibbonEdit::OnShow
- AFXRIBBONEDIT/CMFCRibbonEdit::Redraw
- AFXRIBBONEDIT/CMFCRibbonEdit::SetACCData
- AFXRIBBONEDIT/CMFCRibbonEdit::SetEditText
- AFXRIBBONEDIT/CMFCRibbonEdit::SetTextAlign
- AFXRIBBONEDIT/CMFCRibbonEdit::SetWidth
helpviewer_keywords:
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CanBeStretched
- CMFCRibbonEdit [MFC], CMFCRibbonEdit
- CMFCRibbonEdit [MFC], CopyFrom
- CMFCRibbonEdit [MFC], CreateEdit
- CMFCRibbonEdit [MFC], DestroyCtrl
- CMFCRibbonEdit [MFC], DropDownList
- CMFCRibbonEdit [MFC], EnableSpinButtons
- CMFCRibbonEdit [MFC], GetCompactSize
- CMFCRibbonEdit [MFC], GetEditText
- CMFCRibbonEdit [MFC], GetIntermediateSize
- CMFCRibbonEdit [MFC], GetTextAlign
- CMFCRibbonEdit [MFC], GetWidth
- CMFCRibbonEdit [MFC], HasCompactMode
- CMFCRibbonEdit [MFC], HasFocus
- CMFCRibbonEdit [MFC], HasLargeMode
- CMFCRibbonEdit [MFC], HasSpinButtons
- CMFCRibbonEdit [MFC], IsHighlighted
- CMFCRibbonEdit [MFC], OnAfterChangeRect
- CMFCRibbonEdit [MFC], OnDraw
- CMFCRibbonEdit [MFC], OnDrawLabelAndImage
- CMFCRibbonEdit [MFC], OnDrawOnList
- CMFCRibbonEdit [MFC], OnEnable
- CMFCRibbonEdit [MFC], OnHighlight
- CMFCRibbonEdit [MFC], OnKey
- CMFCRibbonEdit [MFC], OnLButtonDown
- CMFCRibbonEdit [MFC], OnLButtonUp
- CMFCRibbonEdit [MFC], OnRTLChanged
- CMFCRibbonEdit [MFC], OnShow
- CMFCRibbonEdit [MFC], Redraw
- CMFCRibbonEdit [MFC], SetACCData
- CMFCRibbonEdit [MFC], SetEditText
- CMFCRibbonEdit [MFC], SetTextAlign
- CMFCRibbonEdit [MFC], SetWidth
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
ms.openlocfilehash: e1a8f601c9f5798494ee34d3c3987222c14ecfa7
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292201"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit sınıfı

Bir Şerit çubuğunda bulunan bir düzenleme denetimi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Oluşturur bir `CMFCRibbonEdit` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|Belirtir olup olmadığını yüksekliğini `CMFCRibbonEdit` denetim dikey bir Şerit satır yüksekliğini artırabilirsiniz.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Oluşturur bir `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Belirtilen durumunu kopyalar `CMFCRibbonEdit` geçerli nesneye `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|Yeni bir metin kutusu oluşturur `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Yok eder `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Bir liste kutusu bırakır.|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Etkinleştirir ve metin kutusu için değer değiştirme düğmesi aralığı ayarlar.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|Compact VHD'nin boyutunu alır `CFMCRibbonEdit` nesne.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|Metin kutusundaki metni alır.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|Ara VHD'nin boyutunu alır `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Metin kutusunda metnin hizalamasını alır.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|Piksel cinsinden genişliğini alır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Gösteren görüntü için boyut olup olmadığını `CMFCRibbonEdit` denetim compact olabilir.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Belirtir olup olmadığını `CMFCRIbbonEdit` denetim odağa.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Gösteren görüntü için boyut olmadığını `CMFCRibbonEdit` denetimi büyük olabilir.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Metin kutusuna bir değer değiştirme düğmesi olup olmadığını gösterir.|
|[CMFCRibbonEdit::IsHighlighted](#ishighlighted)|Belirtir olup olmadığını `CMFCRibbonEdit` denetim vurgulanır.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Framework tarafından çağırılır, boyutları için görünen dikdörtgen `CMFCRibbonEdit` denetim değişiklikleri.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|Çizmek için framework tarafından çağırılır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|İçin görüntü ve etiket çizmek için framework tarafından çağırılır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Çizmek için framework tarafından çağırılır `CMFCRibbonEdit` komutlar liste kutusu denetimi.|
|[CMFCRibbonEdit::OnEnable](#onenable)|Etkinleştirmek veya devre dışı bırakmak için framework tarafından çağırılır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|İşaretçi girdiğinde veya sınırları bırakır framework tarafından çağırılır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::OnKey](#onkey)|Kullanıcı bir tuş ipucunu bastığında framework tarafından çağırılır ve `CMFCRibbonEdit` denetim odağa.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Güncelleştirmek için framework tarafından çağırılır `CMFCRibbonEdit` kullanıcının sol fare tuşuna denetimde bastığında denetim.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Kullanıcının sol fare düğmesini bıraktığında framework tarafından çağırılır.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Güncelleştirmek için framework tarafından çağırılır `CMFCRibbonEdit` Düzen yönünü değiştiğinde denetim.|
|[CMFCRibbonEdit::OnShow](#onshow)|Göstermek veya gizlemek için framework tarafından çağırılır `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::Redraw](#redraw)|Görüntülenmesini güncelleştirmeleri `CMFCRibbonEdit` denetimi.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|Erişilebilirlik verilerini ayarlar `CMFCRibbonEdit` nesne.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|Metin, metin kutusuna ayarlar.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Metin kutusunda metin hizalamasını ayarlar.|
|[CMFCRibbonEdit::SetWidth](#setwidth)|Metin kutusunun genişliğini ayarlar `CMFCRibbonEdit` denetimi.|

## <a name="remarks"></a>Açıklamalar

## <a name="example"></a>Örnek

Aşağıdaki örnek nasıl oluşturulacağını gösterir. bir `CMFCRibbonEdit` Nesne Döndürme düğmeleri düzenleme denetiminin yanındaki Göster ve metin düzenleme denetiminin ayarlayın. Bu kod parçacığı parçasıdır [MS Office 2007 Demo örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxRibbonEdit.h

##  <a name="canbestretched"></a>  CMFCRibbonEdit::CanBeStretched

Belirtir olup olmadığını yüksekliğini [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim dikey bir Şerit satır yüksekliğini artırabilirsiniz.

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="cmfcribbonedit"></a>  CMFCRibbonEdit::CMFCRibbonEdit

Oluşturur bir [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
[in] Komut kimliği için `CMFCRibbonEdit` denetimi.

*nWidth*<br/>
[in] Piksel cinsinden için metin kutusunun genişliği `CMFCRibbonEdit` denetimi.

*lpszLabel*<br/>
[in] Etiketi `CMFCRibbonEdit` denetimi.

*Bir*<br/>
[in] Küçük resmin dizini için kullanılacak `CMFCRibbonEdit` denetimi. Küçük resimler koleksiyonunu üst Şerit kategorisi tarafından korunur.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonEdit` Denetim büyük bir görüntü kullanmaz.

##  <a name="copyfrom"></a>  CMFCRibbonEdit::CopyFrom

Belirtilen durumunu kopyalar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) geçerli nesneye [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kaynak `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

*Src* tür parametresi olmalıdır `CMFCRibbonEdit`.

##  <a name="createedit"></a>  CMFCRibbonEdit::CreateEdit

Yeni bir metin kutusu oluşturur [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Üst penceresine bir işaretçi `CMFCRibbonEdit` nesne.

*dwEditStyle*<br/>
[in] Metin kutusunun stilini belirtir. Pencere stilleri ile açıklamalar bölümünde listelenen birleştirebilirsiniz [düzenleme denetimi stilleri](/windows/desktop/Controls/edit-control-styles) Windows SDK'da açıklanmıştır.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yeni bir metin kutusu için bir işaretçi; Aksi takdirde NULL.

### <a name="remarks"></a>Açıklamalar

Türetilen bir sınıfta bir özel metin kutusu oluşturmak için bu yöntemi yok sayın.

Aşağıdaki uygulayabilirsiniz [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir metin kutusu için:

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>  CMFCRibbonEdit::DestroyCtrl

Yok eder [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="dropdownlist"></a>  CMFCRibbonEdit::DropDownList

Bir liste kutusu bırakır.

```
virtual void DropDownList();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntemi hiçbir şey yapmaz. Açılan bir liste kutusu için bu yöntemi yok sayın.

##  <a name="enablespinbuttons"></a>  CMFCRibbonEdit::EnableSpinButtons

Etkinleştirir ve metin kutusu için değer değiştirme düğmesi aralığı ayarlar.

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
[in] Değer değiştirme düğmesi minimum değer.

*nMax*<br/>
[in] Değer değiştirme düğmesi maksimum değer.

### <a name="remarks"></a>Açıklamalar

Döndürme düğmelerini görüntüle yukarı ve aşağı oka ve sabit bir değer kümesi ile taşımak kullanıcıları etkinleştirin.

##  <a name="getcompactsize"></a>  CMFCRibbonEdit::GetCompactSize

Compact VHD'nin boyutunu alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` nesne.

### <a name="return-value"></a>Dönüş Değeri

Compact boyutunu `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="getedittext"></a>  CMFCRibbonEdit::GetEditText

Metin kutusundaki metni alır.

```
CString GetEditText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

##  <a name="getintermediatesize"></a>  CMFCRibbonEdit::GetIntermediateSize

Ara VHD'nin boyutunu alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` nesne.

### <a name="return-value"></a>Dönüş Değeri

Ara boyutu `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="gettextalign"></a>  CMFCRibbonEdit::GetTextAlign

Metin kutusunda metnin hizalamasını alır.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin hizalama numaralandırılmış değeri. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer aşağıdaki düzenleme denetimi stilleri biridir:

- **ES_LEFT** sola hizalama

- **ES_CENTER** ortaya hizalama için

- **Es_rıght** sağa hizalama

Bu stiller hakkında daha fazla bilgi için bkz: [Düzenle denetim stilleri](/windows/desktop/Controls/edit-control-styles).

##  <a name="getwidth"></a>  CMFCRibbonEdit::GetWidth

Piksel cinsinden genişliğini alır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*bInFloatyMode*<br/>
[in] TRUE ise `CMFCRibbonEdit` denetimidir kayan modunda; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Piksel cinsinden genişliği, `CMFCRibbonEdit` denetimi.

### <a name="remarks"></a>Açıklamalar

##  <a name="hascompactmode"></a>  CMFCRibbonEdit::HasCompactMode

Gösteren görüntü için boyut olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim compact olabilir.

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem her zaman TRUE döndürür. Görüntü boyutu compact olup olmadığını belirtmek için bu yöntemi yok sayın.

##  <a name="hasfocus"></a>  CMFCRibbonEdit::HasFocus

Belirtir olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim odağa.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise `CMFCRibbonEdit` denetim odağa; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="haslargemode"></a>  CMFCRibbonEdit::HasLargeMode

Gösteren görüntü için boyut olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim büyük olabilir.

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman false değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem her zaman false değerini döndürür. Görüntü boyutu büyük olup olmadığını belirtmek için bu yöntemi yok sayın.

##  <a name="hasspinbuttons"></a>  CMFCRibbonEdit::HasSpinButtons

Metin kutusuna bir değer değiştirme düğmesi olup olmadığını gösterir.

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusuna bir değer değiştirme düğmesi varsa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="ishighlighted"></a>  CMFCRibbonEdit::IsHighlighted

Belirtir olup olmadığını [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim vurgulanır.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

TRUE ise `CMFCRibbonEdit` denetimidir vurgulanan; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onafterchangerect"></a>  CMFCRibbonEdit::OnAfterChangeRect

Framework tarafından çağırılır, boyutları için görünen dikdörtgen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi Değiştir.

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` denetimi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>  CMFCRibbonEdit::OnDraw

Çizmek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` denetimi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawlabelandimage"></a>  CMFCRibbonEdit::OnDrawLabelAndImage

İçin görüntü ve etiket çizmek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` denetimi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawonlist"></a>  CMFCRibbonEdit::OnDrawOnList

Çizmek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) komutlar liste kutusu denetimi.

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçiye `CMFCRibbonEdit` denetimi.

*strText*<br/>
[in] Görüntülenecek metni [ ] (../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit sınıfı").

*nTextOffset*<br/>
[in] Görüntülenecek metni liste kutusuna sol tarafındaki piksel cinsinden uzaklığı.

*Rect*<br/>
[in] İçin görünen dikdörtgen `CMFCRibbonEdit` denetimi.

*bIsSelected*<br/>
[in] Bu parametre kullanılmaz.

*bHighlighted*<br/>
[in] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Hızlı Erişim Araç çubuğunu özelleştirme olanağı Şerit denetimleri komutlar liste kutusu görüntüler.

##  <a name="onenable"></a>  CMFCRibbonEdit::OnEnable

Etkinleştirmek veya devre dışı bırakmak için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bSistemlerde*<br/>
[in] Denetimi etkinleştirmek için TRUE; Denetimin devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onhighlight"></a>  CMFCRibbonEdit::OnHighlight

İşaretçi girdiğinde veya sınırları bırakır framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
[in] İşaretçinin sınırları içinde ise TRUE `CMFCRibbonEdit` denetler; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onkey"></a>  CMFCRibbonEdit::OnKey

Kullanıcı bir tuş ipucunu bastığında framework tarafından çağırılır ve [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim odağa.

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Parametreler

*bIsMenuKey*<br/>
[in] Tuş ipucunu bir açılır menü görüntüleyen TRUE; Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Olay işleniyorsa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttondown"></a>  CMFCRibbonEdit::OnLButtonDown

Güncelleştirmek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) kullanıcının sol fare tuşuna denetimde bastığında denetim.

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttonup"></a>  CMFCRibbonEdit::OnLButtonUp

Kullanıcının sol fare düğmesini bıraktığında framework tarafından çağırılır.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Noktası*<br/>
[in] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

##  <a name="onrtlchanged"></a>  CMFCRibbonEdit::OnRTLChanged

Güncelleştirmek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) Düzen yönünü değiştiğinde denetim.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parametreler

*bIsRTL*<br/>
[in] Sağdan sola düzen ise TRUE; Soldan sağa düzen ise FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onshow"></a>  CMFCRibbonEdit::OnShow

Göstermek veya gizlemek için framework tarafından çağırılır [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bBilgi Göster*<br/>
[in] Denetim göstermek için TRUE; Denetimi gizlemek için FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="redraw"></a>  CMFCRibbonEdit::Redraw

Görünümünü güncelleştirir [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem için görünen dikdörtgen çizer `CMFCRibbonEdit` dolaylı olarak çağırarak [CWnd::RedrawWindow](/windows/desktop/api/winuser/nf-winuser-redrawwindow) RDW_INVALIDATE RDW_ERASE ve RDW_UPDATENOW bayraklarıyla ayarlayın.

##  <a name="setaccdata"></a>  CMFCRibbonEdit::SetACCData

Erişilebilirlik verilerini ayarlar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesne.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Üst penceresine bir işaretçi `CMFCRibbonEdit` nesne.

*Veri*<br/>
Erişilebilirlik verilerini `CMFCRibbonEdit` nesne.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="setedittext"></a>  CMFCRibbonEdit::SetEditText

Metin, metin kutusuna ayarlar.

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
[in] Metin kutusu metni.

##  <a name="settextalign"></a>  CMFCRibbonEdit::SetTextAlign

Metin kutusunda metin hizalamasını ayarlar.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
[in] Metin hizalama numaralandırılmış değeri. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Parametre *nAlign* denetim stilleri aşağıdaki düzen, biridir:

- ES_LEFT sola hizalama

- ES_CENTER ortaya hizalama için

- Es_rıght sağa hizalama

Bu stiller hakkında daha fazla bilgi için bkz: [Düzenle denetim stilleri](/windows/desktop/Controls/edit-control-styles).

##  <a name="setwidth"></a>  CMFCRibbonEdit::SetWidth

Metin kutusunun genişliğini ayarlar [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi.

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
[in] Metin kutusunun piksel cinsinden genişliği.

*bInFloatyMode*<br/>
Kayan modu genişliğini ayarlamak için TRUE; Normal mod genişliğini ayarlamak için FALSE.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonEdit` Denetleyebilir, görüntüleme moduna bağlı olarak iki genişlikleri: modu ve normal mod kayan.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
