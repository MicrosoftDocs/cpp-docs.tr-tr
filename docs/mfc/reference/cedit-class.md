---
title: Cedıt sınıfı
ms.date: 09/12/2018
f1_keywords:
- CEdit
- AFXWIN/CEdit
- AFXWIN/CEdit::CEdit
- AFXWIN/CEdit::CanUndo
- AFXWIN/CEdit::CharFromPos
- AFXWIN/CEdit::Clear
- AFXWIN/CEdit::Copy
- AFXWIN/CEdit::Create
- AFXWIN/CEdit::Cut
- AFXWIN/CEdit::EmptyUndoBuffer
- AFXWIN/CEdit::FmtLines
- AFXWIN/CEdit::GetCueBanner
- AFXWIN/CEdit::GetFirstVisibleLine
- AFXWIN/CEdit::GetHandle
- AFXWIN/CEdit::GetHighlight
- AFXWIN/CEdit::GetLimitText
- AFXWIN/CEdit::GetLine
- AFXWIN/CEdit::GetLineCount
- AFXWIN/CEdit::GetMargins
- AFXWIN/CEdit::GetModify
- AFXWIN/CEdit::GetPasswordChar
- AFXWIN/CEdit::GetRect
- AFXWIN/CEdit::GetSel
- AFXWIN/CEdit::HideBalloonTip
- AFXWIN/CEdit::LimitText
- AFXWIN/CEdit::LineFromChar
- AFXWIN/CEdit::LineIndex
- AFXWIN/CEdit::LineLength
- AFXWIN/CEdit::LineScroll
- AFXWIN/CEdit::Paste
- AFXWIN/CEdit::PosFromChar
- AFXWIN/CEdit::ReplaceSel
- AFXWIN/CEdit::SetCueBanner
- AFXWIN/CEdit::SetHandle
- AFXWIN/CEdit::SetHighlight
- AFXWIN/CEdit::SetLimitText
- AFXWIN/CEdit::SetMargins
- AFXWIN/CEdit::SetModify
- AFXWIN/CEdit::SetPasswordChar
- AFXWIN/CEdit::SetReadOnly
- AFXWIN/CEdit::SetRect
- AFXWIN/CEdit::SetRectNP
- AFXWIN/CEdit::SetSel
- AFXWIN/CEdit::SetTabStops
- AFXWIN/CEdit::ShowBalloonTip
- AFXWIN/CEdit::Undo
helpviewer_keywords:
- CEdit [MFC], CEdit
- CEdit [MFC], CanUndo
- CEdit [MFC], CharFromPos
- CEdit [MFC], Clear
- CEdit [MFC], Copy
- CEdit [MFC], Create
- CEdit [MFC], Cut
- CEdit [MFC], EmptyUndoBuffer
- CEdit [MFC], FmtLines
- CEdit [MFC], GetCueBanner
- CEdit [MFC], GetFirstVisibleLine
- CEdit [MFC], GetHandle
- CEdit [MFC], GetHighlight
- CEdit [MFC], GetLimitText
- CEdit [MFC], GetLine
- CEdit [MFC], GetLineCount
- CEdit [MFC], GetMargins
- CEdit [MFC], GetModify
- CEdit [MFC], GetPasswordChar
- CEdit [MFC], GetRect
- CEdit [MFC], GetSel
- CEdit [MFC], HideBalloonTip
- CEdit [MFC], LimitText
- CEdit [MFC], LineFromChar
- CEdit [MFC], LineIndex
- CEdit [MFC], LineLength
- CEdit [MFC], LineScroll
- CEdit [MFC], Paste
- CEdit [MFC], PosFromChar
- CEdit [MFC], ReplaceSel
- CEdit [MFC], SetCueBanner
- CEdit [MFC], SetHandle
- CEdit [MFC], SetHighlight
- CEdit [MFC], SetLimitText
- CEdit [MFC], SetMargins
- CEdit [MFC], SetModify
- CEdit [MFC], SetPasswordChar
- CEdit [MFC], SetReadOnly
- CEdit [MFC], SetRect
- CEdit [MFC], SetRectNP
- CEdit [MFC], SetSel
- CEdit [MFC], SetTabStops
- CEdit [MFC], ShowBalloonTip
- CEdit [MFC], Undo
ms.assetid: b1533c30-7f10-4663-88d3-8b7f2c9f7024
ms.openlocfilehash: 0e15472ddaad214d575a7479680454ae6b4d3178
ms.sourcegitcommit: 1839405b97036891b6e4d37c99def044d6f37eff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88561628"
---
# <a name="cedit-class"></a>Cedıt sınıfı

Windows düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Syntax

