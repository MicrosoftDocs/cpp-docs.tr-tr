---
description: 'Daha fazla bilgi edinin: CButton sınıfı'
title: CButton sınıfı
ms.date: 11/04/2016
f1_keywords:
- CButton
- AFXWIN/CButton
- AFXWIN/CButton::CButton
- AFXWIN/CButton::Create
- AFXWIN/CButton::DrawItem
- AFXWIN/CButton::GetBitmap
- AFXWIN/CButton::GetButtonStyle
- AFXWIN/CButton::GetCheck
- AFXWIN/CButton::GetCursor
- AFXWIN/CButton::GetIcon
- AFXWIN/CButton::GetIdealSize
- AFXWIN/CButton::GetImageList
- AFXWIN/CButton::GetNote
- AFXWIN/CButton::GetNoteLength
- AFXWIN/CButton::GetSplitGlyph
- AFXWIN/CButton::GetSplitImageList
- AFXWIN/CButton::GetSplitInfo
- AFXWIN/CButton::GetSplitSize
- AFXWIN/CButton::GetSplitStyle
- AFXWIN/CButton::GetState
- AFXWIN/CButton::GetTextMargin
- AFXWIN/CButton::SetBitmap
- AFXWIN/CButton::SetButtonStyle
- AFXWIN/CButton::SetCheck
- AFXWIN/CButton::SetCursor
- AFXWIN/CButton::SetDropDownState
- AFXWIN/CButton::SetIcon
- AFXWIN/CButton::SetImageList
- AFXWIN/CButton::SetNote
- AFXWIN/CButton::SetSplitGlyph
- AFXWIN/CButton::SetSplitImageList
- AFXWIN/CButton::SetSplitInfo
- AFXWIN/CButton::SetSplitSize
- AFXWIN/CButton::SetSplitStyle
- AFXWIN/CButton::SetState
- AFXWIN/CButton::SetTextMargin
helpviewer_keywords:
- CButton [MFC], CButton
- CButton [MFC], Create
- CButton [MFC], DrawItem
- CButton [MFC], GetBitmap
- CButton [MFC], GetButtonStyle
- CButton [MFC], GetCheck
- CButton [MFC], GetCursor
- CButton [MFC], GetIcon
- CButton [MFC], GetIdealSize
- CButton [MFC], GetImageList
- CButton [MFC], GetNote
- CButton [MFC], GetNoteLength
- CButton [MFC], GetSplitGlyph
- CButton [MFC], GetSplitImageList
- CButton [MFC], GetSplitInfo
- CButton [MFC], GetSplitSize
- CButton [MFC], GetSplitStyle
- CButton [MFC], GetState
- CButton [MFC], GetTextMargin
- CButton [MFC], SetBitmap
- CButton [MFC], SetButtonStyle
- CButton [MFC], SetCheck
- CButton [MFC], SetCursor
- CButton [MFC], SetDropDownState
- CButton [MFC], SetIcon
- CButton [MFC], SetImageList
- CButton [MFC], SetNote
- CButton [MFC], SetSplitGlyph
- CButton [MFC], SetSplitImageList
- CButton [MFC], SetSplitInfo
- CButton [MFC], SetSplitSize
- CButton [MFC], SetSplitStyle
- CButton [MFC], SetState
- CButton [MFC], SetTextMargin
ms.assetid: cdc76d5b-31da-43c5-bc43-fde4cb39de5b
ms.openlocfilehash: af7b9bec8298942bcb414e83be24257dd62652cb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122583"
---
# <a name="cbutton-class"></a>CButton sınıfı

