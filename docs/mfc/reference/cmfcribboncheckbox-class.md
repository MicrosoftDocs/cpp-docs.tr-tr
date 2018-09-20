---
title: CMFCRibbonCheckBox sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0b10004551a594d6f969ffaf7893cd2e7efe2d76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396564"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox sınıfı

`CMFCRibbonCheckBox` Sınıfı bir Şerit paneli, hızlı erişim araç çubuğu veya açılır menü ekleyebileceğiniz bir onay kutusu uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|(Geçersiz kılmaları [CMFCRibbonButton::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|(Geçersiz kılmaları [CMFCRibbonButton::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|(Geçersiz kılmaları [CMFCRibbonButton::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz kılmaları `CMFCRibbonButton::IsDrawTooltipImage`.)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|(Geçersiz kılmaları [CMFCRibbonButton::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|(Geçersiz kılmaları [CMFCRibbonBaseElement::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonCheckBox::OnDrawOnList](#ondrawonlist)|(Geçersiz kılmaları `CMFCRibbonButton::OnDrawOnList`.)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|(Geçersiz kılmaları [CMFCRibbonButton::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>Açıklamalar

Kullanılacak bir `CMFCRibbonCheckBox` uygulamanızda kodunuza aşağıdaki oluşturucuyu ekleyin:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```
Burada *nID* onay kutusunu komut kimliği ve *lpszText* onay kutusunun metin etiketi.

Bir Şerit paneline bir onay kutusunu kullanarak ekleyebilirsiniz [CMFCRibbonPanel::Add](../../mfc/reference/cmfcribbonpanel-class.md#add).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxribboncheckbox.h

##  <a name="cmfcribboncheckbox"></a>  CMFCRibbonCheckBox::CMFCRibbonCheckBox

Bir Şerit onay kutusunu nesnesinin Oluşturucusu

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*nID*<br/>
[in] Komut kimliğini belirtir.

*lpszText*<br/>
[in] Metin etiketini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Bir Şerit onay kutusunu nesnesi oluşturur.

### <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesne oluşturmak gösterilmiştir `CMFCRibbonCheckBox` sınıfı.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

##  <a name="getcompactsize"></a>  CMFCRibbonCheckBox::GetCompactSize

Geçersiz kılındığında, onay kutusunu compact boyutunu alır.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Onay kutusuyla ilişkili CDC işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CSize` onay kutusunu compact boyutunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kılınmazsa, onay kutusunu Ara boyutu döndürür.

##  <a name="getintermediatesize"></a>  CMFCRibbonCheckBox::GetIntermediateSize

Onay kutusunu Ara boyutunu alır.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bu onay kutusu ile ilişkili CDC işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

A `CSize` onay kutusunu Ara boyutu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kılınmazsa, Ara boyutu olarak varsayılan onay kutusunun boyutunu hesaplar ( `AFX_CHECK_BOX_DEFAULT_SIZE`) artı metin boyutu ve kenar boşlukları.

##  <a name="getregularsize"></a>  CMFCRibbonCheckBox::GetRegularSize

Onay kutusunu normal boyutunu alır.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bu onay kutusu ile ilişkili CDC nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Döndürür bir `CSize` onay kutusunu normal boyutunu içeren nesne.

### <a name="remarks"></a>Açıklamalar

Kılınmazsa, onay kutusunu Ara boyutu döndürür.

##  <a name="isdrawtooltipimage"></a>  CMFCRibbonCheckBox::IsDrawTooltipImage

Bir araç ipucu görüntüsü onay kutusuyla ilişkili olup olmadığını belirtir.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusu ile ilişkili bir araç ipucu görüntüsü ise TRUE ya da aksi takdirde FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>  CMFCRibbonCheckBox::OnDraw

Belirtilen bir cihaz bağlamı kullanma onay kutusunu çizmek için framework tarafından çağırılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Onay kutusu Çiz edileceği CDC işaretçisi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawmenuimage"></a>  CMFCRibbonCheckBox::OnDrawMenuImage

Onay kutusu için bir menü görüntüsü çizilmesi gerektiğinde framework tarafından çağırılır.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

[in] *CDC** bu CDC işaretçisine onay kutusuyla ilişkili.

*CRect*<br/>
[in] A `CRect` nesne, menü görüntüsü çizmek dikdörtgen belirtme.

### <a name="return-value"></a>Dönüş Değeri

Görüntü çizilmiş TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Kılınmazsa, false değerini döndürür.

##  <a name="ondrawonlist"></a>  CMFCRibbonCheckBox::OnDrawOnList

Onay kutusunu komutlar liste kutusunda çizilmesi gerektiğinde framework tarafından çağırılır.

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
[in] Onay kutusu Çiz cihaz bağlamı işaretçisi.

*strText*<br/>
[in] Görünen metin.

*nTextOffset*<br/>
[in] Görüntülenecek metni liste kutusuna sol tarafındaki piksel cinsinden uzaklığı.

*Rect*<br/>
[in] Onay kutusu için görünen dikdörtgen.

*bIsSelected*<br/>
[in] Onay kutusunun seçili ya da aksi takdirde FALSE ise TRUE.

*bHighlighted*<br/>
[in] Onay kutusunu vurgulanan ya da aksi takdirde FALSE ise TRUE.

### <a name="remarks"></a>Açıklamalar

##  <a name="setaccdata"></a>  CMFCRibbonCheckBox::SetACCData

Onay kutusu için erişilebilirlik verilerini ayarlar.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Onay kutusunun üst pencere.

*Veri*<br/>
Onay kutusu için erişilebilirlik veriler.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem, onay kutusu için erişilebilirlik veri kümeleri ve her zaman TRUE değerini döndürür. Erişilebilirlik veri kümesi ve başarı veya başarısızlık durumu gösteren bir değer döndürmek için bu yöntemi yok sayın.

## <a name="see-also"></a>Ayrıca Bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
