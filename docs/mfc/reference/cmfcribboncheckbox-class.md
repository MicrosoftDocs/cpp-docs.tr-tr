---
title: CMFCRibbonCheckBox Sınıfı
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
ms.openlocfilehash: 089c8056afebef31ff98a435bf145566ae64fe1e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375260"
---
# <a name="cmfcribboncheckbox-class"></a>CMFCRibbonCheckBox Sınıfı

Sınıf, `CMFCRibbonCheckBox` şerit paneline, Hızlı Erişim Araç Çubuğu'na veya açılır menüye ekleyebileceğiniz bir onay kutusu uygular.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonCheckBox : public CMFCRibbonButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](#cmfcribboncheckbox)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCRibbonCheckBox::GetCompactSize](#getcompactsize)|[(CMFCRibbonButton geçersiz kılar::GetCompactSize](../../mfc/reference/cmfcribbonbutton-class.md#getcompactsize).)|
|[CMFCRibbonCheckBox::GetIntermediateSize](#getintermediatesize)|[(CMFCRibbonButton geçersiz kılar::GetIntermediateSize](../../mfc/reference/cmfcribbonbutton-class.md#getintermediatesize).)|
|[CMFCRibbonCheckBox::GetRegularSize](#getregularsize)|[(CMFCRibbonButton geçersiz kılar::GetRegularSize](../../mfc/reference/cmfcribbonbutton-class.md#getregularsize).)|
|[CMFCRibbonCheckBox::IsDrawTooltipImage](#isdrawtooltipimage)|(Geçersiz `CMFCRibbonButton::IsDrawTooltipImage`kılar .)|
|[CMFCRibbonCheckBox::OnDraw](#ondraw)|[(CMFCRibbonButton geçersiz kılar::OnDraw](../../mfc/reference/cmfcribbonbutton-class.md#ondraw).)|
|[CMFCRibbonCheckBox::OnDrawMenuImage](#ondrawmenuimage)|[(CMFCRibbonBaseElement geçersiz kılar::OnDrawMenuImage](../../mfc/reference/cmfcribbonbaseelement-class.md#ondrawmenuimage).)|
|[CMFCRibbonCheckBox::OnDrawonList](#ondrawonlist)|(Geçersiz `CMFCRibbonButton::OnDrawOnList`kılar .)|
|[CMFCRibbonCheckBox::SetACCData](#setaccdata)|[(CMFCRibbonButton geçersiz kılar::SetACCData](../../mfc/reference/cmfcribbonbutton-class.md#setaccdata).)|

## <a name="remarks"></a>Açıklamalar

Uygulamanızda `CMFCRibbonCheckBox` bir a kullanmak için, kodunuza aşağıdaki oluşturucuekleyin:

```
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)
```

*nID* onay kutusu komut kimliği ve *lpszText* onay kutusunun metin etiketidir.

CMFCRibbonPanel kullanarak şerit paneline onay kutusu [ekleyebilirsiniz::Ekle.](../../mfc/reference/cmfcribbonpanel-class.md#add)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)

[CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribboncheckbox.h

## <a name="cmfcribboncheckboxcmfcribboncheckbox"></a><a name="cmfcribboncheckbox"></a>CMFCRibbonCheckBox::CMFCRibbonCheckBox

Şerit onay kutusu nesnesinin oluşturucusu

```
CMFCRibbonCheckBox(
    UINT nID,
    LPCTSTR lpszText);
```

### <a name="parameters"></a>Parametreler

*Nıd*<br/>
[içinde] Komut kimliğini belirtir.

*lpszMetin*<br/>
[içinde] Metin etiketini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Şerit onay kutusu nesnesi oluşturuyor.

### <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfın bir nesnesinin `CMFCRibbonCheckBox` nasıl inşa edilebildiğini gösterir.

[!code-cpp[NVC_MFC_RibbonApp#17](../../mfc/reference/codesnippet/cpp/cmfcribboncheckbox-class_1.cpp)]

## <a name="cmfcribboncheckboxgetcompactsize"></a><a name="getcompactsize"></a>CMFCRibbonCheckBox::GetCompactSize

Geçersiz kılındığında, onay kutusunun kompakt boyutunu alır.

```
virtual CSize GetCompactSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Onay kutusuyla ilişkili CDC işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Onay `CSize` kutusunun kompakt boyutunu içeren bir nesne döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmış sayılmazsa, onay kutusunun ara boyutunu döndürür.

## <a name="cmfcribboncheckboxgetintermediatesize"></a><a name="getintermediatesize"></a>CMFCRibbonCheckBox::GetIntermediateSize

Onay kutusunun ara boyutunu alır.

```
virtual CSize GetIntermediateSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Bu onay kutusuyla ilişkili CDC işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Onay `CSize` kutusunun ara boyutunu içeren bir nesne.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmış değilse, varsayılan onay kutusu boyutu ( `AFX_CHECK_BOX_DEFAULT_SIZE`) artı metin boyutu ve kenar boşlukları olarak ara boyutu hesaplar.

## <a name="cmfcribboncheckboxgetregularsize"></a><a name="getregularsize"></a>CMFCRibbonCheckBox::GetRegularSize

Onay kutusunun normal boyutunu alır.

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Bu onay kutusuyla ilişkili CDC nesnesine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Onay `CSize` kutusunun normal boyutunu içeren bir nesne döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmış sayılmazsa, onay kutusunun ara boyutunu döndürür.

## <a name="cmfcribboncheckboxisdrawtooltipimage"></a><a name="isdrawtooltipimage"></a>CMFCRibbonCheckBox::IsDrawTooltipImage

Onay kutusuyla ilişkili bir araç ipucu görüntüsü olup olmadığını gösterir.

```
virtual BOOL IsDrawTooltipImage() const;
```

### <a name="return-value"></a>Dönüş Değeri

Onay kutusuyla ilişkili bir araç ipucu görüntüsü varsa TRUE'yu döndürür veya değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxondraw"></a><a name="ondraw"></a>CMFCRibbonCheckBox::OnDraw

Belirli bir aygıt bağlamı kullanarak onay kutusunu çizmek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Onay kutusunu çizmek için CDC işaretçisi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxondrawmenuimage"></a><a name="ondrawmenuimage"></a>CMFCRibbonCheckBox::OnDrawMenuImage

Onay kutusu için bir menü görüntüsü çizmek için çerçeve tarafından çağrılır.

```
virtual BOOL OnDrawMenuImage(CDC*, CRect);
```

### <a name="parameters"></a>Parametreler

[içinde] *CDC&#42;*<br/>
Onay kutusuyla ilişkili CDC işaretçisi.

*Crect*<br/>
[içinde] Menü `CRect` görüntüsünü çizecek dikdörtgeni belirten bir nesne.

### <a name="return-value"></a>Dönüş Değeri

Görüntü çizilmişse TRUE veya çizilmezse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Geçersiz kılınmış değilse, FALSE döndürür.

## <a name="cmfcribboncheckboxondrawonlist"></a><a name="ondrawonlist"></a>CMFCRibbonCheckBox::OnDrawonList

Bir komutlistesi kutusunda onay kutusunu çizmek için çerçeve tarafından çağrılır.

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

*Pdc*<br/>
[içinde] Onay kutusunu çizmek için aygıt bağlamını işaretleyin.

*strText*<br/>
[içinde] Görüntü metni.

*nTextOffset*<br/>
[içinde] Piksel olarak, liste kutusunun sol tarafından ekran metnine kadar olan uzaklık.

*Rect*<br/>
[içinde] Onay kutusunun ekran dikdörtgeni.

*bIsSelected*<br/>
[içinde] Onay kutusu seçilirse DOĞRU, yoksa FALSE.

*bVurgulu*<br/>
[içinde] Onay kutusu vurgulanırsa DOĞRU, değilse FALSE.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribboncheckboxsetaccdata"></a><a name="setaccdata"></a>CMFCRibbonCheckBox::SetACCData

Onay kutusu için erişilebilirlik verilerini ayarlar.

```
virtual BOOL SetACCData(
    CWnd* pParent,
    CAccessibilityData& data);
```

### <a name="parameters"></a>Parametreler

*pParent*<br/>
Onay kutusunun ana penceresi.

*Veri*<br/>
Onay kutusunun erişilebilirlik verileri.

### <a name="return-value"></a>Dönüş Değeri

Her zaman TRUE döndürür.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak bu yöntem onay kutusu için erişilebilirlik verilerini ayarlar ve her zaman TRUE döndürür. Erişilebilirlik verilerini ayarlamak ve başarı veya başarısızlığı gösteren bir değer döndürmek için bu yöntemi geçersiz kılın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonPanel Sınıfı](../../mfc/reference/cmfcribbonpanel-class.md)
