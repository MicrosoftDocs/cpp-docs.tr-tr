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
ms.openlocfilehash: 4f973074fbec3d04b1c1a74852b02ff2564217c1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69504944"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit sınıfı

Şerit çubuğunda bulunan bir düzenleme denetimi uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit:: CMFCRibbonEdit](#cmfcribbonedit)|Bir `CMFCRibbonEdit` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit:: Canbeesnetilen](#canbestretched)|`CMFCRibbonEdit` Denetimin yüksekliğinin bir şerit satırının yüksekliğine dikey olarak artırıp artamayacağını gösterir.|
|[CMFCRibbonEdit:: CMFCRibbonEdit](#cmfcribbonedit)|Bir `CMFCRibbonEdit` nesnesi oluşturur.|
|[CMFCRibbonEdit:: CopyFrom](#copyfrom)|Belirtilen `CMFCRibbonEdit` nesnenin durumunu geçerli `CMFCRibbonEdit` nesneye kopyalar.|
|[CMFCRibbonEdit:: CreateEdit](#createedit)|`CMFCRibbonEdit` Nesnesi için yeni bir metin kutusu oluşturur.|
|[CMFCRibbonEdit::D estroyCtrl](#destroyctrl)|`CMFCRibbonEdit` Nesneyi yok eder.|
|[CMFCRibbonEdit::D ropDownList](#dropdownlist)|Liste kutusunu kapatır.|
|[CMFCRibbonEdit:: EnableSpinButtons](#enablespinbuttons)|Metin kutusu için döndürme düğmesinin aralığını belirler ve ayarlar.|
|[CMFCRibbonEdit:: GetCompactSize](#getcompactsize)|`CFMCRibbonEdit` Nesnenin sıkıştırılmış boyutunu alır.|
|[CMFCRibbonEdit:: GetEditText](#getedittext)|Metin kutusundaki metni alır.|
|[CMFCRibbonEdit:: GetIntermediateSize](#getintermediatesize)|`CMFCRibbonEdit` Nesnenin ara boyutunu alır.|
|[CMFCRibbonEdit:: GetTextAlign](#gettextalign)|Metin kutusuna metnin hizalamasını alır.|
|[CMFCRibbonEdit:: GetWidth](#getwidth)|`CMFCRibbonEdit` Denetimin piksel cinsinden genişliğini alır.|
|[CMFCRibbonEdit:: HasCompactMode](#hascompactmode)|`CMFCRibbonEdit` Denetim için görüntü boyutunun sıkıştırılamayacağını belirtir.|
|[CMFCRibbonEdit:: HasFocus](#hasfocus)|`CMFCRIbbonEdit` Denetimin odağa sahip olup olmadığını gösterir.|
|[CMFCRibbonEdit:: HasLargeMode](#haslargemode)|`CMFCRibbonEdit` Denetimin görüntüleme boyutunun büyük olup olmadığını gösterir.|
|[CMFCRibbonEdit:: HasSpinButtons](#hasspinbuttons)|Metin kutusunun bir döndürme düğmesine sahip olup olmadığını gösterir.|
|[CMFCRibbonEdit:: ısvurgulu](#ishighlighted)|`CMFCRibbonEdit` Denetimin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCRibbonEdit:: OnAfterChangeRect](#onafterchangerect)|`CMFCRibbonEdit` Denetim için görüntü dikdörtgeninin boyutları değiştiğinde Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnDraw](#ondraw)|`CMFCRibbonEdit` Denetimi çizmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: Ondrawlabelandımage](#ondrawlabelandimage)|`CMFCRibbonEdit` Denetim için etiket ve resim çizmek üzere Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnDrawOnList](#ondrawonlist)|Bir komut listesi kutusunda `CMFCRibbonEdit` denetimi çizmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnEnable](#onenable)|`CMFCRibbonEdit` Denetimi etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnHighlight](#onhighlight)|İşaretçi `CMFCRibbonEdit` denetimin sınırları içine girdiğinde veya ayrıldığında Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnKey](#onkey)|Kullanıcı bir KeyTip tuşuna bastığında ve `CMFCRibbonEdit` denetim odağa sahip olduğunda Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: Onlbuttonazaltma](#onlbuttondown)|Kullanıcı denetimdeki sol fare düğmesine bastığında `CMFCRibbonEdit` denetimi güncelleştirmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnLButtonUp](#onlbuttonup)|Kullanıcı sol fare düğmesini bıraktığında Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnRTLChanged](#onrtlchanged)|Düzen yön değiştirdiğinde `CMFCRibbonEdit` denetimi güncelleştirmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnShow](#onshow)|`CMFCRibbonEdit` Denetimi göstermek veya gizlemek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: yeniden Çiz](#redraw)|`CMFCRibbonEdit` Denetimin görüntüsünü güncelleştirir.|
|[CMFCRibbonEdit:: SetACCData](#setaccdata)|`CMFCRibbonEdit` Nesne için erişilebilirlik verilerini ayarlar.|
|[CMFCRibbonEdit:: SetEditText](#setedittext)|Metin kutusundaki metni ayarlar.|
|[CMFCRibbonEdit:: SetTextAlign](#settextalign)|Metin kutusunun metin hizalamasını ayarlar.|
|[CMFCRibbonEdit:: SetWidth](#setwidth)|`CMFCRibbonEdit` Denetimin metin kutusunun genişliğini ayarlar.|

## <a name="remarks"></a>Açıklamalar

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCRibbonEdit` nesne oluşturmayı, düzenleme denetiminin yanındaki döndürme düğmelerini göstermeyi ve düzenleme denetiminin metnini ayarlamayı gösterir. Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonEdit. h

##  <a name="canbestretched"></a>CMFCRibbonEdit:: Canbeesnetilen

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin yüksekliğinin bir şerit satırının yüksekliğine dikey olarak artırıp artamayacağını gösterir.

```
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="cmfcribbonedit"></a>CMFCRibbonEdit:: CMFCRibbonEdit

Bir [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi oluşturur.

```
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki `CMFCRibbonEdit` Denetim için komut kimliği.

*nWidth*<br/>
'ndaki `CMFCRibbonEdit` Denetimin metin kutusunun piksel cinsinden genişliği.

*lpszLabel*<br/>
'ndaki `CMFCRibbonEdit` Denetimin etiketi.

*Ngörüntü*<br/>
'ndaki `CMFCRibbonEdit` Denetim için kullanılacak küçük görüntünün dizini. Küçük görüntülerin koleksiyonu üst şerit kategorisi tarafından korunur.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonEdit` Denetim büyük bir görüntü kullanmaz.

##  <a name="copyfrom"></a>CMFCRibbonEdit:: CopyFrom

Belirtilen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin durumunu geçerli [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesine kopyalar.

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*YN*<br/>
'ndaki Kaynak `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

*Src* parametresinin türünde `CMFCRibbonEdit`olması gerekir.

##  <a name="createedit"></a>CMFCRibbonEdit:: CreateEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi için yeni bir metin kutusu oluşturur.

```
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki `CMFCRibbonEdit` Nesnenin üst penceresine yönelik bir işaretçi.

*dwEditStyle*<br/>
'ndaki Metin kutusunun stilini belirtir. Açıklamalar bölümünde listelenen pencere stillerini, Windows SDK açıklanan [düzenleme denetim stilleriyle](/windows/win32/Controls/edit-control-styles) birleştirebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa yeni metin kutusu işaretçisi. Aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Özel metin kutusu oluşturmak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir metin kutusuna uygulayabilirsiniz:

- **WS_CHILD**

- **WS_VISIBLE**

- **WS_DISABLED**

- **WS_GROUP**

- **WS_TABSTOP**

##  <a name="destroyctrl"></a>CMFCRibbonEdit::D estroyCtrl

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesini yok eder.

```
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Açıklamalar

##  <a name="dropdownlist"></a>CMFCRibbonEdit::D ropDownList

Liste kutusunu kapatır.

```
virtual void DropDownList();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Liste kutusunu aşağı eklemek için bu yöntemi geçersiz kılın.

##  <a name="enablespinbuttons"></a>CMFCRibbonEdit:: EnableSpinButtons

Metin kutusu için döndürme düğmesinin aralığını belirler ve ayarlar.

```
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en az*<br/>
'ndaki Döndürme düğmesinin en küçük değeri.

*Ngünde en çok*<br/>
'ndaki Döndürme düğmesinin en büyük değeri.

### <a name="remarks"></a>Açıklamalar

Döndürme düğmeleri, bir yukarı ve aşağı ok görüntüler ve kullanıcıların sabit bir değer kümesi arasında hareket kurmasını sağlar.

##  <a name="getcompactsize"></a>CMFCRibbonEdit:: GetCompactSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin sıkıştırılmış boyutunu alır.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Nesne için bir cihaz bağlamı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Nesnenin sıkıştırılmış boyutu.

### <a name="remarks"></a>Açıklamalar

##  <a name="getedittext"></a>CMFCRibbonEdit:: GetEditText

Metin kutusundaki metni alır.

```
CString GetEditText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

##  <a name="getintermediatesize"></a>CMFCRibbonEdit:: GetIntermediateSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin ara boyutunu alır.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Nesne için bir cihaz bağlamı işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Nesnenin ara boyutu.

### <a name="remarks"></a>Açıklamalar

##  <a name="gettextalign"></a>CMFCRibbonEdit:: GetTextAlign

Metin kutusuna metnin hizalamasını alır.

```
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin hizalaması numaralandırılmış değeri. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer aşağıdaki düzenleme denetimi stillerinden biridir:

- Sol hizalama için **ES_LEFT**

- **ES_CENTER** for Center hizalaması

- Sağ hizalama için **ES_RIGHT**

Bu stiller hakkında daha fazla bilgi için bkz. [Denetim stillerini düzenleme](/windows/win32/Controls/edit-control-styles).

##  <a name="getwidth"></a>CMFCRibbonEdit:: GetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin piksel cinsinden genişliğini alır.

```
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*Binfloatyımode*<br/>
'ndaki `CMFCRibbonEdit` Denetim kayan moddaysa true, aksi durumda false.

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Denetimin piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

##  <a name="hascompactmode"></a>CMFCRibbonEdit:: HasCompactMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin görüntüleme boyutunun sıkıştırılamayacağını gösterir.

```
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman TRUE değerini döndürür. Görüntü boyutunun sıkıştıramayacağını belirtmek için bu yöntemi geçersiz kılın.

##  <a name="hasfocus"></a>CMFCRibbonEdit:: HasFocus

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin odağa sahip olup olmadığını gösterir.

```
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Denetim odağa sahipse true; Aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

##  <a name="haslargemode"></a>CMFCRibbonEdit:: HasLargeMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için görüntüleme boyutunun büyük olup olmadığını gösterir.

```
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE döndürür. Görüntülenen boyutun büyük olup olmadığını belirtmek için bu yöntemi geçersiz kılın.

##  <a name="hasspinbuttons"></a>CMFCRibbonEdit:: HasSpinButtons

Metin kutusunun bir döndürme düğmesine sahip olup olmadığını gösterir.

```
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusunda bir döndürme düğmesi varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

##  <a name="ishighlighted"></a>CMFCRibbonEdit:: ısvurgulu

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin vurgulanıp vurgulanmadığını gösterir.

```
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Denetim vurgulanmışsa true; Aksi takdirde false.

### <a name="remarks"></a>Açıklamalar

##  <a name="onafterchangerect"></a>CMFCRibbonEdit:: OnAfterChangeRect

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim değişikliğinin görüntüleme dikdörtgeninin boyutları değiştiğinde Framework tarafından çağırılır.

```
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Denetim için bir cihaz bağlamı işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>CMFCRibbonEdit:: OnDraw

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini çizmek için Framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Denetim için bir cihaz bağlamı işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawlabelandimage"></a>CMFCRibbonEdit:: Ondrawlabelandımage

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için etiket ve resim çizmek üzere Framework tarafından çağırılır.

```
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Denetim için bir cihaz bağlamı işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawonlist"></a>CMFCRibbonEdit:: OnDrawOnList

Bir Komutlar liste kutusuna [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini çizmek için Framework tarafından çağırılır.

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

*Kökündeki*<br/>
'ndaki `CMFCRibbonEdit` Denetim için bir cihaz bağlamı işaretçisi.

*strText*<br/>
'ndaki Görüntüleme metni [ ] (../../mfc/reference/cmfcribbonedit-class.md "CMFCRibbonEdit sınıfı").

*nTextOffset*<br/>
'ndaki Liste kutusunun sol tarafındaki görüntü metnine göre piksel cinsinden uzaklık.

*Rect*<br/>
'ndaki `CMFCRibbonEdit` Denetimin görüntüleme dikdörtgeni.

*bIsSelected*<br/>
'ndaki Bu parametre kullanılmaz.

*Bvurgulu*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Komutlar liste kutusu, kullanıcıların hızlı erişim araç çubuğunu özelleştirmesini sağlamak için şerit denetimleri görüntüler.

##  <a name="onenable"></a>CMFCRibbonEdit:: OnEnable

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır.

```
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Denetimi etkinleştirmek için TRUE; Denetimi devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onhighlight"></a>CMFCRibbonEdit:: OnHighlight

İşaretçi [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin sınırları içine girdiğinde ya da ayrıldığında Framework tarafından çağırılır.

```
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
'ndaki İşaretçi `CMFCRibbonEdit` denetimin sınırları içinde ise true, aksi durumda false.

### <a name="remarks"></a>Açıklamalar

##  <a name="onkey"></a>CMFCRibbonEdit:: OnKey

Kullanıcı bir KeyTip tuşuna bastığında ve [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi odağa sahip olduğunda Framework tarafından çağırılır.

```
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Parametreler

*Bımenukey*<br/>
'ndaki Keytıp bir açılır menü görüntülüyorsa, doğru. Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Olay işlenirse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttondown"></a>CMFCRibbonEdit:: Onlbuttonazaltma

Kullanıcı denetimdeki sol fare düğmesine bastığında [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncellemek için Framework tarafından çağırılır.

```
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

##  <a name="onlbuttonup"></a>CMFCRibbonEdit:: OnLButtonUp

Kullanıcı sol fare düğmesini bıraktığında Framework tarafından çağırılır.

```
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

##  <a name="onrtlchanged"></a>CMFCRibbonEdit:: OnRTLChanged

Düzen yön değiştirdiğinde [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncellemek için Framework tarafından çağırılır.

```
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parametreler

*bIsRTL*<br/>
'ndaki Düzen sağdan sola ise doğru; Düzen soldan sağa ise FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="onshow"></a>CMFCRibbonEdit:: OnShow

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini göstermek veya gizlemek için Framework tarafından çağırılır.

```
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Denetimi göstermek için TRUE; Denetimi gizlemek için FALSE.

### <a name="remarks"></a>Açıklamalar

##  <a name="redraw"></a>CMFCRibbonEdit:: yeniden Çiz

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin görüntülenmesini güncelleştirir.

```
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCRibbonEdit` [CWnd:: RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) öğesini dolaylı olarak RDW_INVALIDATE, RDW_ERASE ve RDW_UPDATENOW Flags kümesiyle çağırarak nesnenin görüntüleme dikdörtgenini yeniden çizer.

##  <a name="setaccdata"></a>CMFCRibbonEdit:: SetACCData

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi için erişilebilirlik verilerini ayarlar.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
`CMFCRibbonEdit` Nesnenin üst penceresine yönelik işaretçi.

*verileri*<br/>
`CMFCRibbonEdit` Nesne için erişilebilirlik verileri.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="setedittext"></a>CMFCRibbonEdit:: SetEditText

Metin kutusundaki metni ayarlar.

```
void SetEditText(CString strText);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
'ndaki Metin kutusu metni.

##  <a name="settextalign"></a>CMFCRibbonEdit:: SetTextAlign

Metin kutusunun metin hizalamasını ayarlar.

```
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
'ndaki Metin hizalaması numaralandırılmış değeri. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

*NAlign* parametresi aşağıdaki düzenleme denetimi stillerinden biridir:

- Sol hizalama için ES_LEFT

- ES_CENTER for Center hizalaması

- Sağ hizalama için ES_RIGHT

Bu stiller hakkında daha fazla bilgi için bkz. [Denetim stillerini düzenleme](/windows/win32/Controls/edit-control-styles).

##  <a name="setwidth"></a>CMFCRibbonEdit:: SetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için metin kutusunun genişliğini ayarlar.

```
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>Parametreler

*nWidth*<br/>
'ndaki Metin kutusunun piksel cinsinden genişliği.

*Binfloatyımode*<br/>
Kayan mod için genişliği ayarlamak için TRUE; Normal mod için genişliği ayarlamak için FALSE.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonEdit` Denetimin, görüntüleme moduna bağlı olarak iki genişliği vardır: kayan mod ve normal mod.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
