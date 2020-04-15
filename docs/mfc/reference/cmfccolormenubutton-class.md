---
title: CMFCColorMenuButton Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CMFCColorMenuButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableAutomaticButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableDocumentColors
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableOtherButton
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::EnableTearOff
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetAutomaticColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::GetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnChangeParentWnd
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OpenColorDialog
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColor
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorByCmdID
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColorName
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::SetColumnsNumber
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CopyFrom
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::CreatePopupMenu
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::IsEmptyMenuAllowed
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDraw
- AFXCOLORMENUBUTTON/CMFCColorMenuButton::OnDrawOnCustomizeList
helpviewer_keywords:
- CMFCColorMenuButton [MFC], CMFCColorMenuButton
- CMFCColorMenuButton [MFC], EnableAutomaticButton
- CMFCColorMenuButton [MFC], EnableDocumentColors
- CMFCColorMenuButton [MFC], EnableOtherButton
- CMFCColorMenuButton [MFC], EnableTearOff
- CMFCColorMenuButton [MFC], GetAutomaticColor
- CMFCColorMenuButton [MFC], GetColor
- CMFCColorMenuButton [MFC], GetColorByCmdID
- CMFCColorMenuButton [MFC], OnChangeParentWnd
- CMFCColorMenuButton [MFC], OpenColorDialog
- CMFCColorMenuButton [MFC], SetColor
- CMFCColorMenuButton [MFC], SetColorByCmdID
- CMFCColorMenuButton [MFC], SetColorName
- CMFCColorMenuButton [MFC], SetColumnsNumber
- CMFCColorMenuButton [MFC], CopyFrom
- CMFCColorMenuButton [MFC], CreatePopupMenu
- CMFCColorMenuButton [MFC], IsEmptyMenuAllowed
- CMFCColorMenuButton [MFC], OnDraw
- CMFCColorMenuButton [MFC], OnDrawOnCustomizeList
ms.assetid: 42685704-e994-4f7b-9553-62283c27b754
ms.openlocfilehash: 22208aec505033d372f5a80ba2a9641b1bd15874
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367699"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton Sınıfı

