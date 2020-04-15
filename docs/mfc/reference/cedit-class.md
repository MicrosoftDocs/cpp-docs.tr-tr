---
title: CEdit Sınıfı
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
ms.openlocfilehash: 3ca2fe4486ae0751f37d046ef28ed11e60e776ac
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373980"
---
# <a name="cedit-class"></a>CEdit Sınıfı

Windows edit denetiminin işlevselliğini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CEdit : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|Bir `CEdit` denetim nesnesi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|Bir edit denetimi işleminin geri alınıp alınamayacağını belirler.|
|[CEdit::CharFromPos](#charfrompos)|Belirli bir konuma en yakın karakter için çizgi ve karakter dizinlerini alır.|
|[CEdit::Açık](#clear)|Düzen denetimindeki geçerli seçimi (varsa) siler (temizler).|
|[CEdit::Kopyala](#copy)|Denetim denetimindeki geçerli seçimi (varsa) Pano'ya CF_TEXT biçiminde kopyalar.|
|[CEdit::Oluştur](#create)|Windows edit denetimini oluşturur ve `CEdit` nesneye bağlar.|
|[CEdit::Kes](#cut)|Düzendenetimindeki geçerli seçimi (varsa) siler (keser) ve silinen metni panoya CF_TEXT biçiminde kopyalar.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|Bir denetim denetiminin geri alın bayrağını sıfırlar (temizler).|
|[CEdit::FmtLines](#fmtlines)|Çok satırlı bir düzen denetimi içinde yumuşak satır sonu karakterlerinin açılıp kapanan eklenmesini ayarlar.|
|[CEdit::GetCueBanner](#getcuebanner)|Denetim boş olduğunda ve odak olmadığında bir denetim denetiminde metin işareti veya ipucu olarak görüntülenen metni alır.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Bir düzen denetiminde en üstteki görünür satırı belirler.|
|[CEdit::GetHandle](#gethandle)|Birden çok satırlı bir düzen denetimi için şu anda ayrılmış olan belleğe bir tanıtıcı alır.|
|[CEdit::GetHighlight](#gethighlight)|Başlangıç ve bitiş karakterlerinin dizinlerini geçerli denetimde vurgulanan bir metin aralığında alır.|
|[CEdit::GetLimitText](#getlimittext)|Bu `CEdit` içerebileceği maksimum metin miktarını alır.|
|[CEdit::GetLine](#getline)|Bir düzen denetiminden bir metin satırı alır.|
|[CEdit::GetLineCount](#getlinecount)|Çok satırlı düzen denetimindeki satır sayısını alır.|
|[CEdit::GetMargins](#getmargins)|Bunun `CEdit`için sol ve sağ kenar boşluklarını alır.|
|[CEdit::GetModify](#getmodify)|Bir edit denetiminin içeriğinin değiştirilip değiştirilmediğini belirler.|
|[CEdit::GetPasswordChar](#getpasswordchar)|Kullanıcı metin girdiğinde bir denetim denetiminde görüntülenen parola karakterini alır.|
|[CEdit::GetRect](#getrect)|Bir düzeltme denetiminin biçimlendirme dikdörtgenini alır.|
|[CEdit::GetSel](#getsel)|Bir edit denetiminde geçerli seçimin ilk ve son karakter konumlarını alır.|
|[CEdit::HideBalloonTip](#hideballoontip)|Geçerli düzenleme denetimiyle ilişkili balon uçlarını gizler.|
|[CEdit::LimitText](#limittext)|Kullanıcının bir denetim denetimine girebileceği metnin uzunluğunu sınırlar.|
|[CEdit::LineFromChar](#linefromchar)|Belirtilen karakter dizini içeren satır ın satır numarasını alır.|
|[CEdit::LineIndex](#lineindex)|Çok satırlı bir düzen denetimi içinde bir satırın karakter dizini alır.|
|[CEdit::LineLength](#linelength)|Bir düzen denetiminde satırın uzunluğunu alır.|
|[CEdit::LineScroll](#linescroll)|Çok satırlı bir düzen denetiminin metnini kaydırır.|
|[CEdit::Paste](#paste)|Panodaki verileri geçerli imleç konumundaki edit denetimine ekler. Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.|
|[CEdit::PosFromChar](#posfromchar)|Belirtilen karakter dizininin sol üst köşesindeki koordinatları alır.|
|[CEdit::Değiştir](#replacesel)|Bir edit denetimindeki geçerli seçimi belirtilen metinle değiştirir.|
|[CEdit::SetCueBanner](#setcuebanner)|Denetim boşolduğunda ve odak olmadığında bir denetim denetiminde metin işareti veya ipucu olarak görüntülenen metni ayarlar.|
|[CEdit::SetHandle](#sethandle)|Tutamacı, çok satırlı düzenleme denetimi tarafından kullanılacak yerel belleğe ayarlar.|
|[CEdit::SetHighlight](#sethighlight)|Geçerli denetim denetiminde görüntülenen bir metin aralığını vurgular.|
|[CEdit::SetLimitText](#setlimittext)|Bu `CEdit` içerebileceği maksimum metin miktarını ayarlar.|
|[CEdit::SetMargins](#setmargins)|Bunun `CEdit`için sol ve sağ kenar boşluklarını ayarlar.|
|[CEdit::SetModify](#setmodify)|Bir denetim için değişiklik bayrağını ayarlar veya temizler.|
|[CEdit::SetPasswordChar](#setpasswordchar)|Kullanıcı metin girdiğinde bir denetim denetiminde görüntülenen bir parola karakterini ayarlar veya kaldırır.|
|[CEdit::SetReadOnly](#setreadonly)|Bir edit denetiminin salt okunur durumunu ayarlar.|
|[CEdit::SetRect](#setrect)|Çok satırlı bir düzen denetiminin biçimlendirme dikdörtgenini ayarlar ve denetimi güncelleştirir.|
|[CEdit::SetRectNP](#setrectnp)|Denetim penceresini yeniden çizmeden birden çok satırlı bir düzen denetiminin biçimlendirme dikdörtgenini ayarlar.|
|[CEdit::SetSel](#setsel)|Bir denetimde karakter aralığı nı seçer.|
|[CEdit::SetTabStops](#settabstops)|Sekmeyi birden çok satırlı bir düzen denetiminde ayarlar.|
|[CEdit::ShowBalloonTip](#showballoontip)|Geçerli düzenleme denetimiyle ilişkili bir balon ucu görüntüler.|
|[CEdit::Geri Ala](#undo)|Son edit-control işlemini tersine çevirir.|

## <a name="remarks"></a>Açıklamalar

Bir edit denetimi, kullanıcının metin girebileceği dikdörtgen bir alt penceredir.

Bir iletişim şablonundan veya doğrudan kodunuzda bir denetim denetimi oluşturabilirsiniz. Her iki durumda da, `CEdit` `CEdit` önce nesneyi oluşturmak için oluşturucuyu çağırın, sonra Windows edit `CEdit` denetimini oluşturmak ve nesneye eklemek için [Üye Oluştur](#create) işlevini çağırın.

İnşaat, `CEdit`bir sınıftan türetilen tek adımlı bir işlem olabilir. Türemiş sınıf için bir `Create` oluşturucu yazın ve oluşturucu içinden arayın.

`CEdit`'den `CWnd`önemli işlevsellik devralır. `CEdit` Bir nesneden metin ayarlamak ve `CWnd` almak için, çok satırlı bir denetim olsa bile, bir düzen denetiminin tüm içeriğini ayarlayan veya alan [SetWindowText](cwnd-class.md#setwindowtext) ve [GetWindowText](cwnd-class.md#getwindowtext)üye işlevlerini kullanın. Çok satırlı denetimdeki metin çizgileri '\r\n' karakter dizileri ile ayrılır. Ayrıca, bir düzenleme denetimi çok `CEdit` satırlı ise, [getLine,](#getline)SetSel , [GetSel](#getsel) [SetSel](#setsel)ve [ReplaceSel](#replacesel)üye işlevleri çağırarak kontrol metninin bir kısmını almak ve ayarlamak .

Bir düzenleme denetimi tarafından üst öğesine gönderilen Windows bildirim iletilerini işlemek `CDialog`istiyorsanız (genellikle bir sınıf türetilmiş), her ileti için üst sınıfa bir ileti eşlemi girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti-eş-eşlemi girişi aşağıdaki formu alır:

  **ON_**_TEBLİğİ_**(** _id_**,** _üyeFxn_ **)**

bildirim `id` gönderen edit denetiminin alt pencere kimliğini belirtir `memberFxn` ve bildirimi işlemek için yazdığınız üst üye işlevinin adıdır.

Ebeveynin işlev prototipi aşağıdaki gibidir:

**afx_msg** void üyeFxn **( );**

Aşağıda, olası ileti eşlemi girişlerinin bir listesi ve bunların üst öğeye gönderilecekleri durumların açıklaması verilmiştir:

- ON_EN_CHANGE Kullanıcı, bir denetimde metni değiştirmiş olabilecek bir eylemde bulunabilir. EN_UPDATE bildirim iletisinin aksine, bu bildirim iletisi Windows ekranı güncelledikten sonra gönderilir.

- ON_EN_ERRSPACE Denetim denetimi belirli bir isteği karşılamak için yeterli bellek ayıramaz.

- ON_EN_HSCROLL Kullanıcı bir edit denetiminin yatay kaydırma çubuğunu tıklatır. Ekran güncelleştirilmeden önce üst pencere bildirilir.

- ON_EN_KILLFOCUS Edit denetimi giriş odağı kaybeder.

- ON_EN_MAXTEXT Geçerli ekleme, edit denetimi için belirtilen karakter sayısını aştı ve kesildi. Bir edit denetimi ES_AUTOHSCROLL stiline sahip değilse ve eklenecek karakter sayısı, denetim denetiminin genişliğini aşarsa da gönderilir. Bir edit denetimi ES_AUTOVSCROLL stiline sahip olmadığında da gönderilir ve metin eklemeden kaynaklanan toplam satır sayısı, denetim denetiminin yüksekliğini aşar.

- ON_EN_SETFOCUS Bir edit denetimi giriş odağı aldığında gönderildi.

- ON_EN_UPDATE Edit denetimi değiştirilmiş metni görüntülemek üzeredir. Denetim metni biçimlendirdikten sonra gönderilir, ancak gerekirse pencere boyutunun değiştirilebilmeleri için metni taranan metinden önce.

- ON_EN_VSCROLL Kullanıcı bir edit denetiminin dikey kaydırma çubuğunu tıklatır. Ekran güncelleştirilmeden önce üst pencere bildirilir.

İletişim kutusu `CEdit` içinde bir nesne oluşturursanız, kullanıcı iletişim kutusunu kapattığında `CEdit` nesne otomatik olarak yok edilir.

İletişim düzenleyicisini `CEdit` kullanarak iletişim kaynağından bir nesne oluşturursanız, kullanıcı iletişim kutusunu kapattığında `CEdit` nesne otomatik olarak yok edilir.

Bir pencere `CEdit` içinde bir nesne oluşturursanız, onu yok etmek de gerekebilir. Yığının `CEdit` üzerinde nesne oluşturursanız, otomatik olarak yok edilir. Nesneyi `CEdit` **yeni** işlevi kullanarak yığında oluşturursanız, kullanıcı Windows düzenleme denetimini sonlandırdığinde nesneyi yok etmek için nesneyi **silme** çağrısında bulunmalısınız. Nesnede `CEdit` herhangi bir bellek ayırırsanız, `CEdit` ayırmaları elden çıkarmak için yıkıcı geçersiz kılın.

Bir edit denetiminde belirli stilleri değiştirmek için (ES_READONLY gibi) [ModifyStyle](cwnd-class.md#modifystyle)kullanmak yerine denetime belirli iletiler göndermeniz gerekir. Bkz. Windows SDK'daki [Denetim Stillerini Edin.](/windows/win32/Controls/edit-control-styles)

Daha fazla `CEdit`bilgi için Bkz. [Denetimler.](../../mfc/controls-mfc.md)

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](cobject-class.md)

[Ccmdtarget](ccmdtarget-class.md)

[Cwnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxwin.h

## <a name="ceditcanundo"></a><a name="canundo"></a>CEdit::CanUndo

Son edit işleminin geri alınıp alınamayacağına karar vermek için bu işlevi arayın.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son düzenleme işlemi üye işlevine yapılan bir çağrı `Undo` yla geri alınabilirse sıfıra inme; Geri alınamazsa 0.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EM_CANUNDO](/windows/win32/Controls/em-canundo) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın::Geri al.](#undo)

## <a name="ceditcedit"></a><a name="cedit"></a>CEdit::CEdit

Bir `CEdit` nesne inşa eder.

```
CEdit();
```

### <a name="remarks"></a>Açıklamalar

Windows denetim denetimini oluşturmak için [Oluştur'u](#create) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

## <a name="ceditcharfrompos"></a><a name="charfrompos"></a>CEdit::CharFromPos

Bu denetimde belirtilen noktaya en yakın karakterin sıfır tabanlı çizgi ve karakter `CEdit` dizinlerini almak için bu işlevi arayın

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Parametreler

*Pt*<br/>
Bu `CEdit` nesnenin istemci alanında bir noktanın koordinatları.

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı WORD'deki karakter dizini ve yüksek sıralı WORD'deki satır dizini.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu üye işlev, Windows 95 ve Windows NT 4.0 ile başlayarak kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_CHARFROMPOS](/windows/win32/Controls/em-charfrompos) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

## <a name="ceditclear"></a><a name="clear"></a>CEdit::Açık

Düzenle denetimindeki geçerli seçimi (varsa) silmek (temizlemek) için bu işlevi arayın.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Geri `Clear` A.Ş. üye işlevini arayarak [Undo](#undo) gerçekleştirdiği silme işlemi geri alınabilir.

Geçerli seçimi silmek ve silinen içeriği Pano'ya yerleştirmek için [Kes](#cut) üye işlevini arayın.

Daha fazla bilgi için Windows SDK'daki [WM_CLEAR](/windows/win32/dataxchg/wm-clear) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

## <a name="ceditcopy"></a><a name="copy"></a>CEdit::Kopyala

CF_TEXT formatında Pano'ya edit denetimindeki geçerli seçimi (varsa) çekinmeye çalışmak için bu işlevi arayın.

```
void Copy();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [WM_COPY](/windows/win32/dataxchg/wm-copy) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

## <a name="ceditcreate"></a><a name="create"></a>CEdit::Oluştur

Windows edit denetimini oluşturur ve `CEdit` nesneye bağlar.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*Dwstyle*<br/>
Edit denetiminin stilini belirtir. [Denetime herhangi](styles-used-by-mfc.md#edit-styles) bir denetim stilleri birleşimi uygulayın.

*Rect*<br/>
Edit denetiminin boyutunu ve konumunu belirtir. Bir `CRect` nesne veya `RECT` yapı olabilir.

*pParentWnd*<br/>
Edit denetiminin üst penceresini belirtir (genellikle bir). `CDialog` NULL olmamalıdır.

*Nıd*<br/>
Denetim denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfırsız; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Bir nesneyi `CEdit` iki adımda inşa ee. İlk olarak, `CEdit` oluşturucuyu `Create`çağırın ve ardından Windows edit denetimini `CEdit` oluşturan ve nesneye iliştiren ,

Yürütüldüğünde, `Create` Windows [WM_NCCREATE](/windows/win32/winmsg/wm-nccreate), [WM_NCCALCSIZE,](/windows/win32/winmsg/wm-nccalcsize) [WM_CREATE](/windows/win32/winmsg/wm-create)ve [WM_GETMINMAXINFO](/windows/win32/winmsg/wm-getminmaxinfo) iletileri denetim denetimine gönderir.

Bu iletiler varsayılan olarak [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate)ve [OnGetMinMaxInfo](cwnd-class.md#ongetminmaxinfo) üye işlevleri tarafından `CWnd` temel sınıfta işlenir. Varsayılan ileti işlemeyi genişletmek için, `CEdit`yeni sınıfa bir ileti eşlemi ekleyin ve yukarıdaki ileti işleyicisi üye işlevlerini geçersiz kılın. Geçersiz `OnCreate`kılma , örneğin, yeni sınıf için gerekli başlatma gerçekleştirmek için.

Aşağıdaki [pencere stillerini](styles-used-by-mfc.md#window-styles) bir denetime uygulayın.

- WS_CHILD Her Zaman

- WS_VISIBLE Genellikle

- WS_DISABLED Nadiren

- WS_GROUP Denetimleri gruplandırmak için

- WS_TABSTOP Denetimdenetimisekme sırasına eklemek için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

## <a name="ceditcut"></a><a name="cut"></a>CEdit::Kes

Düzenle denetimindeki geçerli seçimi (varsa) silmek (kesmek) için bu işlevi arayın ve silinen metni CF_TEXT biçiminde Pano'ya kopyalayın.

```
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Geri `Cut` A.Ş. üye işlevini arayarak [Undo](#undo) gerçekleştirdiği silme işlemi geri alınabilir.

Silinen metni Panoya yerleştirmeden geçerli seçimi silmek için [Üye](#clear) İcadını Temizle'yi arayın.

Daha fazla bilgi için Windows SDK'daki [WM_CUT](/windows/win32/dataxchg/wm-cut) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

## <a name="ceditemptyundobuffer"></a><a name="emptyundobuffer"></a>CEdit::EmptyUndoBuffer

Bir denetim denetiminin geri alın bayrağını sıfırlamak (temizlemek) için bu işlevi çağırın.

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Açıklamalar

Düzenlenen denetim artık son işlemi geri alamayacak. Geri alabilen bayrak, denetim içindeki bir işlem geri alınabildiği zaman ayarlanır.

[SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) veya [SetHandle](#sethandle) `CWnd` üye işlevleri çağrıldığında geri alameti otomatik olarak temizlenir.

Daha fazla bilgi için Windows SDK'daki [EM_EMPTYUNDOBUFFER](/windows/win32/Controls/em-emptyundobuffer) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

## <a name="ceditfmtlines"></a><a name="fmtlines"></a>CEdit::FmtLines

Çok satırlı bir düzen denetimi içinde yumuşak satır sonu karakterlerinin eklenmesini veya kapamasını ayarlamak için bu işlevi çağırın.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Parametreler

*bAddEOL*<br/>
Yumuşak satır sonu karakterlerinin eklenip eklenmeyeceğini belirtir. TRUE'nun değeri karakterleri ekler; FALSE değeri bunları kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir biçimlendirme oluşursa sıfırolmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Yumuşak bir satır sonu, sözcük kaydırma nedeniyle bozulan bir satırın sonuna iki satır satırı ve bir satır beslemesi eklenir. Sabit satır sonu, bir satır dönüşü ve bir satır beslemesi oluşur. Sabit satır sonuyla biten satırlar' `FmtLines`dan etkilenmez.

Windows yalnızca `CEdit` nesne çok satırlı bir düzen denetimi yse yanıt verir.

`FmtLines`yalnızca [GetHandle](#gethandle) tarafından döndürülen arabelleği ve [WM_GETTEXT](/windows/win32/winmsg/wm-gettext)tarafından döndürülen metni etkiler. Bu edit denetimi içinde metnin görüntülenmesi üzerinde hiçbir etkisi yoktur.

Daha fazla bilgi için Windows SDK'daki [EM_FMTLINES](/windows/win32/Controls/em-fmtlines) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

## <a name="ceditgetcuebanner"></a><a name="getcuebanner"></a>CEdit::GetCueBanner

Denetim boşken bir denetim denetiminde metin işareti veya ipucu olarak görüntülenen metni alır.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[çıkış] İşaret metnini içeren bir dize için işaretçi.

*cchText*<br/>
[içinde] Alınabilecek karakter sayısı. Bu sayı sonlandırıcı NULL karakterini içerir.

### <a name="return-value"></a>Dönüş Değeri

İlk aşırı yükleme için, yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

İkinci aşırı yükleme için, yöntem başarılı olursa işaret metnini içeren bir [CString;](../../atl-mfc-shared/using-cstring.md) aksi takdirde, boş dize ("").

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [EM_GETCUEBANNER](/windows/win32/Controls/em-getcuebanner) iletisini gönderir. Daha fazla bilgi için [Edit_GetCueBannerText](/windows/win32/api/commctrl/nf-commctrl-edit_getcuebannertext) makroya bakın.

## <a name="ceditgetfirstvisibleline"></a><a name="getfirstvisibleline"></a>CEdit::GetFirstVisibleLine

Bir düzen denetiminde en üstteki görünür satırı belirlemek için bu işlevi arayın.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Dönüş Değeri

En üstteki görünür çizginin sıfır tabanlı dizin. Tek satırlı düzen denetimleri için iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EM_GETFIRSTVISIBLELINE](/windows/win32/Controls/em-getfirstvisibleline) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

## <a name="ceditgethandle"></a><a name="gethandle"></a>CEdit::GetHandle

Birden çok satırlı bir düzen denetimi için ayrılan belleğe bir tanıtıcı almak için bu işlevi arayın.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin içeriğini tutan arabelleği tanımlayan yerel bir bellek tutamacı. İletiyi tek satırlı bir düzen denetimine göndermek gibi bir hata oluşursa, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Tutamacı yerel bir bellek tutamacıdır ve parametre olarak yerel bellek tutamacını alan **Yerel** Windows bellek işlevlerinden herhangi biri tarafından kullanılabilir.

`GetHandle`yalnızca çok satırlı düzenleme denetimleri tarafından işlenir.

Yalnızca `GetHandle` iletişim kutusu DS_LOCALEDIT stil bayrak kümesiyle oluşturulmuşsa, iletişim kutusunda çok satırlı bir düzen denetimi için çağrıda deyin. stil DS_LOCALEDIT ayarlanmazsa, yine de sıfır olmayan bir iade değeri alırsınız, ancak döndürülen değeri kullanamazsınız.

> [!NOTE]
> `GetHandle`Windows 95/98 ile çalışmaz. Windows 95/98'i ararsanız, `GetHandle` NULL döndürecektir. `GetHandle`Windows NT, sürüm 3.51 ve daha sonra altında belgelenmiş olarak çalışacaktır.

Daha fazla bilgi için Windows SDK'daki [EM_GETHANDLE](/windows/win32/Controls/em-gethandle) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

## <a name="ceditgethighlight"></a><a name="gethighlight"></a>CEdit::GetHighlight

Geçerli edit denetiminde vurgulanan bir metin aralığındaki ilk ve son karakterlerin dizinlerini alır.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pichStart*|[çıkış] Vurgulanan metin aralığındaki ilk karakterin sıfır tabanlı dizini.|
|*pichEnd*|[çıkış] Vurgulanan metin aralığındaki son karakterin sıfır tabanlı dizini.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [EM_GETHILITE](/windows/win32/Controls/em-gethilite) iletisini gönderir. Her `SetHighlight` `GetHighlight` ikisi de ve şu anda yalnızca UNICODE yapılar için etkinleştirilir.

## <a name="ceditgetlimittext"></a><a name="getlimittext"></a>CEdit::GetLimitText

Bu `CEdit` nesne için metin sınırını almak için bu üye işlevi arayın.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu `CEdit` nesne için TCHAR'larda geçerli metin sınırı.

### <a name="remarks"></a>Açıklamalar

Metin sınırı, tchar'larda, denetimdenetiminin kabul edebileceği maksimum metin miktarıdır.

> [!NOTE]
> Bu üye işlev, Windows 95 ve Windows NT 4.0 ile başlayarak kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_GETLIMITTEXT](/windows/win32/Controls/em-getlimittext) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

## <a name="ceditgetline"></a><a name="getline"></a>CEdit::GetLine

Bir düzen denetiminden bir metin satırı almak için bu işlevi arayın ve *lpszBuffer'a*yerleştirin.

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

*Nındex*<br/>
Çok satırlı bir düzen denetiminden alınacak satır numarasını belirtir. Satır numaraları sıfır tabanlıdır; 0 değeri ilk satırı belirtir. Bu parametre, tek satırlık düzenleme denetimi tarafından yoksayılır.

*lpszBuffer*<br/>
Satırın bir kopyasını alan arabelleğe işaret edin. Arabelleğe ilk sözcük, arabelleğe kopyalanabilecek maksimum TCHA sayısını belirtmelidir.

*nMaxLength*<br/>
Arabelleğe kopyalanabilecek maksimum TCHAR karakter sayısını belirtir. `GetLine`Windows'a arama yapmadan önce *lpszBuffer* ilk kelime bu değeri yerleştirir.

### <a name="return-value"></a>Dönüş Değeri

Kopyalanan karakter sayısı. *nIndex* tarafından belirtilen satır numarası düzenleme denetimindeki satır sayısından büyükse, iade değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Kopyalanan satır null-sonlandırma karakteri içermez.

Daha fazla bilgi için Windows SDK'daki [EM_GETLINE](/windows/win32/Controls/em-getline) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:GetLineCount](#getlinecount).

## <a name="ceditgetlinecount"></a><a name="getlinecount"></a>CEdit::GetLineCount

Çok satırlı düzen denetimindeki satır sayısını almak için bu işlevi arayın.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çoklu satır lı düzen denetimindeki satır sayısını içeren bir ortalık. Edit denetimine metin girilmişse, iade değeri 1'dir.

### <a name="remarks"></a>Açıklamalar

`GetLineCount`yalnızca çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK'daki [EM_GETLINECOUNT](/windows/win32/Controls/em-getlinecount) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

## <a name="ceditgetmargins"></a><a name="getmargins"></a>CEdit::GetMargins

Bu edit denetiminin sol ve sağ kenar boşluklarını almak için bu üye işlevi arayın.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük sıralı WORD'de sol kenar boşluğunun genişliği ve yüksek sıralı WORD'deki sağ kenar boşluğunun genişliği.

### <a name="remarks"></a>Açıklamalar

Kenar boşlukları piksel cinsinden ölçülür.

> [!NOTE]
> Bu üye işlev, Windows 95 ve Windows NT 4.0 ile başlayarak kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_GETMARGINS](/windows/win32/Controls/em-getmargins) bakın.

### <a name="example"></a>Örnek

  [CEditView örneğine bakın:GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditgetmodify"></a><a name="getmodify"></a>CEdit::GetModify

Bir edit denetiminin içeriğinin değiştirilip değiştirilmediğini belirlemek için bu işlevi arayın.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Dönüş Değeri

Edit denetimi içeriği değiştirildiyse sıfırsız; Değişmeden kalmıştır 0.

### <a name="remarks"></a>Açıklamalar

Windows, denetim denetiminin içeriğinin değiştirilip değiştirilmediğini belirten bir iç bayrak tutar. Düzenleme denetimi ilk oluşturulduğunda bu bayrak temizlenir ve [SetModify](#setmodify) üye işlevini çağırarak da temizlenebilir.

Daha fazla bilgi için Windows SDK'daki [EM_GETMODIFY](/windows/win32/Controls/em-getmodify) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

## <a name="ceditgetpasswordchar"></a><a name="getpasswordchar"></a>CEdit::GetPasswordChar

Kullanıcı metin girdiğinde bir denetim denetiminde görüntülenen parola karakterini almak için bu işlevi arayın.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcının yazdığı karakter yerine görüntülenecek karakteri belirtir. Parola karakteri yoksa iade değeri NULL'dur.

### <a name="remarks"></a>Açıklamalar

ES_PASSWORD stiliyle denetim denetimi oluşturursanız, denetimi destekleyen DLL varsayılan parola karakterini belirler. Bildirim veya [InitCommonControlsEx](/windows/win32/api/commctrl/nf-commctrl-initcommoncontrolsex) yöntemi, hangi DLL'nin denetim denetimini desteklediğini belirler. User32.dll denetim denetimini destekliyorsa, varsayılan parola karakteri ASTERISK ('*', U+002A). Comctl32.dll sürüm 6 denetimdenetimini destekliyorsa, varsayılan karakter BLACK CIRCLE ('●', U+25CF). Hangi DLL ve sürümün ortak denetimleri desteklediği hakkında daha fazla bilgi için [Shell ve Ortak Denetimsürümleri'ne](/previous-versions/windows/desktop/legacy/bb776779\(v=vs.85\))bakın.

Bu yöntem, Windows SDK'da açıklanan [EM_GETPASSWORDCHAR](/windows/win32/Controls/em-getpasswordchar) iletisini gönderir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

## <a name="ceditgetrect"></a><a name="getrect"></a>CEdit::GetRect

Bir edit denetiminin biçimlendirme dikdörtgenini almak için bu işlevi arayın.

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Biçimlendirme `RECT` dikdörtgenini alan yapıyı işaret edin.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgeni, metindeki sınırlayıcı dikdörtgendir ve bu dikdörtgen denetim penceresinin boyutundan bağımsızdır.

Birden çok satırlı düzenleme denetiminin biçimlendirme dikdörtgeni [SetRect](#setrect) ve [SetRectNP](#setrectnp) üye işlevleri tarafından değiştirilebilir.

Daha fazla bilgi için Windows SDK'daki [EM_GETRECT](/windows/win32/Controls/em-getrect) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:LimitText](#limittext).

## <a name="ceditgetsel"></a><a name="getsel"></a>CEdit::GetSel

İade değerini veya parametreleri kullanarak geçerli seçimin başlangıç ve bitiş karakter konumlarını (varsa) bir edit denetiminde almak için bu işlevi arayın.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Geçerli seçimdeki ilk karakterin konumunu alacak bir aramaya başvuru.

*nEndChar*<br/>
Geçerli seçimin sonundan sonra ilk seçilmemiş karakterin konumunu alacak bir karşıcıya başvuru.

### <a name="return-value"></a>Dönüş Değeri

DWORD döndüren sürüm, düşük sıralı sözcükteki başlangıç konumunu ve yüksek sıralı sözcükteki seçimin bitiminden sonra ilk seçilmemiş karakterin konumunu içeren bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EM_GETSEL](/windows/win32/Controls/em-getsel) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

## <a name="cedithideballoontip"></a><a name="hideballoontip"></a>CEdit::HideBalloonTip

Geçerli düzenleme denetimiyle ilişkili balon uçlarını gizler.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK'da açıklanan [EM_HIDEBALLOONTIP](/windows/win32/Controls/em-hideballoontip) iletisini gönderir.

## <a name="ceditlimittext"></a><a name="limittext"></a>CEdit::LimitText

Kullanıcının bir denetim denetimine girebileceği metnin uzunluğunu sınırlamak için bu işlevi arayın.

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*nChars*<br/>
Kullanıcının girebileceği metnin uzunluğunu (TCHAR'larda) belirtir. Bu parametre 0 ise, metin uzunluğu bayt UINT_MAX olarak ayarlanır. Bu varsayılan davranıştır.

### <a name="remarks"></a>Açıklamalar

Metin sınırını değiştirmek yalnızca kullanıcının girebileceği metni kısıtlar. Düzenleme denetiminde zaten bulunan herhangi bir metin üzerinde hiçbir etkisi yoktur ve `CWnd` ['deki SetWindowText](cwnd-class.md#setwindowtext) üye işlevi tarafından düzenleme denetimine kopyalanan metnin uzunluğunu etkilemez. Bir `SetWindowText` uygulama, bir düzen denetimine çağrıda belirtilenden daha fazla metin `LimitText`yerleştirmek için işlevi kullanırsa, kullanıcı düzen denetimindeki metinlerden herhangi birini silebilir. Ancak, geçerli seçim insilen metin sınırının altına düşmesine neden olmadığı sürece, metin sınırı kullanıcının varolan metni yeni metinle değiştirmesini engeller.

> [!NOTE]
> Win32'de (Windows NT ve Windows 95/98), [SetLimitText](#setlimittext) bu işlevin yerini alır.

Daha fazla bilgi için Windows SDK'daki [EM_LIMITTEXT](/windows/win32/Controls/em-limittext) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

## <a name="ceditlinefromchar"></a><a name="linefromchar"></a>CEdit::LineFromChar

Belirtilen karakter dizini içeren satır ın satır numarasını almak için bu işlevi arayın.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Edit denetimi metninde istenen karakter için sıfır tabanlı dizin değerini veya -1'i içerir. *nIndex* -1 ise, geçerli satırı, yani caret içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından belirtilen karakter dizini içeren çizginin sıfır tabanlı satır numarası. *nIndex* -1 ise, seçimin ilk karakterini içeren satır ın sayısı döndürülür. Seçim yoksa, geçerli satır numarası döndürülür.

### <a name="remarks"></a>Açıklamalar

Karakter dizini, edit denetiminin başlangıcından itibaren karakter sayısıdır.

Bu üye işlev yalnızca birden fazla satırlı düzenleme denetimleri tarafından kullanılır.

Daha fazla bilgi için Windows SDK'daki [EM_LINEFROMCHAR](/windows/win32/Controls/em-linefromchar) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

## <a name="ceditlineindex"></a><a name="lineindex"></a>CEdit::LineIndex

Çok satırlı bir düzen denetimi içinde bir satırın karakter dizini almak için bu işlevi arayın.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*nLine*<br/>
Düzenle denetimi metninde istenen satırın dizin değerini içerir veya -1 içerir. *nLine* -1 ise, geçerli satırı, yani caret içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen satır numarası düzendenetimindeki satır sayısından büyükse *nLine* veya -1'de belirtilen çizginin karakter dizini.

### <a name="remarks"></a>Açıklamalar

Karakter dizini, düzen denetiminin başlangıcından belirtilen satıra kadar olan karakter sayısıdır.

Bu üye işlev yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK'daki [EM_LINEINDEX](/windows/win32/controls/em-lineindex) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

## <a name="ceditlinelength"></a><a name="linelength"></a>CEdit::LineLength

Bir düzen denetiminde satırın uzunluğunu alır.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*nLine*<br/>
Uzunluğu alınacak çizgideki bir karakterin sıfır tabanlı dizin. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Tek satırlı düzen denetimleri için, iade değeri, tchar'larda, düzen denetimindeki metnin uzunluğudur.

Çok satırlı düzenleme denetimleri için, iade değeri, *nLine* parametresi tarafından belirtilen satırın TCHAR cinsinden uzunluğudur. ANSI metni için uzunluk satırdaki bayt sayısıdır; Unicode metin için uzunluk satırdaki karakter sayısıdır. Uzunluk, satırın sonundaki satır döndürme karakterini içermez.

*nLine* parametresi denetimdeki karakter sayısından fazlaysa, geri dönüş değeri sıfırdır.

*nLine* parametresi -1 ise, iade değeri seçili karakterleri içeren satırlarda seçilmemiş karakter sayısıdır. Örneğin, seçim bir satırın dördüncü karakterinden bir sonraki satırın sonundaki sekizinci karaktere kadar uzanırsa, iade değeri 10'dur. Yani, ilk satırda üç karakter ve diğer satırda yedi karakter.

TCHAR türü hakkında daha fazla bilgi [için, Windows Veri Türleri](/windows/win32/WinProg/windows-data-types)tablosundaki TCHAR satırına bakın.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [EM_LINELENGTH](/windows/win32/Controls/em-linelength) iletitarafından desteklenir.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:LineIndex.](#lineindex)

## <a name="ceditlinescroll"></a><a name="linescroll"></a>CEdit::LineScroll

Çok satırlı bir düzen denetiminin metnini kaydırmak için bu işlevi arayın.

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*nLines*<br/>
Dikey kaydırma yapmak için satır sayısını belirtir.

*nChars*<br/>
Yatay kaydırma yapmak için karakter pozisyonlarının sayısını belirtir. Bu değer, ES_RIGHT veya ES_CENTER stili ne varsa, bu değer yoksayılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlev yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Düzenle denetimi, düzen denetimindeki son metin satırının ötesine dikey olarak kaydırılamıyor. Geçerli satır artı *nLines* tarafından belirtilen satır sayısı düzenleme denetimindeki toplam satır sayısını aşıyorsa, düzenleme denetiminin son satırı düzenleme denetimi penceresinin en üstüne kaydırılanacak şekilde değer ayarlanır.

`LineScroll`herhangi bir satırın son karakterini yatay olarak kaydırmak için kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_LINESCROLL](/windows/win32/Controls/em-linescroll) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:GetFirstVisibleLine](#getfirstvisibleline).

## <a name="ceditpaste"></a><a name="paste"></a>CEdit::Paste

Panodaki verileri ekleme noktasına eklemek için `CEdit` bu işlevi arayın.

```
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Veriler yalnızca Pano CF_TEXT biçiminde veri içeriyorsa eklenir.

Daha fazla bilgi için Windows SDK'daki [WM_PASTE](/windows/win32/dataxchg/wm-paste) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

## <a name="ceditposfromchar"></a><a name="posfromchar"></a>CEdit::PosFromChar

Bu `CEdit` nesneiçinde belirli bir karakterin konumunu (sol üst köşe) almak için bu işlevi arayın.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Parametreler

*Nchar*<br/>
Belirtilen karakterin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

*nChar*tarafından belirtilen karakterin sol üst köşesinin koordinatları.

### <a name="remarks"></a>Açıklamalar

Karakter sıfır tabanlı dizin değeri vererek belirtilir. *nChar* bu `CEdit` nesnedeki son karakterin dizini nden büyükse, iade değeri bu `CEdit` nesnedeki son karakteri geçmiş karakter konumunun koordinatlarını belirtir.

> [!NOTE]
> Bu üye işlev, Windows 95 ve Windows NT 4.0 ile başlayarak kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_POSFROMCHAR](/windows/win32/Controls/em-posfromchar) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:LineFromChar](#linefromchar).

## <a name="ceditreplacesel"></a><a name="replacesel"></a>CEdit::Değiştir

Bir düzenleme denetimindeki geçerli seçimi *lpszNewText*tarafından belirtilen metinle değiştirmek için bu işlevi arayın.

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszNewText*<br/>
Değiştirilen metni içeren null-sonlandırılan dizeyi işaret eder.

*bCanUndo*<br/>
Bu işlevin geri alınabileceğini belirtmek için, bu parametrenin değerini TRUE olarak ayarlayın. Varsayılan değer FALSE'dur.

### <a name="remarks"></a>Açıklamalar

Bir denetimde metnin yalnızca bir bölümünü değiştirir. Metnin tümünün değiştirilmesini istiyorsanız [CWnd::SetWindowText](cwnd-class.md#setwindowtext) üye işlevini kullanın.

Geçerli seçim yoksa, değiştirme metni geçerli imleç konumuna eklenir.

Daha fazla bilgi için Windows SDK'daki [EM_REPLACESEL](/windows/win32/Controls/em-replacesel) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:LineIndex.](#lineindex)

## <a name="ceditsetcuebanner"></a><a name="setcuebanner"></a>CEdit::SetCueBanner

Denetim boşken bir denetim denetiminde metin işareti veya ipucu olarak görüntülenen metni ayarlar.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszMetin*<br/>
[içinde] Denetimde görüntülenecek işaretişaretçiyi içeren bir dize işaretçisi.

*fDrawWhenFocused*<br/>
[içinde] FALSE ise, kullanıcı denetime tıkladığında ve denetime odak verdiğinde işaret başlığı çizilmez.

TRUE ise, işaret afişi denetim odak olsa bile çizilir. Kullanıcı denetimi yazmaya başladığında işaret başlığı kaybolur.

Varsayılan değer FALSE'dur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa DOĞRU; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [EM_SETCUEBANNER](/windows/win32/Controls/em-setcuebanner) iletisini gönderir. Daha fazla bilgi için [Edit_SetCueBannerTextFocused](/windows/win32/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) makroya bakın.

### <a name="example"></a>Örnek

Aşağıdaki [örnek, CEdit::SetCueBanner](#setcuebanner) yöntemini gösterir.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

## <a name="ceditsethandle"></a><a name="sethandle"></a>CEdit::SetHandle

Tutamacı, çok satırlı düzenleme denetimi tarafından kullanılacak yerel belleğe ayarlamak için bu işlevi çağırın.

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Parametreler

*hBuffer*<br/>
Yerel belleğe bir tutamaç içerir. Bu tanıtıcı, LMEM_MOVEABLE bayrağını kullanarak [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc) Windows işlevine yapılan önceki bir çağrı tarafından oluşturulmuş olmalıdır. Belleğin null-sonlandırılan dize içerdiği varsayılır. Bu durumda değilse, ayrılan belleğin ilk bayt 0 olarak ayarlanmalıdır.

### <a name="remarks"></a>Açıklamalar

Edit denetimi, kendi arabelleği ayırmak yerine şu anda görüntülenen metni depolamak için bu arabelleği kullanır.

Bu üye işlev yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Bir uygulama yeni bir bellek tutamacı belirlemeden önce, işletmeyi geçerli bellek arabelleğine getirmek `LocalFree` ve Windows işlevini kullanarak bu belleği serbest etmek için [GetHandle](#gethandle) üye işlevini kullanmalıdır.

`SetHandle`Geri alma arabelleği [(CanUndo](#canundo) üye işlevi sonra 0 döndürür) ve iç modifikasyon bayrağı [(GetModify](#getmodify) üye işlevi sonra 0 döndürür) temizler. Denetim penceresi yeniden çizilir.

Bu üye işlevini, iletişim kutusundaki çok satırlı bir düzen denetiminde yalnızca DS_LOCALEDIT stil bayrak kümesine sahip iletişim kutusunu oluşturduysanız kullanabilirsiniz.

> [!NOTE]
> `GetHandle`Windows 95/98 ile çalışmaz. Windows 95/98'i ararsanız, `GetHandle` NULL döndürecektir. `GetHandle`Windows NT, sürüm 3.51 ve daha sonra altında belgelenmiş olarak çalışacaktır.

Daha fazla bilgi için Windows SDK'da [EM_SETHANDLE,](/windows/win32/Controls/em-sethandle) [LocalAlloc](/windows/win32/api/winbase/nf-winbase-localalloc)ve [LocalFree'e](/windows/win32/api/winbase/nf-winbase-localfree) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

## <a name="ceditsethighlight"></a><a name="sethighlight"></a>CEdit::SetHighlight

Geçerli denetim denetiminde görüntülenen bir metin aralığını vurgular.

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ichStart*|[içinde] Vurgulamak için metin aralığındailk karakterin sıfır tabanlı dizin.|
|*ichEnd*|[içinde] Vurgulamak için metin aralığındason karakterin sıfır tabanlı dizin.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem, Windows SDK'da açıklanan [EM_SETHILITE](/windows/win32/Controls/em-sethilite) iletisini gönderir.  Bu yöntem, Windows SDK'da açıklanan [EM_SETHILITE](/windows/win32/Controls/em-sethilite) iletisini gönderir. Her `SetHighlight` `GetHighlight` ikisi de ve unicode için etkinleştirilir yalnızca oluşturur.

## <a name="ceditsetlimittext"></a><a name="setlimittext"></a>CEdit::SetLimitText

Bu `CEdit` nesne için metin sınırını ayarlamak için bu üye işlevi arayın.

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Karakterlerde yeni metin sınırı.

### <a name="remarks"></a>Açıklamalar

Metin sınırı, karakter olarak, denetim denetiminin kabul edebileceği maksimum metin miktarıdır.

Metin sınırını değiştirmek yalnızca kullanıcının girebileceği metni kısıtlar. Düzenleme denetiminde zaten bulunan herhangi bir metin üzerinde hiçbir etkisi yoktur ve `CWnd` ['deki SetWindowText](cwnd-class.md#setwindowtext) üye işlevi tarafından düzenleme denetimine kopyalanan metnin uzunluğunu etkilemez. Bir `SetWindowText` uygulama, bir düzen denetimine çağrıda belirtilenden daha fazla metin `LimitText`yerleştirmek için işlevi kullanırsa, kullanıcı düzen denetimindeki metinlerden herhangi birini silebilir. Ancak, geçerli seçim insilen metin sınırının altına düşmesine neden olmadığı sürece, metin sınırı kullanıcının varolan metni yeni metinle değiştirmesini engeller.

Bu işlev Win32'de [LimitText'in](#limittext) yerini alır.

Daha fazla bilgi için Windows SDK'daki [EM_SETLIMITTEXT](/windows/win32/Controls/em-setlimittext) bakın.

### <a name="example"></a>Örnek

  [CEditView örneğine bakın:GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditsetmargins"></a><a name="setmargins"></a>CEdit::SetMargins

Bu edit denetiminin sol ve sağ kenar boşluklarını ayarlamak için bu yöntemi çağırın.

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>Parametreler

*nLeft*<br/>
Yeni sol kenar boşluğunun genişliği, pikselolarak.

*nHakkı*<br/>
Yeni sağ kenar boşluğunun piksel genişliği.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
> Bu üye işlev, Windows 95 ve Windows NT 4.0 ile başlayarak kullanılabilir.

Daha fazla bilgi için Windows SDK'daki [EM_SETMARGINS](/windows/win32/Controls/em-setmargins) bakın.

### <a name="example"></a>Örnek

  [CEditView örneğine bakın:GetEditCtrl](ceditview-class.md#geteditctrl).

## <a name="ceditsetmodify"></a><a name="setmodify"></a>CEdit::SetModify

Bir denetim denetimi için değiştirilmiş bayrağı ayarlamak veya temizlemek için bu işlevi çağırın.

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModideğişiklik*<br/>
TRUE değeri metnin değiştirildiğini ve FALSE değerinin değiştirilmediğini gösterir. Varsayılan olarak, değiştirilen bayrak ayarlanır.

### <a name="remarks"></a>Açıklamalar

Değiştirilen bayrak, denetim deki metnin değiştirilip değiştirilmediğini gösterir. Kullanıcı metni değiştirdiğinde otomatik olarak ayarlanır. Değeri [GetModify](#getmodify) üye işlevi ile alınabilir.

Daha fazla bilgi için Windows SDK'daki [EM_SETMODIFY](/windows/win32/Controls/em-setmodify) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:GetModify](#getmodify).

## <a name="ceditsetpasswordchar"></a><a name="setpasswordchar"></a>CEdit::SetPasswordChar

Kullanıcı metin yazdığında bir denetim denetiminde görüntülenen bir parola karakterini ayarlamak veya kaldırmak için bu işlevi arayın.

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Parametreler

*Caner*<br/>
Kullanıcı tarafından yazılan karakterin yerine görüntülenecek karakteri belirtir. *ch* 0 ise, kullanıcı tarafından yazılan gerçek karakterler görüntülenir.

### <a name="remarks"></a>Açıklamalar

Parola karakteri ayarlandığında, bu karakter kullanıcı nın yazdığı her karakter için görüntülenir.

Bu üye işlevin çok satırlı bir düzen denetimi üzerinde hiçbir etkisi yoktur.

`SetPasswordChar` Üye işlev çağrıldığında, `CEdit` *ch*tarafından belirtilen karakteri kullanarak tüm görünür karakterleri yeniden çizecektir.

ES_PASSWORD [stiliyle](styles-used-by-mfc.md#edit-styles) edit denetimi oluşturulursa, varsayılan parola karakteri yıldız işaretine ( ) <strong>\*</strong>ayarlanır. Ch kümesi 0 `SetPasswordChar` ile *ch* çağrılırsa bu stil kaldırılır.

Daha fazla bilgi için Windows SDK'daki [EM_SETPASSWORDCHAR](/windows/win32/Controls/em-setpasswordchar) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

## <a name="ceditsetreadonly"></a><a name="setreadonly"></a>CEdit::SetReadOnly

Bir edit denetiminin salt okunur durumunu ayarlamak için bu işlevi çağırır.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bReadOnly*<br/>
Edit denetiminin salt okunur durumunu ayarlayıp ayarlamayacağını belirtir. TRUE değeri, durumu salt okunur olarak ayarlar; FALSE değeri, durumu okuma/yazma olarak ayarlar.

### <a name="return-value"></a>Dönüş Değeri

İşlem başarılı olursa sıfır veya hata oluşursa 0.

### <a name="remarks"></a>Açıklamalar

Geçerli ayar CWnd dönüş değerinde [ES_READONLY](styles-used-by-mfc.md#edit-styles) bayrağı test ederek [bulunabilir::GetStyle](cwnd-class.md#getstyle).

Daha fazla bilgi için Windows SDK'daki [EM_SETREADONLY](/windows/win32/Controls/em-setreadonly) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

## <a name="ceditsetrect"></a><a name="setrect"></a>CEdit::SetRect

Belirtilen koordinatları kullanarak bir dikdörtgenin boyutlarını ayarlamak için bu işlevi çağırın.

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Biçimlendirme `RECT` dikdörtgeninin yeni boyutlarını belirten yapı veya `CRect` nesneye işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Bu üye yalnızca çok satırlı düzenleme denetimleri tarafından işlenir.

Çok `SetRect` satırlı bir düzen denetiminin biçimlendirme dikdörtgenini ayarlamak için kullanın. Biçimlendirme dikdörtgeni, metindeki sınırlayıcı dikdörtgendir ve bu dikdörtgen denetim penceresinin boyutundan bağımsızdır. Edit denetimi ilk oluşturulduğunda, biçimlendirme dikdörtgeni, denetim penceresinin istemci alanıyla aynıdır. `SetRect` Bir uygulama, üye işlevini kullanarak biçimlendirme dikdörtgenini düzenleme denetimi penceresinden daha büyük veya daha küçük yapabilir.

Biçimlendirme dikdörtgeni pencereden daha büyük sayılsa, denetimde kaydırma çubuğu yoksa, metin kırpılır, sarılmaz. Düzenleme denetimi bir kenarlık içeriyorsa, biçimlendirme dikdörtgeni kenarlının boyutuna göre küçülür. Üye işlev tarafından döndürülen dikdörtgeni `GetRect` ayarlarsanız, dikdörtgeni `SetRect`' ye geçmeden önce kenarlığın boyutunu kaldırmaniz gerekir.

Çağrıldığında, `SetRect` denetim metni de yeniden biçimlendirilir ve yeniden görüntülenir.

Daha fazla bilgi için Windows SDK'daki [EM_SETRECT](/windows/win32/Controls/em-setrect) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

## <a name="ceditsetrectnp"></a><a name="setrectnp"></a>CEdit::SetRectNP

Çok satırlı bir düzen denetiminin biçimlendirme dikdörtgenini ayarlamak için bu işlevi çağırın.

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*Lprect*<br/>
Dikdörtgenin `RECT` yeni `CRect` boyutlarını belirten bir yapıya veya nesneye işaret ediyor.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgeni, metindeki sınırlayıcı dikdörtgendir ve bu dikdörtgen denetim penceresinin boyutundan bağımsızdır.

`SetRectNP`edit-control `SetRect` penceresiyeniden çizilmediği sürece üye işlevle aynıdır.

Edit denetimi ilk oluşturulduğunda, biçimlendirme dikdörtgeni, denetim penceresinin istemci alanıyla aynıdır. `SetRectNP` Üye işlevi arayarak, bir uygulama biçimlendirme dikdörtgenini düzenleme denetimi penceresinden daha büyük veya daha küçük yapabilir.

Biçimlendirme dikdörtgeni pencereden daha büyük sayılsa, denetimde kaydırma çubuğu yoksa, metin kırpılır, sarılmaz.

Bu üye yalnızca çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için Windows SDK'daki [EM_SETRECTNP](/windows/win32/Controls/em-setrectnp) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:SetRect](#setrect).

## <a name="ceditsetsel"></a><a name="setsel"></a>CEdit::SetSel

Bir denetimde bir karakter aralığı seçmek için bu işlevi arayın.

```
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
Düşük sıralı sözcükteki başlangıç konumunu ve yüksek sıralı sözcükteki bitiş konumunu belirtir. Düşük sıralı sözcük 0 ve yüksek sıralı sözcük -1 ise, düzen denetimindeki tüm metin seçilir. Düşük sıralı sözcük -1 ise, geçerli seçim kaldırılır.

*bNoScroll*<br/>
Caret'in görünüme kaydırılıp kaydırılmaması gerektiğini gösterir. FALSE ise, bakım görünümüne kaydırılır. TRUE ise, gözde görünüme kaydırılmış değildir.

*nStartChar*<br/>
Başlangıç konumunu belirtir. *nStartChar* 0 ve *nEndChar* -1 ise, edit denetimindeki tüm metin seçilir. *nStartChar* -1 ise, geçerli seçim kaldırılır.

*nEndChar*<br/>
Bitiş konumunu belirtir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için Windows SDK'daki [EM_SETSEL](/windows/win32/Controls/em-setsel) bakın.

### <a name="example"></a>Örnek

  CEdit örneğine [bakın:GetSel](#getsel).

## <a name="ceditsettabstops"></a><a name="settabstops"></a>CEdit::SetTabStops

Sekme duraklarını çok satırlı bir düzen denetiminde ayarlamak için bu işlevi arayın.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parametreler

*cxEachStop*<br/>
Sekme duraklarının her *cxEachStop* iletişim biriminde ayarlaneceğini belirtir.

*nTabStops*<br/>
*rgTabStops'ta*bulunan sekme duraklarının sayısını belirtir. Bu sayı 1'den büyük olmalıdır.

*rgTabStops*<br/>
İletişim birimlerinde sekme duraklarını belirten imzasız bir dizi imzasız karşıcıya işaret eder. İletişim birimi yatay veya dikey bir uzaklıktır. Bir yatay iletişim birimi, geçerli iletişim taban genişliği biriminin dörtte birine eşittir ve 1 dikey iletişim birimi geçerli iletişim taban yüksekliği biriminin sekizde birine eşittir. İletişim taban birimleri, geçerli sistem yazı tipinin yüksekliğine ve genişliğine göre hesaplanır. `GetDialogBaseUnits` Windows işlevi, geçerli iletişim taban birimlerini piksellerde döndürür.

### <a name="return-value"></a>Dönüş Değeri

Sekmeler ayarlanmışsa sıfır olmayan; aksi takdirde 0.

### <a name="remarks"></a>Açıklamalar

Metin çok satırlı bir düzen denetimine kopyalandığında, metindeki herhangi bir sekme karakteri bir sonraki sekme durağına kadar alan oluşturulmasına neden olur.

Sekme duraklarını varsayılan boyuta ayarlamak için 32 iletişim birimi, bu üye işlevin parametresiz sürümünü arayın. Sekme duraklarını 32'den farklı bir boyuta ayarlamak için *cxEachStop* parametresi olan sürümü arayın. Sekmeyi bir dizi boyuta ayarlamak için, sürümü iki parametreiçeren kullanın.

Bu üye işlev yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

`SetTabStops`otomatik olarak yeniden çizme penceresi. Denetim denetiminde zaten metin için sekme duraklarını değiştirirseniz, akış penceresini yeniden çizmek için [CWnd'yi arayın::Geçersiz Kılma'yı](cwnd-class.md#invalidaterect) tıklatın.

Daha fazla bilgi için Windows SDK'daki [EM_SETTABSTOPS](/windows/win32/Controls/em-settabstops) ve [GetDialogBaseUnits'e](/windows/win32/api/winuser/nf-winuser-getdialogbaseunits) bakın.

### <a name="example"></a>Örnek

  [CEditView örneğine bakın:SetTabStops](ceditview-class.md#settabstops).

## <a name="ceditshowballoontip"></a><a name="showballoontip"></a>CEdit::ShowBalloonTip

Geçerli düzenleme denetimiyle ilişkili bir balon ucu görüntüler.

```
BOOL ShowBalloonTip(PEDITBALLOONTIP pEditBalloonTip);

BOOL ShowBalloonTip(
    LPCWSTR lpszTitle,
    LPCWSTR lpszText,
    INT ttiIcon = TTI_NONE);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pEditBalonİpucu*|[içinde] Balon ucunu açıklayan bir [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) yapısını işaretçi.|
|*lpszTitle*|[içinde] Balon ucunun başlığını içeren unicode dizesini işaretçi.|
|*lpszMetin*|[içinde] Balon uç metnini içeren Unicode dizesini işaretçi.|
|*ttiIcon*|[içinde] Balon ucuyla ilişkilendirilen simge türünü belirten bir **INT.** Varsayılan değer TTI_NONE. Daha fazla bilgi `ttiIcon` için [EDITBALLOONTIP](/windows/win32/api/commctrl/ns-commctrl-editballoontip) yapısının üyesine bakın.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa DOĞRU; aksi takdirde, YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bu işlev, Windows SDK'da açıklanan [EM_SHOWBALLOONTIP](/windows/win32/Controls/em-showballoontip) iletisini gönderir. Daha fazla bilgi için [Edit_ShowBalloonTip](/windows/win32/api/commctrl/nf-commctrl-edit_showballoontip) makroya bakın.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, `m_cedit`geçerli denetim denetimine erişmek için kullanılan bir değişken tanımlar. Bu değişken sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, düzenleme denetimi için bir balon ucu görüntüler. [CEdit::ShowBalloonTip](#showballoontip) yöntemi bir başlık ve balon ucu metni belirtir.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

## <a name="ceditundo"></a><a name="undo"></a>CEdit::Geri Ala

Son edit denetimi işlemini geri almak için bu işlevi çağırın.

```
BOOL Undo();
```

### <a name="return-value"></a>Dönüş Değeri

Tek satırlı bir düzen denetimi için iade değeri her zaman sıfır değildir. Çok satırlı bir düzen denetimi için, geri aladüzen işlemi başarılı olursa geri dönüş değeri sıfırsız veya geri aladenetçi işlemi başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Geri al işlemi de geri alınabilir. Örneğin, silinen metni ilk aramaile `Undo`geri yükleyebilirsiniz. Araya giren bir edit işlemi olmadığı sürece, ikinci bir çağrı yla metni `Undo`yeniden kaldırabilirsiniz.

Daha fazla bilgi için Windows SDK'daki [EM_UNDO](/windows/win32/Controls/em-undo) bakın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek CALCDRIV](../../overview/visual-cpp-samples.md)<br/>
[MFC Numune CMNCTRL2](../../overview/visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](cwnd-class.md)<br/>
[CButton Sınıfı](cbutton-class.md)<br/>
[CComboBox Sınıfı](ccombobox-class.md)<br/>
[CListBox Sınıfı](clistbox-class.md)<br/>
[CScrollBar Sınıfı](cscrollbar-class.md)<br/>
[Cstatic Sınıfı](cstatic-class.md)<br/>
[CDialog Sınıfı](cdialog-class.md)
