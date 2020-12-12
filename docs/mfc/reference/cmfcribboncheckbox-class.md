---
description: 'Daha fazla bilgi edinin: CMFCRibbonCheckBox sınıfı'
title: CMFCRibbonCheckBox sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::CMFCRibbonCheckBox
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetCompactSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetIntermediateSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::GetRegularSize
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::IsDrawTooltipImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDraw
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawMenuImage
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::OnDrawOnList
- AFXRIBBONCHECKBOX/CMFCRibbonCheckBox::SetACCData
helpviewer_keywords:
- CMFCRibbonCheckBox [MFC], CMFCRibbonCheckBox
- CMFCRibbonCheckBox [MFC], GetCompactSize
- CMFCRibbonCheckBox [MFC], GetIntermediateSize
- CMFCRibbonCheckBox [MFC], GetRegularSize
- CMFCRibbonCheckBox [MFC], IsDrawTooltipImage
- CMFCRibbonCheckBox [MFC], OnDraw
- CMFCRibbonCheckBox [MFC], OnDrawMenuImage
- CMFCRibbonCheckBox [MFC], OnDrawOnList
- CMFCRibbonCheckBox [MFC], SetACCData
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
ms.openlocfilehash: 889d9e8935bb26a2a95d28697074dba973e04c21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293748"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox sınıfı

`CMFCRibbonCheckBox`Sınıfı, şerit paneline, hızlı erişim araç çubuğuna veya açılan menüye ekleyebileceğiniz bir onay kutusu uygular.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox:: Cmfcribbononay kutusu](#cmfcribboncheckbox)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox:: GetCompactSize](#getcompactsize)|( [CMFCRibbonButton:: GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).) öğesini geçersiz kılar|
|[CMFCRibbonCheckBox:: GetIntermediateSize](#getintermediatesize)|( [CMFCRibbonButton:: GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).) öğesini geçersiz kılar|
|[CMFCRibbonCheckBox:: GetRegularSize](#getregularsize)|( [CMFCRibbonButton:: GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).) öğesini geçersiz kılar|
|[CMFCRibbonCheckBox:: IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz kılmalar `CMFCRibbonButton::IsDrawTooltipImage` .)|
|[CMFCRibbonCheckBox:: OnDraw](#ondraw)|( [CMFCRibbonButton:: OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw)geçersiz kılar.)|
|[CMFCRibbonCheckBox:: OnDrawMenuImage](#ondrawmenuimage)|( [CMFCRibbonBaseElement:: OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage)geçersiz kılar.)|
|[CMFCRibbonCheckBox:: OnDrawOnList](#ondrawonlist)|(Geçersiz kılmalar `CMFCRibbonButton::OnDrawOnList` .)|
|[CMFCRibbonCheckBox:: SetACCData](#setaccdata)|( [CMFCRibbonButton:: SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata)geçersiz kılar.)|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda kullanmak için `CMFCRibbonCheckBox` , kodunuza aşağıdaki oluşturucuyu ekleyin:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

Burada *Nid* onay kutusu komut kimliği ve *lpszText* onay kutusunun metin etikettir.

Bir şerit paneline [CMFCRibbonPanel:: Add](../../mfc/reference/cmfcribbonpanel-class.md#add)' i kullanarak bir onay kutusu ekleyebilirsiniz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[Cmfcribbondüğmesi](../../mfc/reference/cmfcribbonbutton-class.md)

[Cmfcribbononay kutusu](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncheckbox. h

## <a name="cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a> CMFCRibbonCheckBox:: Cmfcribbononay kutusu

Şerit onay kutusu nesnesinin Oluşturucusu

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*NID*<br/>
'ndaki Komut KIMLIĞINI belirtir.

*lpszText*<br/>
'ndaki Metin etiketini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Şerit onay kutusu nesnesi oluşturur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfının bir nesnesinin nasıl oluşturulduğunu gösterir `CMFCRibbonCheckBox` .

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

## <a name="cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a> CMFCRibbonCheckBox:: GetCompactSize

Geçersiz kılındığında, onay kutusunun sıkıştırılmış boyutunu alır.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Onay kutusuyla ilişkilendirilen CDC işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

`CSize`Onay kutusunun sıkıştırılmış boyutunu içeren bir nesne döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmamışsa, onay kutusunun ara boyutunu döndürür.

## <a name="cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a> CMFCRibbonCheckBox:: GetIntermediateSize

Onay kutusunun ara boyutunu alır.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Bu onay kutusuyla ilişkilendirilen CDC öğesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`CSize`Onay kutusunun ara boyutunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmamışsa, ara boyutunu varsayılan onay kutusu boyutu ( `AFX_CHECK_BOX_DEFAULT_SIZE` ) ve metin boyutu artı kenar boşlukları olarak hesaplar.

## <a name="cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonCheckBox:: GetRegularSize

Onay kutusunun normal boyutunu alır.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Bu onay kutusuyla ilişkili CDC nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`CSize`Onay kutusunun normal boyutunu içeren bir nesne döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmamışsa, onay kutusunun ara boyutunu döndürür.

## <a name="cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a> CMFCRibbonCheckBox:: IsDrawTooltipImage

Onay kutusuyla ilişkili bir araç ipucu görüntüsü olup olmadığını gösterir.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusuyla ilişkili bir araç ipucu görüntüsü varsa TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxondraw"></a><a name="ondraw"></a> CMFCRibbonCheckBox:: OnDraw

Belirtilen cihaz bağlamı kullanılarak onay kutusunu çizmek için Framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Onay kutusunun çizildiği CDC 'ye yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a> CMFCRibbonCheckBox:: OnDrawMenuImage

Onay kutusu için bir menü görüntüsü çizmek üzere Framework tarafından çağırılır.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

'ndaki *CDC&#42;*<br/>
Onay kutusuyla ilişkilendirilen CDC işaretçisi.

*CRect*<br/>
'ndaki `CRect` Menü görüntüsünün çizileceği dikdörtgeni belirten bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Resim çizildiyse TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmamışsa, FALSE döndürür.

## <a name="cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonCheckBox:: OnDrawOnList

Bir komut listesi kutusunda onay kutusunu çizmek için Framework tarafından çağırılır.

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
'ndaki Onay kutusunun çizildiği cihaz bağlamına yönelik işaretçi.

*strText*<br/>
'ndaki Görüntü metni.

*nTextOffset*<br/>
'ndaki Liste kutusunun sol tarafındaki görüntü metnine göre piksel cinsinden uzaklık.

*Rect*<br/>
'ndaki Onay kutusu için dikdörtgen görüntülenir.

*bIsSelected*<br/>
'ndaki Onay kutusu seçiliyse TRUE, değilse FALSE.

*Bvurgulu*<br/>
'ndaki Onay kutusu vurgulanmışsa TRUE, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a> CMFCRibbonCheckBox:: SetACCData

Onay kutusu için erişilebilirlik verilerini ayarlar.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Onay kutusunun ana penceresi.

*data*<br/>
Onay kutusu için erişilebilirlik verileri.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, bu yöntem onay kutusu için erişilebilirlik verilerini ayarlar ve her zaman TRUE döndürür. Erişilebilirlik verilerini ayarlamak ve başarılı veya başarısız olduğunu belirten bir değer döndürmek için bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
