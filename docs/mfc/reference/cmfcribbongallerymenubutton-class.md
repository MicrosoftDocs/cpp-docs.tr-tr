---
description: 'Daha fazla bilgi edinin: Cmfcribbongallermenubtan sınıfı'
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
ms.openlocfilehash: ee527178ba90b968b1968ae0c06dbd8629d8d1e9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321858"
---
# <a name="cmfcribbongallerymenubutton-class"></a>Cmfcribbongallermenubtan sınıfı

Şerit galerileri içeren bir şerit menü düğmesi uygular.
Daha ayrıntılı bilgi için Visual Studio yüklemenizin **VC \\ atlmfc \\ src \\ MFC** klasöründe bulunan kaynak koduna bakın.

## <a name="syntax"></a>Syntax

```
class CMFCRibbonGalleryMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcribbongallermenubtan:: Cmfcribbongallermenubtan](#cmfcribbongallerymenubutton)|Bir nesnesi oluşturur ve başlatır `CMFCRibbonGalleryMenuButton` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfcribbongallermenubtan:: CopyFrom](#copyfrom)|( [Cmfctoolbarmenubtan:: CopyFrom](../../mfc/reference/cmfctoolbarmenubutton-class.md#copyfrom)geçersiz kılar.)|
|[Cmfcribbongallermenubtan:: CreatePopupMenu](#createpopupmenu)|( [Cmfctoolbarmenubtan:: CreatePopupMenu](../../mfc/reference/cmfctoolbarmenubutton-class.md#createpopupmenu)geçersiz kılar.)|
|[Cmfcribbongallermenubtan:: GetPalette](#getpalette)||
|[Cmfcribbongallermenubtan:: HasButton](#hasbutton)|(Geçersiz kılmalar `CMFCToolBarMenuButton::HasButton` .)|
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
└ &nbsp; [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [Cmfctoolbarmenubtan](../../mfc/reference/cmfctoolbarmenubutton-class.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;└ &nbsp; [Cmfcribbongallermenubtan](../../mfc/reference/cmfcribbongallerymenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxribbonpalettegallery. h

## <a name="cmfcribbongallerymenubuttoncopyfrom"></a><a name="copyfrom"></a> Cmfcribbongallermenubtan:: CopyFrom

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

'ndaki *src*<br/>

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbongallerymenubuttoncmfcribbongallerymenubutton"></a><a name="cmfcribbongallerymenubutton"></a> Cmfcribbongallermenubtan:: Cmfcribbongallermenubtan

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
Düğmenin komut KIMLIĞI. Bu değer, Kullanıcı bu düğmeye tıkladığında WM_COMMAND iletisinde gönderilir.

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

Aşağıdaki örnek, sınıfının oluşturucusunun nasıl kullanılacağını göstermektedir `CMFCRibbonGalleryMenuButton` . Bu kod parçacığı, [MS Office 2007 demo örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_MSOffice2007Demo#8](../../mfc/reference/codesnippet/cpp/cmfcribbongallerymenubutton-class_1.cpp)]

## <a name="cmfcribbongallerymenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a> Cmfcribbongallermenubtan:: CreatePopupMenu

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbongallerymenubuttongetpalette"></a><a name="getpalette"></a> Cmfcribbongallermenubtan:: GetPalette

```
CMFCRibbonGallery& GetPalette();
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbongallerymenubuttonhasbutton"></a><a name="hasbutton"></a> Cmfcribbongallermenubtan:: HasButton

```
virtual BOOL HasButton() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="cmfcribbongallerymenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a> Cmfcribbongallermenubtan:: IsEmptyMenuAllowed

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[Cmfctoolbarmenubtan sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)<br/>
[CMFCRibbonGallery sınıfı](../../mfc/reference/cmfcribbongallery-class.md)