Windows düğme denetimlerinin işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CButton : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CButton:: CButton](#cbutton)|Bir `CButton` nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CButton:: Create](#create)|Windows düğme denetimini oluşturur ve `CButton` nesneye ekler.|
|[CButton::D rawItem](#drawitem)|Sahip tarafından çizilmiş bir nesneyi çizmek için geçersiz kılın `CButton` .|
|[CButton:: GetBitmap](#getbitmap)|Daha önce [SetBitmap](#setbitmap)ile ayarlanan bit eşlemin tanıtıcısını alır.|
|[CButton:: GetButtonStyle](#getbuttonstyle)|Düğme Denetim stiliyle ilgili bilgileri alır.|
|[CButton:: GetCheck](#getcheck)|Düğme denetiminin denetim durumunu alır.|
|[CButton:: GetCursor](#getcursor)|Daha önce [SetCursor](#setcursor)ile ayarlanmış imleç resminin tanıtıcısını alır.|
|[CButton:: GetIcon](#geticon)|Daha önce [setIcon](#seticon)ile ayarlanan simgenin tanıtıcısını alır.|
|[CButton:: Getısatıcıboyutu](#getidealsize)|Düğme denetiminin ideal boyutunu alır.|
|[CButton:: GetImageList](#getimagelist)|Düğme denetiminin görüntü listesini alır.|
|[CButton:: GetNote](#getnote)|Geçerli komut bağlantı denetiminin Note bileşenini alır.|
|[CButton:: GetNoteLength](#getnotelength)|Geçerli komut bağlantı denetimi için dekont metninin uzunluğunu alır.|
|[CButton:: GetSplitGlyph](#getsplitglyph)|Geçerli bölme düğmesi denetimiyle ilişkili glifi alır.|
|[CButton:: Getsptımagelist](#getsplitimagelist)|Geçerli bölünmüş düğme denetiminin görüntü listesini alır.|
|[CButton:: Getsplitınfo](#getsplitinfo)|Geçerli bölünmüş düğme denetimini tanımlayan bilgileri alır.|
|[CButton:: GetSplitSize](#getsplitsize)|Geçerli bölünmüş düğme denetiminin aşağı açılan bileşeninin sınırlayıcı dikdörtgenini alır.|
|[CButton:: GetSplitStyle](#getsplitstyle)|Geçerli bölme düğmesi denetimini tanımlayan bölünmüş düğme stillerini alır.|
|[CButton:: GetState](#getstate)|Denetim durumunu, vurgu durumunu ve bir düğme denetiminin odak durumunu alır.|
|[CButton:: GetTextMargin](#gettextmargin)|Düğme denetiminin metin kenar boşluğunu alır.|
|[CButton:: SetBitmap](#setbitmap)|Düğme üzerinde görüntülenecek bir bit eşlem belirtir.|
|[CButton:: SetButtonStyle](#setbuttonstyle)|Bir düğmenin stilini değiştirir.|
|[CButton:: SetCheck](#setcheck)|Düğme denetiminin denetim durumunu ayarlar.|
|[CButton:: SetCursor](#setcursor)|Düğmede görüntülenecek bir imleç resmi belirtir.|
|[CButton:: SetDropDownState](#setdropdownstate)|Geçerli bölünmüş düğme denetiminin açılan durumunu ayarlar.|
|[CButton:: SetIcon](#seticon)|Düğme üzerinde görüntülenecek bir simge belirtir.|
|[CButton:: SetImageList](#setimagelist)|Düğme denetiminin görüntü listesini ayarlar.|
|[CButton:: SetNote](#setnote)|Geçerli komut bağlantı denetimindeki notnu ayarlar.|
|[CButton:: SetSplitGlyph](#setsplitglyph)|Belirtilen glifi geçerli bölme düğmesi denetimiyle ilişkilendirir.|
|[CButton:: Setsptımagelist](#setsplitimagelist)|Bir görüntü listesini geçerli bölünmüş düğme denetimiyle ilişkilendirir.|
|[CButton:: Setsplitınfo](#setsplitinfo)|Geçerli bölünmüş düğme denetimini tanımlayan bilgileri belirtir.|
|[CButton:: SetSplitSize](#setsplitsize)|Geçerli bölünmüş düğme denetiminin aşağı açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.|
|[CButton:: SetSplitStyle](#setsplitstyle)|Geçerli bölünmüş düğme denetiminin stilini ayarlar.|
|[CButton:: SetState](#setstate)|Düğme denetiminin vurgulama durumunu ayarlar.|
|[CButton:: SetTextMargin](#settextmargin)|Düğme denetiminin metin kenar boşluğunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Düğme denetimi, tıklanan ve kapatılagösteren küçük, dikdörtgen bir alt penceredir. Düğmeler tek başına veya gruplar halinde kullanılabilir ve metin olmadan etiketlenebilir ya da görünebilir. Düğme genellikle Kullanıcı tıkladığı zaman görünümü değiştirir.

Tipik düğmeler onay kutusu, radyo düğmesi ve basma düğmeli. Bir `CButton` nesne, [Create](#create) member işlevi tarafından başlatılırken belirtilen [düğme stiline](../../mfc/reference/styles-used-by-mfc.md#button-styles) göre bunlardan herhangi biri olabilir.

Ayrıca, ' den türetilen [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) sınıfı, `CButton` metin yerine bit eşlem görüntülerle etiketlenmiş düğme denetimlerinin oluşturulmasını destekler. Bir `CBitmapButton` düğmenin yukarı, aşağı, odaklanmış ve devre dışı durumları için ayrı bit eşlemlere sahip olabilir.

Bir iletişim kutusu şablonundan ya da doğrudan kodunuzda bir düğme denetimi oluşturabilirsiniz. Her iki durumda da, önce `CButton` nesneyi oluşturmak için oluşturucuyu çağırın `CButton` ; ardından `Create` Windows düğme denetimini oluşturmak ve nesneye iliştirmek için üye işlevini çağırın `CButton` .

Oluşturma, öğesinden türetilmiş bir sınıfta tek adımlı bir işlem olabilir `CButton` . Türetilmiş sınıf için bir Oluşturucu yazın ve `Create` oluşturucuyu içinden çağırın.

Bir düğme denetimi tarafından kendi üst öğesine (genellikle [CDialog](../../mfc/reference/cdialog-class.md)'dan türetilmiş bir sınıf) gönderilen Windows bildirim iletilerini işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşleme girişi ve ileti işleyici üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

**Üzerinde \_** _Bildirim_ **(** _kimlik_, _memberFxn_ **)**

Burada *kimlik* bildirimi gönderen denetimin alt pencere kimliğini belirtir ve *memberFxn* , bildirimi işlemek için yazdığınız ana üye işlevinin adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn();`

Olası ileti eşleme girdileri aşağıdaki gibidir:

|Eşleme girişi|Üst öğeye gönderildi...|
|---------------|----------------------------|
|ON_BN_CLICKED|Kullanıcı bir düğmeye tıklar.|
|ON_BN_DOUBLECLICKED|Kullanıcı bir düğmeye çift tıklar.|

`CButton`İletişim kutusu kaynağından bir nesne oluşturursanız, `CButton` Kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir `CButton` pencere içinde bir nesne oluşturursanız, bunu yok etmeniz gerekebilir. `CButton`Nesnesini, işlevini kullanarak yığında oluşturursanız **`new`** , **`delete`** Kullanıcı Windows düğme denetimini kapattığında nesneyi yok etmek için nesnesini çağırmanız gerekir. `CButton`Nesneyi yığında oluşturursanız veya üst iletişim nesnesine katıştırılmışsa, otomatik olarak yok edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="cbuttoncbutton"></a><a name="cbutton"></a> CButton:: CButton

Bir `CButton` nesnesi oluşturur.

```
CButton();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

## <a name="cbuttoncreate"></a><a name="create"></a> CButton:: Create

Windows düğme denetimini oluşturur ve `CButton` nesneye ekler.

```
virtual BOOL Create(
    LPCTSTR lpszCaption,
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*lpszCaption*<br/>
Düğme denetiminin metnini belirtir.

*dwStyle*<br/>
Düğme denetiminin stilini belirtir. Düğme [stillerinin](../../mfc/reference/styles-used-by-mfc.md#button-styles) herhangi bir birleşimini düğmeye uygulayın.

*Rect*<br/>
Düğme denetiminin boyutunu ve konumunu belirtir. Bir `CRect` nesne ya da `RECT` Yapı olabilir.

*pParentWnd*<br/>
Düğme denetiminin ana penceresini (genellikle a) belirtir `CDialog` . NULL olmaması gerekir.

*NID*<br/>
Düğme denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CButton`İki adımda bir nesne oluşturursunuz. İlk olarak, oluşturucuyu çağırın ve sonra `Create` Windows düğme denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CButton` .

WS_VISIBLE stili verilirse Windows, düğme denetimini etkinleştirmek için gereken tüm iletileri gönderir ve düğmeyi gösterir.

Düğme denetimine aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) uygulayın:

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

- Denetimleri gruplamak Için WS_GROUP

- Düğmeyi sekme sırasına eklemek WS_TABSTOP

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

## <a name="cbuttondrawitem"></a><a name="drawitem"></a> CButton::D rawItem

Sahip tarafından çizilmiş bir düğmenin görsel bir yönü değiştiğinde Framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
[Drawitemstruct](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısına yönelik uzun bir işaretçi. Yapı, çizilecek öğe ve çizim türü hakkında bilgiler içerir.

### <a name="remarks"></a>Açıklamalar

Sahip tarafından çizilmiş bir düğmenin BS_OWNERDRAW stil kümesi vardır. Sahip tarafından çizilmiş bir nesne için çizim uygulamak üzere bu üye işlevini geçersiz kılın `CButton` . Uygulamanın, üye işlevi sonlandırılmadan önce *Lpdrawitemstruct* içinde sağlanan görüntüleme bağlamı için seçilen tüm grafik cihaz ARABIRIMI (GDI) nesnelerini geri yüklemesi gerekir.

Ayrıca [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerlerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

## <a name="cbuttongetbitmap"></a><a name="getbitmap"></a> CButton:: GetBitmap

Daha önce bir düğmeyle ilişkilendirilen bir [bit eşlemin tanıtıcısını](#setbitmap)almak için bu üye işlevi çağırın.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bit eşlem tutamacı. Daha önce bir bit eşlem belirtilmemişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a> CButton:: GetButtonStyle

Düğme Denetim stiliyle ilgili bilgileri alır.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesnenin düğme stillerini döndürür `CButton` . Bu işlev, diğer pencere stillerinden hiçbirini değil yalnızca [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerlerini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttongetcheck"></a><a name="getcheck"></a> CButton:: GetCheck

Radyo düğmesinin veya onay kutusunun denetim durumunu alır.

```
int GetCheck() const;
```

### <a name="return-value"></a>Dönüş Değeri

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON veya BS_3STATE stili ile oluşturulan bir düğme denetimindeki dönüş değeri aşağıdaki değerlerden biridir:

|Değer|Anlamı|
|-----------|-------------|
|BST_UNCHECKED|Düğme durumu işaretli değil.|
|BST_CHECKED|Düğme durumu işaretlendi.|
|BST_INDETERMINATE|Düğme durumu belirsiz (yalnızca düğmenin BS_3STATE veya BS_AUTO3STATE stili varsa geçerlidir).|

Düğmenin başka bir stili varsa, dönüş değeri BST_UNCHECKED.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttongetcursor"></a><a name="getcursor"></a> CButton:: GetCursor

Daha önce, bir düğme ile ilişkili olan, daha önce [SetCursor](#setcursor)ile ayarlanmış bir imlecin tanıtıcısını almak için bu üye işlevini çağırın.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

İmleç resmine yönelik bir tanıtıcı. Daha önce belirtilen imleç yoksa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttongeticon"></a><a name="geticon"></a> CButton:: GetIcon

Bir düğme ile ilişkili olan, daha önce [setIcon](#seticon)ile ayarlanmış bir simgenin tanıtıcısını almak için bu üye işlevini çağırın.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Simgenin bir tutamacı. Daha önce belirtilmemişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttongetidealsize"></a><a name="getidealsize"></a> CButton:: Getısatıcıboyutu

Düğme denetimi için ideal boyutu alır.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Parametreler

*psıze*<br/>
Düğmenin geçerli boyutuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK [düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETIDEALSIZE iletisinin işlevselliğine öykünür.

## <a name="cbuttongetimagelist"></a><a name="getimagelist"></a> CButton:: GetImageList

Düğme denetiminden görüntü listesini almak için bu yöntemi çağırın.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*Pbuttonımagelist*<br/>
Nesnenin görüntü listesine yönelik bir işaretçi `CButton` .

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK [düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETIMAGELIST iletisinin işlevselliğine öykünür.

## <a name="cbuttongetnote"></a><a name="getnote"></a> CButton:: GetNote

Geçerli komut bağlantı denetimiyle ilişkili dekont metnini alır.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Parametreler

*lpszNote*\
dışı Çağıranın ayrılırken ve ayırmayı kaldırmaktan sorumlu olduğu bir arabelleğin işaretçisi. Dönüş değeri TRUE ise, arabellek geçerli komut bağlantı denetimiyle ilişkili olan Note metnini içerir; Aksi takdirde, arabellek değiştirilmez.

*cchNote*\
[in, out] İşaretsiz tamsayı değişkenine yönelik bir işaretçi. Bu yöntem çağrıldığında, değişkeni *lpszNote* parametresi tarafından belirtilen arabelleğin boyutunu içerir. Bu yöntem döndüğünde, return değeri TRUE ise değişkeni geçerli komut bağlantı denetimiyle ilişkili notun boyutunu içerir. Dönüş değeri FALSE ise, değişken notun içermesi için gereken arabellek boyutunu içerir.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklemede, geçerli komut bağlantı denetimiyle ilişkili dekont metnini içeren bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesi.

-veya-

İkinci aşırı yüklemede, bu yöntem başarılı olursa doğru; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK açıklanan [BCM_GETNOTE](/windows/win32/Controls/bcm-getnote) iletisini gönderir.

## <a name="cbuttongetnotelength"></a><a name="getnotelength"></a> CButton:: GetNoteLength

Geçerli komut bağlantı denetimi için dekont metninin uzunluğunu alır.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli komut bağlantı denetimi için, 16 bit Unicode karakterdeki dekont metninin uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK açıklanan [BCM_GETNOTELENGTH](/windows/win32/Controls/bcm-getnotelength) iletisini gönderir.

## <a name="cbuttongetsplitglyph"></a><a name="getsplitglyph"></a> CButton:: GetSplitGlyph

Geçerli bölme düğmesi denetimiyle ilişkili glifi alır.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli bölünmüş düğme denetimiyle ilişkili glif karakteri.

### <a name="remarks"></a>Açıklamalar

Glif, belirli bir yazı tipindeki bir karakterin fiziksel gösterimidir. Örneğin, bir Split Button denetimi Unicode onay işareti karakterinin (U + 2713) glifi ile donatılmış olabilir.

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem `mask` , bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_GLYPH bayrağıyla başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir. İleti işlevi döndüğünde, bu yöntem, `himlGlyph` yapının üyesinden glifi alır.

## <a name="cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a> CButton:: Getsptımagelist

Geçerli bölünmüş düğme denetiminin [görüntü listesini](../../mfc/reference/cimagelist-class.md) alır.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem `mask` , bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_IMAGE bayrağıyla başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir. İleti işlevi döndürüldüğünde, bu yöntem yapının üyelerinden görüntü listesini alır `himlGlyph` .

## <a name="cbuttongetsplitinfo"></a><a name="getsplitinfo"></a> CButton:: Getsplitınfo

Windows 'un geçerli bölünmüş düğme denetimini nasıl çizdiği belirleme parametrelerini alır.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Parametreler

*pInfo*\
dışı Geçerli bölünmüş düğme denetimi hakkında bilgi alan [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısına yönelik işaretçi. Çağıran, yapıyı ayırmaktan sorumludur.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisini gönderir.

## <a name="cbuttongetsplitsize"></a><a name="getsplitsize"></a> CButton:: GetSplitSize

Geçerli bölünmüş düğme denetiminin aşağı açılan bileşeninin sınırlayıcı dikdörtgenini alır.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Parametreler

*Psıze*\
dışı Bir dikdörtgenin açıklamasını alan [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme denetimi genişletildiğinde, liste denetimi veya sayfalayıcı denetimi gibi bir açılan bileşen görüntüleyebilirsiniz. Bu yöntem, açılan bileşeni içeren sınırlayıcı dikdörtgeni alır.

Bu yöntem `mask` , bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_SIZE bayrağıyla başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir. İleti işlevi döndüğünde, bu yöntem yapı üyesinden sınırlayıcı dikdörtgeni alır `size` .

## <a name="cbuttongetsplitstyle"></a><a name="getsplitstyle"></a> CButton:: GetSplitStyle

Geçerli bölme düğmesi denetimini tanımlayan bölünmüş düğme stillerini alır.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölünmüş düğme stillerinin bit düzeyinde birleşimi. Daha fazla bilgi için `uSplitStyle` [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme stilleri hizalama, en boy oranı ve Windows 'un bölünmüş düğme simgesi çizen grafik biçimini belirtir.

Bu yöntem `mask` , bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_STYLE bayrağıyla başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir. İleti işlevi döndüğünde, bu yöntem, yapı üyesinden bölünmüş düğme stillerini alır `uSplitStyle` .

## <a name="cbuttongetstate"></a><a name="getstate"></a> CButton:: GetState

Düğme denetiminin durumunu alır.

```
UINT GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme denetiminin geçerli durumunu gösteren değerlerin birleşimini içeren bir bit alanı. Aşağıdaki tabloda olası değerler listelenmektedir.

|Düğme durumu|Değer|Açıklama|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|İlk durum.|
|BST_CHECKED|0x0001|Düğme denetimi denetlenir.|
|BST_INDETERMINATE|0x0002|Durum belirsiz (yalnızca düğme denetiminin üç durumu olduğunda mümkündür).|
|BST_PUSHED|0x0004|Düğme denetimine basıldığında.|
|BST_FOCUS|0x0008|Düğme denetimi odağa sahiptir.|

### <a name="remarks"></a>Açıklamalar

BS_3STATE veya BS_AUTO3STATE düğme stiliyle bir düğme denetimi, belirsiz durum olarak adlandırılan üçüncü bir duruma sahip bir onay kutusu oluşturur. Belirsiz durum onay kutusunun işaretli veya işaretlenmemiş olmadığını gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttongettextmargin"></a><a name="gettextmargin"></a> CButton:: GetTextMargin

Nesnenin metin kenar boşluğunu almak için bu yöntemi çağırın `CButton` .

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*pmargin*<br/>
Nesnenin metin kenar boşluğuna yönelik bir işaretçi `CButton` .

### <a name="return-value"></a>Dönüş Değeri

Metin kenar boşluğunu döndürür.

### <a name="remarks"></a>Açıklamalar

Başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK [düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETTEXTMARGIN iletisinin işlevselliğine öykünür.

## <a name="cbuttonsetbitmap"></a><a name="setbitmap"></a> CButton:: SetBitmap

Yeni bir bit eşlemi düğmeyle ilişkilendirmek için bu üye işlevini çağırın.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*HBITMAP*<br/>
Bit eşlemin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkilendirilen bir bit eşlemin tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bit eşlem, varsayılan olarak ortalanan düğmenin yüzuna otomatik olarak yerleştirilir. Bit eşlem, düğme için çok büyükse, iki taraftan da kırpılacak. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini belirleyebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)'ın aksine, `SetBitmap` düğme başına yalnızca bir bit eşlem kullanır. Düğmeye basıldığında, bit eşlem aşağı ve sağa doğru görünür.

Bununla işiniz bittiğinde bit eşlemi serbest bırakmaktan siz sorumlusunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a> CButton:: SetButtonStyle

Bir düğmenin stilini değiştirir.

```cpp
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
[Düğme stilini](../../mfc/reference/styles-used-by-mfc.md#button-styles)belirtir.

*bRedraw*<br/>
Düğmenin yeniden çizilip çizmeyeceğini belirtir. Sıfır dışında bir değer düğmeyi yeniden çizer. 0 değeri, düğmeyi yeniden çizmez. Düğme varsayılan olarak yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

`GetButtonStyle`Düğme stilini almak için üye işlevini kullanın. Tam düğme stilinin alt sıra sözcüğü, düğmeye özgü stildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttonsetcheck"></a><a name="setcheck"></a> CButton:: SetCheck

Radyo düğmesinin veya onay kutusunun denetim durumunu ayarlar veya sıfırlar.

```cpp
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*Nhatayla*<br/>
Denetim durumunu belirtir. Bu parametre aşağıdakilerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|BST_UNCHECKED|Düğme durumunu işaretsiz olarak ayarlayın.|
|BST_CHECKED|Düğme durumunu işaretli olarak ayarlayın.|
|BST_INDETERMINATE|Düğme durumunu belirsiz olarak ayarlayın. Bu değer yalnızca, düğme BS_3STATE veya BS_AUTO3STATE stiline sahipse kullanılabilir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevinin basma düğmesi üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttonsetcursor"></a><a name="setcursor"></a> CButton:: SetCursor

Yeni bir imleci düğmeyle ilişkilendirmek için bu üye işlevini çağırın.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
İmlecin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkilendirilen bir imlecin tutamacı.

### <a name="remarks"></a>Açıklamalar

İmleç, varsayılan olarak ortalanan düğme yüzlede otomatik olarak yerleştirilir. İmleç düğme için çok büyükse, iki taraftan da kırpılacak. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini belirleyebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)'ın aksine, `SetCursor` düğme başına yalnızca bir imleç kullanır. Düğmeye basıldığında, imleç aşağı aşağı ve sağa doğru görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a> CButton:: SetDropDownState

Geçerli bölünmüş düğme denetiminin açılan durumunu ayarlar.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Parametreler

*fDropDown*\
'ndaki BST_DROPDOWNPUSHED durumunu ayarlamak için TRUE; Aksi takdirde, FALSE.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bölünmüş düğme denetimi bir BS_SPLITBUTTON veya BS_DEFSPLITBUTTON stiline sahiptir ve sağ tarafındaki bir düğmeden ve aşağı açılan oka oluşur. Daha fazla bilgi için bkz. [düğme stilleri](/windows/win32/Controls/button-styles). Genellikle, açılan durum Kullanıcı açılan oka tıkladığında ayarlanır. Denetimin açılan durumunu programlı bir şekilde ayarlamak için bu yöntemi kullanın. Aşağı açılan ok, durumu belirtmek için gölgeli olarak çizilir.

Bu yöntem, Windows SDK açıklanan [BCM_SETDROPDOWNSTATE](/windows/win32/Controls/bcm-setdropdownstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölünmüş düğme denetimine programlı bir şekilde erişmek için kullanılan *m_splitButton* değişkenini tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, aşağı açılan okun itiltiğini göstermek için Böl düğme denetiminin durumunu ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

## <a name="cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a> CButton:: SetElevationRequired

`elevation required`Denetimin yükseltilmiş bir güvenlik simgesini görüntülemesi için gerekli olan geçerli düğme denetiminin durumunu olarak ayarlar.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Parametreler

*Fyükseltmeden önce gerekli*\
'ndaki Durumu ayarlamak için TRUE `elevation required` ; Aksi takdirde, false.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bir düğme veya komut bağlantısı denetimi bir eylem gerçekleştirmek için yükseltilmiş güvenlik izni gerektiriyorsa, denetimi `elevation required` duruma ayarlayın. Daha sonra Windows, denetimde kullanıcı hesabı denetimi (UAC) Shield simgesini görüntüler. Daha fazla bilgi için bkz. [Kullanıcı hesabı denetimi](/windows/win32/uxguide/winenv-uac).

Bu yöntem, Windows SDK açıklanan [BCM_SETSHIELD](/windows/win32/Controls/bcm-setshield) iletisini gönderir.

## <a name="cbuttonseticon"></a><a name="seticon"></a> CButton:: SetIcon

Düğme ile yeni bir simge ilişkilendirmek için bu üye işlevi çağırın.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*HICON*<br/>
Bir simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkili bir simgenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Simge, varsayılan olarak ortalanan düğmenin yüzuna otomatik olarak yerleştirilir. Simge düğme için çok büyükse, her iki taraftan da kırpılacak. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini belirleyebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md)'ın aksine, `SetIcon` düğme başına yalnızca bir simge kullanır. Düğmeye basıldığında, simge aşağı ve sağa aşağı doğru görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttonsetimagelist"></a><a name="setimagelist"></a> CButton:: SetImageList

Nesnenin görüntü listesini ayarlamak için bu yöntemi çağırın `CButton` .

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*Pbuttonımagelist*<br/>
Yeni görüntü listesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK [düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_SETIMAGELIST iletisinin işlevselliğine öykünür.

## <a name="cbuttonsetnote"></a><a name="setnote"></a> CButton:: SetNote

Geçerli komut bağlantı denetimi için dekont metnini ayarlar.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Parametreler

*lpszNote*\
'ndaki Komut bağlantısı denetimi için dekont metni olarak ayarlanan bir Unicode dize işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK açıklanan [BCM_SETNOTE](/windows/win32/Controls/bcm-setnote) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, komut bağlantısı denetimine programlı olarak erişmek için kullanılan *m_cmdLink* değişkenini tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, komut bağlantısı denetimi için dekont metnini ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

## <a name="cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a> CButton:: SetSplitGlyph

Belirtilen glifi geçerli bölme düğmesi denetimiyle ilişkilendirir.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Parametreler

*chGlyph*\
'ndaki Bölme düğmesi aşağı açılan oku olarak kullanılacak glifi belirten bir karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Glif, belirli bir yazı tipindeki bir karakterin fiziksel gösterimidir. *ChGlyph* parametresi glif olarak kullanılmaz, ancak bunun yerine sistem tarafından tanımlanan bir karakter kümesinden bir karakter seçmek için kullanılır. Varsayılan aşağı açılan ok karakteri bir ' 6 ' karakteriyle belirtilir ve Unicode karaktere, sıyah aşağı Işaret ÜÇGENI (U + 25BC) benzer.

Bu yöntem, `mask` bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_GLYPH bayrağıyla ve, `himlGlyph` *chGlyph* parametresi ile birlikte başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir.

## <a name="cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a> CButton:: Setsptımagelist

Bir [görüntü listesini](../../mfc/reference/cimagelist-class.md) geçerli bölünmüş düğme denetimiyle ilişkilendirir.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Parametreler

*Psptımagelist*\
'ndaki Geçerli bölme düğmesi denetimine atanacak bir [Ciımagelist](../../mfc/reference/cimagelist-class.md) nesnesine yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, `mask` bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_IMAGE bayrağıyla ve `himlGlyph` ' ı *psptımagelist* parametresiyle başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir.

## <a name="cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a> CButton:: Setsplitınfo

Windows 'un geçerli bölünmüş düğme denetimini nasıl çizdiği belirleyen parametreleri belirtir.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Parametreler

*pInfo*\
'ndaki Geçerli bölünmüş düğme denetimini tanımlayan [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, Windows SDK açıklanan [BCM_SETSPLITINFO](/windows/win32/Controls/bcm-setsplitinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton` bölünmüş düğme denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölme düğmesi aşağı açılan ok için kullanılan glifi değiştirir. Örnek, varsayılan aşağı açılan üçgen karakter için yukarıyı gösteren üçgen bir karakter koyar. Görüntülenen glif, yapının üyesinde belirttiğiniz karaktere bağlıdır `himlGlyph` `BUTTON_SPLITINFO` . Aşağıyı gösteren üçgen karakter ' 6 ' karakteriyle belirtilir ve yukarıyı gösteren üçgen karakter ' 5 ' karakteriyle belirtilir. Karşılaştırma için bkz. kolay yöntem, [CButton:: SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

## <a name="cbuttonsetsplitsize"></a><a name="setsplitsize"></a> CButton:: SetSplitSize

Geçerli bölünmüş düğme denetiminin aşağı açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Parametreler

*Psıze*\
'ndaki Bir sınırlayıcı dikdörtgeni tanımlayan [Boyut](/windows/win32/api/windef/ns-windef-size) yapısına yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme denetimi genişletildiğinde, liste denetimi veya sayfalayıcı denetimi gibi bir açılan bileşen görüntüleyebilirsiniz. Bu yöntem, açılan bileşeni içeren sınırlayıcı dikdörtgenin boyutunu belirtir.

Bu yöntem, `mask` bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_SIZE bayrağıyla ve `size` ' ı *psize* parametresiyle birlikte başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton` bölünmüş düğme denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölme düğmesi aşağı açılan okunun boyutunu iki katına çıkarır.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

## <a name="cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a> CButton:: SetSplitStyle

Geçerli bölünmüş düğme denetiminin stilini ayarlar.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Parametreler

*uSplitStyle*\
'ndaki Bölünmüş düğme stillerinin bit düzeyinde birleşimi. Daha fazla bilgi için `uSplitStyle` [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme stilleri hizalama, en boy oranı ve Windows 'un bölünmüş düğme simgesi çizen grafik biçimini belirtir. Daha fazla bilgi için `uSplitStyle` [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesine bakın.

Bu yöntem, `mask` bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısının üyesini BCSIF_STYLE bayrağıyla ve `uSplitStyle` *uSplitStyle* parametresiyle birlikte başlatır ve ardından bu yapıyı Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton` bölünmüş düğme denetimine programlı bir şekilde erişmek için kullanılan değişkenini tanımlar.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölünmüş düğme açılır okun stilini ayarlar. BCSS_ALIGNLEFT stil düğmenin sol tarafındaki oku görüntüler ve BCSS_STRETCH Stili, düğmeyi yeniden boyutlandırdığınızda açılan okun oranlarını korur.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

## <a name="cbuttonsetstate"></a><a name="setstate"></a> CButton:: SetState

Düğme denetiminin vurgulanıp vurgulanmayacağını ayarlar.

```cpp
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
Düğmenin vurgulanıp vurgulanmayacağını belirtir. Sıfır dışında bir değer düğmeyi vurgular; 0 değeri tüm vurgulamayı kaldırır.

### <a name="remarks"></a>Açıklamalar

Vurgulama, düğme denetiminin dış kısmını etkiler. Radyo düğmesinin veya onay kutusunun denetim durumunu etkilemez.

Kullanıcı farenin sol düğmesini tıkladığı ve tuttuğunda düğme denetimi otomatik olarak vurgulanır. Kullanıcı fare düğmesini bıraktığında vurgulama kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttonsettextmargin"></a><a name="settextmargin"></a> CButton:: SetTextMargin

Nesnenin metin kenar boşluğunu ayarlamak için bu yöntemi çağırın `CButton` .

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*pmargin*<br/>
Yeni metin kenar boşluğuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK [düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_SETTEXTMARGIN iletisinin işlevselliğine öykünür.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[Cedıt sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton sınıfı](../../mfc/reference/cbitmapbutton-class.md)<br/>
[CDialog sınıfı](../../mfc/reference/cdialog-class.md)
