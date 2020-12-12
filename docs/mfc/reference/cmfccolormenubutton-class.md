---
description: 'Daha fazla bilgi edinin: Cmfccolormenubtan sınıfı'
title: Cmfccolormenubtan sınıfı
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
ms.openlocfilehash: 4ba0934e872adc4e4b33c2ae5700ecb0fc46e6d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327670"
---
# <a name="cmfccolormenubutton-class"></a>Cmfccolormenubtan sınıfı

Sınıfı, bir `CMFCColorMenuButton` menü komutunu veya Renk Seçici iletişim kutusu Başlatan bir araç çubuğu düğmesini destekler.

## <a name="syntax"></a>Syntax

```
class CMFCColorMenuButton : public CMFCToolBarMenuButton
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cmfccolormenubtan:: Cmfccolormenubtan](#cmfccolormenubutton)|Bir `CMFCColorMenuButton` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfccolormenubtan:: EnableAutomaticButton](#enableautomaticbutton)|Normal renk düğmelerinin üzerine yerleştirilmiş bir "otomatik" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem otomatik düğmesi **Otomatik** olarak etiketlenir.)|
|[Cmfccolormenubtan:: EnableDocumentColors](#enabledocumentcolors)|Sistem renkleri yerine belgeye özgü renklerin görüntülenmesini mümkün bir şekilde sunar.|
|[Cmfccolormenubtan:: EnableOtherButton](#enableotherbutton)|Normal renk düğmelerinin altına yerleştirilmiş bir "diğer" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem "diğer" düğmesi **daha fazla renk** etiketlidir.)|
|[Cmfccolormenubtan:: EnableTearOff](#enabletearoff)|Renk bölmesini koparma olanağı sağlar.|
|[Cmfccolormenubtan:: GetAutomaticColor](#getautomaticcolor)|Geçerli otomatik rengi alır.|
|[Cmfccolormenubtan:: GetColor](#getcolor)|Geçerli düğmenin rengini alır.|
|[Cmfccolormenubtan:: GetColorByCmdID](#getcolorbycmdid)|Belirtilen bir komut KIMLIĞINE karşılık gelen rengi alır.|
|[Cmfccolormenubtan:: OnChangeParentWnd](#onchangeparentwnd)|Ana pencere değiştiğinde Framework tarafından çağırılır.|
|[Cmfccolormenubtan:: OpenColorDialog](#opencolordialog)|Renk seçimi iletişim kutusunu açar.|
|[Cmfccolormenubtan:: SetColor](#setcolor)|Geçerli renk düğmesinin rengini ayarlar.|
|[Cmfccolormenubtan:: Setcolorbycmdıd](#setcolorbycmdid)|Belirtilen renk menü düğmesinin rengini ayarlar.|
|[Cmfccolormenubtan:: SetColorName](#setcolorname)|Belirtilen renk için yeni bir ad ayarlar.|
|[Cmfccolormenubtan:: SetColumns numarası](#setcolumnsnumber)|Bir nesne tarafından görüntülenen sütun sayısını ayarlar `CMFCColorBar` .|

### <a name="protected-methods"></a>Korumalı Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cmfccolormenubtan:: CopyFrom](#copyfrom)|Başka bir araç çubuğu düğmesini geçerli düğmeye kopyalar.|
|[Cmfccolormenubtan:: CreatePopupMenu](#createpopupmenu)|Renk Seçici iletişim kutusu oluşturur.|
|[Cmfccolormenubtan:: IsEmptyMenuAllowed](#isemptymenuallowed)|Boş menülerin desteklenip desteklenmediğini gösterir.|
|[Cmfccolormenubtan:: OnDraw](#ondraw)|Bir düğmeye bir resim göstermek için Framework tarafından çağırılır.|
|[Cmfccolormenubtan:: OnDrawOnCustomizeList](#ondrawoncustomizelist)|Bir `CMFCColorMenuButton` araç çubuğu özelleştirmesi iletişim kutusu listesinde bir nesne görüntülenmeden önce Framework tarafından çağırılır.|

## <a name="remarks"></a>Açıklamalar

Orijinal menü komutunu veya araç çubuğu düğmesini bir nesneyle değiştirmek için `CMFCColorMenuButton` , `CMFCColorMenuButton` nesneyi oluşturun, uygun [CMFCColorBar sınıf](../../mfc/reference/cmfccolorbar-class.md) stillerini ayarlayın ve ardından `ReplaceButton` [CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md) sınıfının yöntemini çağırın. Bir araç çubuğunu özelleştirirseniz, [CMFCToolBarsCustomizeDialog:: ReplaceButton](../../mfc/reference/cmfctoolbarscustomizedialog-class.md#replacebutton) yöntemini çağırın.

Renk Seçici iletişim kutusu, [Cmfccolormenubtan:: CreatePopupMenu](#createpopupmenu) olay işleyicisinin işlenmesi sırasında oluşturulur. Olay işleyicisi ana çerçeveye bir WM_COMMAND iletisiyle bildirir. `CMFCColorMenuButton`Nesnesi, orijinal menü komutuna veya araç çubuğu düğmesine atanan DENETIM kimliğini gönderir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, sınıfındaki çeşitli yöntemler kullanılarak renk menü düğmesi oluşturmayı ve yapılandırmayı gösterir `CMFCColorMenuButton` . Örnekte, `CPalette` önce bir nesne oluşturulur ve ardından sınıfın bir nesnesini oluşturmak için kullanılır `CMFCColorMenuButton` . `CMFCColorMenuButton`Daha sonra nesnesi otomatik ve diğer düğmelerini etkinleştirerek ve rengini ve sütun sayısını ayarlayarak yapılandırılır. Bu kod, [sözcük paneli örneğinin](../../overview/visual-cpp-samples.md)bir parçasıdır.

[!code-cpp[NVC_MFC_WordPad#5](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_1.h)]
[!code-cpp[NVC_MFC_WordPad#6](../../mfc/reference/codesnippet/cpp/cmfccolormenubutton-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)

[Cmfctoolbarmenubtan](../../mfc/reference/cmfctoolbarmenubutton-class.md)

[Cmfccolormenubtan](../../mfc/reference/cmfccolormenubutton-class.md)

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcolormenubtan. h

## <a name="cmfccolormenubuttoncmfccolormenubutton"></a><a name="cmfccolormenubutton"></a> Cmfccolormenubtan:: Cmfccolormenubtan

Bir `CMFCColorMenuButton` nesnesi oluşturur.

```
CMFCColorMenuButton();

