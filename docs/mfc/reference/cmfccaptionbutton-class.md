---
description: 'Daha fazla bilgi edinin: CMFCCaptionButton sınıfı'
title: CMFCCaptionButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::CMFCCaptionButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetHit
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetIconID
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetRect
- AFXCAPTIONBUTTON/CMFCCaptionButton::GetSize
- AFXCAPTIONBUTTON/CMFCCaptionButton::IsMiniFrameButton
- AFXCAPTIONBUTTON/CMFCCaptionButton::Move
- AFXCAPTIONBUTTON/CMFCCaptionButton::OnDraw
- AFXCAPTIONBUTTON/CMFCCaptionButton::SetMiniFrameButton
helpviewer_keywords:
- CMFCCaptionButton [MFC], CMFCCaptionButton
- CMFCCaptionButton [MFC], GetHit
- CMFCCaptionButton [MFC], GetIconID
- CMFCCaptionButton [MFC], GetRect
- CMFCCaptionButton [MFC], GetSize
- CMFCCaptionButton [MFC], IsMiniFrameButton
- CMFCCaptionButton [MFC], Move
- CMFCCaptionButton [MFC], OnDraw
- CMFCCaptionButton [MFC], SetMiniFrameButton
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
ms.openlocfilehash: 6c3c1cbeea4a548f2951276b3ad43cb598cf22a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327748"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton sınıfı

`CMFCCaptionButton`Sınıfı, yerleştirme bölmesi veya mini çerçeve penceresi için başlık çubuğunda görüntülenen bir düğme uygular. Genellikle Framework, otomatik olarak açıklamalı alt yazı düğmeleri oluşturur.

