---
title: CMFCRibbonEdit Sınıfı
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
ms.openlocfilehash: ab621a05f9b658eee9babb14e257680fa95e0f96
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375172"
---
# <a name="cmfcribbonedit-class"></a>CMFCRibbonEdit Sınıfı

Şerit çubuğunda bulunan bir denetim uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
class CMFCRibbonEdit : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Bir `CMFCRibbonEdit` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonEdit::CanBeStretched](#canbestretched)|`CMFCRibbonEdit` Denetimyüksekliğinin dikey olarak şerit satırının yüksekliğine yükselip artamayacağını gösterir.|
|[CMFCRibbonEdit::CMFCRibbonEdit](#cmfcribbonedit)|Bir `CMFCRibbonEdit` nesne inşa eder.|
|[CMFCRibbonEdit::CopyFrom](#copyfrom)|Belirtilen `CMFCRibbonEdit` nesnenin durumunu geçerli `CMFCRibbonEdit` nesneye kopyalar.|
|[CMFCRibbonEdit::CreateEdit](#createedit)|`CMFCRibbonEdit` Nesne için yeni bir metin kutusu oluşturur.|
|[CMFCRibbonEdit::DestroyCtrl](#destroyctrl)|Nesneyi `CMFCRibbonEdit` yok eder.|
|[CMFCRibbonEdit::DropDownList](#dropdownlist)|Liste kutusunu düşürür.|
|[CMFCRibbonEdit::EnableSpinButtons](#enablespinbuttons)|Metin kutusu için döndürme düğmesinin aralığını etkinleştirer ve ayarlar.|
|[CMFCRibbonEdit::GetCompactSize](#getcompactsize)|`CFMCRibbonEdit` Nesnenin kompakt boyutunu alır.|
|[CMFCRibbonEdit::GetEditText](#getedittext)|Metin kutusundaki metni alır.|
|[CMFCRibbonEdit::GetIntermediateSize](#getintermediatesize)|`CMFCRibbonEdit` Nesnenin ara boyutunu alır.|
|[CMFCRibbonEdit::GetTextAlign](#gettextalign)|Metin kutusundaki metnin hizalanmasını alır.|
|[CMFCRibbonEdit::GetWidth](#getwidth)|`CMFCRibbonEdit` Denetimin genişliğini, piksel olarak alır.|
|[CMFCRibbonEdit::HasCompactMode](#hascompactmode)|Denetimin ekran boyutunun `CMFCRibbonEdit` kompakt olup olmadığını gösterir.|
|[CMFCRibbonEdit::HasFocus](#hasfocus)|Denetimin `CMFCRIbbonEdit` odak noktası olup olmadığını gösterir.|
|[CMFCRibbonEdit::HasLargeMode](#haslargemode)|Denetimin görüntü boyutunun `CMFCRibbonEdit` büyük olup olmadığını gösterir.|
|[CMFCRibbonEdit::HasSpinButtons](#hasspinbuttons)|Metin kutusunun döndürme düğmesi olup olmadığını gösterir.|
|[CMFCRibbonEdit::Vurgulanmış](#ishighlighted)|Denetimin `CMFCRibbonEdit` vurgulanıp vurgulanmadığını gösterir.|
|[CMFCRibbonEdit::OnAfterChangeRect](#onafterchangerect)|Denetim için ekran dikdörtgeninin boyutları değiştiğinde `CMFCRibbonEdit` çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnDraw](#ondraw)|Kontrolü çekmek için çerçeve `CMFCRibbonEdit` tarafından çağrıldı.|
|[CMFCRibbonEdit::OnDrawLabelAndImage](#ondrawlabelandimage)|`CMFCRibbonEdit` Denetim için etiket ve görüntü çizmek için çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnDrawOnList](#ondrawonlist)|Bir komut listesi kutusunda `CMFCRibbonEdit` denetim çizmek için çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnEnable](#onenable)|`CMFCRibbonEdit` Denetimi etkinleştirmek veya devre dışı etmek için çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnHighlight](#onhighlight)|İşaretçi `CMFCRibbonEdit` denetimin sınırlarını girdiğinde veya ayrıldığında çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnKey](#onkey)|Kullanıcı bir tuş ucuna bastığında ve `CMFCRibbonEdit` denetim odaknoktası olduğunda çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnLButtonDown](#onlbuttondown)|Kullanıcı `CMFCRibbonEdit` denetimde sol fare düğmesine bastığında denetimi güncelleştirmek için çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnLButtonUp](#onlbuttonup)|Kullanıcı sol fare düğmesini serbest bıraktığında çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnRTLChanged](#onrtlchanged)|Düzen yön değiştirdiğinde `CMFCRibbonEdit` denetimi güncelleştirmek için çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::OnShow](#onshow)|Denetimi göstermek veya gizlemek için `CMFCRibbonEdit` çerçeve tarafından çağrılır.|
|[CMFCRibbonEdit::Yeniden çiz](#redraw)|Denetimin ekranını `CMFCRibbonEdit` güncelleştirir.|
|[CMFCRibbonEdit::SetACCData](#setaccdata)|`CMFCRibbonEdit` Nesneiçin erişilebilirlik verilerini ayarlar.|
|[CMFCRibbonEdit::SetEditText](#setedittext)|Metin kutusundaki metni ayarlar.|
|[CMFCRibbonEdit::SetTextAlign](#settextalign)|Metin kutusunun metin hizasını ayarlar.|
|[CMFCRibbonEdit::Set Width](#setwidth)|`CMFCRibbonEdit` Denetim için metin kutusunun genişliğini ayarlar.|

## <a name="remarks"></a>Açıklamalar

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCRibbonEdit` nesnenin nasıl oluşturulabildiğini, döndürme denetiminin yanındaki döndürme düğmelerini nasıl göstereceğimi ve denetim metnini nasıl ayarlayamacını gösterir. Bu kod parçacığı MS Office [2007 Demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#7](../../mfc/reference/codesnippet/cpp/cmfcribbonedit-class_1.cpp)]

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxRibbonEdit.h

## <a name="cmfcribboneditcanbestretched"></a><a name="canbestretched"></a>CMFCRibbonEdit::CanBeStretched

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin yüksekliğinin dikey olarak bir şerit satırının yüksekliğine yükselip artamayacağını gösterir.

```cpp
virtual BOOL CanBeStretched();
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditcmfcribbonedit"></a><a name="cmfcribbonedit"></a>CMFCRibbonEdit::CMFCRibbonEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi oluşturuyor.

```cpp
CMFCRibbonEdit(
    UINT nID,
    int nWidth,
    LPCTSTR lpszLabel = NULL,
    int nImage = -1);

CMFCRibbonEdit();
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] `CMFCRibbonEdit` Denetim için komut kimliği.

*Nwidth*<br/>
[içinde] `CMFCRibbonEdit` Denetim için metin kutusunun piksel genişliği.

*lpszEtiket*<br/>
[içinde] `CMFCRibbonEdit` Kontrol için etiket.

*nImage*<br/>
[içinde] Denetim için kullanılacak küçük görüntü `CMFCRibbonEdit` dizini. Küçük görüntülerin toplanması üst şerit kategorisi tarafından korunur.

### <a name="remarks"></a>Açıklamalar

Denetim `CMFCRibbonEdit` büyük bir görüntü kullanmaz.

## <a name="cmfcribboneditcopyfrom"></a><a name="copyfrom"></a>CMFCRibbonEdit::CopyFrom

Belirtilen [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin durumunu geçerli [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesine kopyalar.

```cpp
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kaynak `CMFCRibbonEdit` nesne.

### <a name="remarks"></a>Açıklamalar

*Src* parametresi türünde `CMFCRibbonEdit`olmalıdır.

## <a name="cmfcribboneditcreateedit"></a><a name="createedit"></a>CMFCRibbonEdit::CreateEdit

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesi için yeni bir metin kutusu oluşturur.

```cpp
virtual CMFCRibbonRichEditCtrl* CreateEdit(
    CWnd* pWndParent,
    DWORD dwEditStyle);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] `CMFCRibbonEdit` Nesnenin ana penceresine bir işaretçi.

*dwEditStyle*<br/>
[içinde] Metin kutusunun stilini belirtir. Açıklamalar bölümünde listelenen pencere stillerini Windows SDK'da açıklanan [denetim stilleriyle](/windows/win32/Controls/edit-control-styles) birleştirebilirsiniz.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olduysa yeni metin kutusuna işaretçi; aksi takdirde, NULL.

### <a name="remarks"></a>Açıklamalar

Özel bir metin kutusu oluşturmak için türetilmiş bir sınıfta bu yöntemi geçersiz kılın.

Aşağıdaki [Pencere Stilleri'ni](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir metin kutusuna uygulayabilirsiniz:

- **Ws_chıld**

- **Ws_vısıble**

- **Ws_dısabled**

- **WS_GROUP**

- **WS_TABSTOP**

## <a name="cmfcribboneditdestroyctrl"></a><a name="destroyctrl"></a>CMFCRibbonEdit::DestroyCtrl

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesini yok eder.

```cpp
virtual void DestroyCtrl();
```

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditdropdownlist"></a><a name="dropdownlist"></a>CMFCRibbonEdit::DropDownList

Liste kutusunu düşürür.

```cpp
virtual void DropDownList();
```

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem hiçbir şey yapmaz. Liste kutusunu düşürmek için bu yöntemi geçersiz kılın.

## <a name="cmfcribboneditenablespinbuttons"></a><a name="enablespinbuttons"></a>CMFCRibbonEdit::EnableSpinButtons

Metin kutusu için döndürme düğmesinin aralığını etkinleştirer ve ayarlar.

```cpp
void EnableSpinButtons(
    int nMin,
    int nMax);
```

### <a name="parameters"></a>Parametreler

*nMin*<br/>
[içinde] Döndürme düğmesinin minimum değeri.

*nMax*<br/>
[içinde] Döndürme düğmesinin maksimum değeri.

### <a name="remarks"></a>Açıklamalar

Döndürme düğmeleri yukarı ve aşağı ok görüntüler ve kullanıcıların sabit bir değer kümesi nde hareket etmesini sağlar.

## <a name="cmfcribboneditgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonEdit::GetCompactSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin kompakt boyutunu alır.

```cpp
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Nesne için aygıt bağlamını `CMFCRibbonEdit` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `CMFCRibbonEdit` kompakt boyutu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgetedittext"></a><a name="getedittext"></a>CMFCRibbonEdit::GetEditText

Metin kutusundaki metni alır.

```cpp
CString GetEditText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusundaki metin.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonEdit::GetIntermediateSize

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin ara boyutunu alır.

```cpp
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Nesne için aygıt bağlamını `CMFCRibbonEdit` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Nesnenin `CMFCRibbonEdit` ara boyutu.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditgettextalign"></a><a name="gettextalign"></a>CMFCRibbonEdit::GetTextAlign

Metin kutusundaki metnin hizalanmasını alır.

```cpp
int GetTextAlign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin hizalama numaralandırılmış değer. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

Döndürülen değer aşağıdaki edit denetim stillerinden biridir:

- Sol hizalama için **ES_LEFT**

- Merkez hizalama için **ES_CENTER**

- Doğru hizalama için **ES_RIGHT**

Bu stiller hakkında daha fazla bilgi için Denetim [Stillerini Edit'e](/windows/win32/Controls/edit-control-styles)bakın.

## <a name="cmfcribboneditgetwidth"></a><a name="getwidth"></a>CMFCRibbonEdit::GetWidth

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin piksel olarak genişliğini alır.

```cpp
int GetWidth(BOOL bInFloatyMode = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*bInFloatyMode*<br/>
[içinde] `CMFCRibbonEdit` Denetim kayan moddaysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Denetimin `CMFCRibbonEdit` piksel genişliği.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonedithascompactmode"></a><a name="hascompactmode"></a>CMFCRibbonEdit::HasCompactMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimiiçin ekran boyutunun kompakt olup olmadığını gösterir.

```cpp
virtual BOOL HasCompactMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem her zaman TRUE döndürür. Ekran boyutunun kompakt olup olmadığını belirtmek için bu yöntemi geçersiz kılın.

## <a name="cmfcribbonedithasfocus"></a><a name="hasfocus"></a>CMFCRibbonEdit::HasFocus

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin odak noktası olup olmadığını gösterir.

```cpp
virtual BOOL HasFocus() const;
```

### <a name="return-value"></a>Dönüş Değeri

Doğru kontrol `CMFCRibbonEdit` odak varsa; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbonedithaslargemode"></a><a name="haslargemode"></a>CMFCRibbonEdit::HasLargeMode

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin ekran boyutunun büyük olup olmadığını gösterir.

```cpp
virtual BOOL HasLargeMode() const;
```

### <a name="return-value"></a>Dönüş Değeri

Her zaman FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem her zaman FALSE döndürür. Görüntü boyutunun büyük olup olmadığını belirtmek için bu yöntemi geçersiz kılın.

## <a name="cmfcribbonedithasspinbuttons"></a><a name="hasspinbuttons"></a>CMFCRibbonEdit::HasSpinButtons

Metin kutusunun döndürme düğmesi olup olmadığını gösterir.

```cpp
virtual BOOL HasSpinButtons() const;
```

### <a name="return-value"></a>Dönüş Değeri

Metin kutusunda döndürme düğmesi varsa TRUE; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditishighlighted"></a><a name="ishighlighted"></a>CMFCRibbonEdit::Vurgulanmış

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin vurgulanıp vurgulanmadığını gösterir.

```cpp
virtual BOOL IsHighlighted() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CMFCRibbonEdit` Denetim vurgulanırsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonafterchangerect"></a><a name="onafterchangerect"></a>CMFCRibbonEdit::OnAfterChangeRect

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için ekran dikdörtgeninin boyutları değiştiğinde çerçeve tarafından çağrılır.

```cpp
virtual void OnAfterChangeRect(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Denetim için aygıt bağlamını işaretçi. `CMFCRibbonEdit`

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondraw"></a><a name="ondraw"></a>CMFCRibbonEdit::OnDraw

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetim çizmek için çerçeve tarafından çağrıldı.

```cpp
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Denetim için aygıt bağlamını işaretçi. `CMFCRibbonEdit`

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondrawlabelandimage"></a><a name="ondrawlabelandimage"></a>CMFCRibbonEdit::OnDrawLabelAndImage

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için etiket ve görüntü çizmek için çerçeve tarafından çağrılır.

```cpp
virtual void OnDrawLabelAndImage(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Denetim için aygıt bağlamını işaretçi. `CMFCRibbonEdit`

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonEdit::OnDrawOnList

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini komutlistesi kutusunda çizmek için çerçeve tarafından çağrılır.

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

*Pdc*<br/>
[içinde] Denetim için aygıt bağlamını işaretçi. `CMFCRibbonEdit`

*strText*<br/>
[içinde] Görüntü metni. [ ](../../mfc/reference/cmfcribbonedit-class.md "cmfcribbonedit sınıfı")

*nTextOffset*<br/>
[içinde] Pikselolarak, liste kutusunun sol tarafından ekran metnine kadar uzaklık.

*Rect*<br/>
[içinde] Denetim için ekran dikdörtgeni. `CMFCRibbonEdit`

*bIsSelected*<br/>
[içinde] Bu parametre kullanılmaz.

*bVurgulu*<br/>
[içinde] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

Komutlar listesi kutusu, kullanıcıların hızlı erişim araç çubuğunu özelleştirmelerini sağlamak için şerit denetimlerini görüntüler.

## <a name="cmfcribboneditonenable"></a><a name="onenable"></a>CMFCRibbonEdit::OnEnable

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini etkinleştirmek veya devre dışı etmek için çerçeve tarafından çağrılır.

```cpp
virtual void OnEnable(BOOL bEnable);
```

### <a name="parameters"></a>Parametreler

*bEtkinleştir*<br/>
[içinde] DOĞRU denetimi etkinleştirmek için; Denetimi devre dışı bırakabilmek için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonhighlight"></a><a name="onhighlight"></a>CMFCRibbonEdit::OnHighlight

İşaretçi [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin sınırlarını girdiğinde veya ayrıldığında çerçeve tarafından çağrılır.

```cpp
virtual void OnHighlight(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bVurgu*<br/>
[içinde] İşaretçi `CMFCRibbonEdit` denetimin sınırlarındaysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonkey"></a><a name="onkey"></a>CMFCRibbonEdit::OnKey

Kullanıcı bir tuş ucuna bastığında ve [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi odak noktası olduğunda çerçeve tarafından çağrılır.

```cpp
virtual BOOL OnKey(BOOL bIsMenuKey);
```

### <a name="parameters"></a>Parametreler

*bIsMenuKey*<br/>
[içinde] Anahtar ucu açılır menü yütse DOĞRU; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Olay ele alındıysa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonlbuttondown"></a><a name="onlbuttondown"></a>CMFCRibbonEdit::OnLButtonDown

Kullanıcı denetimde sol fare düğmesine bastığında [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncelleştirmek için çerçeve tarafından çağrılır.

```cpp
virtual void OnLButtonDown(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonlbuttonup"></a><a name="onlbuttonup"></a>CMFCRibbonEdit::OnLButtonUp

Kullanıcı sol fare düğmesini serbest bıraktığında çerçeve tarafından çağrılır.

```cpp
virtual void OnLButtonUp(CPoint point);
```

### <a name="parameters"></a>Parametreler

*Nokta*<br/>
[içinde] Bu parametre kullanılmaz.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonrtlchanged"></a><a name="onrtlchanged"></a>CMFCRibbonEdit::OnRTLChanged

Düzen yön değiştirdiğinde [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini güncelleştirmek için çerçeve tarafından çağrılır.

```cpp
virtual void OnRTLChanged(BOOL bIsRTL);
```

### <a name="parameters"></a>Parametreler

*bIsRTL*<br/>
[içinde] Düzen sağdan sola doğruysa DOĞRU; Düzen soldan sağa ise YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditonshow"></a><a name="onshow"></a>CMFCRibbonEdit::OnShow

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimini göstermek veya gizlemek için çerçeve tarafından çağrılır.

```cpp
virtual void OnShow(BOOL bShow);
```

### <a name="parameters"></a>Parametreler

*bGöster*<br/>
[içinde] DOĞRU kontrol göstermek için; Kontrol gizlemek için YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditredraw"></a><a name="redraw"></a>CMFCRibbonEdit::Yeniden çiz

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetiminin ekranını güncelleştirir.

```cpp
virtual void Redraw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, dolaylı olarak CWnd çağırarak `CMFCRibbonEdit` nesne için ekran dikdörtgeni yeniden çizer::RDW_INVALIDATE, RDW_ERASE ve RDW_UPDATENOW bayrakları ayarlanmış yeniden çizim [penceresi.](/windows/win32/api/winuser/nf-winuser-redrawwindow)

## <a name="cmfcribboneditsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonEdit::SetACCData

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) nesnesinin erişilebilirlik verilerini ayarlar.

```cpp
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Nesne için ana pencereye `CMFCRibbonEdit` işaretçi.

*Veri*<br/>
Nesnenin `CMFCRibbonEdit` erişilebilirlik verileri.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboneditsetedittext"></a><a name="setedittext"></a>CMFCRibbonEdit::SetEditText

Metin kutusundaki metni ayarlar.

```cpp
void SetEditText(CString strText);
```

### <a name="parameters"></a>Parametreler

*strText*<br/>
[içinde] Metin kutusunun metni.

## <a name="cmfcribboneditsettextalign"></a><a name="settextalign"></a>CMFCRibbonEdit::SetTextAlign

Metin kutusunun metin hizasını ayarlar.

```cpp
void SetTextAlign(int nAlign);
```

### <a name="parameters"></a>Parametreler

*nAlign*<br/>
[içinde] Metin hizalama numaralandırılmış değer. Olası değerler için Açıklamalar bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

*nAlign* parametresi aşağıdaki düzenle denetim stillerinden biridir:

- Sol hizalama için ES_LEFT

- Merkez hizalama için ES_CENTER

- Doğru hizalama için ES_RIGHT

Bu stiller hakkında daha fazla bilgi için Denetim [Stillerini Edit'e](/windows/win32/Controls/edit-control-styles)bakın.

## <a name="cmfcribboneditsetwidth"></a><a name="setwidth"></a>CMFCRibbonEdit::Set Width

[CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md) denetimi için metin kutusunun genişliğini ayarlar.

```cpp
void SetWidth(
    int nWidth,
    BOOL bInFloatyMode = FALSE);
```

### <a name="parameters"></a>Parametreler

*Nwidth*<br/>
[içinde] Metin kutusunun piksel genişliği.

*bInFloatyMode*<br/>
True kayan modu için genişlik ayarlamak için; Normal mod için genişliği ayarlamak için FALSE.

### <a name="remarks"></a>Açıklamalar

Denetim, `CMFCRibbonEdit` ekran moduna bağlı olarak iki genişliğe sahiptir: kayan mod ve normal mod.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonButton Sınıfı](../../mfc/reference/cmfcribbonbutton-class.md)<br/>
[CMFCRibbonBar Sınıfı](../../mfc/reference/cmfcribbonbar-class.md)