CMFCColorMenuButton(
    UINT uiCmdID,
    LPCTSTR lpszText,
    CPalette* pPalette=NULL);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Düğme komut KIMLIĞI.

*lpszText*<br/>
'ndaki Düğme metni.

*pPalette*<br/>
'ndaki Düğmenin renk paleti için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu varsayılan oluşturucudur. Nesnenin geçerli rengi ve otomatik rengi siyahla başlatılır (RGB (0, 0, 0)).

İkinci Oluşturucu, düğmeyi belirtilen komut KIMLIĞINE karşılık gelen renge başlatır.

## <a name="cmfccolormenubuttoncopyfrom"></a><a name="copyfrom"></a> Cmfccolormenubtan:: CopyFrom

Bir [Cmfctoolbarmenubtan Class](../../mfc/reference/cmfctoolbarmenubutton-class.md)ile türetilmiş nesneyi diğerine kopyalar.

```
virtual void CopyFrom(const CMFCToolBarButton& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
'ndaki Kopyalanacak kaynak düğmesi.

### <a name="remarks"></a>Açıklamalar

Nesnesinden türetilmiş nesneleri kopyalamak için bu yöntemi geçersiz kılın `CMFCColorMenuButton` .

## <a name="cmfccolormenubuttoncreatepopupmenu"></a><a name="createpopupmenu"></a> Cmfccolormenubtan:: CreatePopupMenu

Renk Seçici iletişim kutusu oluşturur.

```
virtual CMFCPopupMenu* CreatePopupMenu();
```

### <a name="return-value"></a>Dönüş Değeri

Renk Seçici iletişim kutusunu temsil eden nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Kullanıcı bir renk menü düğmesine bastığında Framework tarafından çağrılır.

## <a name="cmfccolormenubuttonenableautomaticbutton"></a><a name="enableautomaticbutton"></a> Cmfccolormenubtan:: EnableAutomaticButton

Normal renk düğmelerinin üzerine yerleştirilmiş bir "otomatik" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem otomatik düğmesi **Otomatik** olarak etiketlenir.)

```cpp
void EnableAutomaticButton(
    LPCTSTR lpszLabel,
    COLORREF colorAutomatic,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Düğme otomatik hale geldiğinde görüntülenen düğme metnini belirtir.

*colorAutomatic*<br/>
'ndaki Yeni bir otomatik renk belirtir.

*bEnable*<br/>
'ndaki Düğmenin otomatik olup olmadığını belirtir.

### <a name="remarks"></a>Açıklamalar

Otomatik düğme geçerli varsayılan rengi uygular.

## <a name="cmfccolormenubuttonenabledocumentcolors"></a><a name="enabledocumentcolors"></a> Cmfccolormenubtan:: EnableDocumentColors

Sistem renkleri yerine belgeye özgü renklerin görüntülenmesini mümkün bir şekilde sunar.

```cpp
void EnableDocumentColors(
    LPCTSTR lpszLabel,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Düğme metnini belirtir.

*bEnable*<br/>
'ndaki Belgeye özgü renkleri göstermek için TRUE, sistem renklerini göstermek için FALSE.

### <a name="remarks"></a>Açıklamalar

Kullanıcı bir renk menü düğmesine tıkladığında geçerli belge renklerini veya sistem paleti renklerini göstermek için bu yöntemi kullanın.

## <a name="cmfccolormenubuttonenableotherbutton"></a><a name="enableotherbutton"></a> Cmfccolormenubtan:: EnableOtherButton

Normal renk düğmelerinin altına yerleştirilmiş bir "diğer" düğmesini etkinleştirip devre dışı bırakır. (Standart sistem "diğer" düğmesi **daha fazla renk** etiketlidir.)

```cpp
void EnableOtherButton(
    LPCTSTR lpszLabel,
    BOOL bAltColorDlg=TRUE,
    BOOL bEnable=TRUE);
```

### <a name="parameters"></a>Parametreler

*lpszLabel*<br/>
'ndaki Düğme metnini belirtir.

*bAltColorDlg*<br/>
'ndaki İletişim kutusunu göstermek için TRUE `CMFCColorDialog` , standart sistem rengi iletişim kutusunu göstermek IÇIN FALSE değerini belirtin.

*bEnable*<br/>
'ndaki "Diğer" düğmesini göstermek için TRUE değerini belirtin; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonenabletearoff"></a><a name="enabletearoff"></a> Cmfccolormenubtan:: EnableTearOff

Renk bölmesini koparma olanağı sağlar.

```cpp
void EnableTearOff(
    UINT uiID,
    int nVertDockColumns=-1,
    int nHorzDockRows=-1);
```

### <a name="parameters"></a>Parametreler

*Uııd*<br/>
'ndaki Yırma bölmesinin KIMLIĞINI belirtir.

*nVertDockColumns*<br/>
'ndaki Koparma durumundayken dikey olarak sabitlenmiş renk bölmesindeki sütun sayısını belirtir.

*nHorzDockRows*<br/>
'ndaki Koparma durumundayken yatay olarak sabitlenmiş renk bölmesi için satır sayısını belirtir.

### <a name="remarks"></a>Açıklamalar

Düğmeye basıldığında açılan renk bölmesi için "Tear" özelliğini etkinleştirmek için bu yöntemi çağırın `CMFCColorMenuButton` .

## <a name="cmfccolormenubuttongetautomaticcolor"></a><a name="getautomaticcolor"></a> Cmfccolormenubtan:: GetAutomaticColor

Geçerli otomatik rengi alır.

```
COLORREF GetAutomaticColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli otomatik rengi temsil eden bir RGB renk değeri.

### <a name="remarks"></a>Açıklamalar

[Cmfccolormenubtan:: EnableAutomaticButton](#enableautomaticbutton)tarafından ayarlanan otomatik rengi elde etmek için bu yöntemi çağırın.

## <a name="cmfccolormenubuttongetcolor"></a><a name="getcolor"></a> Cmfccolormenubtan:: GetColor

Geçerli düğmenin rengini alır.

```
COLORREF GetColor() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğmenin rengi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttongetcolorbycmdid"></a><a name="getcolorbycmdid"></a> Cmfccolormenubtan:: GetColorByCmdID

Belirtilen bir komut KIMLIĞINE karşılık gelen rengi alır.

```
static COLORREF GetColorByCmdID(UINT uiCmdID);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Bir komut KIMLIĞI.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen komut KIMLIĞINE karşılık gelen renk.

### <a name="remarks"></a>Açıklamalar

Bir uygulamada birkaç renk düğmesi olduğunda bu yöntemi kullanın. Kullanıcı bir renk düğmesine tıkladığında, düğme kendi komut KIMLIĞINI bir WM_COMMAND iletisinde üst öğesine gönderir. `GetColorByCmdID`Yöntemi, karşılık gelen rengi almak için komut kimliğini kullanır.

## <a name="cmfccolormenubuttonisemptymenuallowed"></a><a name="isemptymenuallowed"></a> Cmfccolormenubtan:: IsEmptyMenuAllowed

Boş menülerin desteklenip desteklenmediğini gösterir.

```
virtual BOOL IsEmptyMenuAllowed() const;
```

### <a name="return-value"></a>Dönüş Değeri

Boş menülere izin veriliyorsa sıfır dışı; Aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Boş menüler varsayılan olarak desteklenir. Türetilmiş sınıftaki bu davranışı değiştirmek için bu yöntemi geçersiz kılın.

## <a name="cmfccolormenubuttononchangeparentwnd"></a><a name="onchangeparentwnd"></a> Cmfccolormenubtan:: OnChangeParentWnd

Ana pencere değiştiğinde Framework tarafından çağırılır.

```
virtual void OnChangeParentWnd(CWnd* pWndParent);
```

### <a name="parameters"></a>Parametreler

*pWndParent*<br/>
'ndaki Yeni ana pencereye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonondraw"></a><a name="ondraw"></a> Cmfccolormenubtan:: OnDraw

Bir düğmeye bir resim göstermek için Framework tarafından çağırılır.

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

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Yeniden çizilebilir alanı alan bir dikdörtgen.

*Pımages*<br/>
'ndaki Araç çubuğu görüntülerinin listesini gösterir.

*bHorz*<br/>
'ndaki Araç çubuğunun yatay yerleştirilmiş durumda olduğunu belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

*bCustomizeMode*<br/>
'ndaki Uygulamanın özelleştirme modunda olduğunu belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

*bHighlight*<br/>
'ndaki Düğmenin vurgulanmasını belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer FALSE 'dur.

*bDrawBorder*<br/>
'ndaki Düğme kenarlığının görüntülendiğini belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

*Bgride Disabledbutton*<br/>
'ndaki Devre dışı bırakılan düğmelerin gri (soluk) olduğunu belirtmek için TRUE; Aksi takdirde, FALSE. Varsayılan değer TRUE 'dur.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonondrawoncustomizelist"></a><a name="ondrawoncustomizelist"></a> Cmfccolormenubtan:: OnDrawOnCustomizeList

Bir `CMFCColorMenuButton` araç çubuğu özelleştirmesi iletişim kutusu listesinde bir nesne görüntülenmeden önce Framework tarafından çağırılır.

```
virtual int OnDrawOnCustomizeList(
    CDC* pDC,
    const CRect& rect,
    BOOL bSelected);
```

### <a name="parameters"></a>Parametreler

*Kökündeki*<br/>
'ndaki Cihaz bağlamına yönelik bir işaretçi.

*Rect*<br/>
'ndaki Çizilecek düğmeyi sınıralan dikdörtgen.

*bSelected*<br/>
'ndaki TRUE, düğmenin seçili durumda olduğunu belirtir; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Düğmenin genişliği.

### <a name="remarks"></a>Açıklamalar

`CMFCColorMenuButton`Araç çubuğu özelleştirme işlemi sırasında liste kutusunda bir nesne görüntülendiğinde, bu yöntem Framework tarafından çağırılır.

## <a name="cmfccolormenubuttonopencolordialog"></a><a name="opencolordialog"></a> Cmfccolormenubtan:: OpenColorDialog

Renk seçimi iletişim kutusunu açar.

```
virtual BOOL OpenColorDialog(
    const COLORREF colorDefault,
    COLORREF& colorRes);
```

### <a name="parameters"></a>Parametreler

*colorDefault*<br/>
'ndaki Renk iletişim kutusunda seçilen varsayılan renk.

*colorRes*<br/>
dışı Kullanıcının renk iletişim kutusundan seçtiği rengi döndürür.

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı yeni bir renk seçerse sıfır dışı; Aksi takdirde, sıfır.

### <a name="remarks"></a>Açıklamalar

Menü düğmesine tıklandığında, bir renk iletişim kutusu açmak için bu yöntemi çağırın. Dönüş değeri sıfır değilse, kullanıcının seçtiği renk *colorRes* parametresinde saklanır. Standart renk iletişim kutusu ve [CMFCColorDialog sınıfı](../../mfc/reference/cmfccolordialog-class.md) iletişim kutusu arasında geçiş yapmak Için [Cmfccolormenubtan:: EnableOtherButton](#enableotherbutton) metodunu kullanın.

## <a name="cmfccolormenubuttonsetcolor"></a><a name="setcolor"></a> Cmfccolormenubtan:: SetColor

Geçerli renk düğmesinin rengini ayarlar.

```
virtual void SetColor(
    COLORREF clr,
    BOOL bNotify=TRUE);
```

### <a name="parameters"></a>Parametreler

*clr*<br/>
'ndaki Bir RGB renk değeri.

*bNotify*<br/>
'ndaki Herhangi bir ilişkili menü düğmesine veya araç çubuğu düğmesine *clr* parametre rengini uygulamak için true; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Geçerli renk düğmesinin rengini değiştirmek için bu yöntemi çağırın. *BNotify* parametresi sıfır değilse, ilişkili herhangi bir açılan menü veya araç çubuğundaki karşılık gelen düğmenin rengi *clr* parametresi tarafından belirtilen renkle değiştirilir.

## <a name="cmfccolormenubuttonsetcolorbycmdid"></a><a name="setcolorbycmdid"></a> Cmfccolormenubtan:: Setcolorbycmdıd

Belirtilen renk menü düğmesinin rengini ayarlar.

```
static void SetColorByCmdID(
    UINT uiCmdID,
    COLORREF color);
```

### <a name="parameters"></a>Parametreler

*Uıımıdıd*<br/>
'ndaki Renk menü düğmesinin kaynak KIMLIĞI.

*Renk*<br/>
'ndaki Bir RGB renk değeri.

## <a name="cmfccolormenubuttonsetcolorname"></a><a name="setcolorname"></a> Cmfccolormenubtan:: SetColorName

Belirtilen renk için yeni bir ad ayarlar.

```
static void SetColorName(
    COLORREF color,
    const CString& strName);
```

### <a name="parameters"></a>Parametreler

*Renk*<br/>
'ndaki Adı değişiklik olan rengin RGB değeri.

*strName*<br/>
'ndaki Rengin yeni adı.

### <a name="remarks"></a>Açıklamalar

## <a name="cmfccolormenubuttonsetcolumnsnumber"></a><a name="setcolumnsnumber"></a> Cmfccolormenubtan:: SetColumns numarası

Renk seçim denetiminde görüntülenecek sütun sayısını ayarlar ( [CMFCColorBar](../../mfc/reference/cmfccolorbar-class.md) nesnesi).

```cpp
void SetColumnsNumber(int nColumns);
```

### <a name="parameters"></a>Parametreler

*nColumns*<br/>
'ndaki Görüntülenecek sütun sayısı.

### <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[Sınıflar](../../mfc/reference/mfc-classes.md)<br/>
[CMFCColorBar sınıfı](../../mfc/reference/cmfccolorbar-class.md)<br/>
[CMFCToolBar sınıfı](../../mfc/reference/cmfctoolbar-class.md)<br/>
[CMFCToolBarsCustomizeDialog sınıfı](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)<br/>
[CMFCColorButton sınıfı](../../mfc/reference/cmfccolorbutton-class.md)