## <a name="syntax"></a>Syntax

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionButton:: CMFCCaptionButton](#cmfccaptionbutton)|Bir CMFCCaptionButton nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCCaptionButton:: GetHit](#gethit)|Düğme tarafından temsil edilen komutu döndürür.|
|[CMFCCaptionButton:: Getıconıd](#geticonid)|Düğmeyle ilişkili görüntü KIMLIĞINI döndürür.|
|[CMFCCaptionButton:: GetRect](#getrect)|Düğmenin kapladığı dikdörtgeni döndürür.|
|[CMFCCaptionButton:: GetSize](#getsize)|Düğmenin genişliğini ve yüksekliğini döndürür.|
|[CMFCCaptionButton:: IsMiniFrameButton](#isminiframebutton)|Başlık çubuğunun yüksekliğinin mini boyut olarak ayarlanmış olup olmadığını gösterir.|
|[CMFCCaptionButton:: Move](#move)|Düğme çizim konumunu ve pencere durumu göster ' i ayarlar.|
|[CMFCCaptionButton:: OnDraw](#ondraw)|Başlık düğmesini çizer.|
|[CMFCCaptionButton:: SetMiniFrameButton](#setminiframebutton)|Başlık çubuğunun mini boyutunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

[Cpgframewnd sınıfından](../../mfc/reference/cpaneframewnd-class.md) bir sınıf türetebilirsiniz ve `AddButton` bir mini çerçeve penceresine açıklamalı alt yazı düğmeleri eklemek için Protected yöntemini kullanabilirsiniz.

Cbölmesi Framewnd. h iki tür Başlık düğmesi için komut kimliklerini tanımlar:

- Takma bölmesi otomatik gizleme modunu desteklediğinde bir PIN düğmesi görüntüleyen AFX_CAPTION_BTN_PIN.

- AFX_CAPTION_BTN_CLOSE, bölme kapatılabilir veya gizleniyorsa bir **Kapat** düğmesi görüntüler.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir nesnesinin nasıl oluşturulduğunu `CMFCCaptionButton` ve başlık çubuğunun mini boyutunu nasıl ayarlayabileceğinizi gösterir.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcaptionbutton. h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a> CMFCCaptionButton:: CMFCCaptionButton

Bir `CMFCCaptionButton` nesnesi oluşturur.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Parametreler

*nHit*<br/>
'ndaki Düğmeyle ilişkili komut.

*bLeftAlign*<br/>
'ndaki Düğmenin sola hizalanıp Hizalanmadığını belirtir.

Aşağıdaki tabloda *nHit* parametresi için olası değerler listelenmektedir.

|Değer|Komut|
|-----------|-------------|
|AFX_HTCLOSE|Kapat düğmesi.|
|HTMINBUTTON|Simge durumuna küçült.|
|HTMAXBUTTON|Ekranı Kapla düğmesi.|
|AFX_HTLEFTBUTTON|Sol ok düğmesi.|
|AFX_HTRIGHTBUTTON|Sağ ok düğmesi.|
|AFX_HTMENU|Aşağı ok menü düğmesi.|
|HTNOWHERE|Varsayılan değer; bir komutu temsil eder.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, resim yazısı düğmeleri bir komutla ilişkili değildir.

Açıklamalı altyazı düğmeleri sağ veya sol tarafta hizalanır.

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a> CMFCCaptionButton:: GetHit

Düğme tarafından temsil edilen komutu döndürür.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme tarafından temsil edilen komut.

Aşağıdaki tabloda olası dönüş değerleri listelenmektedir.

|Değer|Komut|
|-----------|-------------|
|AFX_HTCLOSE|Kapat düğmesi.|
|HTMINBUTTON|Simge durumuna küçült.|
|HTMAXBUTTON|Ekranı Kapla düğmesi.|
|AFX_HTLEFTBUTTON|Sol ok düğmesi.|
|AFX_HTRIGHTBUTTON|Sağ ok düğmesi.|
|AFX_HTMENU|Aşağı ok menü düğmesi.|
|HTNOWHERE|Varsayılan değer; bir komutu temsil eder.|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a> CMFCCaptionButton:: Getıconıd

Düğmeyle ilişkili görüntü KIMLIĞINI döndürür.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
'ndaki Sol veya sağ ok görüntü kimlikleri için TRUE; Yukarı veya aşağı ok görüntü kimlikleri için yanlış.

*Büyütülmüş*<br/>
'ndaki En yüksek görüntü KIMLIĞI için TRUE; Görüntü KIMLIĞINI en aza indirmek için FALSE.

### <a name="return-value"></a>Dönüş Değeri

Görüntü KIMLIĞI.

### <a name="remarks"></a>Açıklamalar

Parametreler, simge durumuna küçültme veya ekranı kaplama düğmeleri için görüntü kimliklerini belirtir.

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a> CMFCCaptionButton:: GetRect

Düğmenin kapladığı dikdörtgeni döndürür.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin konumunu temsil eden dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Düğmeyi göremiyorsanız döndürülen boyut 0 ' dır.

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a> CMFCCaptionButton:: GetSize

Düğmenin genişliğini ve yüksekliğini döndürür.

```
static CSize GetSize();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin dış boyutları.

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut düğme kenar boşluğu ve kenarlık içerir.

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a> CMFCCaptionButton:: IsMiniFrameButton

Başlık çubuğunun yüksekliğinin mini boyut olarak ayarlanmış olup olmadığını gösterir.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Resim yazısı mini boyut olarak ayarlandıysa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a> CMFCCaptionButton:: Move

Düğme çizim konumunu ve pencere durumu göster ' i ayarlar.

```cpp
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*PANI*<br/>
'ndaki Yeni konum.

*bHide*<br/>
'ndaki Düğmenin gösterilip gösterilmeyeceğini belirtir.

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a> CMFCCaptionButton:: OnDraw

Başlık düğmesini çizer.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Düğme için bir cihaz bağlamı işaretçisi.

*bActive*<br/>
'ndaki Etkin bir düğme görüntüsü çizip çizmeyeceğinizi belirtir.

*bHorz*<br/>
'ndaki Türetilmiş bir sınıfta kullanılmak üzere ayrılmıştır.

*Büyütülmüş*<br/>
'ndaki Ekranı kaplayan bir düğme görüntüsü çizip çizmediği.

*bDisabled*<br/>
'ndaki Etkin bir düğme görüntüsü çizip çizmeyeceğinizi belirtir.

### <a name="remarks"></a>Açıklamalar

Düğme, bir en yüksek Ekranı Kapla veya simge durumuna küçültme düğmesi olduğunda, *Bekranı kaplamış* parametresi kullanılır.

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a> CMFCCaptionButton:: SetMiniFrameButton

Başlık çubuğunun mini boyutunu ayarlar.

```cpp
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
'ndaki Mini başlık çubuğunun yüksekliği için doğru; Varsayılan başlık çubuğunun yüksekliği için yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Cbölmesi Framewnd sınıfı](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane sınıfı](../../mfc/reference/cdockablepane-class.md)
