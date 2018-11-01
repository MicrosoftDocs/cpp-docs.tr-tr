---
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
ms.openlocfilehash: ae1b444d424693a2372389fb27fcec90133b3a7d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50662858"
---
# <a name="cbutton-class"></a>CButton sınıfı

Windows düğme denetimleri işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CButton : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CButton::CButton](#cbutton)|Oluşturur bir `CButton` nesne.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CButton::Create](#create)|Windows düğme denetimini oluşturur ve ona ekler `CButton` nesne.|
|[CButton::DrawItem](#drawitem)|Bir sahip tarafından çizilmiş çizmek için geçersiz kılma `CButton` nesne.|
|[CButton::GetBitmap](#getbitmap)|Bit eşlem ile önceden ayarlanan tanıtıcısını alır [SetBitmap](#setbitmap).|
|[CButton::GetButtonStyle](#getbuttonstyle)|Düğme denetimi stil hakkındaki bilgileri alır.|
|[CButton::GetCheck](#getcheck)|Bir düğme denetimi onay durumunu alır.|
|[CButton::GetCursor](#getcursor)|İmleç görüntü tanıtıcısı ile önceden ayarlanan alır [SetCursor](#setcursor).|
|[CButton::GetIcon](#geticon)|İle önceden ayarlanan simgesi tanıtıcısını alır [SetIcon](#seticon).|
|[CButton::GetIdealSize](#getidealsize)|Düğme denetimini ideal VHD'nin boyutunu alır.|
|[CButton::GetImageList](#getimagelist)|Düğme denetimini görüntü listesini alır.|
|[CButton::GetNote](#getnote)|Geçerli komut bağlantı denetimi Not bileşeninin alır.|
|[CButton::GetNoteLength](#getnotelength)|Geçerli komut bağlantı denetimi için Not metnin uzunluğunu alır.|
|[CButton::GetSplitGlyph](#getsplitglyph)|Geçerli Bölünmüş düğme denetimi ile ilişkili simge alır.|
|[CButton::GetSplitImageList](#getsplitimagelist)|Geçerli Bölünmüş düğme denetimi için resim listesi alır.|
|[CButton::GetSplitInfo](#getsplitinfo)|Geçerli Bölünmüş düğme denetimi tanımlayan bilgileri alır.|
|[CButton::GetSplitSize](#getsplitsize)|Geçerli Bölünmüş düğme denetimi aşağı açılan bileşeninin sınırlayıcı dikdörtgeni alır.|
|[CButton::GetSplitStyle](#getsplitstyle)|Geçerli Bölünmüş düğme denetimi tanımlayan Bölünmüş düğme stilleri alır.|
|[CButton::GetState](#getstate)|Onay durumu, vurgulama durumunu ve bir düğme denetimi odak durumunu alır.|
|[CButton::GetTextMargin](#gettextmargin)|Düğme denetiminin metin kenar alır.|
|[CButton::SetBitmap](#setbitmap)|Düğme üzerinde görüntülenecek bir bit eşlem belirtir.|
|[CButton::SetButtonStyle](#setbuttonstyle)|Bir düğmenin stilini değiştirir.|
|[CButton::SetCheck](#setcheck)|Bir düğme denetimi onay durumunu ayarlar.|
|[CButton::SetCursor](#setcursor)|Düğme üzerinde görüntülenecek imleç resmi belirtir.|
|[CButton::SetDropDownState](#setdropdownstate)|Geçerli Bölünmüş düğme denetimi aşağı açılan durumunu ayarlar.|
|[CButton::SetIcon](#seticon)|Düğme üzerinde görüntülenecek bir simge belirtir.|
|[CButton::SetImageList](#setimagelist)|Düğme denetiminin resim listesi ayarlar.|
|[CButton::SetNote](#setnote)|Not, geçerli komut bağlantı denetimi ayarlar.|
|[CButton::SetSplitGlyph](#setsplitglyph)|Belirtilen karakter geçerli Bölünmüş düğme denetimi ile ilişkilendirir.|
|[CButton::SetSplitImageList](#setsplitimagelist)|Görüntü listesi geçerli Bölünmüş düğme denetimi ile ilişkilendirir.|
|[CButton::SetSplitInfo](#setsplitinfo)|Geçerli Bölünmüş düğme denetimi tanımlayan bilgileri belirtir.|
|[CButton::SetSplitSize](#setsplitsize)|Geçerli Bölünmüş düğme denetimi aşağı açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.|
|[CButton::SetSplitStyle](#setsplitstyle)|Geçerli Bölünmüş düğme denetiminin stilini ayarlar.|
|[CButton::SetState](#setstate)|Bir düğme denetimi vurgulama durumunu ayarlar.|
|[CButton::SetTextMargin](#settextmargin)|Düğme denetiminin metin kenar ayarlar.|

## <a name="remarks"></a>Açıklamalar

Bir düğme denetimi açıp tıklanabilir bir dikdörtgen, küçük bir alt penceredir. Düğmeler, tek başına veya grup kullanılabilir ve ya da etiketli veya olmadan metin olarak görünür. Kullanıcı tıkladığında bir düğme genellikle görünümünü değiştirir.

Tipik düğmeler, onay kutusu, radyo düğmesi ve basma düğmesi bulunur. A `CButton` nesne aşağıdakilerden herhangi biri, dönüşebilir göre [button style](../../mfc/reference/styles-used-by-mfc.md#button-styles) başlatılmasını tarafından belirtilen [Oluştur](#create) üye işlevi.

Ayrıca, [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md) türetilmiş sınıf `CButton` metin yerine bit eşlem görüntülerle etiketlenmiş düğme denetimleri oluşturmayı destekler. A `CBitmapButton` bir düğme kullanıcının, aşağı, odaklanmış ve devre durumları için ayrı bir bit eşlemler olabilir.

Bir iletişim kutusu şablonundan ya da kodunuzda doğrudan bir düğme denetimi oluşturabilirsiniz. Her iki durumda da Oluşturucu çağırmanız `CButton` oluşturmak için `CButton` nesne; ardından çağırarak `Create` üye işlevi Windows oluşturmak için düğme denetimi ve ekleyebilir `CButton` nesne.

Yapı, türetilen bir sınıf tek adımlı işlemde olabilir `CButton`. Bir oluşturucu çağrı ve türetilen sınıf için yazma `Create` gelen oluşturucu içinde.

Düğme denetimi tarafından yollanır Windows bildirim iletilerini işlemek isterseniz (öğesinden türetilmiş bir sınıf genellikle [CDialog](../../mfc/reference/cdialog-class.md)), üst sınıfın her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

**ON_** bildirim **(**`id`, `memberFxn` **)**

Burada `id` bildirimi gönderilmesi denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazdığınız üst üye işlev adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

**afx_msg** `void` `memberFxn` **();**

Olası ileti eşlemesi girişleri aşağıdaki gibidir:

|Eşleme girişi|Ne zaman üst gönderilmesini...|
|---------------|----------------------------|
|ON_BN_CLICKED|Kullanıcı bir düğmesine tıklar.|
|ON_BN_DOUBLECLICKED|Kullanıcı bir düğmeye çift tıklamaları birbirinden ayırma.|

Oluşturursanız, bir `CButton` bir iletişim kutusu kaynağı nesneden `CButton` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

Oluşturursanız, bir `CButton` nesnesi bir pencere içinde yok etmek gerekebilir. Oluşturursanız `CButton` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** kullanıcı Windows kapandığında yok etmek için nesneye button denetimi. Oluşturursanız `CButton` nesne iletişim katıştırılmış nesne yığını veya üzerinde otomatik olarak yok.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

`CButton`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="cbutton"></a>  CButton::CButton

Oluşturur bir `CButton` nesne.

```
CButton();
```

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#1](../../mfc/reference/codesnippet/cpp/cbutton-class_1.cpp)]

##  <a name="create"></a>  CButton::Create

Windows düğme denetimini oluşturur ve ona ekler `CButton` nesne.

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
Düğme denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [düğmesi stilleri](../../mfc/reference/styles-used-by-mfc.md#button-styles) düğmesine.

*Rect*<br/>
Düğme denetiminin boyutunu ve konumunu belirtir. Ya da olabilir bir `CRect` nesnesi veya bir `RECT` yapısı.

*pParentWnd*<br/>
Düğme denetiminin üst penceresine, genellikle belirtir bir `CDialog`. NULL olmamalıdır.

*nID*<br/>
Düğme denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CButton` iki adımda nesne. İlk olarak, oluşturucusunu çağırın ve ardından arama `Create`, hangi Windows düğme denetimini oluşturur ve ona ekler `CButton` nesne.

Ws_vısıble stili belirtilmezse, Windows düğme denetimini etkinleştirmek ve düğmeyi göstermek için gerekli tüm iletileri gönderir.

Aşağıdaki uygulama [pencere stilleri](../../mfc/reference/styles-used-by-mfc.md#window-styles) bir düğme denetimi için:

- WS_CHILD her zaman

- Ws_vısıble genellikle

- Ws_dısabled nadiren

- WS_GROUP grup denetimleri için

- WS_TABSTOP için düğmeyi sekme sırasını ekleyin

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#2](../../mfc/reference/codesnippet/cpp/cbutton-class_2.cpp)]

##  <a name="drawitem"></a>  CButton::DrawItem

Sahip tarafından çizilmiş bir düğmenin görsel bir özelliği değiştiğinde framework tarafından çağırılır.

```
virtual void DrawItem(LPDRAWITEMSTRUCT lpDrawItemStruct);
```

### <a name="parameters"></a>Parametreler

*lpDrawItemStruct*<br/>
Uzun bir işaretçi bir [DRAWITEMSTRUCT](../../mfc/reference/drawitemstruct-structure.md) yapısı. Yapı çizilecek öğesi ve gerekli çizim türü hakkında bilgi içerir.

### <a name="remarks"></a>Açıklamalar

Özelleştirilmiş olarak çizilen bir düğme BS_OWNERDRAW stil kümesi vardır. Çizim için bir sahip tarafından çizilmiş uygulamak için bu üye işlevi geçersiz kılma `CButton` nesne. Uygulama görünen bağlam sağlanan için seçilen tüm grafik cihaz arabirimi (GDI) nesneleri geri yüklemeniz gerekir *lpDrawItemStruct* önce üye işlevi sonlandırır.

Ayrıca bkz: [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#3](../../mfc/reference/codesnippet/cpp/cbutton-class_3.cpp)]

##  <a name="getbitmap"></a>  CButton::GetBitmap

İle önceden ayarlanmış bir bit eşlem tanıtıcısını almak için bu üye işlevi çağrısı [SetBitmap](#setbitmap), yani bir düğme ile ilişkili.

```
HBITMAP GetBitmap() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir bit eşlem işleyici. Hiçbir bit eşlem daha önce belirtilen yoksa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="getbuttonstyle"></a>  CButton::GetButtonStyle

Düğme denetimi stil hakkındaki bilgileri alır.

```
UINT GetButtonStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düğme stilleri bu döndürür `CButton` nesne. Bu işlev yalnızca döndürür [BS_](../../mfc/reference/styles-used-by-mfc.md#button-styles) stil değerleri, herhangi bir pencere stilleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="getcheck"></a>  CButton::GetCheck

Radyo düğmesinin veya onay kutusunun onay durumunu alır.

```
int GetCheck() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri bir düğme denetimi BS_AUTOCHECKBOX bs_autoradıobutton, BS_AUTO3STATE, BS_CHECKBOX, bs_radıobutton ile oluşturulan veya BS_3STATE stili aşağıdaki değerlerden biri:

|Değer|Açıklama|
|-----------|-------------|
|BST_UNCHECKED|Düğme durumu olarak işaretli değildir.|
|BST_CHECKED|Düğme durumu denetlenir.|
|BST_INDETERMINATE|Düğme durumu belirsiz olan (yalnızca düğme BS_3STATE veya BS_AUTO3STATE stili varsa geçerlidir).|

Düğmeyi herhangi diğer stil varsa, dönüş değeri BST_UNCHECKED olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="getcursor"></a>  CButton::GetCursor

İle önceden ayarlanmış bir imleç tanıtıcısını almak için bu üye işlevi çağrısı [SetCursor](#setcursor), yani bir düğme ile ilişkili.

```
HCURSOR GetCursor();
```

### <a name="return-value"></a>Dönüş Değeri

İmleç görüntü için bir tanıtıcı. Hiçbir imleç daha önce belirtilen yoksa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="geticon"></a>  CButton::GetIcon

İle önceden ayarlanan simge tanıtıcısını almak için bu üye işlevi çağrısı [SetIcon](#seticon), yani bir düğme ile ilişkili.

```
HICON GetIcon() const;
```

### <a name="return-value"></a>Dönüş Değeri

Simge tanıtıcı. Herhangi bir simge daha önce belirtilen yoksa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="getidealsize"></a>  CButton::GetIdealSize

İdeal boyutu için düğme denetimini alır.

```
BOOL GetIdealSize(SIZE* psize);
```

### <a name="parameters"></a>Parametreler

*psize*<br/>
Düğmenin geçerli boyutu için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi BCM_GETIDEALSIZE ileti işlevselliğini açıklandığı öykünür [düğmeleri](https://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK'sı bölümünü.

##  <a name="getimagelist"></a>  CButton::GetImageList

Görüntü listesi düğme denetiminden almak için bu yöntemi çağırın.

```
BOOL GetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*pbuttonImagelist*<br/>
Resim listesi için bir işaretçi `CButton` nesne.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi BCM_GETIMAGELIST ileti işlevselliğini açıklandığı öykünür [düğmeleri](https://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK'sı bölümünü.

##  <a name="getnote"></a>  CButton::GetNote

Geçerli komut bağlantı denetimle ilişkili not metni alır.

```
CString GetNote() const;

BOOL GetNote(
    LPTSTR lpszNote,
    UINT* cchNote) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszNote*|[out] İşaretçi bir arabellek ayırma ve serbest bırakılıyor çağıran sorumludur. Dönüş değeri TRUE ise, geçerli komut bağlantı denetimle ilişkili not metni arabellek içerir. Aksi takdirde, arabellek değiştirilmez.|
|*cchNote*|[out içinde] Bir işaretsiz tamsayı değişkeni için bir işaretçi.<br /><br /> Bu yöntem çağrıldığında, değişkeni tarafından belirtilen arabellek boyutu içeren *lpszNote* parametresi.<br /><br /> Ne zaman dönüş değeri TRUE değişkeni ise bu yöntemi döndürür, geçerli komut bağlantı denetimle ilişkili Not boyutunu içerir. Dönüş değeri FALSE ise, değişken Not içerecek şekilde gerekli arabellek boyutunu içerir.|

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yükleme içinde bir [CString](../../atl-mfc-shared/using-cstring.md) geçerli komut bağlantı denetimle ilişkili not metni içeren nesne.

veya

İkinci aşırı yükleme, bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_COMMANDLINK BS_DEFCOMMANDLINK mi denetimleri ile kullanın.

Bu yöntem gönderir [BCM_GETNOTE](/windows/desktop/Controls/bcm-getnote) Windows SDK'da açıklanan ileti.

##  <a name="getnotelength"></a>  CButton::GetNoteLength

Geçerli komut bağlantı denetimi için Not metnin uzunluğunu alır.

```
UINT GetNoteLength() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli komut bağlantı denetimi için 16 bitlik Unicode karakterleriyle Not metnin uzunluğu.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_COMMANDLINK BS_DEFCOMMANDLINK mi denetimleri ile kullanın.

Bu yöntem gönderir [BCM_GETNOTELENGTH](/windows/desktop/Controls/bcm-getnotelength) Windows SDK'da açıklanan ileti.

##  <a name="getsplitglyph"></a>  CButton::GetSplitGlyph

Geçerli Bölünmüş düğme denetimi ile ilişkili simge alır.

```
TCHAR GetSplitGlyph() const;
```

### <a name="return-value"></a>Dönüş Değeri

Karakter karakter geçerli Bölünmüş düğme denetimi ile ilişkili.

### <a name="remarks"></a>Açıklamalar

Bir karakter bir karakter, belirli bir yazı tipi fiziksel gösterimidir. Örneğin, Bölünmüş düğme denetimini onay işareti karakterin Unicode karakter ile düzenlenmiş (U + 2713).

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_GLYPH bayrağı ve ardından, yapı gönderir yapısıyla [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) açıklanan iletisi Windows SDK'sı. İleti işlevi döndüğünde, bu yöntem glif alır `himlGlyph` yapı üyesi.

##  <a name="getsplitimagelist"></a>  CButton::GetSplitImageList

Alır [görüntü listesi](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetimi için.

```
CImageList* GetSplitImageList() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) nesne.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_IMAGE bayrağı ve ardından, yapı gönderir yapısıyla [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) açıklanan iletisi Windows SDK'sı. İleti işlevi döndüğünde, bu yöntem, görüntü listesinden görüntü alır. `himlGlyph` yapı üyesi.

##  <a name="getsplitinfo"></a>  CButton::GetSplitInfo

Nasıl Windows geçerli bölünmüş düğmesi denetimi çizen belirlemek parametrelerini alır.

```
BOOL GetSplitInfo(PBUTTON_SPLITINFO pInfo) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pInfo*|[out] İşaretçi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) yapısı geçerli Bölünmüş düğme denetimi ile ilgili bilgileri alır. Yapı ayırma için çağıran sorumludur.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bu yöntem gönderir [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Windows SDK'da açıklanan ileti.

##  <a name="getsplitsize"></a>  CButton::GetSplitSize

Geçerli Bölünmüş düğme denetimi aşağı açılan bileşeninin sınırlayıcı dikdörtgeni alır.

```
BOOL GetSplitSize(LPSIZE pSize) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSize*|[out] İşaretçi bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı bir dikdörtgen açıklamasını alır.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bölünmüş düğme denetimi genişletildiğinde, onu bir liste denetimini veya çağrı cihazı denetimi gibi bir açılan bileşen görüntüleyebilirsiniz. Bu yöntem açılan bileşeni içeren dikdörtgen alır.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_SIZE bayrağı ve ardından, yapı gönderir yapısıyla [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) açıklanan iletisi Windows SDK'sı. İleti işlevi döndüğünde, bu yöntem gelen sınırlayıcı dikdörtgeni alır `size` yapı üyesi.

##  <a name="getsplitstyle"></a>  CButton::GetSplitStyle

Geçerli Bölünmüş düğme denetimi tanımlayan Bölünmüş düğme stilleri alır.

```
UINT GetSplitStyle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bölünmüş düğme stilleri Bitsel bir birleşimi. Daha fazla bilgi için `uSplitStyle` üyesi [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) yapısı.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bölünmüş düğme stilleri, hizalama, en boy oranı ve bir Bölünmüş düğme simgesi ile Windows çizer grafik biçiminde belirtin.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_STYLE bayrağı ve ardından, yapı gönderir yapısıyla [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) açıklanan iletisi Windows SDK'sı. İleti işlevi döndüğünde, bu yöntem, Bölünmüş düğme stillerini alır. `uSplitStyle` yapı üyesi.

##  <a name="getstate"></a>  CButton::GetState

Bir düğme denetimi durumunu alır.

```
UINT GetState() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir düğme denetimi geçerli durumunu gösteren kombinaci hodnot bir bit alanı. Olası değerler aşağıdaki tabloda listelenmektedir.

|Düğme durumu|Değer|Açıklama|
|------------------|-----------|-----------------|
|BST_UNCHECKED|0x0000|Başlangıç durumu.|
|BST_CHECKED|0x0001|Düğme denetimini denetlenir.|
|BST_INDETERMINATE|0x0002|Durum (düğme denetimini üç duruma sahip olduğunda belirsiz yalnızca) mümkündür.|
|BST_PUSHED|0x0004|Düğme denetimini basıldığında.|
|BST_FOCUS|0x0008|Düğme denetim odağa sahip.|

### <a name="remarks"></a>Açıklamalar

Bir düğme denetimi BS_3STATE veya BS_AUTO3STATE düğmesi stiliyle belirlenmemiş duruma adlı üçüncü bir duruma sahip bir onay kutusu oluşturur. Belirlenmemiş bir durum, onay kutusunu işaretli veya işaretlenmemiş olduğunu gösterir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="gettextmargin"></a>  CButton::GetTextMargin

Metin Kenar almak için bu yöntemi çağırın `CButton` nesne.

```
BOOL GetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*pmargin*<br/>
Metin Kenar işaretçisi `CButton` nesne.

### <a name="return-value"></a>Dönüş Değeri

Metin Kenar döndürür.

### <a name="remarks"></a>Açıklamalar

Başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi BCM_GETTEXTMARGIN ileti işlevselliğini açıklandığı öykünür [düğmeleri](https://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK'sı bölümünü.

##  <a name="setbitmap"></a>  CButton::SetBitmap

Yeni bir bit eşlem düğmesi ile ilişkilendirmek için bu üye işlevini çağırın.

```
HBITMAP SetBitmap(HBITMAP hBitmap);
```

### <a name="parameters"></a>Parametreler

*Hbıtmap*<br/>
Bir bit eşlem tanıtıcısı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmesi ile ilişkili bir bit eşlem tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

Bit eşlem otomatik olarak varsayılan olarak Orta düğmeye değişmiştir yerleştirilir. Bit eşlem düğmesi için çok büyük ise, iki tarafında kırpılır. Aşağıdakiler dahil olmak üzere diğer hizalama seçeneklerini birini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Farklı [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetBitmap` düğme başına yalnızca bir bit eşlem kullanır. Düğmeye basıldığında, aşağı ve sağa kaydırılacak bit eşlem görünür.

Bit eşlem ile işiniz bittiğinde serbest için sorumlu olursunuz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#4](../../mfc/reference/codesnippet/cpp/cbutton-class_4.cpp)]

##  <a name="setbuttonstyle"></a>  CButton::SetButtonStyle

Bir düğmenin stilini değiştirir.

```
void SetButtonStyle(
    UINT nStyle,
    BOOL bRedraw = TRUE);
```

### <a name="parameters"></a>Parametreler

*nStyle*<br/>
Belirtir [button style](../../mfc/reference/styles-used-by-mfc.md#button-styles).

*bRedraw*<br/>
Düğmenin yeniden çizilmesi olup olmadığını belirtir. Sıfır dışında bir değeri, düğmeyi yeniden çizer. 0 değeri, düğmeyi çizmez. Düğme, varsayılan olarak çizilir.

### <a name="remarks"></a>Açıklamalar

Kullanım `GetButtonStyle` düğme stilini almak için üye işlevi. Düşük düzey sözcüğü Tamamla düğmesine stili düğme özgü stilidir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#5](../../mfc/reference/codesnippet/cpp/cbutton-class_5.cpp)]

##  <a name="setcheck"></a>  CButton::SetCheck

Ayarlar veya radyo düğmesinin veya onay kutusunun onay durumunu sıfırlar.

```
void SetCheck(int nCheck);
```

### <a name="parameters"></a>Parametreler

*Nbakım*<br/>
Onay durumunu belirtir. Bu parametre, aşağıdakilerden biri olabilir:

|Değer|Açıklama|
|-----------|-------------|
|BST_UNCHECKED|Düğme durumu işaretlenmemiş olarak ayarlayın.|
|BST_CHECKED|Düğme işaretli durumuna ayarlayın.|
|BST_INDETERMINATE|Düğme durumu belirsiz şekilde ayarlayın. Bu değer yalnızca düğme BS_3STATE veya BS_AUTO3STATE bir stile sahipse kullanılabilir.|

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi bir basma düğmesi üzerinde etkisi yoktur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#6](../../mfc/reference/codesnippet/cpp/cbutton-class_6.cpp)]

##  <a name="setcursor"></a>  CButton::SetCursor

Yeni imleç düğmesi ile ilişkilendirmek için bu üye işlevini çağırın.

```
HCURSOR SetCursor(HCURSOR hCursor);
```

### <a name="parameters"></a>Parametreler

*hCursor*<br/>
İmleç tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce düğmesi ile ilişkili bir imleç tanıtıcı.

### <a name="remarks"></a>Açıklamalar

İmleç, otomatik olarak varsayılan olarak Orta düğmeye değişmiştir yerleştirilir. İmleç düğme için çok büyük ise, iki tarafında kırpılır. Aşağıdakiler dahil olmak üzere diğer hizalama seçeneklerini birini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Farklı [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetCursor` düğme başına yalnızca bir imleç kullanır. Düğmeye basıldığında, imleç aşağı ve sağa kaydırma için görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#7](../../mfc/reference/codesnippet/cpp/cbutton-class_7.cpp)]

##  <a name="setdropdownstate"></a>  CButton::SetDropDownState

Geçerli Bölünmüş düğme denetimi aşağı açılan durumunu ayarlar.

```
BOOL SetDropDownState(BOOL fDropDown);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fDropDown*|[in] BST_DROPDOWNPUSHED durumu ayarlamak için TRUE; Aksi takdirde FALSE.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bölünmüş düğme denetimini BS_SPLITBUTTON veya BS_DEFSPLITBUTTON stili vardır ve bir düğmeyi ve sağındaki açılan oku oluşur. Daha fazla bilgi için [düğme stilleri](/windows/desktop/Controls/button-styles). Genellikle, kullanıcı aşağı açılan okunu tıkladığında açılan durumu ayarlanır. Aşağı açılan durum denetimi program üzerinden ayarlamak için bu yöntemi kullanın. Aşağı açılan oku durumu göstermek için gölgeli çizilir.

Bu yöntem gönderir [BCM_SETDROPDOWNSTATE](/windows/desktop/Controls/bcm-setdropdownstate) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar *m_splitButton*diğer bir deyişle, Bölünmüş düğme denetimi programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, açılan liste okunu gönderildiğinde belirtmek için Bölünmüş düğme denetimi durumunu ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#6](../../mfc/reference/codesnippet/cpp/cbutton-class_11.cpp)]

##  <a name="setelevationrequired"></a>  CButton::SetElevationRequired

Geçerli bir düğme denetimi için ayarlar `elevation required`, yükseltilmiş güvenlik simge görüntülemek denetim için gerekli.

```
BOOL SetElevationRequired(BOOL fElevationRequired);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*fElevationRequired*|[in] Kümesi true `elevation required` durum; Aksi takdirde FALSE.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir düğme veya komut bağlantı denetimi bir eylemi gerçekleştirmek için yükseltilmiş bir güvenlik izni gerektiriyorsa, denetimin kümesine `elevation required` durumu. Sonuç olarak, Windows kullanıcı hesabı denetimi (UAC) Kalkan simgesi denetiminde görüntüler. Daha fazla bilgi için bkz: "Kullanıcı hesabı denetimi" [MSDN](http://go.microsoft.com/fwlink/p/?linkid=18507).

Bu yöntem gönderir [BCM_SETSHIELD](/windows/desktop/Controls/bcm-setshield) Windows SDK'da açıklanan ileti.

##  <a name="seticon"></a>  CButton::SetIcon

Rapordaki yeni simge, düğme ile ilişkilendirmek için bu üye işlevini çağırın.

```
HICON SetIcon(HICON hIcon);
```

### <a name="parameters"></a>Parametreler

*hIcon*<br/>
Simge tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Daha önce ilişkili düğme simge tanıtıcı.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak Orta düğmeye değişmiştir simge otomatik olarak yer alır. Simge düğme için çok büyük ise, iki tarafında kırpılır. Aşağıdakiler dahil olmak üzere diğer hizalama seçeneklerini birini seçebilirsiniz:

- BS_TOP

- BS_LEFT

- BS_RIGHT

- BS_CENTER

- BS_BOTTOM

- BS_VCENTER

Aksine [CBitmapButton](../../mfc/reference/cbitmapbutton-class.md), düğme başına dört bit eşlemler kullanan `SetIcon` düğme başına yalnızca bir simge kullanılır. Düğmeye basıldığında, aşağı ve sağa kaydırılacak simgesi görünür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#8](../../mfc/reference/codesnippet/cpp/cbutton-class_8.cpp)]

##  <a name="setimagelist"></a>  CButton::SetImageList

Görüntü listesi için bu yöntemi çağırın `CButton` nesne.

```
BOOL SetImageList(PBUTTON_IMAGELIST pbuttonImagelist);
```

### <a name="parameters"></a>Parametreler

*pbuttonImagelist*<br/>
Yeni görüntü listesi için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi BCM_SETIMAGELIST ileti işlevselliğini açıklandığı öykünür [düğmeleri](https://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK'sı bölümünü.

##  <a name="setnote"></a>  CButton::SetNote

Not metni geçerli komut bağlantı denetimi için ayarlar.

```
BOOL SetNote(LPCTSTR lpszNote);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*lpszNote*|[in] Komut bağlantı denetimi için Not metni olarak ayarlanmış bir Unicode dize işaretçisi.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_COMMANDLINK BS_DEFCOMMANDLINK mi denetimleri ile kullanın.

Bu yöntem gönderir [BCM_SETNOTE](/windows/desktop/Controls/bcm-setnote) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar *m_cmdLink*, yani komut bağlantı denetimi programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Not metni komut bağlantı denetimi için ayarlar.

[!code-cpp[NVC_MFC_CButton_s1#7](../../mfc/reference/codesnippet/cpp/cbutton-class_12.cpp)]

##  <a name="setsplitglyph"></a>  CButton::SetSplitGlyph

Belirtilen karakter geçerli Bölünmüş düğme denetimi ile ilişkilendirir.

```
BOOL SetSplitGlyph(TCHAR chGlyph);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*chGlyph*|[in] Bölünmüş düğme açılan liste okunu kullanılacak karakter belirten bir karakter.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca BS_SPLITBUTTON veya BS_DEFSPLITBUTTON düğmeye stil denetimleri ile kullanın.

Bir karakter bir karakter, belirli bir yazı tipi fiziksel gösterimidir. *ChGlyph* parametresi karakter kullanılmaz, ancak bunun yerine sistem tarafından tanımlanan karakter kümesinden bir simge seçmek için kullanılır. Varsayılan açılan liste okunu karakter '6' karakteriyle belirtilir ve Unicode karakteri aşağı siyah ÜÇGEN (U + 25BC) benzer.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_GLYPH bayrağıyla yapısı ve `himlGlyph` üyesiyle *chGlyph* parametresi ve ardından gönderen içindeki yapı [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Windows SDK'da açıklanan ileti.

##  <a name="setsplitimagelist"></a>  CButton::SetSplitImageList

İlişkilendirir bir [görüntü listesi](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetimi ile.

```
BOOL SetSplitImageList(CImageList* pSplitImageList);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSplitImageList*|[in] İşaretçi bir [Cımagelist](../../mfc/reference/cimagelist-class.md) geçerli Bölünmüş düğme denetimi atamak için nesne.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_IMAGE bayrağıyla yapısı ve `himlGlyph` üyesiyle *pSplitImageList* parametresi ve gönderir Bu yapıda [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Windows SDK'da açıklanan ileti.

##  <a name="setsplitinfo"></a>  CButton::SetSplitInfo

Nasıl Windows geçerli bölünmüş düğmesi denetimi çizen belirleyen parametreleri belirtir.

```
BOOL SetSplitInfo(PBUTTON_SPLITINFO pInfo);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pInfo*|[in] İşaretçi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) geçerli Bölünmüş düğme denetimi tanımlayan yapısını.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bu yöntem gönderir [BCM_SETSPLITINFO](/windows/desktop/Controls/bcm-setsplitinfo) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_splitButton`diğer bir deyişle, Bölünmüş düğme denetimi programlı olarak erişmek için kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği için Bölünmüş düğme açılan liste okunu kullanılan glif değişir. Örneğin, varsayılan aşağı işaret eden üçgen karakter için yukarı işaret eden bir üçgen glif yerini alır. Belirttiğiniz karakter görüntülenen glif bağımlı `himlGlyph` üyesi `BUTTON_SPLITINFO` yapısı. Aşağı işaret eden üçgen glif karakteriyle ' 6 belirtilir 've yukarı gösteren üçgen glif karakteriyle 5 ' belirtildiğinden'. Kolaylık yöntemi karşılaştırması için bkz [CButton::SetSplitGlyph](#setsplitglyph).

[!code-cpp[NVC_MFC_CButton_s1#4](../../mfc/reference/codesnippet/cpp/cbutton-class_13.cpp)]

##  <a name="setsplitsize"></a>  CButton::SetSplitSize

Geçerli Bölünmüş düğme denetimi aşağı açılan bileşeninin sınırlayıcı dikdörtgenini ayarlar.

```
BOOL SetSplitSize(LPSIZE pSize);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pSize*|[in] İşaretçi bir [BOYUTU](https://msdn.microsoft.com/library/windows/desktop/dd145106) sınırlayıcı bir dikdörtgen açıklayan yapısı.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bölünmüş düğme denetimi genişletildiğinde, onu bir liste denetimini veya çağrı cihazı denetimi gibi bir açılan bileşen görüntüleyebilirsiniz. Bu yöntem açılan bileşeni içeren dikdörtgen boyutunu belirtir.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_SIZE bayrağıyla yapısı ve `size` üyesiyle *pSize* parametresi ve yapı gönderir içinde [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_splitButton`diğer bir deyişle, Bölünmüş düğme denetimi programlı olarak erişmek için kullanılır. Bu değişken, aşağıdaki örnekte kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği Bölünmüş düğme açılan liste okunu boyutunun iki katına çıkar.

[!code-cpp[NVC_MFC_CButton_s1#5](../../mfc/reference/codesnippet/cpp/cbutton-class_14.cpp)]

##  <a name="setsplitstyle"></a>  CButton::SetSplitStyle

Geçerli Bölünmüş düğme denetiminin stilini ayarlar.

```
BOOL SetSplitStyle(UINT uSplitStyle);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*uSplitStyle*|[in] Bölünmüş düğme stilleri Bitsel bir birleşimi. Daha fazla bilgi için `uSplitStyle` üyesi [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) yapısı.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem yalnızca düğme stilini BS_SPLITBUTTON BS_DEFSPLITBUTTON mi denetimleri ile kullanın.

Bölünmüş düğme stilleri, hizalama, en boy oranı ve bir Bölünmüş düğme simgesi ile Windows çizer grafik biçiminde belirtin. Daha fazla bilgi için `uSplitStyle` üyesi [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) yapısı.

Bu yöntem başlatır `mask` üyesi bir [BUTTON_SPLITINFO](/windows/desktop/api/commctrl/ns-commctrl-tagbutton_splitinfo) BCSIF_STYLE bayrağıyla yapısı ve `uSplitStyle` üyesiyle *uSplitStyle* parametresi ve ardından gönderen içindeki yapı [BCM_GETSPLITINFO](/windows/desktop/Controls/bcm-getsplitinfo) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği değişkeni tanımlar `m_splitButton`diğer bir deyişle, Bölünmüş düğme denetimi programlı olarak erişmek için kullanılır.

[!code-cpp[NVC_MFC_CButton_s1#1](../../mfc/reference/codesnippet/cpp/cbutton-class_10.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, Bölünmüş düğme aşağı açılan ok stilini ayarlar. Düğmeyi yeniden boyutlandırdığınızda BCSS_STRETCH stili açılan arrow'un oranını korur ve BCSS_ALIGNLEFT stili düğme sol tarafındaki oku görüntüler.

[!code-cpp[NVC_MFC_CButton_s1#3](../../mfc/reference/codesnippet/cpp/cbutton-class_15.cpp)]

##  <a name="setstate"></a>  CButton::SetState

Bir düğme denetimi veya vurgulanır olup olmadığını belirler.

```
void SetState(BOOL bHighlight);
```

### <a name="parameters"></a>Parametreler

*bHighlight*<br/>
Düğme vurgulanmasını olup olmadığını belirtir. Sıfır dışında bir değeri, düğmeyi vurgular; 0 değeri herhangi bir vurgulama kaldırır.

### <a name="remarks"></a>Açıklamalar

Vurgulama düğmesi denetimi dış etkiler. Radyo düğmesinin veya onay kutusunun onay durumunu bir etkisi yoktur.

Kullanıcı tıkladığında ve farenin sol düğmesine tutan bir düğme denetimi otomatik olarak vurgulanır. Kullanıcı fare düğmesini bıraktığında Vurgulama kaldırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CButton#9](../../mfc/reference/codesnippet/cpp/cbutton-class_9.cpp)]

##  <a name="settextmargin"></a>  CButton::SetTextMargin

Metin Kenar ayarlamak için bu yöntemi çağırın `CButton` nesne.

```
BOOL SetTextMargin(RECT* pmargin);
```

### <a name="parameters"></a>Parametreler

*pmargin*<br/>
Yeni metin kenar işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olduğunda TRUE döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi BCM_SETTEXTMARGIN ileti işlevselliğini açıklandığı öykünür [düğmeleri](https://msdn.microsoft.com/library/windows/desktop/bb775943) Windows SDK'sı bölümünü.

## <a name="see-also"></a>Ayrıca Bkz.

[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[CComboBox Sınıfı](../../mfc/reference/ccombobox-class.md)<br/>
[CEdit Sınıfı](../../mfc/reference/cedit-class.md)<br/>
[CListBox Sınıfı](../../mfc/reference/clistbox-class.md)<br/>
[CScrollBar Sınıfı](../../mfc/reference/cscrollbar-class.md)<br/>
[CStatic Sınıfı](../../mfc/reference/cstatic-class.md)<br/>
[CBitmapButton Sınıfı](../../mfc/reference/cbitmapbutton-class.md)<br/>
[CDialog Sınıfı](../../mfc/reference/cdialog-class.md)
