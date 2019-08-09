---
title: Cmfcribbongallermenubtan sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CMFCRibbonGalleryMenuButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CopyFrom
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::CreatePopupMenu
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::GetPalette
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::HasButton
- AFXRIBBONPALETTEGALLERY/CMFCRibbonGalleryMenuButton::IsEmptyMenuAllowed
helpviewer_keywords:
- CMFCRibbonGalleryMenuButton [MFC], CMFCRibbonGalleryMenuButton
- CMFCRibbonGalleryMenuButton [MFC], CopyFrom
- CMFCRibbonGalleryMenuButton [MFC], CreatePopupMenu
- CMFCRibbonGalleryMenuButton [MFC], GetPalette
- CMFCRibbonGalleryMenuButton [MFC], HasButton
- CMFCRibbonGalleryMenuButton [MFC], IsEmptyMenuAllowed
ms.assetid: 4d459d9b-8b1a-4371-92f6-dc4ce6cc42c8
ms.openlocfilehash: 0ec295fa64b835064435992a398d4292ccf26f38
ms.sourcegitcommit: bd7ddc044f9083246614b602ef6a758775313214
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68866186"
---
# <a name="cmfcribbongallerymenubutton-class"></a>Cmfcribbongallermenubtan sınıfı

Şerit galerileri içeren bir şerit menü düğmesi uygular.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC\\atlmfc\\\\src MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Sözdizimi

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcribbongallermenubtan:: Cmfcribbongallermenubtan](#cmfcribbongallerymenubutton)|Bir `CMFCRibbonGalleryMenuButton` nesnesi oluşturur ve başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcribbongallermenubtan:: CopyFrom](#copyfrom)|( [Cmfctoolbarmenubtan:: CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom)geçersiz kılar.)|
|[Cmfcribbongallermenubtan:: CreatePopupMenu](#createpopupmenu)|( [Cmfctoolbarmenubtan:: CreatePopupMenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu)geçersiz kılar.)|
|[Cmfcribbongallermenubtan:: GetPalette](#getpalette)||
|[Cmfcribbongallermenubtan:: HasButton](#hasbutton)|(Geçersiz `CMFCToolBarMenuButton::HasButton`kılmalar.)|
|[Cmfcribbongallermenubtan:: IsEmptyMenuAllowed](#isemptymenuallowed)|( [Cmfctoolbarmenubtan:: IsEmptyMenuAllowed](../../mfc/reference/cmfctoolbarmenubutton-class.md#isemptymenuallowed)geçersiz kılınır.)|

### <a name="remarks"></a>Açıklamalar

Galeri menü düğmesi, ok ile bir açılır menü olarak görüntülenir. Kullanıcı bu düğmeye tıkladığında bir görüntü Galerisi görüntülenir. Galeri menü düğmesi oluşturduğunuzda, bu görüntüleri içeren bir görüntü listesi belirtmeniz gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir menü düğmesinde madde işaretlerinin bir galerinin nasıl görüntüleneceğini gösterir:

```cpp
BOOL CMainFrame::OnShowPopupMenu (CMFCPopupMenu* pMenuPopup)
{
    int nBulletIndex = pMenuBar->CommandToIndex (ID_PARA_BULLETS);

    if (nBulletIndex>= 0)
    {
        CMFCToolBarButton* pExButton =
        pMenuBar->GetButton(nBulletIndex);
        ASSERT_VALID (pExButton);

        CMFCRibbonGalleryMenuButton paletteBullet (
        pExButton->m_nID,
        pExButton->GetImage (),
        pExButton->m_strText);

        InitBulletPalette (&paletteBullet.GetPalette ());

        pMenuBar->ReplaceButton (ID_PARA_BULLETS,
        paletteBullet);
    }
}
```

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)\
└&nbsp;[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfctoolbarmenubtan](../../mfc/reference/cmfctoolbarmenubutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└&nbsp;[Cmfcribbongallermenubtan](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonpalettegallery. h

##  <a name="copyfrom"></a>Cmfcribbongallermenubtan:: CopyFrom

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="remarks"></a>Açıklamalar

##  <a name="cmfcribbongallerymenubutton"></a>Cmfcribbongallermenubtan:: Cmfcribbongallermenubtan

Bir [Cmfcribbongallermenubtan](../../mfc/reference/cmfcribbongallerymenubutton-class.md) nesnesi oluşturur ve başlatır.

```
CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    CMFCToolBarImages& imagesPalette);

CMFCRibbonGalleryMenuButton(
    UINT uiID,
    int iImage,
    LPCTSTR lpszText,
    UINT uiImagesPaletteResID = 0,
    int cxPaletteImage = 0);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
Düğmenin komut KIMLIĞI. Bu, Kullanıcı bu düğmeye tıkladığında WM_COMMAND iletisinde gönderilen değerdir.

*IImage*<br/>
Galeri menü düğmesiyle görüntülenecek görüntünün dizini. Görüntüler *ımabir palet* parametresinde depolanır.

*lpszText*<br/>
Menü düğmesinde görüntülenecek metin.

*Imate paleti*<br/>
Galeride görüntülenecek görüntülerin listesini içerir.

*Uııma, Paletteresid*<br/>
Galeride görüntülenecek görüntülerin görüntü listesinin kaynak KIMLIĞI.

*Cxpaletteımage*<br/>
Galeride görüntülenecek resmin piksel cinsinden genişliğini belirtir.

### <a name="remarks"></a>Açıklamalar

Galeri menü düğmesi, ok içeren bir açılır menü olarak görüntülenir. Kullanıcı bu düğmeye tıkladığında bir görüntü Galerisi görüntülenir.

### <a name="example"></a>Örnek

Aşağıdaki örnek, `CMFCRibbonGalleryMenuButton` sınıfının oluşturucusunun nasıl kullanılacağını göstermektedir. Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

##  <a name="createpopupmenu"></a>Cmfcribbongallermenubtan:: CreatePopupMenu

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="getpalette"></a>Cmfcribbongallermenubtan:: GetPalette

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="hasbutton"></a>Cmfcribbongallermenubtan:: HasButton

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

##  <a name="isemptymenuallowed"></a>Cmfcribbongallermenubtan:: IsEmptyMenuAllowed

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCToolBarMenuButton Sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[CMFCRibbonGallery Sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
