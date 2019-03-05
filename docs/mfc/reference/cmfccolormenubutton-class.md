---
title: CMFCColorMenuButton sınıfı
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
ms.openlocfilehash: 64d61cc9464ef0877baad33a8685cee1482f240d
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57301343"
---
# <a name="cmfccolormenubutton-class"></a>CMFCColorMenuButton sınıfı

`CMFCColorMenuButton` Sınıfı, bir menü komutu veya bir Renk Seçici iletişim kutusunu başlatan bir araç çubuğu düğmesini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::CMFCColorMenuButton](#cmfccolormenubutton)|Oluşturur bir `CMFCColorMenuButton` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton)|Sağlar ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğme **otomatik**.)|
|[CMFCColorMenuButton::EnableDocumentColors](#enabledocumentcolors)|Sistem renkleri yerine belgeye özgü renkleri görüntülenmesini sağlar.|
|[CMFCColorMenuButton::EnableOtherButton](#enableotherbutton)|Sağlar ve normal renk düğmelerin altında konumlandırılmış bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha fazla renk**.)|
|[CMFCColorMenuButton::EnableTearOff](#enabletearoff)|Bir renk bölmesi ayırma olanağı sağlar.|
|[CMFCColorMenuButton::GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengini alır.|
|[CMFCColorMenuButton::GetColor](#getcolor)|Geçerli düğmenin rengini alır.|
|[CMFCColorMenuButton::GetColorByCmdID](#getcolorbycmdid)|Belirtilen komut kimliğine karşılık gelen rengi alır.|
|[CMFCColorMenuButton::OnChangeParentWnd](#onchangeparentwnd)|Ana pencereyi değiştiğinde framework tarafından çağırılır.|
|[CMFCColorMenuButton::OpenColorDialog](#opencolordialog)|Bir renk seçimi iletişim kutusunu açar.|
|[CMFCColorMenuButton::SetColor](#setcolor)|Geçerli renk düğmesi rengini ayarlar.|
|[CMFCColorMenuButton::SetColorByCmdID](#setcolorbycmdid)|Belirtilen renk menü düğmesi rengini ayarlar.|
|[CMFCColorMenuButton::SetColorName](#setcolorname)|Belirtilen "rengin" yeni adını ayarlar.|
|[CMFCColorMenuButton::SetColumnsNumber](#setcolumnsnumber)|Tarafından görüntülenen sütunların sayısını ayarlar bir `CMFCColorBar` nesne.|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CMFCColorMenuButton::CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesi geçerli düğmeyi kopyalar.|
|[CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu)|Bir Renk Seçici iletişim kutusu oluşturur.|
|[CMFCColorMenuButton::IsEmptyMenuAllowed](#isemptymenuallowed)|Boş Menü desteklenip desteklenmediğini gösterir.|
|[CMFCColorMenuButton::OnDraw](#ondraw)|Görüntü üzerindeki bir düğme görüntülemek için framework tarafından çağırılır.|
|[CMFCColorMenuButton::OnDrawOnCustomizeList](#ondrawoncustomizelist)|Önce framework tarafından çağırılır bir `CMFCColorMenuButton` nesnesi, bir araç çubuğu özelleştirme iletişim kutusunda listede görüntülenir.|

## <a name="remarks"></a>Açıklamalar

Orijinal menü komut veya araç çubuğu düğmesi ile değiştirmek için bir `CMFCColorMenuButton` nesne, oluşturma `CMFCColorMenuButton` her uygun ayarlanmış nesnesi, [CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md) stilleri ve sonra çağrı `ReplaceButton` yöntemi[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfı. Bir araç çubuğunu özelleştirme, çağrı [CMFCToolBarsCustomizeDialog::ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) yöntemi.

Renk Seçici iletişim kutusu işlenmesi sırasında oluşturulan [CMFCColorMenuButton::CreatePopupMenu](#createpopupmenu) olay işleyicisi. Olay işleyicisi ana çerçeve WM_COMMAND ileti ile uyarır. `CMFCColorMenuButton` Özgün menü komut veya araç çubuğu düğmesi atanan denetim kimliği nesneyi gönderir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, oluşturmak ve çeşitli yöntemleri kullanarak bir renk menü düğmesi yapılandırmak gösterilmiştir `CMFCColorMenuButton` sınıfı. Örnekte, bir `CPalette` nesne ilk oluşturulduğunda ve ardından bir nesne oluşturmak için kullanılan `CMFCColorMenuButton` sınıfı. `CMFCColorMenuButton` Nesne ardından yapılandırılmış, otomatik ve diğer düğmeleri etkinleştirme ve rengini ve sütun sayısını ayarlama. Bu kod parçası olan [Word paneli örnek](../../visual-cpp-samples.md).

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[CMFCToolBarMenuButton](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[CMFCColorMenuButton](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcolormenubutton.h

##  <a name="cmfccolormenubutton"></a>  CMFCColorMenuButton::CMFCColorMenuButton

Oluşturur bir `CMFCColorMenuButton` nesne.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Bir düğme komut kimliği.

*lpszText*<br/>
[in] Düğme metni.

*pPalette*<br/>
[in] Düğmenin renk paletini işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan oluşturucudur. Nesnenin geçerli ve otomatik rengi siyah (RGB (0, 0, 0))'olarak başlatılır.

İkinci Oluşturucu, belirtilen komut kimliğine karşılık gelen renk düğmeyi başlatır

##  <a name="copyfrom"></a>  CMFCColorMenuButton::CopyFrom

Bir kopyalar [CMFCToolBarMenuButton sınıfı](../../mfc/reference/cmfctoolbarmenubutton-class.md)-başka bir nesne türetilmiş.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
[in] Kopyalanacak kaynak düğmesi.

### <a name="remarks"></a>Açıklamalar

Öğesinden türetilen kopyalama nesneler bu yöntemi geçersiz kılın `CMFCColorMenuButton` nesne.

##  <a name="createpopupmenu"></a>  CMFCColorMenuButton::CreatePopupMenu

Bir Renk Seçici iletişim kutusu oluşturur.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Bir Renk Seçici iletişim kutusunu temsil eden bir nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, kullanıcı renk menü düğmesine bastığında çerçevesi tarafından çağrılır.

##  <a name="enableautomaticbutton"></a>  CMFCColorMenuButton::EnableAutomaticButton

Sağlar ve normal renk düğmeleri konumlandırılmış bir "Otomatik" düğmesini devre dışı bırakır. (Standart sistem otomatik düğme **otomatik**.)

```
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Düğme otomatik hale geldiğinde görüntülenen düğme metnini belirtir.

*colorAutomatic*<br/>
[in] Yeni bir otomatik rengini belirtir.

*bSistemlerde*<br/>
[in] Düğme otomatik olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Otomatik düğmenin geçerli varsayılan rengi uygular.

##  <a name="enabledocumentcolors"></a>  CMFCColorMenuButton::EnableDocumentColors

Sistem renkleri yerine belgeye özgü renkleri görüntülenmesini sağlar.

```
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Düğme metnini belirtir.

*bSistemlerde*<br/>
[in] Belgeye özgü renkleri ya da sistem renkleri görüntülemek için yanlış görüntülemek için TRUE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir renk menü düğmesine tıkladığında, geçerli belge renkleri veya sistem palet renkleri görüntülemek için bu yöntemi kullanın.

##  <a name="enableotherbutton"></a>  CMFCColorMenuButton::EnableOtherButton

Sağlar ve normal renk düğmelerin altında konumlandırılmış bir "diğer" düğmesini devre dışı bırakır. ("Diğer" düğmesi olarak etiketlenmiş standart sistem **daha fazla renk**.)

```
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
[in] Düğme metnini belirtir.

*bAltColorDlg*<br/>
[in] Görüntülemek için TRUE belirtin `CMFCColorDialog` iletişim kutusu ya da standart sistem renk iletişim kutusu görüntülemek için FALSE.

*bSistemlerde*<br/>
[in] "Diğer" bir düğme görüntülemek için TRUE; belirtin. Aksi takdirde FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

##  <a name="enabletearoff"></a>  CMFCColorMenuButton::EnableTearOff

Bir renk bölmesi ayırma olanağı sağlar.

```
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Parametreler

*uiID*<br/>
[in] Bölünmüş bölmesinde Kimliğini belirtir.

*nVertDockColumns*<br/>
[in] Bölünmüş durumundayken dikey yerleşik renk bölmesinde sütun sayısını belirtir.

*nHorzDockRows*<br/>
[in] Yatay olarak yerleşik renk bölmesi etkinleştiriliyorken durumundayken için satır sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Zaman POP renk bölmesi için "etkinleştiriliyorken" özelliğini etkinleştirmek için bu yöntemi çağırın `CMFCColorMenuButton` düğmesine basıldığında.

##  <a name="getautomaticcolor"></a>  CMFCColorMenuButton::GetAutomaticColor

Geçerli otomatik rengini alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik rengi temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

Ayarlama tarafından otomatik renk elde etmek için bu yöntemi çağırın [CMFCColorMenuButton::EnableAutomaticButton](#enableautomaticbutton).

##  <a name="getcolor"></a>  CMFCColorMenuButton::GetColor

Geçerli düğmenin rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme rengi.

### <a name="remarks"></a>Açıklamalar

##  <a name="getcolorbycmdid"></a>  CMFCColorMenuButton::GetColorByCmdID

Belirtilen komut kimliğine karşılık gelen rengi alır.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Komut kimliği.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut kimliğine karşılık gelen rengi

### <a name="remarks"></a>Açıklamalar

Bir uygulamada birkaç renk düğmesi varsa, bu yöntemi kullanın. Kullanıcı bir renk düğmesine tıkladığında, düğmeyi komut Kimliğini kendi üst öğesine WM_COMMAND ileti gönderir. `GetColorByCmdID` Yöntemi, karşılık gelen renk almak için komut Kimliğini kullanır.

##  <a name="isemptymenuallowed"></a>  CMFCColorMenuButton::IsEmptyMenuAllowed

Boş Menü desteklenip desteklenmediğini gösterir.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş ise sıfır olmayan menüleri izin verilir; Aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Boş menü, varsayılan olarak desteklenir. Türetilmiş sınıf içinde bu davranışı değiştirmek için bu yöntemi yok sayın.

##  <a name="onchangeparentwnd"></a>  CMFCColorMenuButton::OnChangeParentWnd

Ana pencereyi değiştiğinde framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
[in] Yeni üst penceresine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondraw"></a>  CMFCColorMenuButton::OnDraw

Görüntü üzerindeki bir düğme görüntülemek için framework tarafından çağırılır.

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

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Alan çizilmesini sınırların bir dikdörtgen.

*pImages*<br/>
[in] Araç çubuğu görüntülerinin listesine yönlendirir.

*bHorz*<br/>
[in] Araç bir yatay takılı durumda olduğunu belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

*bCustomizeMode*<br/>
[in] Uygulamayı özelleştirme modunda olduğunu belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer false'tur.

*bHighlight*<br/>
[in] Düğme vurgulanana belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer false'tur.

*bDrawBorder*<br/>
[in] Düğmenin kenarlık görüntüleneceğini belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

*bGrayDisabledButtons*<br/>
[in] Çıkış devre dışı düğme gri (devre dışı) olduğunu belirtmek için TRUE; Aksi takdirde FALSE. Varsayılan değer True'dur.

### <a name="remarks"></a>Açıklamalar

##  <a name="ondrawoncustomizelist"></a>  CMFCColorMenuButton::OnDrawOnCustomizeList

Önce framework tarafından çağırılır bir `CMFCColorMenuButton` nesnesi, bir araç çubuğu özelleştirme iletişim kutusunda listede görüntülenir.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*pDC*<br/>
[in] Bir cihaz bağlamı için bir işaretçi.

*Rect*<br/>
[in] Çizilecek düğme sınırların bir dikdörtgen.

*bSelected*<br/>
[in] TRUE, düğme seçili durumda olduğunu belirtir. Aksi takdirde FALSE.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

Bu yöntem çerçeve tarafından çağrılır, bir `CMFCColorMenuButton` araç çubuğu özelleştirme işlemi sırasında nesne liste kutusunda görüntülenir.

##  <a name="opencolordialog"></a>  CMFCColorMenuButton::OpenColorDialog

Bir renk seçimi iletişim kutusunu açar.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametreler

*colorDefault*<br/>
[in] Renk iletişim kutusunda seçili varsayılan rengi.

*colorRes*<br/>
[out] Renk iletişim kutusundan kullanıcının seçtiği bir renk döndürür.

### <a name="return-value"></a>Dönüş Değeri

Yeni bir renk kullanıcının seçtiği olursa sıfır dışı; Aksi takdirde sıfır.

### <a name="remarks"></a>Açıklamalar

Menü düğmesine tıklandığında, bir renk iletişim kutusu açmak için bu yöntemi çağırın. Dönüş değeri sıfır değilse, kullanıcının seçtiği bir renk depolanan *colorRes* parametresi. Kullanım [CMFCColorMenuButton::EnableOtherButton](#enableotherbutton) standart renk iletişim kutusu arasında geçiş yapmak için gereken yöntemini ve [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu.

##  <a name="setcolor"></a>  CMFCColorMenuButton::SetColor

Geçerli renk düğmesi rengini ayarlar.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Parametreler

*CLR*<br/>
[in] Bir RGB renk değeri.

*bNotify*<br/>
[in] DOĞRU uygulamak için *clr* parametresi renge herhangi ilişkili menü veya araç çubuğu düğmesini; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Geçerli renk düğmesi rengini değiştirmek için bu yöntemi çağırın. Varsa *bNotify* parametresi, sıfır olmayan, herhangi bir ilişkili açılan menü veya araç karşılık gelen bir düğme rengi tarafından belirtilen renk değiştirilecek *clr* parametresi.

##  <a name="setcolorbycmdid"></a>  CMFCColorMenuButton::SetColorByCmdID

Belirtilen renk menü düğmesi rengini ayarlar.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Parametreler

*uiCmdID*<br/>
[in] Renk menü düğmesi kaynak kimliği.

*Renk*<br/>
[in] Bir RGB renk değeri.

##  <a name="setcolorname"></a>  CMFCColorMenuButton::SetColorName

Belirtilen "rengin" yeni adını ayarlar.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
[in] Adı değişiklikleri renk RGB değeri.

*strName*<br/>
[in] Renk yeni adı.

### <a name="remarks"></a>Açıklamalar

##  <a name="setcolumnsnumber"></a>  CMFCColorMenuButton::SetColumnsNumber

Bir renk seçimi denetiminde görüntülenecek sütun sayısını ayarlar ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) nesne).

```
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nColumns*<br/>
[in] Görüntülenecek sütun sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar Sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar Sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog Sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton Sınıfı](../../mfc/reference/cmfccolorbutton-class.md)
