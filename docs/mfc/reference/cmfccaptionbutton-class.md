---
title: CMFCCaptionButton Sınıfı
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
ms.openlocfilehash: fb47e4373bf53e66dd4af17c89fe2f761858fbfd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367747"
---
# <a name="cmfccaptionbutton-class"></a>CMFCCaptionButton Sınıfı

Sınıf, `CMFCCaptionButton` yerleştirme bölmesi veya mini çerçeve penceresi için resim yazısı çubuğunda görüntülenen bir düğme uygular. Genellikle, çerçeve otomatik olarak resim yazısı düğmeleri oluşturur.

## <a name="syntax"></a>Sözdizimi

```
class CMFCCaptionButton : public CObject
```

## <a name="members"></a>Üyeler

### <a name="constructors"></a>Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCCaptionButton::CMFCCaptionButton](#cmfccaptionbutton)|CMFCCaptionButton nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCCaptionButton::GetHit](#gethit)|Düğme tarafından temsil edilen komutu döndürür.|
|[CMFCCaptionButton::GetIconID](#geticonid)|Düğmeyle ilişkili görüntü kimliğini döndürür.|
|[CMFCCaptionButton::GetRect](#getrect)|Düğmetarafından işgal edilen dikdörtgeni döndürür.|
|[CMFCCaptionButton::GetSize](#getsize)|Düğmenin genişliğini ve yüksekliğini verir.|
|[CMFCCaptionButton::IsMiniFrameButton](#isminiframebutton)|Başlık çubuğu yüksekliğinin mini boyuta ayarlanıp ayarlmadığını gösterir.|
|[CMFCCaptionButton::Taşı](#move)|Düğme çizim konumu ve pencere gösteri durumu ayarlar.|
|[CMFCCaptionButton::OnDraw](#ondraw)|Resim yazısı düğmesini çizer.|
|[CMFCCaptionButton::SetMiniFrameButton](#setminiframebutton)|Başlık çubuğunun mini boyutunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

[CPaneFrameWnd Class'tan](../../mfc/reference/cpaneframewnd-class.md) bir sınıf türetebilir ve `AddButton`mini çerçeve penceresine resim yazısı düğmeleri eklemek için korumalı yöntemi kullanabilirsiniz.

CPaneFrameWnd.h, iki tür resim yazısı düğmesi için komut tanımlarını tanımlar:

- AFX_CAPTION_BTN_PIN, yerleştirme bölmesi otomatik gizleme modunu desteklediğinde bir pin düğmesi görüntüler.

- bölme kapatıldığında veya gizlendiğinde **Kapat** düğmesini görüntüleyen AFX_CAPTION_BTN_CLOSE.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir `CMFCCaptionButton` nesnenin nasıl oluşturup başlık çubuğunun mini boyutunun ayarlanıştını gösterir.

[!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/cpp/cmfccaptionbutton-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcaptionbutton.h

## <a name="cmfccaptionbuttoncmfccaptionbutton"></a><a name="cmfccaptionbutton"></a>CMFCCaptionButton::CMFCCaptionButton

Bir `CMFCCaptionButton` nesne inşa eder.

```
CMFCCaptionButton();

CMFCCaptionButton(
    UINT nHit,
    BOOL bLeftAlign = FALSE);
```

### <a name="parameters"></a>Parametreler

*nHit*<br/>
[içinde] Düğmeyle ilişkili komut.

*bLeftAlign*<br/>
[içinde] Düğmenin sola hizalanıp hizalanmayacağını belirtir.

Aşağıdaki tabloda *nHit* parametresi için olası değerler listeleilmektedir.

|Değer|Komut|
|-----------|-------------|
|AFX_HTCLOSE|Düğmeyi kapat.|
|HTMINBUTTON|Simge durumuna küçült düğmesi.|
|HTMAXBUTTON|En üst düzeye çıkar düğmesi.|
|AFX_HTLEFTBUTTON|Sol ok tuşu.|
|AFX_HTRIGHTBUTTON|Sağ ok tuşu.|
|AFX_HTMENU|Aşağı ok menü düğmesi.|
|HTNOWHERE|Varsayılan değer; hiçbir komutu temsil etmez.|

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, resim yazısı düğmeleri bir komutla ilişkili değildir.

Resim yazısı düğmeleri sağda veya solda hizalanır.

## <a name="cmfccaptionbuttongethit"></a><a name="gethit"></a>CMFCCaptionButton::GetHit

Düğme tarafından temsil edilen komutu döndürür.

```
UINT GetHit() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme tarafından temsil edilen komut.

Aşağıdaki tabloda olası iade değerleri listelenilmektedir.

|Değer|Komut|
|-----------|-------------|
|AFX_HTCLOSE|Düğmeyi kapat.|
|HTMINBUTTON|Simge durumuna küçült düğmesi.|
|HTMAXBUTTON|En üst düzeye çıkar düğmesi.|
|AFX_HTLEFTBUTTON|Sol ok tuşu.|
|AFX_HTRIGHTBUTTON|Sağ ok tuşu.|
|AFX_HTMENU|Aşağı ok menü düğmesi.|
|HTNOWHERE|Varsayılan değer; hiçbir komutu temsil etmez.|

## <a name="cmfccaptionbuttongeticonid"></a><a name="geticonid"></a>CMFCCaptionButton::GetIconID

Düğmeyle ilişkili görüntü kimliğini döndürür.

```
virtual CMenuImages::IMAGES_IDS GetIconID(
    BOOL bHorz,
    BOOL bMaximized = FALSE) const;
```

### <a name="parameters"></a>Parametreler

*bHorz*<br/>
[içinde] Sol veya sağ ok görüntü titremleri için DOĞRU; Yukarı veya aşağı ok görüntü titreşmeleri için YANLIŞ.

*bMaximized*<br/>
[içinde] Görüntü kimliğini en üst düzeye çıkarmak için DOĞRU; En aza indirgenme görüntü kimliği için YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Görüntü kimliği.

### <a name="remarks"></a>Açıklamalar

Parametreler, resim yazısı düğmelerini en aza indirmek veya en üst düzeye çıkarmak için resim eklerini belirtir.

## <a name="cmfccaptionbuttongetrect"></a><a name="getrect"></a>CMFCCaptionButton::GetRect

Düğmetarafından işgal edilen dikdörtgeni döndürür.

```
virtual CRect GetRect() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin konumunu temsil eden dikdörtgen.

### <a name="remarks"></a>Açıklamalar

Düğmeyi göremiyorsanız, döndürülen boyut 0'dır.

## <a name="cmfccaptionbuttongetsize"></a><a name="getsize"></a>CMFCCaptionButton::GetSize

Düğmenin genişliğini ve yüksekliğini verir.

```
static CSize GetSize();
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin dış boyutları.

### <a name="remarks"></a>Açıklamalar

Döndürülen boyut düğme kenar boşluğu ve kenarlık içerir.

## <a name="cmfccaptionbuttonisminiframebutton"></a><a name="isminiframebutton"></a>CMFCCaptionButton::IsMiniFrameButton

Başlık çubuğu yüksekliğinin mini boyuta ayarlanıp ayarlmadığını gösterir.

```
BOOL IsMiniFrameButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

Resim yazısı mini boyuta ayarlanmışsa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccaptionbuttonmove"></a><a name="move"></a>CMFCCaptionButton::Taşı

Düğme çizim konumu ve pencere gösteri durumu ayarlar.

```
void Move(
    const CPoint& ptTo,
    BOOL bHide = FALSE);
```

### <a name="parameters"></a>Parametreler

*ptTo*<br/>
[içinde] Yeni yer.

*bHide*<br/>
[içinde] Düğmeyi gösterip göstermeyeceğim.

## <a name="cmfccaptionbuttonondraw"></a><a name="ondraw"></a>CMFCCaptionButton::OnDraw

Resim yazısı düğmesini çizer.

```
virtual void OnDraw(
    CDC* pDC,
    BOOL bActive,
    BOOL bHorz = TRUE,
    BOOL bMaximized = TRUE,
    BOOL bDisabled = FALSE);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Düğme için aygıt bağlamını işaretleyin.

*bAktif*<br/>
[içinde] Etkin bir düğme görüntüsü çizmek ister.

*bHorz*<br/>
[içinde] Türemiş bir sınıfta kullanılmak üzere ayrılmıştır.

*bMaximized*<br/>
[içinde] Maksimize bir düğme görüntüsü çizmek ister.

*bDevre dışı*<br/>
[içinde] Etkin bir düğme görüntüsü çizmek ister.

### <a name="remarks"></a>Açıklamalar

*bMaximized* parametresi, düğme en üst düzeye çıkarma veya en aza indirme düğmesi olduğunda kullanılır.

## <a name="cmfccaptionbuttonsetminiframebutton"></a><a name="setminiframebutton"></a>CMFCCaptionButton::SetMiniFrameButton

Başlık çubuğunun mini boyutunu ayarlar.

```
void SetMiniFramebutton(BOOL bSet = TRUE);
```

### <a name="parameters"></a>Parametreler

*bSet*<br/>
[içinde] Mini başlık çubuğu yüksekliği için DOĞRU; Varsayılan başlık çubuğu yüksekliği için FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CPaneFrameWnd Sınıf](../../mfc/reference/cpaneframewnd-class.md)<br/>
[CDockablePane Sınıfı](../../mfc/reference/cdockablepane-class.md)
