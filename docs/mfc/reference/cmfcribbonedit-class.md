---
description: 'Daha fazla bilgi edinin: CMFCRibbonEdit sınıfı'
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
ms.openlocfilehash: 83920c9779af10861e32ce964e91af767a3d9e96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193115"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit sınıfı

Şerit çubuğunda bulunan bir düzenleme denetimi uygular.

## <a name="syntax"></a>Syntax

```cpp
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
|[CMFCRibbonEdit:: Canbeesnetilen](#canbestretched)|`CMFCRibbonEdit`Denetimin yüksekliğinin bir şerit satırının yüksekliğine dikey olarak artırıp artamayacağını gösterir.|
|[CMFCRibbonEdit:: CMFCRibbonEdit](#cmfcribbonedit)|Bir `CMFCRibbonEdit` nesnesi oluşturur.|
|[CMFCRibbonEdit:: CopyFrom](#copyfrom)|Belirtilen `CMFCRibbonEdit` nesnenin durumunu geçerli `CMFCRibbonEdit` nesneye kopyalar.|
|[CMFCRibbonEdit:: CreateEdit](#createedit)|Nesnesi için yeni bir metin kutusu oluşturur `CMFCRibbonEdit` .|
|[CMFCRibbonEdit::D estroyCtrl](#destroyctrl)|Nesneyi yok eder `CMFCRibbonEdit` .|
|[CMFCRibbonEdit::D ropDownList](#dropdownlist)|Liste kutusunu kapatır.|
|[CMFCRibbonEdit:: EnableSpinButtons](#enablespinbuttons)|Metin kutusu için döndürme düğmesinin aralığını belirler ve ayarlar.|
|[CMFCRibbonEdit:: GetCompactSize](#getcompactsize)|Nesnenin sıkıştırılmış boyutunu alır `CFMCRibbonEdit` .|
|[CMFCRibbonEdit:: GetEditText](#getedittext)|Metin kutusundaki metni alır.|
|[CMFCRibbonEdit:: GetIntermediateSize](#getintermediatesize)|Nesnenin ara boyutunu alır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: GetTextAlign](#gettextalign)|Metin kutusuna metnin hizalamasını alır.|
|[CMFCRibbonEdit:: GetWidth](#getwidth)|Denetimin piksel cinsinden genişliğini alır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: HasCompactMode](#hascompactmode)|Denetim için görüntü boyutunun `CMFCRibbonEdit` sıkıştırılamayacağını belirtir.|
|[CMFCRibbonEdit:: HasFocus](#hasfocus)|`CMFCRIbbonEdit`Denetimin odağa sahip olup olmadığını gösterir.|
|[CMFCRibbonEdit:: HasLargeMode](#haslargemode)|Denetimin görüntüleme boyutunun büyük olup olmadığını gösterir `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: HasSpinButtons](#hasspinbuttons)|Metin kutusunun bir döndürme düğmesine sahip olup olmadığını gösterir.|
|[CMFCRibbonEdit:: ısvurgulu](#ishighlighted)|`CMFCRibbonEdit`Denetimin vurgulanıp vurgulanmadığını gösterir.|
|[CMFCRibbonEdit:: OnAfterChangeRect](#onafterchangerect)|Denetim için görüntü dikdörtgeninin boyutları değiştiğinde Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: OnDraw](#ondraw)|Denetimi çizmek için Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: Ondrawlabelandımage](#ondrawlabelandimage)|Denetim için etiket ve resim çizmek üzere Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: OnDrawOnList](#ondrawonlist)|`CMFCRibbonEdit`Bir komut listesi kutusunda denetimi çizmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnEnable](#onenable)|Denetimi etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: OnHighlight](#onhighlight)|İşaretçi denetimin sınırları içine girdiğinde veya ayrıldığında Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: OnKey](#onkey)|Kullanıcı bir KeyTip tuşuna bastığında ve denetim odağa sahip olduğunda Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: Onlbuttonazaltma](#onlbuttondown)|`CMFCRibbonEdit`Kullanıcı denetimdeki sol fare düğmesine bastığında denetimi güncelleştirmek için Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnLButtonUp](#onlbuttonup)|Kullanıcı sol fare düğmesini bıraktığında Framework tarafından çağırılır.|
|[CMFCRibbonEdit:: OnRTLChanged](#onrtlchanged)|Düzen yön değiştirdiğinde denetimi güncelleştirmek için Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: OnShow](#onshow)|Denetimi göstermek veya gizlemek için Framework tarafından çağırılır `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: yeniden Çiz](#redraw)|Denetimin görüntüsünü güncelleştirir `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: SetACCData](#setaccdata)|Nesne için erişilebilirlik verilerini ayarlar `CMFCRibbonEdit` .|
|[CMFCRibbonEdit:: SetEditText](#setedittext)|Metin kutusundaki metni ayarlar.|
|[CMFCRibbonEdit:: SetTextAlign](#settextalign)|Metin kutusunun metin hizalamasını ayarlar.|
|[CMFCRibbonEdit:: SetWidth](#setwidth)|Denetimin metin kutusunun genişliğini ayarlar `CMFCRibbonEdit` .|

## <a name="remarks"></a>Açıklamalar

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCRibbonEdit` nesne oluşturmayı, düzenleme denetiminin yanındaki döndürme düğmelerini göstermeyi ve düzenleme denetiminin metnini ayarlamayı gösterir. Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonEdit. h

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a> CMFCRibbonEdit:: Canbeesnetilen

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin yüksekliğinin bir şerit satırının yüksekliğine dikey olarak artırıp artamayacağını gösterir.

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a> CMFCRibbonEdit:: CMFCRibbonEdit

Bir [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi oluşturur.

```cpp
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Denetim için komut KIMLIĞI `CMFCRibbonEdit` .

*nWidth*<br/>
'ndaki Denetimin metin kutusunun piksel cinsinden genişliği `CMFCRibbonEdit` .

*lpszLabel*<br/>
'ndaki `CMFCRibbonEdit` Denetimin etiketi.

*Ngörüntü*<br/>
'ndaki Denetim için kullanılacak küçük görüntünün dizini `CMFCRibbonEdit` . Küçük görüntülerin koleksiyonu üst şerit kategorisi tarafından korunur.

### <a name="remarks"></a>Açıklamalar

`CMFCRibbonEdit`Denetim büyük bir görüntü kullanmaz.

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonEdit:: CopyFrom

Belirtilen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin durumunu geçerli [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesine kopyalar.

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Kaynak `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

*Src* parametresinin türünde olması gerekir `CMFCRibbonEdit` .

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a> CMFCRibbonEdit:: CreateEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi için yeni bir metin kutusu oluşturur.

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Nesnenin üst penceresine yönelik bir işaretçi `CMFCRibbonEdit` .

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

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a> CMFCRibbonEdit::D estroyCtrl

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesini yok eder.

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a> CMFCRibbonEdit::D ropDownList

Liste kutusunu kapatır.

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Liste kutusunu aşağı eklemek için bu yöntemi geçersiz kılın.

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a> CMFCRibbonEdit:: EnableSpinButtons

Metin kutusu için döndürme düğmesinin aralığını belirler ve ayarlar.

```cpp
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

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a> CMFCRibbonEdit:: GetCompactSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin sıkıştırılmış boyutunu alır.

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Nesne için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

### <a name="return-value"></a>Dönüş Değeri

Nesnenin sıkıştırılmış boyutu `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a> CMFCRibbonEdit:: GetEditText

Metin kutusundaki metni alır.

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonEdit:: GetIntermediateSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin ara boyutunu alır.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Nesne için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

### <a name="return-value"></a>Dönüş Değeri

Nesnenin ara boyutu `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a> CMFCRibbonEdit:: GetTextAlign

Metin kutusuna metnin hizalamasını alır.

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin hizalaması numaralandırılmış değeri. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer aşağıdaki düzenleme denetimi stillerinden biridir:

- Sol hizalama için **ES_LEFT**

- Orta hizalama için **ES_CENTER**

- Sağ hizalama için **ES_RIGHT**

Bu stiller hakkında daha fazla bilgi için bkz. [Denetim stillerini düzenleme](/windows/win32/Controls/edit-control-styles).

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a> CMFCRibbonEdit:: GetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin piksel cinsinden genişliğini alır.

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*Binfloatyımode*<br/>
'ndaki `CMFCRibbonEdit` Denetim kayan MODDAYSA true, aksi durumda false.

### <a name="return-value"></a>Dönüş Değeri

Denetimin piksel cinsinden genişliği `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a> CMFCRibbonEdit:: HasCompactMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin görüntüleme boyutunun sıkıştırılamayacağını gösterir.

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman TRUE değerini döndürür. Görüntü boyutunun sıkıştıramayacağını belirtmek için bu yöntemi geçersiz kılın.

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a> CMFCRibbonEdit:: HasFocus

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin odağa sahip olup olmadığını gösterir.

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit`Denetim odağa SAHIPSE true; aksi takdırde false.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a> CMFCRibbonEdit:: HasLargeMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için görüntüleme boyutunun büyük olup olmadığını gösterir.

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem her zaman FALSE döndürür. Görüntülenen boyutun büyük olup olmadığını belirtmek için bu yöntemi geçersiz kılın.

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a> CMFCRibbonEdit:: HasSpinButtons

Metin kutusunun bir döndürme düğmesine sahip olup olmadığını gösterir.

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusunda bir döndürme düğmesi varsa doğru; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a> CMFCRibbonEdit:: ısvurgulu

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin vurgulanıp vurgulanmadığını gösterir.

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit`Denetim vurgulanmışsa true; aksi takdırde false.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a> CMFCRibbonEdit:: OnAfterChangeRect

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim değişikliğinin görüntüleme dikdörtgeninin boyutları değiştiğinde Framework tarafından çağırılır.

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Denetim için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a> CMFCRibbonEdit:: OnDraw

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini çizmek için Framework tarafından çağırılır.

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Denetim için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a> CMFCRibbonEdit:: Ondrawlabelandımage

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için etiket ve resim çizmek üzere Framework tarafından çağırılır.

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Denetim için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonEdit:: OnDrawOnList

Bir Komutlar liste kutusuna [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini çizmek için Framework tarafından çağırılır.

```cpp
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
'ndaki Denetim için bir cihaz bağlamı işaretçisi `CMFCRibbonEdit` .

*strText*<br/>
'ndaki Görüntü metni [](../../mfc/reference/cmfcribbonedit-class.md "CMFCRibbonEdit sınıfı") .

*nTextOffset*<br/>
'ndaki Liste kutusunun sol tarafındaki görüntü metnine göre piksel cinsinden uzaklık.

*Rect*<br/>
'ndaki Denetimin görüntüleme dikdörtgeni `CMFCRibbonEdit` .

*bIsSelected*<br/>
'ndaki Bu parametre kullanılmaz.

*Bvurgulu*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Komutlar liste kutusu, kullanıcıların hızlı erişim araç çubuğunu özelleştirmesini sağlamak için şerit denetimleri görüntüler.

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a> CMFCRibbonEdit:: OnEnable

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini etkinleştirmek veya devre dışı bırakmak için Framework tarafından çağırılır.

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEnable*<br/>
'ndaki Denetimi etkinleştirmek için TRUE; Denetimi devre dışı bırakmak için FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a> CMFCRibbonEdit:: OnHighlight

İşaretçi [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin sınırları içine girdiğinde ya da ayrıldığında Framework tarafından çağırılır.

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
'ndaki İşaretçi denetimin sınırları içinde ise TRUE `CMFCRibbonEdit` , aksi durumda false.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a> CMFCRibbonEdit:: OnKey

Kullanıcı bir KeyTip tuşuna bastığında ve [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi odağa sahip olduğunda Framework tarafından çağırılır.

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Parametreler

*Bımenukey*<br/>
'ndaki Keytıp bir açılır menü görüntülüyorsa, doğru. Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Olay işlenirse doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a> CMFCRibbonEdit:: Onlbuttonazaltma

Kullanıcı denetimdeki sol fare düğmesine bastığında [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncellemek için Framework tarafından çağırılır.

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a> CMFCRibbonEdit:: OnLButtonUp

Kullanıcı sol fare düğmesini bıraktığında Framework tarafından çağırılır.

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parametreler

*seçeneğinin*<br/>
'ndaki Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a> CMFCRibbonEdit:: OnRTLChanged

Düzen yön değiştirdiğinde [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncellemek için Framework tarafından çağırılır.

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parametreler

*bIsRTL*<br/>
'ndaki Düzen sağdan sola ise doğru; Düzen soldan sağa ise FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a> CMFCRibbonEdit:: OnShow

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini göstermek veya gizlemek için Framework tarafından çağırılır.

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bShow*<br/>
'ndaki Denetimi göstermek için TRUE; Denetimi gizlemek için FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a> CMFCRibbonEdit:: yeniden Çiz

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin görüntülenmesini güncelleştirir.

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CMFCRibbonEdit` RDW_INVALIDATE, RDW_ERASE ve RDW_UPDATENOW bayrakları kümesiyle [CWnd:: RedrawWindow](/windows/win32/api/winuser/nf-winuser-redrawwindow) dolaylı olarak çağırarak nesnenin görüntüleme dikdörtgenini yeniden çizer.

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonEdit:: SetACCData

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi için erişilebilirlik verilerini ayarlar.

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Nesnenin üst penceresine yönelik işaretçi `CMFCRibbonEdit` .

*data*<br/>
Nesne için erişilebilirlik verileri `CMFCRibbonEdit` .

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a> CMFCRibbonEdit:: SetEditText

Metin kutusundaki metni ayarlar.

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
'ndaki Metin kutusu metni.

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a> CMFCRibbonEdit:: SetTextAlign

Metin kutusunun metin hizalamasını ayarlar.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
'ndaki Metin hizalaması numaralandırılmış değeri. Olası değerler için açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

*NAlign* parametresi aşağıdaki düzenleme denetimi stillerinden biridir:

- Sol hizalama için ES_LEFT

- Orta hizalama için ES_CENTER

- Sağ hizalama için ES_RIGHT

Bu stiller hakkında daha fazla bilgi için bkz. [Denetim stillerini düzenleme](/windows/win32/Controls/edit-control-styles).

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a> CMFCRibbonEdit:: SetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için metin kutusunun genişliğini ayarlar.

```cpp
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

`CMFCRibbonEdit`Denetimin, görüntüleme moduna bağlı olarak iki genişliği vardır: kayan mod ve normal mod.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
