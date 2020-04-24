---
title: CButton Sınıfı
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
ms.openlocfilehash: 74b07dc8144e853714ea73c8235f1259538a0c12
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81752759"
---
# <a name="cbutton-class"></a>CButton Sınıfı

Windows düğmesi denetimlerinin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CButton : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CButton::CButton](#cbutton)|Bir `CButton` nesne inşa eder.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CButton::Oluştur](#create)|Windows düğmesi denetimini oluşturur ve `CButton` nesneye bağlar.|
|[CButton::DrawItem](#drawitem)|Sahibi tarafından çizilmiş `CButton` bir nesne çizmek için geçersiz kılma.|
|[CButton::GetBitmap](#getbitmap)|[SetBitmap](#setbitmap)ile daha önce ayarlanmış bit eşlemi nin tutamacını alır.|
|[CButton::GetButtonStyle](#getbuttonstyle)|Düğme denetim stili hakkında bilgi alır.|
|[CButton::GetCheck](#getcheck)|Düğme denetiminin denetim durumunu alır.|
|[CButton::GetCursor](#getcursor)|[SetCursor](#setcursor)ile daha önce ayarlanmış imleç görüntüsünün tutamacını alır.|
|[CButton::GetIcon](#geticon)|[SetIcon](#seticon)ile daha önce ayarlanmış simgenin tutamacını alır.|
|[CButton::GetIdealSize](#getidealsize)|Düğme denetiminin ideal boyutunu alır.|
|[CButton::GetImageList](#getimagelist)|Düğme denetiminin görüntü listesini alır.|
|[CButton::GetNote](#getnote)|Geçerli komut bağlantısı denetiminin not bileşenini alır.|
|[CButton::GetNoteLength](#getnotelength)|Geçerli komut bağlantısı denetimi için not metninin uzunluğunu alır.|
|[CButton::GetSplitGlyph](#getsplitglyph)|Geçerli bölme düğmesi denetimiyle ilişkili glifleri alır.|
|[CButton::GetSplitImageList](#getsplitimagelist)|Geçerli bölme düğmesi denetimi için görüntü listesini alır.|
|[CButton::GetSplitInfo](#getsplitinfo)|Geçerli bölme düğmesi denetimini tanımlayan bilgileri alır.|
|[CButton::GetSplitSize](#getsplitsize)|Geçerli bölme düğmesi denetiminin açılır bileşeninin sınırlayıcı dikdörtgenini alır.|
|[CButton::GetSplitStyle](#getsplitstyle)|Geçerli split düğmesi denetimini tanımlayan bölünmüş düğme stillerini alır.|
|[CButton::GetState](#getstate)|Denetim durumunu alır, durumu vurgular ve düğme denetiminin odak durumunu alır.|
|[CButton::GetTextMargin](#gettextmargin)|Düğme denetiminin metin kenar boşluğunu alır.|
|[CButton::SetBitmap](#setbitmap)|Düğmede görüntülenecek bir bit eşlemi belirtir.|
|[CButton::SetButtonStyle](#setbuttonstyle)|Düğmenin stilini değiştirir.|
|[CButton::SetCheck](#setcheck)|Düğme denetiminin denetim durumunu ayarlar.|
|[CButton::SetCursor](#setcursor)|Düğmede görüntülenecek bir imleç görüntüsünü belirtir.|
|[CButton::SetDropDownState](#setdropdownstate)|Geçerli bölme düğmesi denetiminin açılır durumunu ayarlar.|
|[CButton::SetIcon](#seticon)|Düğmede görüntülenecek bir simge belirtir.|
|[CButton::SetImageList](#setimagelist)|Düğme denetiminin görüntü listesini ayarlar.|
|[CButton::SetNote](#setnote)|Geçerli komut bağlantısı denetiminde notu ayarlar.|
|[CButton:SetSplitGlyph](#setsplitglyph)|Geçerli split düğmesi denetimi ile belirli bir gph ilişkilendirer.|
|[CButton::SetSplitImageList](#setsplitimagelist)|Bir görüntü listesini geçerli bölme düğmesi denetimiyle ilişkilendirer.|
|[CButton:SetSplitInfo](#setsplitinfo)|Geçerli bölme düğmesi denetimini tanımlayan bilgileri belirtir.|
|[CButton::SetSplitSize](#setsplitsize)|Geçerli bölme düğmesi denetiminin açılır bileşeninin sınırlayıcı dikdörtgenini ayarlar.|
|[CButton::SetSplitStyle](#setsplitstyle)|Geçerli bölme düğmesi denetiminin stilini ayarlar.|
|[CButton::SetState](#setstate)|Düğme denetiminin vurgulama durumunu ayarlar.|
|[CButton::SetTextMargin](#settextmargin)|Düğme denetiminin metin kenar boşluğunu ayarlar.|

## <a name="remarks"></a>Açıklamalar

Düğme denetimi, tıklanabilen ve kapatabilen küçük, dikdörtgen bir alt penceredir. Düğmeler tek başına veya gruplar halinde kullanılabilir ve etiketlenebilir veya metin olmadan görünebilir. Bir düğme genellikle kullanıcı tıklattığında görünümünü değiştirir.

Tipik düğmeler onay kutusu, radyo düğmesi ve düğmedir. Bir `CButton` nesne, [Üye Oluştur](#create) işlevi tarafından başlatılmasında belirtilen [düğme stiline](../../mfc/reference/styles-used-by-mfc.md#button-styles) göre bunlardan herhangi biri olabilir.

Buna ek olarak, metin yerine `CButton` bitmap görüntüleriyle etiketlenmiş düğme denetimlerinin oluşturulmasını destekleyen [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) sınıfı. Bir `CBitmapButton` düğmenin yukarı, aşağı, odaklanmış ve devre dışı bırakılmış durumları için ayrı bit eşlemleri olabilir.

Bir iletişim şablonundan veya doğrudan kodunuzda bir düğme denetimi oluşturabilirsiniz. Her iki durumda da, `CButton` `CButton` önce nesneoluşturmak için oluşturucuyu arayın; ardından Windows `Create` düğmesi denetimini oluşturmak ve `CButton` nesneye takmak için üye işlevi arayın.

İnşaat, `CButton`bir sınıftan türetilen tek adımlı bir işlem olabilir. Türemiş sınıf için bir `Create` oluşturucu yazın ve oluşturucu içinden arayın.

Bir düğme denetimi tarafından üst öğesine gönderilen Windows bildirim iletilerini (genellikle [CDialog'dan](../../mfc/reference/cdialog-class.md)türetilmiş bir sınıf) işlemek istiyorsanız, her ileti için üst sınıfa bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti-eş-eşlemi girişi aşağıdaki formu alır:

**ON\_**_Bildirimi_ **(** _id_, _üyeFxn_ **)**

*id* bildirimi gönderen denetimin alt pencere kimliğini belirtir ve *memberFxn* bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Ebeveynin işlev prototipi aşağıdaki gibidir:

`afx_msg void memberFxn();`

Olası ileti-eşlemi girişleri aşağıdaki gibidir:

|Harita girişi|Ebeveyne ne zaman gönderilir...|
|---------------|----------------------------|
|ON_BN_CLICKED|Kullanıcı bir düğmeyi tıklatıyor.|
|ON_BN_DOUBLECLICKED|Kullanıcı bir düğmeyi çift tıklatıyor.|

Bir iletişim `CButton` kaynağından bir nesne oluşturursanız, kullanıcı iletişim kutusunu kapattığında `CButton` nesne otomatik olarak yok edilir.

Bir pencere `CButton` içinde bir nesne oluşturursanız, onu yok etmek gerekebilir. Nesneyi `CButton` **yeni** işlevi kullanarak yığında oluşturursanız, kullanıcı Windows düğmesi denetimini kapattığında nesneyi yok etmek için nesneyi **sil'i** aramanız gerekir. Nesneyi `CButton` yığında oluşturursanız veya üst iletişim nesnesine katıştırılırsa, otomatik olarak yok edilir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Ccmdtarget](../../mfc/reference/ccmdtarget-class.md)

[Cwnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="cbuttoncbutton"></a><a name="cbutton"></a>CButton::CButton

Bir `CButton` nesne inşa eder.

```
CButton();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

## <a name="cbuttoncreate"></a><a name="create"></a>CButton::Oluştur

Windows düğmesi denetimini oluşturur ve `CButton` nesneye bağlar.

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

*Dwstyle*<br/>
Düğme denetiminin stilini belirtir. [Düğme stillerinin](../../mfc/reference/styles-used-by-mfc.md#button-styles) herhangi bir birleşimini düğmeye uygulayın.

*Rect*<br/>
Düğme denetiminin boyutunu ve konumunu belirtir. Bir `CRect` nesne veya yapı `RECT` olabilir.

*pParentWnd*<br/>
Düğme denetiminin ana penceresini belirtir, `CDialog`genellikle bir . NULL olmamalıdır.

*Nıd*<br/>
Düğme denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CButton` iki adımda inşa ee. İlk olarak, oluşturucuyu `Create`çağırın ve ardından Windows düğmesi denetimini `CButton` oluşturan ve nesneye iliştiren ,

WS_VISIBLE stili verilirse, Windows düğmeyi etkinleştirmek ve düğmeyi göstermek için gereken tüm iletileri kontrol eder.

Aşağıdaki [pencere stillerini](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir düğme denetimine uygulayın:

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_GROUP Denetimleri gruplandırmak için

- WS_TABSTOP Düğmeyi sekme sırasına eklemek için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

## <a name="cbuttondrawitem"></a><a name="drawitem"></a>CButton::DrawItem

Sahip tarafından çizilen düğmenin görsel yönü değiştiğinde çerçeve tarafından çağrılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
[DRAWITEMSTRUCT](/windows/win32/api/winuser/ns-winuser-drawitemstruct) yapısıiçin uzun bir işaretçi. Yapı, çizilecek öğe ve gerekli çizim türü hakkında bilgi içerir.

### <a name="remarks"></a>Açıklamalar

Sahip tarafından çizilen bir düğme, BS_OWNERDRAW stil kümesine sahiptir. Sahibi tarafından çizilen `CButton` bir nesne için çizim uygulamak için bu üye işlevi geçersiz kılın. Uygulama, üye işlev sona erdirilmeden önce *lpDrawItemStruct'ta* sağlanan ekran bağlamı için seçilen tüm grafik aygıtı arabirimi (GDI) nesnelerini geri yüklemelidir.

Ayrıca [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerlerine bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

## <a name="cbuttongetbitmap"></a><a name="getbitmap"></a>CButton::GetBitmap

Daha önce [SetBitmap](#setbitmap)ile ayarlanmış bir bitmap, bir düğme ile ilişkili işlemek almak için bu üye işlevi arayın.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bitmap için bir tutamaç. Daha önce bit eşlemi belirtilmemişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttongetbuttonstyle"></a><a name="getbuttonstyle"></a>CButton::GetButtonStyle

Düğme denetim stili hakkında bilgi alır.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CButton` nesne için düğme stillerini döndürür. Bu işlev, diğer pencere stillerinden herhangi birini değil, yalnızca [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerlerini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttongetcheck"></a><a name="getcheck"></a>CButton::GetCheck

Radyo düğmesinin veya onay kutusunun onay durumunu alır.

```
int GetCheck() const;
```

### <a name="return-value"></a>Dönüş Değeri

BS_AUTOCHECKBOX, BS_AUTORADIOBUTTON, BS_AUTO3STATE, BS_CHECKBOX, BS_RADIOBUTTON veya BS_3STATE stiliyle oluşturulan bir düğme denetiminden gelen dönüş değeri aşağıdaki değerlerden biridir:

|Değer|Anlamı|
|-----------|-------------|
|Bst_unchecked|Düğme durumu işaretlenmedi.|
|BST_CHECKED|Düğme durumu kontrol edilir.|
|BST_INDETERMINATE|Düğme durumu belirsizdir (yalnızca düğmede BS_3STATE veya BS_AUTO3STATE stili varsa geçerlidir).|

Düğmenin başka bir stili varsa, iade değeri BST_UNCHECKED.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttongetcursor"></a><a name="getcursor"></a>CButton::GetCursor

Daha önce [SetCursor](#setcursor)ile ayarlanmış bir imleç tutamacı almak için bu üye işlevi arayın, bir düğme ile ilişkili.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

İmleç resmine bir tutamaç. İmleç yoksa NULL daha önce belirtilmemişse.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttongeticon"></a><a name="geticon"></a>CButton::GetIcon

Daha önce [SetIcon](#seticon)ile ayarlanmış bir simgenin tutamacını almak için bu üye işlevi arayın, bir düğme ile ilişkilidir.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Simgenin tutamacı. Daha önce simge belirtilmemişse NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttongetidealsize"></a><a name="getidealsize"></a>CButton::GetIdealSize

Düğme kontrolü için ideal boyutu alır.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Parametreler

*psize*<br/>
Düğmenin geçerli boyutuna işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'nın [Düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETIDEALSIZE iletinin işlevselliğini taklit eder.

## <a name="cbuttongetimagelist"></a><a name="getimagelist"></a>CButton::GetImageList

Görüntü listesini düğme denetiminden almak için bu yöntemi arayın.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*pbuttonImagelist*<br/>
`CButton` Nesnenin görüntü listesine bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'nın [Düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETIMAGELIST iletisinin işlevselliğini taklit eder.

## <a name="cbuttongetnote"></a><a name="getnote"></a>CButton::GetNote

Geçerli komut bağlantısı denetimiyle ilişkili not metnini alır.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszNote*|[çıkış] Arayanın ayırma ve ayırma dan sorumlu olduğu bir arabelleğe işaretçi. İade değeri TRUE ise, arabellek geçerli komut bağlantısı denetimi ile ilişkili not metnini içerir; aksi takdirde arabellek değişmez.|
|*cchNote*|[içinde, dışarı] İmzasız bir tamsayı değişkenine işaretçi.<br /><br /> Bu yöntem çağrıldığında, değişken *lpszNote* parametresi tarafından belirtilen arabellek boyutunu içerir.<br /><br /> Bu yöntem döndüğünde, iade değeri TRUE ise değişken, geçerli komut bağlantısı denetimiyle ilişkili notun boyutunu içerir. İade değeri FALSE ise, değişken notu içermek için gereken arabellek boyutunu içerir.|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yüklemede, geçerli komut bağlantısı denetimiyle ilişkili not metnini içeren bir [CString](../../atl-mfc-shared/using-cstring.md) nesnesi.

-veya-

İkinci aşırı yükte, bu yöntem başarılı olursa TRUE; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK'da açıklanan [BCM_GETNOTE](/windows/win32/Controls/bcm-getnote) iletisini gönderir.

## <a name="cbuttongetnotelength"></a><a name="getnotelength"></a>CButton::GetNoteLength

Geçerli komut bağlantısı denetimi için not metninin uzunluğunu alır.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli komut bağlantısı denetimi için 16 bit Unicode karakterlerinde not metninin uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK'da açıklanan [BCM_GETNOTELENGTH](/windows/win32/Controls/bcm-getnotelength) iletisini gönderir.

## <a name="cbuttongetsplitglyph"></a><a name="getsplitglyph"></a>CButton::GetSplitGlyph

Geçerli bölme düğmesi denetimiyle ilişkili glifleri alır.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli split düğmesi denetimiyle ilişkili glyph karakteri.

### <a name="remarks"></a>Açıklamalar

Glifler, belirli bir yazı tipindeki bir karakterin fiziksel temsilidir. Örneğin, bölünmüş düğme denetimi Unicode onay işareti karakterinin (U+2713) glifleri ile dekore edilebilir.

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, BCSIF_GLYPH `mask` bayrağı olan bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesini başolarak karşılar ve bu yapıyı Windows SDK'da açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletiye gönderir. İleti işlevi döndüğünde, bu yöntem yapının `himlGlyph` üyesinden glifleri alır.

## <a name="cbuttongetsplitimagelist"></a><a name="getsplitimagelist"></a>CButton::GetSplitImageList

Geçerli bölme düğmesi denetimi için [görüntü listesini](../../mfc/reference/cimagelist-class.md) alır.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

[CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, BCSIF_IMAGE `mask` bayrağı olan [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesini başolarak karşılar ve bu yapıyı Windows SDK'da açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletiye gönderir. İleti işlevi döndüğünde, bu yöntem yapının `himlGlyph` üyesinden görüntü listesini alır.

## <a name="cbuttongetsplitinfo"></a><a name="getsplitinfo"></a>CButton::GetSplitInfo

Windows'un geçerli bölme düğmesi denetimini nasıl çizer ini belirleyen parametreleri alır.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pınfo*|[çıkış] Geçerli bölme düğmesi denetimi hakkında bilgi alan [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapıyı işaretleyin. Arayanın yapısı ayırmakla yükümlü olduğu kişi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, Windows SDK'da açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisini gönderir.

## <a name="cbuttongetsplitsize"></a><a name="getsplitsize"></a>CButton::GetSplitSize

Geçerli bölme düğmesi denetiminin açılır bileşeninin sınırlayıcı dikdörtgenini alır.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSize*|[çıkış] Dikdörtgenin açıklamasını alan bir [SIZE](/windows/win32/api/windef/ns-windef-size) yapısına işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölme düğmesi denetimi genişletildiğinde, liste denetimi veya çağrı cihazı denetimi gibi açılır bir bileşeni görüntüleyebilir. Bu yöntem, açılır bileşeni içeren sınırlayıcı dikdörtgeni alır.

Bu yöntem, BCSIF_SIZE `mask` bayrağı olan bir [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesini başolarak karşılar ve bu yapıyı Windows SDK'da açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletiye gönderir. İleti işlevi döndüğünde, bu yöntem yapının `size` üyesinden sınırlayıcı dikdörtgeni alır.

## <a name="cbuttongetsplitstyle"></a><a name="getsplitstyle"></a>CButton::GetSplitStyle

Geçerli split düğmesi denetimini tanımlayan bölünmüş düğme stillerini alır.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölünmüş düğme stillerinin bitwise kombinasyonu. Daha fazla bilgi `uSplitStyle` için [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesine bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme stilleri, Windows'un bölünmüş düğme simgesini çizdiği hizalamayı, en boy oranını ve grafik biçimini belirtir.

Bu yöntem, BCSIF_STYLE `mask` bayrağı olan [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesini başolarak karşılar ve bu yapıyı Windows SDK'da açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletiye gönderir. İleti işlevi döndüğünde, bu yöntem yapının `uSplitStyle` üyesinden bölünmüş düğme stillerini alır.

## <a name="cbuttongetstate"></a><a name="getstate"></a>CButton::GetState

Düğme denetiminin durumunu alır.

```
UINT GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme denetiminin geçerli durumunu gösteren değerlerin birleşimini içeren bir bit alanı. Aşağıdaki tabloda olası değerler listeleilmektedir.

|Düğme Durumu|Değer|Açıklama|
|------------------|-----------|-----------------|
|Bst_unchecked|0x0000|İlk durum.|
|BST_CHECKED|0x0001|Düğme denetimi kontrol edilir.|
|BST_INDETERMINATE|0x0002|Durum belirsizdir (yalnızca düğme denetiminin üç durumu olduğunda mümkündür).|
|BST_PUSHED|0x0004|Düğme kontrolüne basılır.|
|BST_FOCUS|0x0008|Düğme denetimi odak noktası vardır.|

### <a name="remarks"></a>Açıklamalar

BS_3STATE veya BS_AUTO3STATE düğme stiline sahip bir düğme denetimi, belirsiz durum olarak adlandırılan üçüncü bir durumu olan bir onay kutusu oluşturur. Belirsiz durum, onay kutusunun ne işaretli ne de işaretlenmemiş olduğunu gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttongettextmargin"></a><a name="gettextmargin"></a>CButton::GetTextMargin

`CButton` Nesnenin metin kenar boşluğu almak için bu yöntemi arayın.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*kenar boşluğu*<br/>
`CButton` Nesnenin metin kenar boşluğuna işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Metin kenar boşluğunu döndürür.

### <a name="remarks"></a>Açıklamalar

Sıfırsız eğer başarılı; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'nın [Düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi BCM_GETTEXTMARGIN iletisinin işlevselliğini taklit eder.

## <a name="cbuttonsetbitmap"></a><a name="setbitmap"></a>CButton::SetBitmap

Yeni bir bit eşlemeyi düğmeyle ilişkilendirmek için bu üye işlevini arayın.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Bitmap'in sapı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkili bir bit eşlemi nin tutamacı.

### <a name="remarks"></a>Açıklamalar

Bit map otomatik olarak varsayılan olarak ortalanmış, düğmenin yüzüne yerleştirilir. Bit eşlemi düğme için çok büyükse, her iki tarafta da kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton'ın](../../mfc/reference/cbitmapbutton-class.md)aksine, `SetBitmap` düğme başına yalnızca bir bit eşlem kullanır. Düğmeye basıldığında, bit eşlemi aşağı ve sağa kayıyor gibi görünür.

Bit map'i ile bitirdiğinizde serbest bırakmaksizin sorumlusunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

## <a name="cbuttonsetbuttonstyle"></a><a name="setbuttonstyle"></a>CButton::SetButtonStyle

Düğmenin stilini değiştirir.

```cpp
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
[Düğme stilini](../../mfc/reference/styles-used-by-mfc.md#button-styles)belirtir.

*bRedraw*<br/>
Düğmenin yeniden çizilip çizilmeyeceğini belirtir. Sıfır olmayan bir değer düğmeyi yeniden çizer. 0 değeri düğmeyi yeniden çizmez. Düğme varsayılan olarak yeniden çizilir.

### <a name="remarks"></a>Açıklamalar

Düğme `GetButtonStyle` stilini almak için üye işlevini kullanın. Tam düğme stilinin düşük sıralı sözcüğü düğmeye özgü stildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

## <a name="cbuttonsetcheck"></a><a name="setcheck"></a>CButton::SetCheck

Radyo düğmesinin veya onay kutusunun onay durumunu ayarlar veya sıfırlar.

```cpp
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*nCheck*<br/>
Çek durumunu belirtir. Bu parametre aşağıdakilerden biri olabilir:

|Değer|Anlamı|
|-----------|-------------|
|Bst_unchecked|Düğme durumunu işaretlenmemiş olarak ayarlayın.|
|BST_CHECKED|Düğme durumunu denetlemek üzere ayarlayın.|
|BST_INDETERMINATE|Düğme durumunu belirsiz olarak ayarlayın. Bu değer yalnızca düğmede BS_3STATE veya BS_AUTO3STATE tarzı varsa kullanılabilir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevin bir düğme üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

## <a name="cbuttonsetcursor"></a><a name="setcursor"></a>CButton::SetCursor

Yeni bir imleç le düğmeyle ilişkilendirmek için bu üye işlevini arayın.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
İmleç sapı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkili bir imleç tutamacı.

### <a name="remarks"></a>Açıklamalar

İmleç otomatik olarak düğmenin yüzüne yerleştirilir ve varsayılan olarak ortalanır. İmleç düğme için çok büyükse, her iki tarafta kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton'ın](../../mfc/reference/cbitmapbutton-class.md)aksine, `SetCursor` düğme başına yalnızca bir imleç kullanır. Düğmeye basıldığında imleç aşağı ve sağa kayıyor gibi görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

## <a name="cbuttonsetdropdownstate"></a><a name="setdropdownstate"></a>CButton::SetDropDownState

Geçerli bölme düğmesi denetiminin açılır durumunu ayarlar.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fDropDown*|[içinde] DOĞRU BST_DROPDOWNPUSHED devlet ayarlamak için; aksi takdirde, YANLIŞ.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bölünmüş düğme denetimi, BS_SPLITBUTTON veya BS_DEFSPLITBUTTON stiline sahiptir ve bir düğme ve sağındaki açılır oktan oluşur. Daha fazla bilgi için [Düğme Stilleri'ne](/windows/win32/Controls/button-styles)bakın. Genellikle, kullanıcı açılır ok'u tıklattığında açılır durum ayarlanır. Denetimin açılır durumunu programlı olarak ayarlamak için bu yöntemi kullanın. Açılan ok durumu belirtmek için gölgeli olarak çizilir.

Bu yöntem, Windows SDK'da açıklanan [BCM_SETDROPDOWNSTATE](/windows/win32/Controls/bcm-setdropdownstate) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölme düğmesi denetimine programlı olarak erişmek için kullanılan *değişkeni, m_splitButton*tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan oka basılarak bölünmüş düğme denetiminin durumunu ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

## <a name="cbuttonsetelevationrequired"></a><a name="setelevationrequired"></a>CButton::SetelevationGerekli

Geçerli düğme denetiminin `elevation required`durumunu, denetimin yükseltilmiş bir güvenlik simgesini görüntülemesi için gerekli olan duruma ayarlar.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fYükseklik Gerekli*|[içinde] DOĞRU devlet `elevation required` ayarlamak için; aksi takdirde, YANLIŞ.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir düğme veya komut bağlantısı denetimi bir eylem gerçekleştirmek için yüksek `elevation required` güvenlik izni gerektiriyorsa, denetimi duruma göre ayarlayın. Daha sonra, Windows denetimde Kullanıcı Hesabı Denetimi (UAC) kalkanı simgesini görüntüler. Daha fazla bilgi için [MSDN'deki](https://go.microsoft.com/fwlink/p/?linkid=18507)"Kullanıcı Hesabı Denetimi" adlı kullanıcı hesabına bakın.

Bu yöntem, Windows SDK'da açıklanan [BCM_SETSHIELD](/windows/win32/Controls/bcm-setshield) iletisini gönderir.

## <a name="cbuttonseticon"></a><a name="seticon"></a>CButton::SetIcon

Yeni bir simgeyi düğmeyle ilişkilendirmek için bu üye işlevini arayın.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*Hıcon*<br/>
Bir simgenin tutamacı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmeyle ilişkili bir simgenin tutamacı.

### <a name="remarks"></a>Açıklamalar

Simge otomatik olarak varsayılan olarak ortalanmış düğmenin yüzüne yerleştirilir. Simge düğme için çok büyükse, her iki tarafta kırpılır. Aşağıdakiler de dahil olmak üzere diğer hizalama seçeneklerini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Düğme başına dört bit eşlem kullanan [CBitmapButton'ın](../../mfc/reference/cbitmapbutton-class.md)aksine, `SetIcon` düğme başına yalnızca bir simge kullanır. Düğmeye basıldığında, simge aşağı ve sağa kayıyor gibi görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

## <a name="cbuttonsetimagelist"></a><a name="setimagelist"></a>CButton::SetImageList

Nesnenin görüntü listesini ayarlamak için `CButton` bu yöntemi çağırın.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*pbuttonImagelist*<br/>
Yeni resim listesiiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'nın [Düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi, BCM_SETIMAGELIST iletisinin işlevselliğini taklit eder.

## <a name="cbuttonsetnote"></a><a name="setnote"></a>CButton::SetNote

Geçerli komut bağlantısı denetimi için not metnini ayarlar.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszNote*|[içinde] Komut bağlantısı denetimi için not metni olarak ayarlanan Unicode dizesini işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_COMMANDLINK veya BS_DEFCOMMANDLINK olan denetimlerle kullanın.

Bu yöntem, Windows SDK'da açıklanan [BCM_SETNOTE](/windows/win32/Controls/bcm-setnote) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, komut bağlantısı denetimine programlı olarak erişmek için kullanılan değişken, *m_cmdLink*tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği komut bağlantısı denetimi için not metnini ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

## <a name="cbuttonsetsplitglyph"></a><a name="setsplitglyph"></a>CButton:SetSplitGlyph

Geçerli split düğmesi denetimi ile belirli bir gph ilişkilendirer.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*chGlyph*|[içinde] Split düğmesi açılır ok olarak kullanılacak glifleri belirten bir karakter.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Glifler, belirli bir yazı tipindeki bir karakterin fiziksel temsilidir. *ChGlyph* parametresi glifler olarak kullanılmaz, ancak bunun yerine sistem tanımlı glifler kümesinden bir glifler seçmek için kullanılır. Varsayılan açılır ok glyph karakteri '6' tarafından belirtilir ve Unicode karakteri BLACK DOWN-POINTING TRIANGLE (U+25BC) benzer.

Bu yöntem, BCSIF_GLYPH `mask` bayrağı ile [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının `himlGlyph` üyesi ve *chGlyph* parametresi ile üye baş harflerini ve sonra windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletibu yapı gönderir.

## <a name="cbuttonsetsplitimagelist"></a><a name="setsplitimagelist"></a>CButton::SetSplitImageList

Bir [görüntü listesini](../../mfc/reference/cimagelist-class.md) geçerli bölme düğmesi denetimiyle ilişkilendirer.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSplitImageList*|[içinde] Geçerli bölme düğmesi denetimine atamak üzere [CImageList](../../mfc/reference/cimagelist-class.md) nesnesine işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, BCSIF_IMAGE `mask` bayrağı ve *pSplitImageList* parametresi ile `himlGlyph` üye ile [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapısı üyesi ni aparatlar ve sonra Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisi bu yapıyı gönderir.

## <a name="cbuttonsetsplitinfo"></a><a name="setsplitinfo"></a>CButton:SetSplitInfo

Windows'un geçerli bölme düğmesi denetimini nasıl çizer ini belirleyen parametreleri belirtir.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Pınfo*|[içinde] Geçerli bölme düğmesi denetimini tanımlayan [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) bir yapıyı işaretleyin.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bu yöntem, Windows SDK'da açıklanan [BCM_SETSPLITINFO](/windows/win32/Controls/bcm-setsplitinfo) iletisini gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton`bölme düğmesi denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölme düğmesi açılır ok için kullanılan glifleri değiştirir. Örnek, varsayılan aşağı işaret lisi üçgen glyph için yukarı işaretli üçgen gph yerine geçer. Görüntülenen `himlGlyph` `BUTTON_SPLITINFO` glyph, yapının üyesinde belirttiğiniz karaktere bağlıdır. Aşağı işaret üçgeni glyph bir karakter '6' tarafından belirtilir ve yukarı işaretleme üçgen glyph bir karakter '5' ile belirtilir. Karşılaştırma için, kolaylık yöntemi, [CButton bakın:SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

## <a name="cbuttonsetsplitsize"></a><a name="setsplitsize"></a>CButton::SetSplitSize

Geçerli bölme düğmesi denetiminin açılır bileşeninin sınırlayıcı dikdörtgenini ayarlar.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSize*|[içinde] Sınırlayıcı bir dikdörtgenaçıklayan bir [BOYUT](/windows/win32/api/windef/ns-windef-size) yapısıiçin işaretçi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölme düğmesi denetimi genişletildiğinde, liste denetimi veya çağrı cihazı denetimi gibi açılır bir bileşeni görüntüleyebilir. Bu yöntem, açılır bileşeni içeren sınırlayıcı dikdörtgenin boyutunu belirtir.

Bu yöntem, BCSIF_SIZE `mask` bayrağı ve *pSize* parametresi `size` ile üye ile [bir BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesi ni aparatlar ve sonra windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisinde bu yapıyı gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton`bölme düğmesi denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar. Bu değişken aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölünmüş düğme açılır ok boyutunu iki katına çıkar.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

## <a name="cbuttonsetsplitstyle"></a><a name="setsplitstyle"></a>CButton::SetSplitStyle

Geçerli bölme düğmesi denetiminin stilini ayarlar.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*uSplitStyle*|[içinde] Bölünmüş düğme stillerinin bitwise kombinasyonu. Daha fazla bilgi `uSplitStyle` için [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesine bakın.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi yalnızca düğme stili BS_SPLITBUTTON veya BS_DEFSPLITBUTTON olan denetimlerle kullanın.

Bölünmüş düğme stilleri, Windows'un bölünmüş düğme simgesini çizdiği hizalamayı, en boy oranını ve grafik biçimini belirtir. Daha fazla bilgi `uSplitStyle` için [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) yapının üyesine bakın.

Bu yöntem, BCSIF_STYLE `mask` bayrağı ve *uSplitStyle* parametresi ile `uSplitStyle` üye ile [BUTTON_SPLITINFO](/windows/win32/api/commctrl/ns-commctrl-button_splitinfo) bir yapının üyesi nial ve sonra Windows SDK açıklanan [BCM_GETSPLITINFO](/windows/win32/Controls/bcm-getsplitinfo) iletisi bu yapıyı gönderir.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_splitButton`bölme düğmesi denetimine programlı olarak erişmek için kullanılan değişkeni tanımlar.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bölme düğmesinin açılır ok stilini ayarlar. BCSS_ALIGNLEFT stili düğmenin sol tarafındaki oku görüntüler ve düğmeyi yeniden boyutlandırdığınızda BCSS_STRETCH stili açılır okun oranlarını korur.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

## <a name="cbuttonsetstate"></a><a name="setstate"></a>CButton::SetState

Düğme denetiminin vurgulanıp vurgulanmadığını ayarlar.

```cpp
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bVurgu*<br/>
Düğmenin vurgulanıp vurgulanmayacağını belirtir. Sıfır olmayan bir değer düğmeyi vurgular; 0 değeri herhangi bir vurgulama kaldırır.

### <a name="remarks"></a>Açıklamalar

Vurgulama, düğme denetiminin dış kısmını etkiler. Bir radyo düğmesinin veya onay kutusunun onay durumu üzerinde hiçbir etkisi yoktur.

Kullanıcı sol fare düğmesini tıklatıp tuttuğunda düğme denetimi otomatik olarak vurgulanır. Kullanıcı fare düğmesini serbest bıraktığunda vurgulama kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

## <a name="cbuttonsettextmargin"></a><a name="settextmargin"></a>CButton::SetTextMargin

Nesnenin metin kenar boşluğunu `CButton` ayarlamak için bu yöntemi çağırın.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*kenar boşluğu*<br/>
Yeni metin kenar boşluğuiçin bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı doğru döndürür, başarısızlık false.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, Windows SDK'nın [Düğmeler](/windows/win32/controls/buttons) bölümünde açıklandığı gibi, BCM_SETTEXTMARGIN iletisinin işlevselliğini taklit eder.

## <a name="see-also"></a>Ayrıca bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[Cstatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton Sınıfı](../../mfc/reference/cbitmapbutton-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