```
class CEdit : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Cedıt:: Cedıt](#cedit)|Bir `CEdit` denetim nesnesi oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cedıt:: CanUndo](#canundo)|Bir düzenleme denetimi işleminin geri döndürülüp alınamayacağını belirler.|
|[Cedıt:: CharFromPos](#charfrompos)|Belirtilen konuma en yakın karakterin satır ve karakter dizinlerini alır.|
|[Cedıt:: Clear](#clear)|Düzenleme denetimindeki geçerli seçimi (varsa) siler (siler).|
|[Cedıt:: Copy](#copy)|Düzenleme denetimindeki geçerli seçimi (varsa) Pano 'ya CF_TEXT biçiminde kopyalar.|
|[Cedıt:: Create](#create)|Windows düzenleme denetimini oluşturur ve `CEdit` nesneye ekler.|
|[Cedıt:: kes](#cut)|Düzenleme denetimindeki geçerli seçimi (varsa) siler ve silinen metni CF_TEXT biçimde panoya kopyalar.|
|[Cedıt:: EmptyUndoBuffer](#emptyundobuffer)|Bir düzenleme denetiminin geri alma bayrağını sıfırlar (temizler).|
|[Cedıt:: FmtLines](#fmtlines)|Çok satırlı bir düzenleme denetimi içinde, yumuşak çizgi kesme karakterlerinin dahil edilmesini veya kapatılmasını ayarlar.|
|[Cedıt:: Getcuebaşlık](#getcuebanner)|Denetim boş olduğunda ve odağa sahip olmadığında, metin ipucu veya ipucu olarak görüntülenen metni bir düzenleme denetiminde alır.|
|[Cedıt:: GetFirstVisibleLine](#getfirstvisibleline)|Bir düzenleme denetimindeki en üstteki görünür çizgiyi belirler.|
|[Cedıt:: GetHandle](#gethandle)|Birden çok satırlık bir düzenleme denetimi için ayrılmış olan belleğe yönelik bir tanıtıcı alır.|
|[Cedıt:: GetHighlight](#gethighlight)|Geçerli düzenleme denetiminde vurgulanan bir metin aralığındaki Başlangıç ve bitiş karakterlerinin dizinlerini alır.|
|[Cedıt:: GetLimitText](#getlimittext)|Bu, içerebileceği maksimum metin miktarını alır `CEdit` .|
|[Cedıt:: GetLine](#getline)|Bir düzenleme denetiminden bir metin satırı alır.|
|[Cedıt:: GetLineCount](#getlinecount)|Birden çok satırlık düzenleme denetimindeki satır sayısını alır.|
|[Cedıt:: Getkenar boşlukları](#getmargins)|Bunun için sol ve sağ kenar boşluklarını alır `CEdit` .|
|[Cedıt:: GetModify](#getmodify)|Bir düzenleme denetimi içeriğinin değiştirilip değiştirilmediğini belirler.|
|[Cedıt:: GetPasswordChar](#getpasswordchar)|Kullanıcı metin girdiğinde bir düzenleme denetiminde görünen parola karakterini alır.|
|[Cedıt:: GetRect](#getrect)|Bir düzenleme denetiminin biçimlendirme dikdörtgenini alır.|
|[Cedıt:: GetSel](#getsel)|Bir düzenleme denetimindeki geçerli seçimin ilk ve son karakter konumlarını alır.|
|[Cedıt:: HideBalloonTip](#hideballoontip)|Geçerli düzenleme denetimiyle ilişkili balon ucunu gizler.|
|[Cedıt:: LimitText](#limittext)|Kullanıcının bir düzenleme denetimine girebileceği metnin uzunluğunu sınırlandırır.|
|[Cedıt:: LineFromChar](#linefromchar)|Belirtilen karakter dizinini içeren satırın satır numarasını alır.|
|[Cedıt:: lineIndex](#lineindex)|Çok satırlı bir düzenleme denetimindeki bir çizginin karakter dizinini alır.|
|[Cedıt:: LineLength](#linelength)|Bir düzenleme denetimindeki bir çizginin uzunluğunu alır.|
|[Cedıt:: LineScroll](#linescroll)|Birden çok satırlı bir düzenleme denetiminin metnini kaydırır.|
|[Cedıt::P aste](#paste)|Panodaki verileri, geçerli imleç konumundaki düzenleme denetimine ekler. Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.|
|[Cedıt::P osFromChar](#posfromchar)|Belirtilen karakter dizininin sol üst köşesinin koordinatlarını alır.|
|[Cedıt:: ReplaceSel](#replacesel)|Bir düzenleme denetimindeki geçerli seçimi belirtilen metinle değiştirir.|
|[Cedıt:: Setcuebaşlık](#setcuebanner)|Denetim boş olduğunda ve odağa sahip olmadığında, metin ipucu veya ipucu olarak görüntülenen metni bir düzenleme denetiminde ayarlar.|
|[Cedıt:: SetHandle](#sethandle)|Tanıtıcıyı, çok satırlı bir düzenleme denetimi tarafından kullanılacak yerel bellek olarak ayarlar.|
|[Cedıt:: SetHighlight](#sethighlight)|Geçerli düzenleme denetiminde görüntülenen bir metin aralığını vurgular.|
|[Cedıt:: SetLimitText](#setlimittext)|Bu, içerebileceği maksimum metin miktarını ayarlar `CEdit` .|
|[Cedıt:: Setkenar boşlukları](#setmargins)|Bunun için sol ve sağ kenar boşluklarını ayarlar `CEdit` .|
|[Cedıt:: SetModify](#setmodify)|Bir düzenleme denetimi için değişiklik bayrağını ayarlar veya temizler.|
|[Cedıt:: SetPasswordChar](#setpasswordchar)|Kullanıcı metin girdiğinde bir düzenleme denetiminde görünen parola karakterini ayarlar veya kaldırır.|
|[Cedıt:: SetReadOnly](#setreadonly)|Bir düzenleme denetiminin salt okunurdur durumunu ayarlar.|
|[Cedıt:: SetRect](#setrect)|Birden çok satırlı bir düzenleme denetiminin biçimlendirme dikdörtgenini ayarlar ve denetimi günceller.|
|[Cedıt:: SetRectNP](#setrectnp)|Denetim penceresini yeniden çizmeksizin, çok satırlı bir düzenleme denetiminin biçimlendirme dikdörtgenini ayarlar.|
|[Cedıt:: SetSel](#setsel)|Bir düzenleme denetimindeki bir karakter aralığı seçer.|
|[Cedıt:: Settabstop](#settabstops)|Birden çok satırlık düzenleme denetimindeki sekme duraklarının ayarlar.|
|[Cedıt:: ShowBalloonTip](#showballoontip)|Geçerli düzenleme denetimiyle ilişkili bir balon ipucu görüntüler.|
|[Cedıt:: Undo](#undo)|Son düzenleme denetimi işlemini tersine çevirir.|

## <a name="remarks"></a>Açıklamalar

Düzenleme denetimi, kullanıcının metin girebileceği dikdörtgen bir alt penceredir.

Bir iletişim kutusu şablonundan ya da doğrudan kodunuzda bir düzenleme denetimi oluşturabilirsiniz. Her iki durumda da, önce nesneyi oluşturmak `CEdit` için oluşturucuyu çağırın `CEdit` , sonra Windows düzenleme denetimini oluşturmak ve bunu nesnesine eklemek Için üye [Oluştur](#create) işlevini çağırın `CEdit` .

Oluşturma, öğesinden türetilmiş bir sınıfta tek adımlı bir işlem olabilir `CEdit` . Türetilmiş sınıf için bir Oluşturucu yazın ve `Create` oluşturucuyu içinden çağırın.

`CEdit` , ' den önemli işlevleri devralır `CWnd` . Bir nesneden metin ayarlamak ve almak için `CEdit` , `CWnd` çok satırlı bir denetim olsa da, bir düzenleme denetiminin tüm içeriğini ayarlama veya alma, [SetWindowText](cwnd-class.md#setwindowtext) ve [GetWindowText](cwnd-class.md#getwindowtext)üye işlevlerini kullanın. Çok satırlı bir denetimdeki metin satırları ' \r\n ' karakter dizileri ile ayrılır. Ayrıca, bir düzenleme denetimi çok fazla ise, `CEdit` [getline](#getline), [SetSel](#setsel), [GetSel](#getsel)ve [ReplaceSel](#replacesel)üye işlevlerini çağırarak denetimin metninin bir parçasını alın ve ayarlayın.

Bir düzenleme denetimi tarafından kendi üst öğesine (genellikle öğesinden türetilmiş bir sınıf) gönderilen Windows bildirim iletilerini işlemek istiyorsanız `CDialog` , her ileti için üst sınıfa bir ileti eşleme girişi ve ileti işleyici üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

  **On_**_bildirimi_**(** _kimlik_**,** _memberFxn_ **)**

Burada `id` bildirimi gönderen düzenleme denetiminin alt pencere kimliğini belirtir ve `memberFxn` bildirimi işlemek için yazdığınız ana üye işlevinin adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

**afx_msg** void memberFxn **();**

Aşağıda olası ileti eşleme girişlerinin listesi ve bunların üst öğeye gönderileceği durumların açıklaması verilmiştir:

- ON_EN_CHANGE Kullanıcı, düzenleme denetiminde metin değiştirmiş olabilecek bir eylem gerçekleştirmiştir. EN_UPDATE bildirim iletisinin aksine, Windows ekranı güncelleştirdikten sonra bu bildirim iletisi gönderilir.

- ON_EN_ERRSPACE düzenleme denetimi belirli bir isteği karşılamak için yeterli bellek ayıramıyor.

- Kullanıcı bir düzenleme denetiminin yatay kaydırma çubuğuna tıkladığı ON_EN_HSCROLL. Ekran güncellenmeye başlamadan önce üst pencereye bildirim gönderilir.

- ON_EN_KILLFOCUS düzenleme denetimi giriş odağını kaybeder.

- Geçerli ekleme ON_EN_MAXTEXT, düzenleme denetimi için belirtilen karakter sayısını aştı ve kesildi. Ayrıca, bir düzenleme denetiminin ES_AUTOHSCROLL stili yoksa ve eklenecek karakter sayısı düzenleme denetiminin genişliğini aştıklarında gönderilir. Ayrıca, bir düzenleme denetiminin ES_AUTOVSCROLL stili yoksa ve metin ekleme işleminden kaynaklanan toplam satır sayısı düzenleme denetiminin yüksekliğini aşacağından de gönderilir.

- Bir düzenleme denetimi giriş odağını aldığında ON_EN_SETFOCUS gönderilir.

- Düzenleme denetimi ON_EN_UPDATE değiştirilen metni göstermek üzere. Denetim metni biçimlendirdikten sonra, ancak gerektiğinde pencere boyutunun değiştirilenebilmesi için metni görüntülemeden önce gönderilir.

- Kullanıcı bir düzenleme denetiminin dikey kaydırma çubuğuna tıkladığı ON_EN_VSCROLL. Ekran güncellenmeye başlamadan önce üst pencereye bildirim gönderilir.

`CEdit`İletişim kutusu içinde bir nesne oluşturursanız, `CEdit` Kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

İletişim kutusu `CEdit` düzenleyicisini kullanarak bir iletişim kaynağından bir nesne oluşturursanız, `CEdit` Kullanıcı iletişim kutusunu kapattığında nesne otomatik olarak yok edilir.

Bir `CEdit` pencere içinde bir nesne oluşturursanız, bunu yok etmeniz de gerekebilir. `CEdit`Nesneyi yığında oluşturursanız, otomatik olarak yok edilir. `CEdit`Nesnesini, işlevini kullanarak yığında oluşturursanız **`new`** , **`delete`** Kullanıcı Windows düzenleme denetimini sonlandırdığında nesneyi yok etmek için nesnesini çağırmanız gerekir. Nesnede herhangi bir bellek ayırırsanız `CEdit` , `CEdit` ayırmaların atılacağı yıkıcıyı geçersiz kılın.

Bir düzenleme denetimindeki belirli stilleri değiştirmek için (ES_READONLY gibi), [ModifyStyle](cwnd-class.md#modifystyle)kullanmak yerine denetime belirli iletiler göndermeniz gerekir. Bkz. Windows SDK [Denetim stillerini düzenleme](/windows/win32/Controls/edit-control-styles) .

Hakkında daha fazla bilgi için `CEdit` bkz. [denetimler](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxwin. h

## <a name="ceditcanundo"></a><a name="canundo"></a> Cedıt:: CanUndo

Son düzenleme işleminin geri alınamayacağı olup olmadığını öğrenmek için bu işlevi çağırın.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son düzenleme işlemi, üye işlevine yapılan bir çağrı ile geri alınmışsa, sıfır dışında, Eğer `Undo` geri alınamayacağı 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_CANUNDO](/windows/win32/Controls/em-canundo) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: Undo](#undo)örneğine bakın.

## <a name="ceditcedit"></a><a name="cedit"></a> Cedıt:: Cedıt

Bir `CEdit` nesnesi oluşturur.

```
CEdit();
```

### <a name="remarks"></a>Açıklamalar

Windows düzenleme denetimini oluşturmak için [Oluştur](#create) ' a kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

## <a name="ceditcharfrompos"></a><a name="charfrompos"></a> Cedıt:: CharFromPos

Bu denetimde belirtilen noktaya en yakın karakterin sıfır tabanlı satırını ve karakter dizinlerini almak için bu işlevi çağırın `CEdit`

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Parametreler

*yönergelerinin*<br/>
Bu nesnenin istemci alanındaki bir noktanın koordinatları `CEdit` .

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı SÖZCÜĞE ait karakter dizini ve yüksek sıralı SÖZCÜKTEKI satır dizini.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu üye işlevi, Windows 95 ve Windows NT 4,0 ' den itibaren kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_CHARFROMPOS](/windows/win32/Controls/em-charfrompos) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

## <a name="ceditclear"></a><a name="clear"></a> Cedıt:: Clear

Düzenleme denetimindeki geçerli seçimi (varsa) silmek için bu işlevi çağırın.

```cpp
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Tarafından gerçekleştirilen silme, `Clear` [geri alma](#undo) üye işlevi çağırarak geri alınabilir.

Geçerli seçimi silmek ve silinen içeriği panoya yerleştirmek için [Kes](#cut) üye işlevini çağırın.

Daha fazla bilgi için Windows SDK [WM_CLEAR](/windows/win32/dataxchg/wm-clear) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

## <a name="ceditcopy"></a><a name="copy"></a> Cedıt:: Copy

Düzenleme denetimindeki geçerli seçimi (varsa) CF_TEXT biçimde panoya eklemek için bu işlevi çağırın.

```cpp
void Copy();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [WM_COPY](/windows/win32/dataxchg/wm-copy) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

## <a name="ceditcreate"></a><a name="create"></a> Cedıt:: Create

Windows düzenleme denetimini oluşturur ve `CEdit` nesneye ekler.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Düzenleme denetiminin stilini belirtir. Denetime [düzenleme stillerinin](styles-used-by-mfc.md#edit-styles) herhangi bir birleşimini uygulayın.

*Rect*<br/>
Düzenleme denetiminin boyutunu ve konumunu belirtir. Bir `CRect` nesne veya yapı olabilir `RECT` .

*pParentWnd*<br/>
Düzenleme denetiminin üst penceresini (genellikle a `CDialog` ) belirtir. NULL olmaması gerekir.

*NID*<br/>
Düzenleme denetiminin KIMLIĞINI belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

`CEdit`İki adımda bir nesne oluşturursunuz. İlk olarak, `CEdit` oluşturucuyu çağırın ve sonra `Create` Windows düzenleme denetimini oluşturan ve bunu nesnesine ekleyen çağırın `CEdit` .

`Create`Yürütüldüğünde Windows, düzenleme denetimine [WM_NCCREATE](/windows/win32/winmsg/wm-nccreate), [WM_NCCALCSIZE](/windows/win32/winmsg/wm-nccalcsize), [WM_CREATE](/windows/win32/winmsg/wm-create)ve [WM_GETMINMAXINFO](/windows/win32/winmsg/wm-getminmaxinfo) iletileri gönderir.

Bu iletiler, temel sınıftaki [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate)ve [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) member işlevleri tarafından varsayılan olarak işlenir `CWnd` . Varsayılan ileti işlemeyi genişletmek için, öğesinden bir sınıf türetebilir `CEdit` , yeni sınıfa bir ileti haritası ekleyin ve yukarıdaki ileti işleyici üye işlevlerini geçersiz kılın. `OnCreate`Yeni sınıf için gerekli başlatmayı gerçekleştirmek üzere örneğin, öğesini geçersiz kılın.

Bir düzenleme denetimine aşağıdaki [pencere stillerini](styles-used-by-mfc.md#window-styles) uygulayın.

- WS_CHILD her zaman

- Genellikle WS_VISIBLE

- WS_DISABLED nadiren

- Denetimleri gruplamak Için WS_GROUP

- Düzenleme denetimini sekme sırasına dahil etmek Için WS_TABSTOP

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

## <a name="ceditcut"></a><a name="cut"></a> Cedıt:: kes

Düzenleme denetimindeki geçerli seçimi (varsa) silmek ve silinen metni pano 'ya CF_TEXT biçimde kopyalamak için bu işlevi çağırın.

```cpp
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Tarafından gerçekleştirilen silme, `Cut` [geri alma](#undo) üye işlevi çağırarak geri alınabilir.

Silinen metni panoya yerleştirmeksizin geçerli seçimi silmek için, [clear](#clear) member işlevini çağırın.

Daha fazla bilgi için Windows SDK [WM_CUT](/windows/win32/dataxchg/wm-cut) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

## <a name="ceditemptyundobuffer"></a><a name="emptyundobuffer"></a> Cedıt:: EmptyUndoBuffer

Bir düzenleme denetiminin geri alma bayrağını sıfırlamak için bu işlevi çağırın (temizleyin).

```cpp
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimi artık son işlemi geri alamıyor. Düzenleme denetimindeki bir işlem geri alınmışsa her seferinde geri alma bayrağı ayarlanır.

[SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) veya [SetHandle](#sethandle) üye işlevleri çağrıldığında geri alma bayrağı otomatik olarak temizlenir `CWnd` .

Daha fazla bilgi için Windows SDK [EM_EMPTYUNDOBUFFER](/windows/win32/Controls/em-emptyundobuffer) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

## <a name="ceditfmtlines"></a><a name="fmtlines"></a> Cedıt:: FmtLines

Çok satırlı bir düzenleme denetimi içinde, yumuşak çizgi kesme karakterlerinin dahil edilmesini veya kapatılmasını ayarlamak için bu işlevi çağırın.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Parametreler

*Rozdeol*<br/>
Yumuşak çizgi kesme karakterlerinin eklenip eklenmeyeceğini belirtir. DOĞRU değeri, karakterleri ekler; FALSE değeri onları kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir biçimlendirme oluşursa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yumuşak çizgi kesmesi, iki satır dönüşünden ve sözcük kaydırma nedeniyle kopuk bir satırın sonuna eklenen bir satır akışından oluşur. Sabit çizgi kesmesi, bir satır başı ve bir satır akışından oluşur. Sabit satır sonuyla biten satırlar tarafından etkilenmez `FmtLines` .

Windows yalnızca `CEdit` nesne çok satırlı bir düzenleme denetimi ise yanıt verir.

`FmtLines` yalnızca [GetHandle](#gethandle) tarafından döndürülen arabelleği ve [wm_gettext](/windows/win32/winmsg/wm-gettext)tarafından döndürülen metni etkiler. Düzenleme denetimindeki metnin görüntülenmesini etkilemez.

Daha fazla bilgi için Windows SDK [EM_FMTLINES](/windows/win32/Controls/em-fmtlines) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

## <a name="ceditgetcuebanner"></a><a name="getcuebanner"></a> Cedıt:: Getcuebaşlık

Denetim boş olduğunda, bir düzenleme denetimindeki metin ipucu veya ipucu olarak görüntülenen metni alır.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
dışı İpucu metnini içeren bir dizeye yönelik işaretçi.

*cchText*<br/>
'ndaki Alınabilecek karakterlerin sayısı. Bu sayı, Sonlandırıcı NULL karakterini içerir.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yükleme için, Yöntem başarılı olursa TRUE; Aksi halde yanlış.

İkinci aşırı yükleme için, Yöntem başarılı olursa işaret metnini içeren bir [CString](../../atl-mfc-shared/using-cstring.md) ; Aksi takdirde, boş dize ("").

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [EM_GETCUEBANNER](/windows/win32/Controls/em-getcuebanner) iletisini gönderir. Daha fazla bilgi için [Edit_GetCueBannerText](/windows/win32/api/commctrl/nf-commctrl-edit_getcuebannertext) makroya bakın.

## <a name="ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a> Cedıt:: GetFirstVisibleLine

Bir düzenleme denetimindeki en üstteki görünür çizgiyi öğrenmek için bu işlevi çağırın.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Dönüş Değeri

En üstteki görünür çizginin sıfır tabanlı dizini. Tek satırlı düzenleme denetimleri için, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_GETFIRSTVISIBLELINE](/windows/win32/Controls/em-getfirstvisibleline) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

## <a name="ceditgethandle"></a><a name="gethandle"></a> Cedıt:: GetHandle

Birden çok satırlı bir düzenleme denetimi için geçerli olarak ayrılmış belleğe yönelik bir tanıtıcı almak için bu işlevi çağırın.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin içeriğini tutan arabelleği tanımlayan yerel bir bellek tanıtıcısı. İletiyi tek satırlık bir düzenleme denetimine göndermek gibi bir hata oluşursa, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı yerel bir bellek tanıtıcıdır ve bir yerel bellek tanıtıcısını parametre olarak alan **Yerel** Windows belleği işlevleri tarafından kullanılabilir.

`GetHandle` yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

`GetHandle`İletişim kutusunda, iletişim kutusu DS_LOCALEDIT stil bayrağı ayarlanmış olarak oluşturulduysa, çok satırlı bir düzenleme denetimi için çağrı yapın. DS_LOCALEDIT stili ayarlanmamışsa, sıfır dışında bir dönüş değeri almaya devam edersiniz, ancak döndürülen değeri kullanamazsınız.

> [!NOTE]
> `GetHandle` , Windows 95/98 ile çalışmaz. `GetHandle`Windows 95/98 ' de çağırırsanız, null döndürür. `GetHandle` Windows NT altında belgelendiği gibi çalışır, sürüm 3,51 ve üzeri.

Daha fazla bilgi için Windows SDK [em_gethandle](/windows/win32/Controls/em-gethandle) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

## <a name="ceditgethighlight"></a><a name="gethighlight"></a> Cedıt:: GetHighlight

Geçerli düzenleme denetiminde vurgulanan bir metin aralığındaki ilk ve son karakterlerin dizinlerini alır.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Parametreler

*pichStart*\
dışı Vurgulanmış metin aralığındaki ilk karakterin sıfır tabanlı dizini.

*pichEnd*\
dışı Vurgulanan metin aralığındaki son karakterin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [EM_GETHILITE](/windows/win32/Controls/em-gethilite) iletisini gönderir. Her ikisi de `SetHighlight` `GetHighlight` Şu anda yalnızca UNICODE derlemeler için etkinleştirilmiştir.

## <a name="ceditgetlimittext"></a><a name="getlimittext"></a> Cedıt:: GetLimitText

Bu nesne için metin sınırını almak üzere bu üye işlevi çağırın `CEdit` .

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu nesne için geçerli metin sınırı (TCHARs) `CEdit` .

### <a name="remarks"></a>Açıklamalar

Metin sınırı, düzenleme denetiminin kabul edebileceği, TCHARs 'ta bulunan en fazla metin miktarıdır.

> [!NOTE]
> Bu üye işlevi, Windows 95 ve Windows NT 4,0 ' den itibaren kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_GETLIMITTEXT](/windows/win32/Controls/em-getlimittext) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

## <a name="ceditgetline"></a><a name="getline"></a> Cedıt:: GetLine

Bir düzenleme denetiminden bir metin satırı almak ve *lpszBuffer*'e yerleştirmeleri için bu işlevi çağırın.

```
int GetLine(
    int nIndex,
    LPTSTR lpszBuffer) const;

int GetLine(
    int nIndex,
    LPTSTR lpszBuffer,
    int nMaxLength) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Birden çok satırlık bir düzenleme denetiminden alınacak satır numarasını belirtir. Satır numaraları sıfır tabanlıdır; 0 değeri ilk satırı belirtir. Bu parametre, tek satırlık bir düzenleme denetimi tarafından yok sayılır.

*lpszBuffer*<br/>
Çizginin bir kopyasını alan arabelleği işaret eder. Arabelleğin ilk sözcüğü, arabelleğe kopyalanabilecek maksimum sayıda TCHARs sayısını belirtmelidir.

*nMaxLength*<br/>
Arabelleğe kopyalanabilecek maksimum TCHAR karakter sayısını belirtir. `GetLine` Windows 'a çağrı yapmadan önce bu değeri *lpszBuffer* 'in ilk sözcüğüne koyar.

### <a name="return-value"></a>Dönüş Değeri

Gerçekte kopyalanmış karakterlerin sayısı. *NIndex* tarafından belirtilen satır numarası, düzenleme denetimindeki satır sayısından büyükse, dönüş değeri 0 ' dır.

### <a name="remarks"></a>Açıklamalar

Kopyalanmış satır, null sonlandırma karakteri içermiyor.

Daha fazla bilgi için Windows SDK [EM_GETLINE](/windows/win32/Controls/em-getline) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: GetLineCount](#getlinecount)örneğine bakın.

## <a name="ceditgetlinecount"></a><a name="getlinecount"></a> Cedıt:: GetLineCount

Birden çok satırlı düzenleme denetimindeki satır sayısını almak için bu işlevi çağırın.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Birden çok satırlı düzenleme denetimindeki satır sayısını içeren bir tamsayı. Düzenleme denetimine metin girildiyse, dönüş değeri 1 ' dir.

### <a name="remarks"></a>Açıklamalar

`GetLineCount` yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK [EM_GETLINECOUNT](/windows/win32/Controls/em-getlinecount) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

## <a name="ceditgetmargins"></a><a name="getmargins"></a> Cedıt:: Getkenar boşlukları

Bu düzenleme denetiminin sol ve sağ kenar boşluklarını almak için bu üye işlevini çağırın.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı sözcükteki sol kenar boşluğunun genişliği ve yüksek sıralı SÖZCÜKTEKI sağ kenar boşluğunun genişliği.

### <a name="remarks"></a>Açıklamalar

Kenar boşlukları piksel cinsinden ölçülür.

> [!NOTE]
> Bu üye işlevi, Windows 95 ve Windows NT 4,0 ' den itibaren kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_GETMARGINS](/windows/win32/Controls/em-getmargins) bakın.

### <a name="example"></a>Örnek

  [CEditView:: GetEditCtrl](ceditview-class.md#geteditctrl)örneğine bakın.

## <a name="ceditgetmodify"></a><a name="getmodify"></a> Cedıt:: GetModify

Bir düzenleme denetimi içeriğinin değiştirilip değiştirilmediğini öğrenmek için bu işlevi çağırın.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetimi içerikleri değiştirildiyse sıfır dışı; değiştirilmemiş ise 0.

### <a name="remarks"></a>Açıklamalar

Windows, düzenleme denetimi içeriklerinin değiştirilip değiştirilmediğini belirten bir iç bayrak tutar. Bu bayrak, düzenleme denetimi ilk oluşturulduğunda temizlenir ve [SetModify](#setmodify) üye işlevi çağırarak da temizlenir.

Daha fazla bilgi için Windows SDK [EM_GETMODIFY](/windows/win32/Controls/em-getmodify) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

## <a name="ceditgetpasswordchar"></a><a name="getpasswordchar"></a> Cedıt:: GetPasswordChar

Kullanıcı metin girdiğinde bir düzenleme denetiminde görüntülenen parola karakterini almak için bu işlevi çağırın.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının girdiği karakter yerine görüntülenecek karakteri belirtir. Parola karakteri yoksa dönüş değeri NULL olur.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimini ES_PASSWORD stili ile oluşturursanız, denetimi destekleyen DLL varsayılan parola karakterini belirler. Manifest veya [InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex) yöntemi, hangi dll 'nin düzenleme denetimini desteklediğini belirler. user32.dll düzenleme denetimini destekliyorsa, varsayılan parola karakteri yıldız IŞARETIDIR (' * ', U + 002A). comctl32.dll sürüm 6 düzenleme denetimini destekliyorsa, varsayılan karakter sıyah DAIRE (' ● ', U + 25CF) olur. Hangi DLL ve sürüm ortak denetimleri desteklediğine ilişkin daha fazla bilgi için bkz. [Shell ve Common Controls sürümleri](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\)).

Bu yöntem, Windows SDK açıklanan [EM_GETPASSWORDCHAR](/windows/win32/Controls/em-getpasswordchar) iletisini gönderir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

## <a name="ceditgetrect"></a><a name="getrect"></a> Cedıt:: GetRect

Bir düzenleme denetiminin biçimlendirme dikdörtgenini almak için bu işlevi çağırın.

```cpp
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
`RECT`Biçimlendirme dikdörtgenini alan yapıya işaret eder.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgeni, metin, düzenleme denetimi penceresinin boyutundan bağımsız olan sınırlayıcı dikdörtgendir.

Çok satırlı bir düzenleme denetiminin biçimlendirme dikdörtgeni [SetRect](#setrect) ve [SetRectNP](#setrectnp) üye işlevleri tarafından değiştirilebilir.

Daha fazla bilgi için Windows SDK [EM_GETRECT](/windows/win32/Controls/em-getrect) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: LimitText](#limittext)örneğine bakın.

## <a name="ceditgetsel"></a><a name="getsel"></a> Cedıt:: GetSel

Bir düzenleme denetimindeki geçerli seçimin (varsa) başlangıç ve bitiş karakter konumlarını, dönüş değeri veya parametreleri kullanarak almak için bu işlevi çağırın.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Geçerli seçimdeki ilk karakterin konumunu alacak bir tamsayıya başvuru.

*nEndChar*<br/>
Geçerli seçimin sonundan sonra seçili olmayan ilk karakterin konumunu alacak bir tamsayıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

Bir DWORD döndüren sürüm, düşük sıralı sözcüğe başlangıç konumunu içeren bir değer ve yüksek sıralı sözcükteki seçimin sonundan sonra seçili olmayan ilk karakterin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_GETSEL](/windows/win32/Controls/em-getsel) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

## <a name="cedithideballoontip"></a><a name="hideballoontip"></a> Cedıt:: HideBalloonTip

Geçerli düzenleme denetimiyle ilişkili balon ucunu gizler.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK açıklanan [EM_HIDEBALLOONTIP](/windows/win32/Controls/em-hideballoontip) iletisini gönderir.

## <a name="ceditlimittext"></a><a name="limittext"></a> Cedıt:: LimitText

Kullanıcının bir düzenleme denetimine girebileceği metnin uzunluğunu sınırlamak için bu işlevi çağırın.

```cpp
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*Nchar 'lar*<br/>
Kullanıcının girebileceği metnin uzunluğunu (TCHARs) belirtir. Bu parametre 0 ise, metin uzunluğu UINT_MAX bayt olarak ayarlanır. Bu, varsayılan davranıştır.

### <a name="remarks"></a>Açıklamalar

Metin sınırını değiştirmek yalnızca kullanıcının girebileceği metni kısıtlar. Düzenleme denetimindeki hiçbir metin üzerinde hiçbir etkisi yoktur ve içindeki [SetWindowText](cwnd-class.md#setwindowtext) üye işlevi tarafından düzenleme denetimine kopyalanmış metnin uzunluğunu da etkilemez `CWnd` . Bir uygulama, `SetWindowText` çağrısında belirtilen bir düzenleme denetimine daha fazla metin yerleştirmek için işlevini kullanıyorsa `LimitText` , Kullanıcı düzenleme denetimindeki herhangi bir metni silebilir. Ancak, metin sınırı kullanıcının varolan metni yeni metinle değiştirmesini engeller. geçerli seçim silinmemişse metnin metin sınırının altına düşmesine neden olur.

> [!NOTE]
> Win32 (Windows NT ve Windows 95/98) içinde, [SetLimitText](#setlimittext) bu işlevin yerini alır.

Daha fazla bilgi için Windows SDK [EM_LIMITTEXT](/windows/win32/Controls/em-limittext) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

## <a name="ceditlinefromchar"></a><a name="linefromchar"></a> Cedıt:: LineFromChar

Belirtilen karakter dizinini içeren satırın satır numarasını almak için bu işlevi çağırın.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Düzenleme denetiminin metninde istenen karakterin sıfır tabanlı dizin değerini içerir veya-1 ' i içerir. *Nindex* -1 ise, geçerli satırı, diğer bir deyişle, giriş işaretini içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

*NIndex*tarafından belirtilen karakter dizinini içeren satırın sıfır tabanlı satır numarası. *Nindex* -1 ise, seçimin ilk karakterini içeren satırın numarası döndürülür. Seçim yoksa, geçerli satır numarası döndürülür.

### <a name="remarks"></a>Açıklamalar

Karakter dizini, düzenleme denetiminin başındaki karakter sayısıdır.

Bu üye işlevi yalnızca birden çok satırlık düzenleme denetimleri tarafından kullanılır.

Daha fazla bilgi için Windows SDK [EM_LINEFROMCHAR](/windows/win32/Controls/em-linefromchar) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

## <a name="ceditlineindex"></a><a name="lineindex"></a> Cedıt:: lineIndex

Birden çok satırlı düzenleme denetimindeki bir çizginin karakter dizinini almak için bu işlevi çağırın.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*nLine*<br/>
Düzenleme denetiminin metninde istenen çizginin dizin değerini içerir veya-1 ' i içerir. *NLine* -1 ise, geçerli satırı, diğer bir deyişle, giriş işaretini içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen satır sayısı düzenleme denetimindeki satır sayısından büyükse, *nLine* veya-1 ' de belirtilen çizginin karakter dizini.

### <a name="remarks"></a>Açıklamalar

Karakter dizini, düzenleme denetiminin başından belirtilen satıra kadar olan karakter sayısıdır.

Bu üye işlevi yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK [EM_LINEINDEX](/windows/win32/controls/em-lineindex) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

## <a name="ceditlinelength"></a><a name="linelength"></a> Cedıt:: LineLength

Bir düzenleme denetimindeki bir çizginin uzunluğunu alır.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*nLine*<br/>
Uzunluğu alınacak olan satırdaki bir karakterin sıfır tabanlı dizini. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Tek satırlı düzenleme denetimleri için, dönüş değeri, düzenleme denetimindeki metnin, TCHARs cinsinden uzunluğudur.

Çok satırlı düzenleme denetimleri için, dönüş değeri *nLine* parametresi tarafından belirtilen satırın TCHARs cinsinden uzunluğudur. ANSI metni için uzunluk, satırdaki bayt sayısıdır; Unicode metin için uzunluk, satırdaki karakter sayısıdır. Uzunluk, satırın sonundaki satır başı karakteri içermez.

*NLine* parametresi denetimdeki karakter sayısından büyükse, dönüş değeri sıfırdır.

*NLine* parametresi-1 ise, dönüş değeri seçili karakterleri içeren satırlardaki seçilmemiş karakterlerin sayısıdır. Örneğin, seçim bir sonraki satırın sonundaki sekizinci karakter aracılığıyla bir satırın dördüncü karakterinden genişlese, dönüş değeri 10 ' dur. Diğer bir deyişle, ilk satırda üç karakter ve sonraki adımda yedi.

TCHAR türü hakkında daha fazla bilgi için, [Windows veri türleri](/windows/win32/WinProg/windows-data-types)'NDEKI tablodaki TCHAR satırına bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [EM_LINELENGTH](/windows/win32/Controls/em-linelength) iletisi tarafından desteklenir.

### <a name="example"></a>Örnek

  [Cedıt:: lineIndex](#lineindex)örneğine bakın.

## <a name="ceditlinescroll"></a><a name="linescroll"></a> Cedıt:: LineScroll

Birden çok satırlı bir düzenleme denetiminin metnini kaydırmak için bu işlevi çağırın.

```cpp
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*nsatırlar*<br/>
Dikey olarak kaydırılan satır sayısını belirtir.

*Nchar 'lar*<br/>
Yatay olarak kaydırılacak karakter konumlarının sayısını belirtir. Düzenleme denetiminin ES_RIGHT veya ES_CENTER stili varsa, bu değer yoksayılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

Düzenleme denetimi, düzenleme denetimindeki metnin son satırını aşan dikey olarak kaydırmaz. Geçerli satır ve *nLines* tarafından belirtilen satır sayısı, düzenleme denetimindeki toplam satır sayısını aşarsa, düzenleme denetiminin son satırı düzenleme denetimi penceresinin en üstüne kaydırılabilmesi için değer ayarlanır.

`LineScroll` , herhangi bir satırın son karakterinin ötesinde yatay olarak kaydırmak için kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_LINESCROLL](/windows/win32/Controls/em-linescroll) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: GetFirstVisibleLine](#getfirstvisibleline)örneğine bakın.

## <a name="ceditpaste"></a><a name="paste"></a> Cedıt::P aste

Panodaki verileri ekleme noktasındaki öğesine eklemek için bu işlevi çağırın `CEdit` .

```cpp
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.

Daha fazla bilgi için Windows SDK [WM_PASTE](/windows/win32/dataxchg/wm-paste) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

## <a name="ceditposfromchar"></a><a name="posfromchar"></a> Cedıt::P osFromChar

Bu nesne içindeki belirli bir karakterin konumunu (sol üst köşesinden) almak için bu işlevi çağırın `CEdit` .

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
Belirtilen karakterin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

*Nchar*tarafından belirtilen karakterin sol üst köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Karakter, sıfır tabanlı dizin değeri vererek belirtilir. *Nchar* , bu nesnedeki son karakterin dizininden büyükse `CEdit` , dönüş değeri bu nesnedeki son karakteri geçen karakter konumunun koordinatlarını belirtir `CEdit` .

> [!NOTE]
> Bu üye işlevi, Windows 95 ve Windows NT 4,0 ' den itibaren kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_POSFROMCHAR](/windows/win32/Controls/em-posfromchar) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: LineFromChar](#linefromchar)örneğine bakın.

## <a name="ceditreplacesel"></a><a name="replacesel"></a> Cedıt:: ReplaceSel

Bir düzenleme denetimindeki geçerli seçimi *lpszNewText*tarafından belirtilen metinle değiştirmek için bu işlevi çağırın.

```cpp
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszNewText*<br/>
Değiştirme metnini içeren, null ile sonlandırılmış bir dizeye işaret eder.

*bCanUndo*<br/>
Bu işlevin geri alınamayacağı belirtmek için bu parametrenin değerini TRUE olarak ayarlayın. Varsayılan değer FALSE 'dur.

### <a name="remarks"></a>Açıklamalar

Yalnızca bir düzenleme denetimindeki metnin bir kısmını değiştirir. Metnin tamamını değiştirmek istiyorsanız [CWnd:: SetWindowText](cwnd-class.md#setwindowtext) üye işlevini kullanın.

Geçerli seçim yoksa, değiştirme metni geçerli imleç konumuna eklenir.

Daha fazla bilgi için Windows SDK [EM_REPLACESEL](/windows/win32/Controls/em-replacesel) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: lineIndex](#lineindex)örneğine bakın.

## <a name="ceditsetcuebanner"></a><a name="setcuebanner"></a> Cedıt:: Setcuebaşlık

Denetim boş olduğunda, bir düzenleme denetimindeki metin ipucu veya ipucu olarak görüntülenen metni ayarlar.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
'ndaki Düzenleme denetiminde görüntülenecek ipucunu içeren bir dizeye yönelik işaretçi.

*Fdrawwhenodaklanmış*<br/>
'ndaki FALSE ise, Kullanıcı düzenleme denetimine tıkladığında ve odağı denetime verdiği zaman ipucu başlığı çizilmez.

TRUE ise, denetim odağa sahip olsa bile işaret başlığı çizilir. Kullanıcı denetime yazmaya başladığında işaret başlığı kaldırılır.

Varsayılan değer FALSE 'dur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [EM_SETCUEBANNER](/windows/win32/Controls/em-setcuebanner) iletisini gönderir. Daha fazla bilgi için [Edit_SetCueBannerTextFocused](/windows/win32/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) makroya bakın.

### <a name="example"></a>Örnek

Aşağıdaki örnek, [Cedıt:: Setcuebaşlık](#setcuebanner) yöntemini gösterir.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

## <a name="ceditsethandle"></a><a name="sethandle"></a> Cedıt:: SetHandle

İşleyiciyi birden çok satırlık bir düzenleme denetimi tarafından kullanılacak yerel belleğe ayarlamak için bu işlevi çağırın.

```cpp
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Parametreler

*hBuffer*<br/>
Yerel belleğe yönelik bir tanıtıcı içerir. Bu tanıtıcının, LMEM_MOVEABLE bayrağı kullanılarak [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) Windows işlevine yapılan önceki bir çağrı tarafından oluşturulmuş olması gerekir. Belleğin, null ile sonlandırılmış bir dize içerdiği varsayılır. Durum bu değilse, ayrılan belleğin ilk baytı 0 olarak ayarlanmalıdır.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimi daha sonra bu arabelleği kullanarak, kendi arabelleğini ayırmak yerine o sırada görüntülenen metni depolar.

Bu üye işlevi yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

Bir uygulama yeni bir bellek tanıtıcısı ayarlamadan önce, geçerli bellek arabelleğine yönelik tanıtıcıyı almak ve Windows işlevini kullanarak belleği boşaltmak için [GetHandle](#gethandle) üye işlevini kullanmalıdır `LocalFree` .

`SetHandle` geri alma arabelleğini temizler ( [CanUndo](#canundo) üye işlevi 0 döndürür) ve iç değişiklik bayrağı ( [GetModify](#getmodify) üye işlevi 0 döndürür). Düzenleme denetimi penceresi yeniden çizilir.

Bu üye işlevi, iletişim kutusunda DS_LOCALEDIT Style bayrağıyla ayarlanmış iletişim kutusunu oluşturduysanız, birden çok satırlı düzenleme denetiminde kullanabilirsiniz.

> [!NOTE]
> `GetHandle` , Windows 95/98 ile çalışmaz. `GetHandle`Windows 95/98 ' de çağırırsanız, null döndürür. `GetHandle` Windows NT altında belgelendiği gibi çalışır, sürüm 3,51 ve üzeri.

Daha fazla bilgi için Windows SDK [em_sethandle](/windows/win32/Controls/em-sethandle), [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc)ve [LocalFree](/windows/win32/api/winbase/nf-winbase-localfree) bölümüne bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

## <a name="ceditsethighlight"></a><a name="sethighlight"></a> Cedıt:: SetHighlight

Geçerli düzenleme denetiminde görüntülenen bir metin aralığını vurgular.

```cpp
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Parametreler

*ichStart*\
'ndaki Vurgulanacak metin aralığındaki ilk karakterin sıfır tabanlı dizini.

*ichEnd*\
'ndaki Vurgulanacak metin aralığındaki son karakterin sıfır tabanlı dizini.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK açıklanan [EM_SETHILITE](/windows/win32/Controls/em-sethilite) iletisini gönderir.  Bu yöntem, Windows SDK açıklanan [EM_SETHILITE](/windows/win32/Controls/em-sethilite) iletisini gönderir. Her ikisi de `SetHighlight` `GetHighlight` yalnızca UNICODE derlemeler için etkinleştirilmiştir.

## <a name="ceditsetlimittext"></a><a name="setlimittext"></a> Cedıt:: SetLimitText

Bu nesne için metin sınırını ayarlamak için bu üye işlevini çağırın `CEdit` .

```cpp
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Parametreler

*Ngünde en çok*<br/>
Karakter cinsinden yeni metin sınırı.

### <a name="remarks"></a>Açıklamalar

Metin sınırı, düzenleme denetiminin kabul edebileceği, karakter cinsinden maksimum metin miktarıdır.

Metin sınırını değiştirmek yalnızca kullanıcının girebileceği metni kısıtlar. Düzenleme denetimindeki hiçbir metin üzerinde hiçbir etkisi yoktur ve içindeki [SetWindowText](cwnd-class.md#setwindowtext) üye işlevi tarafından düzenleme denetimine kopyalanmış metnin uzunluğunu da etkilemez `CWnd` . Bir uygulama, `SetWindowText` çağrısında belirtilen bir düzenleme denetimine daha fazla metin yerleştirmek için işlevini kullanıyorsa `LimitText` , Kullanıcı düzenleme denetimindeki herhangi bir metni silebilir. Ancak, metin sınırı kullanıcının varolan metni yeni metinle değiştirmesini engeller. geçerli seçim silinmemişse metnin metin sınırının altına düşmesine neden olur.

Bu işlev, Win32 içindeki [LimitText](#limittext) 'i değiştirir.

Daha fazla bilgi için Windows SDK [EM_SETLIMITTEXT](/windows/win32/Controls/em-setlimittext) bakın.

### <a name="example"></a>Örnek

  [CEditView:: GetEditCtrl](ceditview-class.md#geteditctrl)örneğine bakın.

## <a name="ceditsetmargins"></a><a name="setmargins"></a> Cedıt:: Setkenar boşlukları

Bu düzenleme denetiminin sol ve sağ kenar boşluklarını ayarlamak için bu yöntemi çağırın.

```cpp
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>Parametreler

*nLeft*<br/>
Yeni sol kenar boşluğunun piksel cinsinden genişliği.

*Nsağ*<br/>
Yeni sağ kenar boşluğunun piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu üye işlevi, Windows 95 ve Windows NT 4,0 ' den itibaren kullanılabilir.

Daha fazla bilgi için Windows SDK [EM_SETMARGINS](/windows/win32/Controls/em-setmargins) bakın.

### <a name="example"></a>Örnek

  [CEditView:: GetEditCtrl](ceditview-class.md#geteditctrl)örneğine bakın.

## <a name="ceditsetmodify"></a><a name="setmodify"></a> Cedıt:: SetModify

Bir düzenleme denetiminin değiştirilmiş bayrağını ayarlamak veya temizlemek için bu işlevi çağırın.

```cpp
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
DOĞRU değeri, metnin değiştirildiğini ve yanlış değerinin değiştirilmemiş olduğunu gösterir. Varsayılan olarak, değiştirilen bayrak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Değiştirilen bayrak, düzenleme denetimindeki metnin değiştirilip değiştirilmediğini belirtir. Kullanıcı metni her değiştirdiğinde otomatik olarak ayarlanır. Değeri [GetModify](#getmodify) üye işleviyle alınmış olabilir.

Daha fazla bilgi için Windows SDK [EM_SETMODIFY](/windows/win32/Controls/em-setmodify) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: GetModify](#getmodify)örneğine bakın.

## <a name="ceditsetpasswordchar"></a><a name="setpasswordchar"></a> Cedıt:: SetPasswordChar

Kullanıcı metin yazdığında bir düzenleme denetiminde görüntülenecek bir parola karakteri ayarlamak veya kaldırmak için bu işlevi çağırın.

```cpp
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*<br/>
Kullanıcı tarafından yazılan karakterin yerine görüntülenecek karakteri belirtir. *Ch* 0 ise, Kullanıcı tarafından yazılan gerçek karakterler görüntülenir.

### <a name="remarks"></a>Açıklamalar

Bir parola karakteri ayarlandığında, bu karakter Kullanıcı türlerindeki her karakter için görüntülenir.

Bu üye işlevin çok satırlı bir düzenleme denetimi üzerinde hiçbir etkisi yoktur.

`SetPasswordChar`Üye işlevi çağrıldığında, `CEdit` tüm görünür karakterleri *ch*tarafından belirtilen karakteri kullanarak yeniden çizer.

Düzenleme denetimi [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) stille oluşturulduysa, varsayılan parola karakteri bir yıldız işareti () olarak ayarlanır <strong>\*</strong> . `SetPasswordChar` *Ch* kümesi 0 olarak çağrılırsa bu stil kaldırılır.

Daha fazla bilgi için Windows SDK [EM_SETPASSWORDCHAR](/windows/win32/Controls/em-setpasswordchar) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

## <a name="ceditsetreadonly"></a><a name="setreadonly"></a> Cedıt:: SetReadOnly

Bir düzenleme denetiminin salt okunurdur durumunu ayarlamak için bu işlevi çağırır.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bReadOnly*<br/>
Düzenleme denetiminin salt okuma durumunun ayarlanacağını mı yoksa kaldırılacağını mı belirtir. DOĞRU değeri, durumu salt okunurdur olarak ayarlar; FALSE değeri, durumu okuma/yazma olarak ayarlar.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır dışı veya bir hata oluşursa 0.

### <a name="remarks"></a>Açıklamalar

Geçerli ayar [CWnd:: GetStyle](cwnd-class.md#getstyle)dönüş değerindeki [ES_READONLY](styles-used-by-mfc.md#edit-styles) bayrağını test ederek bulunabilir.

Daha fazla bilgi için Windows SDK [EM_SETREADONLY](/windows/win32/Controls/em-setreadonly) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

## <a name="ceditsetrect"></a><a name="setrect"></a> Cedıt:: SetRect

Belirtilen koordinatları kullanarak bir dikdörtgenin boyutlarını ayarlamak için bu işlevi çağırın.

```cpp
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
`RECT` `CRect` Biçimlendirme dikdörtgeninin yeni boyutlarını belirten yapıya veya nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Bu üye yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

`SetRect`Birden çok satırlı bir düzenleme denetiminin biçimlendirme dikdörtgenini ayarlamak için kullanın. Biçimlendirme dikdörtgeni, metin, düzenleme denetimi penceresinin boyutundan bağımsız olan sınırlayıcı dikdörtgendir. Düzenleme denetimi ilk oluşturulduğunda, biçimlendirme dikdörtgeni, düzenleme denetimi penceresinin istemci alanı ile aynı olur. `SetRect`Bir uygulama, üye işlevini kullanarak, biçimlendirme dikdörtgeninin düzenleme denetimi penceresinden daha büyük veya daha küçük olmasını sağlayabilir.

Düzenleme denetiminde kaydırma çubuğu yoksa, biçimlendirme dikdörtgeni pencereden daha büyük olursa metin kırpılmaz, kaydırılmaz. Düzenleme denetimi bir kenarlık içeriyorsa, biçimlendirme dikdörtgeni kenarlığın boyutuyla azaltılır. Üye işlevi tarafından döndürülen dikdörtgeni ayarlarsanız `GetRect` , dikdörtgeni geçirmeden önce kenarlığın boyutunu kaldırmanız gerekir `SetRect` .

`SetRect`Çağrıldığında, düzenleme denetiminin metni de yeniden biçimlendirilir ve yeniden görüntülenir.

Daha fazla bilgi için Windows SDK [EM_SETRECT](/windows/win32/Controls/em-setrect) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

## <a name="ceditsetrectnp"></a><a name="setrectnp"></a> Cedıt:: SetRectNP

Birden çok satırlı bir düzenleme denetiminin biçimlendirme dikdörtgenini ayarlamak için bu işlevi çağırın.

```cpp
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
`RECT` `CRect` Dikdörtgenin yeni boyutlarını belirten bir yapıya veya nesneye işaret eder.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgeni, metin, düzenleme denetimi penceresinin boyutundan bağımsız olan sınırlayıcı dikdörtgendir.

`SetRectNP` , `SetRect` düzenleme denetimi penceresi yeniden çizilmediğinden, üye işlevi ile aynıdır.

Düzenleme denetimi ilk oluşturulduğunda, biçimlendirme dikdörtgeni, düzenleme denetimi penceresinin istemci alanı ile aynı olur. `SetRectNP`Bir uygulama, üye işlevini çağırarak, biçimlendirme dikdörtgeninin düzenleme denetimi penceresinden daha büyük veya daha küçük olmasını sağlayabilir.

Düzenleme denetiminde kaydırma çubuğu yoksa, biçimlendirme dikdörtgeni pencereden daha büyük olursa metin kırpılmaz, kaydırılmaz.

Bu üye yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK [EM_SETRECTNP](/windows/win32/Controls/em-setrectnp) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: SetRect](#setrect)örneğine bakın.

## <a name="ceditsetsel"></a><a name="setsel"></a> Cedıt:: SetSel

Bir düzenleme denetimindeki bir karakter aralığı seçmek için bu işlevi çağırın.

```cpp
void SetSel(
    DWORD dwSelection,
    BOOL bNoScroll = FALSE);

void SetSel(
    int nStartChar,
    int nEndChar,
    BOOL bNoScroll = FALSE);
```

### <a name="parameters"></a>Parametreler

*dwSelection*<br/>
Düşük sıralı sözcükteki başlangıç konumunu ve yüksek sıralı sözcükteki bitiş konumunu belirtir. Düşük sıralı sözcük 0 ise ve yüksek sıralı kelime-1 ise, düzenleme denetimindeki tüm metinler seçilidir. Düşük sıralı sözcük-1 ise, geçerli seçim kaldırılır.

*bNoScroll*<br/>
Giriş işaretinin görünüm olarak kaydırılmayacağını gösterir. FALSE ise, giriş işareti görünüme kaydırıldı. TRUE ise, şapka işareti görünüme kaydırılamaz.

*nStartChar*<br/>
Başlangıç konumunu belirtir. *NStartChar* 0 Ise ve *nEndChar* -1 ise, düzenleme denetimindeki tüm metin seçilidir. *NStartChar* -1 ise, geçerli seçim kaldırılır.

*nEndChar*<br/>
Bitiş konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK [EM_SETSEL](/windows/win32/Controls/em-setsel) bakın.

### <a name="example"></a>Örnek

  [Cedıt:: GetSel](#getsel)örneğine bakın.

## <a name="ceditsettabstops"></a><a name="settabstops"></a> Cedıt:: Settabstop

Birden çok satırlı bir düzenleme denetimindeki sekme duraklarının ayarlanması için bu işlevi çağırın.

```cpp
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parametreler

*cxEachStop*<br/>
Sekme duraklarının her *cxEachStop* diyalog birimlerinde ayarlanacağını belirtir.

*Ntabstop*<br/>
*Rgtabstop*'da bulunan sekme duraklarının sayısını belirtir. Bu sayı 1 ' den büyük olmalıdır.

*Rgtabstop*<br/>
İletişim kutusu birimlerindeki sekme duraklarını belirten işaretsiz tamsayılar dizisine işaret eder. İletişim kutusu birimi yatay veya dikey bir uzaklığına sahiptir. Bir yatay iletişim kutusu birimi, geçerli iletişim kutusu taban genişliği biriminin dörtte birine eşit ve 1 dikey iletişim birimi geçerli iletişim kutusu Taban yükseklik biriminin sekizde birine eşit. İletişim kutusu temel birimleri geçerli sistem yazı tipinin yüksekliği ve genişliğine göre hesaplanır. `GetDialogBaseUnits`Windows işlevi, geçerli iletişim kutusu taban birimlerini piksel cinsinden döndürür.

### <a name="return-value"></a>Dönüş Değeri

Sekmeler ayarlandıysa sıfır dışı; Aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Metin, çok satırlı bir düzenleme denetimine kopyalandığında, metindeki herhangi bir sekme karakteri bir sonraki sekme durmasına kadar boşluk oluşturulmasına neden olur.

Sekme duraklarının varsayılan boyut olan 32 iletişim birimi olarak ayarlanması için, bu üye işlevin parametresiz sürümünü çağırın. Sekme duraklarının 32 dışında bir boyuta ayarlanması için, bu sürümü *cxEachStop* parametresiyle çağırın. Sekme duraklarının bir boyut dizisine göre ayarlanması için sürümü iki parametresiyle kullanın.

Bu üye işlevi yalnızca birden çok satırlık düzenleme denetimleri tarafından işlenir.

`SetTabStops` düzenleme penceresini otomatik olarak yeniden çizmez. Düzenleme denetiminde zaten bulunan metin için sekme duraklarının değiştirilmesini değiştirirseniz, düzenleme penceresini yeniden çizmek için [CWnd:: InvalidateRect](cwnd-class.md#invalidaterect) ' ı çağırın.

Daha fazla bilgi için Windows SDK [EM_SETTABSTOPS](/windows/win32/Controls/em-settabstops) ve [GetDialogBaseUnits](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) bölümüne bakın.

### <a name="example"></a>Örnek

  [CEditView:: Settabstop](ceditview-class.md#settabstops)örneğine bakın.

## <a name="ceditshowballoontip"></a><a name="showballoontip"></a> Cedıt:: ShowBalloonTip

Geçerli düzenleme denetimiyle ilişkili bir balon ipucu görüntüler.

```
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,
    LPCWSTR lpszText,
    INT ttiIcon = TTI_NONE);
```

### <a name="parameters"></a>Parametreler

*pEditBalloonTip*\
'ndaki Balon ipucunu açıklayan bir [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) yapısına yönelik işaretçi.

*lpszTitle*\
'ndaki Balon ipucunun başlığını içeren bir Unicode dize işaretçisi.

*lpszText*\
'ndaki Balon ipucu metnini içeren bir Unicode dize işaretçisi.

*ttiIcon*\
'ndaki Balon ipucuyla ilişkilendirilecek simgenin türünü belirten bir **Int** . Varsayılan değer TTI_NONE. Daha fazla bilgi için `ttiIcon` [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) yapısının üyesine bakın.

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde, FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK açıklanan [EM_SHOWBALLOONTIP](/windows/win32/Controls/em-showballoontip) iletisini gönderir. Daha fazla bilgi için [Edit_ShowBalloonTip](/windows/win32/api/commctrl/nf-commctrl-edit_showballoontip) makroya bakın.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_cedit` geçerli düzenleme denetimine erişmek için kullanılan bir değişkenini tanımlar. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir düzenleme denetimi için balon ipucu görüntüler. [Cedıt:: ShowBalloonTip](#showballoontip) yöntemi bir başlık ve balon ipucu metnini belirtir.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

## <a name="ceditundo"></a><a name="undo"></a> Cedıt:: Undo

Son düzenleme denetimi işlemini geri almak için bu işlevi çağırın.

```
BOOL Undo();
```

### <a name="return-value"></a>Dönüş Değeri

Tek satırlık bir düzenleme denetimi için, dönüş değeri her zaman sıfır dışı olur. Birden çok satırlık bir düzenleme denetimi için geri alma işlemi başarılı olursa dönüş değeri sıfır değildir veya geri alma işlemi başarısız olursa 0 olur.

### <a name="remarks"></a>Açıklamalar

Geri alma işlemi de geri alınabilir. Örneğin, silinen metni ilk çağrısıyla birlikte geri yükleyebilirsiniz `Undo` . Aradaki düzenleme işlemi olmadığı sürece, ikinci bir çağrısıyla metni yeniden kaldırabilirsiniz `Undo` .

Daha fazla bilgi için Windows SDK [EM_UNDO](/windows/win32/Controls/em-undo) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd sınıfı](cwnd-class.md)<br/>
[CButton sınıfı](cbutton-class.md)<br/>
[CComboBox sınıfı](ccombobox-class.md)<br/>
[CListBox sınıfı](clistbox-class.md)<br/>
[CScrollBar sınıfı](cscrollbar-class.md)<br/>
[CStatic sınıfı](cstatic-class.md)<br/>
[CDialog sınıfı](cdialog-class.md)