Sınıf, `CMFCColorMenuButton` renk seçici iletişim kutusunu başlatan bir menü komutunu veya araç çubuğu düğmesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Bir `CMFCColorMenuButton` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Normal renk düğmelerinin üzerine konumlandırılmış bir "otomatik" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem otomatik düğmesi **Otomatik**olarak etiketlenmiştir.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Sistem renkleri yerine belgeye özgü renklerin görüntülenmesini sağlar.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Normal renk düğmelerinin altına konumlandırılmış bir "diğer" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem "diğer" düğmesi **Daha Fazla Renk**olarak etiketlenir.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Renk bölmesini yırtma olanağı sağlar.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|
|[CMFCColorMenuButton::GetColor](#getcolor)|Geçerli düğmenin rengini alır.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Belirtilen bir komut kimliğine karşılık gelen rengi alır.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Üst pencere değiştiğinde çerçeve tarafından çağrılır.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Renk seçimi iletişim kutusunu açar.|
|[CMFCColorMenuButton::SetColor](#setcolor)|Geçerli renk düğmesinin rengini ayarlar.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Belirtilen renk menüsü düğmesinin rengini ayarlar.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Belirtilen renk için yeni bir ad ayarlar.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Bir `CMFCColorBar` nesne tarafından görüntülenen sütun sayısını ayarlar.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Geçerli düğmeye başka bir araç çubuğu düğmesini kopyalar.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Renk seçici iletişim kutusu oluşturur.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Boş menülerin desteklenip desteklenmediğini gösterir.|
|[CMFCColorMenuButton::OnDraw](#ondraw)|Bir düğmeüzerinde bir görüntü görüntülemek için çerçeve tarafından çağrılır.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Araç çubuğu özelleştirme `CMFCColorMenuButton` iletişim kutusu listesinde bir nesne görüntülenmeden önce çerçeve tarafından çağrılır.|

## <a name="remarks"></a>Açıklamalar

Özgün menü komutunu veya araç çubuğu `CMFCColorMenuButton` düğmesini `CMFCColorMenuButton` bir nesneyle değiştirmek için nesneyi oluşturun, uygun `ReplaceButton` [CMFCColorBar Sınıf](../../mfc/reference/cmfccolorbar-class.md) stillerini ayarlayın ve ardından [CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfının yöntemini arayın. Bir araç çubuğunu özelleştirirseniz, [CMFCToolBarsCustomizeDialog'u arayın::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) yöntemini.

[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) olay işleyicisi işleyicisi işlenme sırasında renk seçici iletişim kutusu oluşturulur. Olay işleyicisi, ana çerçeveyi WM_COMMAND bir iletiyle birlikte not alar. Nesne, `CMFCColorMenuButton` özgün menü komutu veya araç çubuğu düğmesine atanan denetim kimliğini gönderir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfta çeşitli yöntemler kullanarak bir renk menüsü düğmesinin `CMFCColorMenuButton` nasıl oluşturulup yapılandırılabildiğini gösterir. Örnekte, önce `CPalette` bir nesne oluşturulur ve daha sonra `CMFCColorMenuButton` sınıfın bir nesnesini oluşturmak için kullanılır. Nesne `CMFCColorMenuButton` daha sonra otomatik ve diğer düğmelerini etkinleştirerek ve rengini ve sütun sayısını ayarlayarak yapılandırılır. Bu [kod, Word Pad örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[Cmfctoolbarmenubutton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[Cmfccolormenubutton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolormenubutton.h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a>CMFCColorMenuButton::CMFCColorMenuButton

Bir `CMFCColorMenuButton` nesne inşa eder.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[içinde] Düğme komut kimliği.

*lpszMetin*<br/>
[içinde] Düğme metni.

*pPalette*<br/>
[içinde] Düğmenin renk paletine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu varsayılan oluşturucudur. Nesnenin geçerli rengi ve otomatik rengi siyaha (RGB(0, 0, 0)) başharfle başlanır.

İkinci oluşturucu, düğmeyi belirtilen komut kimliğine karşılık gelen renge ait bir düğmeye ait hale gelir.

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a>CMFCColorMenuButton::CopyFrom

Bir [CMFCToolBarMenuButton Sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)türetilmiş nesneyi diğerine kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[içinde] Kaynak düğmesi kopyala.

### <a name="remarks"></a>Açıklamalar

`CMFCColorMenuButton` Nesneden türetilen nesneleri kopyalamak için bu yöntemi geçersiz kılın.

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a>CMFCColorMenuButton::CreatePopupMenu

Renk seçici iletişim kutusu oluşturur.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Renk seçici iletişim kutusunu temsil eden bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı bir renk menüsü düğmesine bastığında çerçeve tarafından çağrılır.

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a>CMFCColorMenuButton::EnableAutomaticButton

Normal renk düğmelerinin üzerine konumlandırılmış bir "otomatik" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem otomatik düğmesi **Otomatik**olarak etiketlenmiştir.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Düğme otomatik olduğunda görüntülenen düğme metnini belirtir.

*Colorautomatic*<br/>
[içinde] Yeni bir otomatik renk belirtir.

*bEtkinleştir*<br/>
[içinde] Düğmenin otomatik olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Otomatik düğme geçerli varsayılan rengi uygular.

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a>CMFCColorMenuButton::EnableDocumentColors

Sistem renkleri yerine belgeye özgü renklerin görüntülenmesini sağlar.

```
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Düğme metnini belirtir.

*bEtkinleştir*<br/>
[içinde] Belgeye özgü renkleri görüntülemek için DOĞRU veya sistem renklerini görüntülemek için FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir renk menüsü düğmesini tıklattığında geçerli belge renklerini veya sistem palet renklerini görüntülemek için bu yöntemi kullanın.

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a>CMFCColorMenuButton::EnableOtherButton

Normal renk düğmelerinin altına konumlandırılmış bir "diğer" düğmeyi etkinleştirer ve devre dışı kılabilir. (Standart sistem "diğer" düğmesi **Daha Fazla Renk**olarak etiketlenir.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszEtiket*<br/>
[içinde] Düğme metnini belirtir.

*bAltColorDlg*<br/>
[içinde] `CMFCColorDialog` İletişim kutusunu görüntülemek için TRUE veya standart sistem renk iletişim kutusunu görüntülemek için FALSE'u belirtin.

*bEtkinleştir*<br/>
[içinde] "Diğer" düğmesini görüntülemek için TRUE belirtin; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a>CMFCColorMenuButton::EnableTearOff

Renk bölmesini yırtma olanağı sağlar.

```
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[içinde] Yırtılma bölmesinin kimliğini belirtir.

*nVertDockSütunlar*<br/>
[içinde] Yırtılma durumunda dikey olarak sabitlenmiş renk bölmesindeki sütun sayısını belirtir.

*nHorzDockRows*<br/>
[içinde] Yırtılma durumunda yatay olarak sabitlenmiş renk bölmesinin satır sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

`CMFCColorMenuButton` Düğmeye basıldığında açılan renk bölmesi için "yırtılma" özelliğini etkinleştirmek için bu yöntemi arayın.

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a>CMFCColorMenuButton::GetAutomaticColor

Geçerli otomatik rengi alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik rengi temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

CMFCColorMenuButton tarafından ayarlanan otomatik rengi elde etmek için bu yöntemi [arayın::EnableAutomaticButton](#enableautomaticbutton).

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a>CMFCColorMenuButton::GetColor

Geçerli düğmenin rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin rengi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a>CMFCColorMenuButton::GetColorByCmdID

Belirtilen bir komut kimliğine karşılık gelen rengi alır.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[içinde] Bir komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliğine karşılık gelen renk.

### <a name="remarks"></a>Açıklamalar

Bir uygulamada birkaç renk düğmeniz varsa bu yöntemi kullanın. Kullanıcı bir renk düğmesini tıklattığında, düğme komut kimliğini WM_COMMAND iletisi olarak üst öğesine gönderir. Yöntem, `GetColorByCmdID` karşılık gelen rengi almak için komut kimliğini kullanır.

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a>CMFCColorMenuButton::IsEmptyMenuAllowed

Boş menülerin desteklenip desteklenmediğini gösterir.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş menülere izin veriliyorsa sıfıra inme; aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Boş menüler varsayılan olarak desteklenir. Türemiş sınıfta bu davranışı değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a>CMFCColorMenuButton::OnChangeParentWnd

Üst pencere değiştiğinde çerçeve tarafından çağrılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[içinde] Yeni üst pencereiçin bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a>CMFCColorMenuButton::OnDraw

Bir düğmeüzerinde bir görüntü görüntülemek için çerçeve tarafından çağrılır.

```
virtual void OnDraw(
    CDC* pDC,
    const CRect& rect,
    CMFCToolBarImages* pImages,
    BOOL bHorz=TRUE,
    BOOL bCustomizeMode=FALSE,
    BOOL bHighlight=FALSE,
    BOOL bDrawBorder=TRUE,
    BOOL bGrayDisabledButtons=TRUE);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Alanı yeniden çizilecek sınırlayan bir dikdörtgen.

*pImages*<br/>
[içinde] Araç çubuğu görüntülerinin listesine işaret edin.

*bHorz*<br/>
[içinde] Araç çubuğunun yatay olarak sabitlenmiş durumda olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

*bCustomizeMode*<br/>
[içinde] UYGULAMAnin özelleştirme modunda olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan FALSE'dır.

*bVurgu*<br/>
[içinde] DÜĞMENin vurgulandığına dikkat etmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan FALSE'dır.

*bDrawBorder*<br/>
[içinde] Düğmenin kenarlığı görüntülenen belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

*bGrayDisabledButtons*<br/>
[içinde] Devre dışı bırakılan düğmelerin gri (soluk) olduğunu belirtmek için TRUE; aksi takdirde, YANLIŞ. Varsayılan TRUE'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a>CMFCColorMenuButton::OnDrawOnCustomizeList

Araç çubuğu özelleştirme `CMFCColorMenuButton` iletişim kutusu listesinde bir nesne görüntülenmeden önce çerçeve tarafından çağrılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Pdc*<br/>
[içinde] Aygıt bağlamına işaretçi.

*Rect*<br/>
[içinde] Çizilecek düğmeyi sınırlayan bir dikdörtgen.

*bSelected*<br/>
[içinde] TRUE, düğmenin seçili durumda olduğunu belirtir; aksi takdirde, YANLIŞ.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

Araç çubuğu özelleştirme işlemi sırasında `CMFCColorMenuButton` liste kutusunda bir nesne görüntülendiğinde, bu yöntem çerçeve tarafından çağrılır.

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a>CMFCColorMenuButton::OpenColorDialog

Renk seçimi iletişim kutusunu açar.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametreler

*colorDefault*<br/>
[içinde] Renk iletişim kutusunda seçilen varsayılan renk.

*colorRes*<br/>
[çıkış] Kullanıcının renk iletişim kutusundan seçtiği rengi döndürür.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı yeni bir renk seçerse sıfırolmayan; aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Menü düğmesine tıklandığında, renk iletişim kutusunu açmak için bu yöntemi arayın. İade değeri sıfır değilse, kullanıcının seçtiği renk *colorRes* parametresinde depolanır. Standart renk iletişim kutusu ile [CMFCColorDialog Class](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu arasında geçiş yapmak için [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) yöntemini kullanın.

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a>CMFCColorMenuButton::SetColor

Geçerli renk düğmesinin rengini ayarlar.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Parametreler

*Clr*<br/>
[içinde] RGB renk değeri.

*bNotify*<br/>
[içinde] *Clr* parametre rengini ilişkili menü düğmesine veya araç çubuğu düğmesine uygulamak için TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Geçerli renk düğmesinin rengini değiştirmek için bu yöntemi arayın. *bNotify* parametresi sıfır değilse, ilişkili açılır menüveya araç çubuğundaki ilgili düğmenin rengi *clr* parametresi tarafından belirtilen renge değiştirilir.

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a>CMFCColorMenuButton::SetColorByCmdID

Belirtilen renk menüsü düğmesinin rengini ayarlar.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[içinde] Renkli menü düğmesinin kaynak kimliği.

*color*<br/>
[içinde] RGB renk değeri.

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a>CMFCColorMenuButton::SetColorName

Belirtilen renk için yeni bir ad ayarlar.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*color*<br/>
[içinde] Adı değişen rengin RGB değeri.

*strName*<br/>
[içinde] Rengin yeni adı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a>CMFCColorMenuButton::SetColumnsNumber

Renk seçimi denetiminde [(CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) nesnesi) görüntülenecek sütun sayısını ayarlar.

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nSütunlar*<br/>
[içinde] Görüntülenecek sütun sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog Sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton Sınıfı](../../mfc/reference/cmfccolorbutton-class.md)
