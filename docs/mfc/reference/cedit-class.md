---
title: CEdit sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fc11631b6a9b4c675d488d69c5575a89853e64a3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50079278"
---
# <a name="cedit-class"></a>CEdit sınıfı

Windows düzenleme denetimi işlevlerini sağlar.

## <a name="syntax"></a>Sözdizimi

```
class CEdit : public CWnd
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CEdit::CEdit](#cedit)|Oluşturur bir `CEdit` denetim nesnesi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CEdit::CanUndo](#canundo)|Bir düzenleme denetimi işlem geri alınamaz olup olmadığını belirler.|
|[CEdit::CharFromPos](#charfrompos)|Satır ve karakter dizinleri belirtilen konuma yakın karakteri alır.|
|[CEdit::Clear](#clear)|Geçerli seçimi (eğer varsa) düzenleme siler (temizler) denetler.|
|[CEdit::Copy](#copy)|Geçerli seçimi CF_TEXT biçiminde panoya düzenleme denetiminde (varsa) kopyalar.|
|[CEdit::Create](#create)|Windows düzenleme denetimi oluşturur ve ona ekler `CEdit` nesne.|
|[CEdit::Cut](#cut)|Siler (keser) düzenleme geçerli seçimi (eğer varsa) denetim ve silinen metin CF_TEXT Pano'ya kopyalar biçimlendirin.|
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|(Temizler) geri bayrağı, bir düzenleme denetimini sıfırlar.|
|[CEdit::FmtLines](#fmtlines)|Yazılım satır sonu karakterleri dahil edilmesi, çok satırlı düzenleme denetimi içinde açıp ayarlar.|
|[CEdit::GetCueBanner](#getcuebanner)|Metin işareti ya da Denetim boş ve odağa sahip olduğunda bir düzenleme denetimindeki ipucu olarak görüntülenir metni alır.|
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|Bir düzenleme denetimi en üstte görünür satırda belirler.|
|[CEdit::GetHandle](#gethandle)|Şu anda bir çok satırlı düzenleme denetim için ayrılan bellek işleyici alır.|
|[CEdit::GetHighlight](#gethighlight)|Başlangıç ve bitiş geçerli düzenleme denetimine vurgulanan metnin bir aralıktaki karakterler dizinleri alır.|
|[CEdit::GetLimitText](#getlimittext)|Bu metin en uzun süreyi alır `CEdit` içerebilir.|
|[CEdit::GetLine](#getline)|Bir metin satırı bir düzenleme denetimi alır.|
|[CEdit::GetLineCount](#getlinecount)|Çok satırlı düzenleme denetiminde satır sayısını alır.|
|[CEdit::GetMargins](#getmargins)|Bunun için sol ve sağ kenar boşluklarını alır `CEdit`.|
|[CEdit::GetModify](#getmodify)|Bir düzenleme denetimi içeriğini değiştirilmiş olup olmadığını belirler.|
|[CEdit::GetPasswordChar](#getpasswordchar)|Kullanıcının metin girdiğinde bir düzenleme denetiminde gösterilen parola karakteri alır.|
|[CEdit::GetRect](#getrect)|Biçimlendirme dikdörtgen bir düzenleme denetimi alır.|
|[CEdit::GetSel](#getsel)|İlk ve son karakterin bir düzenleme denetimindeki geçerli bölüm konumlarını alır.|
|[CEdit::HideBalloonTip](#hideballoontip)|Geçerli bir düzenleme denetimi ile ilişkili herhangi bir balon ipucu gizler.|
|[CEdit::LimitText](#limittext)|Kullanıcının bir düzenleme denetimine girebilirsiniz metnin uzunluğunu kısıtlar.|
|[CEdit::LineFromChar](#linefromchar)|Belirtilen karakter dizinini içeren satırı satır sayısını alır.|
|[CEdit::LineIndex](#lineindex)|Çok satırlı düzenleme denetimi içinde bir satırın karakter dizinini alır.|
|[CEdit::LineLength](#linelength)|Bir satırda bir düzenleme denetimi uzunluğunu alır.|
|[CEdit::LineScroll](#linescroll)|Çok satırlı düzenleme denetiminin metni kaydırır.|
|[CEdit::Paste](#paste)|Verileri düzenleme denetimine geçerli imleç konumu panodan ekler. Yalnızca Pano CF_TEXT biçiminde veri içeriyorsa, veriler eklenir.|
|[CEdit::PosFromChar](#posfromchar)|Belirtilen karakter dizinini, sol üst köşesinin koordinatlarını alır.|
|[CEdit::ReplaceSel](#replacesel)|Bir düzenleme denetimindeki geçerli bölüm belirtilen metinle değiştirir.|
|[CEdit::SetCueBanner](#setcuebanner)|Metin işareti ya da Denetim boş ve odağa sahip olduğunda bir düzenleme denetimindeki ipucu olarak görüntülenen metin ayarlar.|
|[CEdit::SetHandle](#sethandle)|Birden çok satırlı düzenleme denetimi tarafından kullanılacak olan yerel belleğe tanıtıcı ayarlar.|
|[CEdit::SetHighlight](#sethighlight)|Öne çıkan özellikleri geçerli görüntülenen metin aralığı bir düzenleme denetimi.|
|[CEdit::SetLimitText](#setlimittext)|Bu metin en uzun süreyi ayarlar `CEdit` içerebilir.|
|[CEdit::SetMargins](#setmargins)|Bunun için sol ve sağ kenar boşluğu ayarlar `CEdit`.|
|[CEdit::SetModify](#setmodify)|Bir düzenleme denetimi için değişiklik bayrağını kaldırır veya ayarlar.|
|[CEdit::SetPasswordChar](#setpasswordchar)|Kullanıcının metin girdiğinde bir düzenleme denetiminde gösterilen bir parola karakteri kaldırır veya ayarlar.|
|[CEdit::SetReadOnly](#setreadonly)|Bir düzenleme denetimi salt okunur durumunu ayarlar.|
|[CEdit::SetRect](#setrect)|Çok satırlı düzenleme denetiminin biçimlendirme dikdörtgen ayarlar ve denetim güncelleştirir.|
|[CEdit::SetRectNP](#setrectnp)|Çok satırlı düzenleme denetiminin biçimlendirme dikdörtgen denetimi penceresi yeniden olmadan ayarlar.|
|[CEdit::SetSel](#setsel)|Karakter aralığı içinde bir düzenleme denetimi seçer.|
|[CEdit::SetTabStops](#settabstops)|Birden çok satırda sekme duraklarını kümelerini düzenleme denetimi.|
|[CEdit::ShowBalloonTip](#showballoontip)|Geçerli bir düzenleme denetimi ile ilişkili bir balon ipucu görüntüler.|
|[CEdit::Undo](#undo)|Son düzenleme işlemi tersine çevirir.|

## <a name="remarks"></a>Açıklamalar

Bir düzenleme denetimi, kullanıcının metin girebileceği bir dikdörtgen alt penceredir.

Bir iletişim kutusu şablonundan ya da kodunuzda doğrudan bir düzenleme denetimi oluşturabilirsiniz. Her iki durumda da Oluşturucu çağırmanız `CEdit` oluşturulacağını `CEdit` nesnesi ve ardından arama [Oluştur](#create) üye işlevi Windows düzenleme denetimi ve ekleyebilir `CEdit` nesne.

Yapı, türetilen bir sınıf tek adımlı işlemde olabilir `CEdit`. Bir oluşturucu çağrı ve türetilen sınıf için yazma `Create` gelen oluşturucu içinde.

`CEdit` önemli işlevsellik devralır `CWnd`. Metinden almak ve ayarlamak için bir `CEdit` nesnesi `CWnd` üye işlevleri [SetWindowText](cwnd-class.md#setwindowtext) ve [GetWindowText](cwnd-class.md#getwindowtext), hangi ayarlama veya alma bir düzenleme tüm içeriğini denetlemek, olsa bile, çok satırlı bir denetimdir. Çok satırlı bir denetimdeki metin satırlarını '\r\n' karakter sıraları tarafından ayrılır. Ayrıca, bir düzenleme denetimi çok satırlı ise, alma ve denetimin metninin bir parçası çağırarak ayarlayabilirsiniz `CEdit` üye işlevleri [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel)ve [ ReplaceSel](#replacesel).

Bir düzenleme denetimi tarafından yollanır Windows bildirim iletilerini işlemek isterseniz (öğesinden türetilmiş bir sınıf genellikle `CDialog`), üst sınıfın her ileti için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleyin.

Her ileti eşleme girişi aşağıdaki biçimi alır:

  **ON_**_bildirim_**(** _kimliği_**,** _memberFxn_ **)**

Burada `id` bildirimi gönderilmesi düzenleme denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazdığınız üst üye işlev adıdır.

Üst öğenin işlev prototipi aşağıdaki gibidir:

**afx_msg** void memberFxn **();**

Olası ileti eşlemesi girişleri ve açıklamasını, bunların üst gönderilecek örneklerinin listesi aşağıda verilmiştir:

- ON_EN_CHANGE kullanıcının bir düzenleme denetiminde metni değiştirmiş bir eylem duruma getirdi. Windows görüntü güncelleştirmeleri sonrasında EN_UPDATE bildirim iletisi, bu bildirim iletisi gönderilir.

- ON_EN_ERRSPACE düzenleme denetiminin, belirli bir istek karşılamak için yeterli bellek ayrılamıyor.

- ON_EN_HSCROLL kullanıcı düzenleme denetiminin yatay kaydırma çubuğunun tıklar. Üst pencere ekran güncelleştirilmeden önce bilgilendirilir.

- On_en_kıllfocus düzenleme denetiminin, giriş odağını kaybediyor.

- ON_EN_MAXTEXT geçerli ekleme belirtilen düzenleme denetimi için karakter sayısını aştı ve kesilmiş olabilir. Ayrıca bir düzenleme denetimi ES_AUTOHSCROLL stili yok ve düzenleme denetiminin genişliğini eklenecek karakter sayısını aşacak gönderilir. Ayrıca bir düzenleme denetimi ES_AUTOVSCROLL stili yok ve bir metin ekleme kaynaklanan satırların toplam sayısı düzenleme denetiminin yüksekliğini aşılmasına gönderilir.

- ON_EN_SETFOCUS bir düzenleme denetimi giriş odağını aldığında gönderilir.

- ON_EN_UPDATE düzenleme denetiminin değiştirilmiş görünen metin hakkında aynıdır. Denetim biçimlendirilmiş metin sonra ancak pencere boyutu değiştirilebilir böylece bunu metin gerekirse ekranları önce gönderilir.

- ON_EN_VSCROLL kullanıcı düzenleme denetiminin dikey kaydırma çubuğu tıklar. Üst pencere ekran güncelleştirilmeden önce bilgilendirilir.

Oluşturursanız, bir `CEdit` nesnesi bir iletişim kutusu içinde `CEdit` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

Oluşturursanız, bir `CEdit` iletişim kutusu Düzenleyicisi kullanılarak iletişim kaynak nesneden `CEdit` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.

Oluşturursanız, bir `CEdit` nesnesi bir pencere içinde de gerekebilir, yok. Oluşturursanız `CEdit` yığında nesne otomatik olarak bozulur. Oluşturursanız `CEdit` kullanarak yığında nesne **yeni** işlevini çağırmalıdır **Sil** kullanıcı Windows sonlandırıldığında yok etmek için nesneye düzenleme denetimi. Herhangi bir bellek ayırdığınızda `CEdit` nesne, geçersiz kılma `CEdit` ayrılmasını atmayı yıkıcı.

Belirli stilleri bir düzenleme denetimi (örneğin, ES_READONLY) değiştirileceğini denetimi kullanmak yerine belirli bir ileti göndermeyi gerekir [ModifyStyle](cwnd-class.md#modifystyle). Bkz: [Düzenle denetim stilleri](/windows/desktop/Controls/edit-control-styles) Windows SDK içinde.

Daha fazla bilgi için `CEdit`, bkz: [denetimleri](../../mfc/controls-mfc.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](cobject-class.md)

[CCmdTarget](ccmdtarget-class.md)

[CWnd](cwnd-class.md)

`CEdit`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxwin.h

##  <a name="canundo"></a>  CEdit::CanUndo

Son düzenleme işlemi geri alınamaz olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL CanUndo() const;
```

### <a name="return-value"></a>Dönüş Değeri

Son düzenleme işlemi için yapılan bir çağrı tarafından alınabilir olursa sıfır dışı `Undo` üye işlevi; 0 geri alınamaz.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_CANUNDO](/windows/desktop/Controls/em-canundo) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::Undo](#undo).

##  <a name="cedit"></a>  CEdit::CEdit

Oluşturur bir `CEdit` nesne.

```
CEdit();
```

### <a name="remarks"></a>Açıklamalar

Kullanım [Oluştur](#create) oluşturmak için Windows düzenleme denetimi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]

##  <a name="charfrompos"></a>  CEdit::CharFromPos

Sıfır tabanlı satır ve bu belirtilen nokta en yakın bir karakterin karakter dizinleri almak için bu işlevi çağırın `CEdit` denetimi

```
int CharFromPos(CPoint pt) const;
```

### <a name="parameters"></a>Parametreler

*PT*<br/>
Bu istemci alanı içinde nokta koordinatları `CEdit` nesne.

### <a name="return-value"></a>Dönüş Değeri

Düşük düzey Word karakter dizinini ve yüksek düzeyli Word satır dizini.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu üye işlevi, Windows 95 ve Windows NT 4.0 sürümlerinde kullanılabilir olan.

Daha fazla bilgi için [EM_CHARFROMPOS](/windows/desktop/Controls/em-charfrompos) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]

##  <a name="clear"></a>  CEdit::Clear

(Temiz) geçerli seçimi düzenleme denetiminde (varsa) silmek için bu işlevi çağırın.

```
void Clear();
```

### <a name="remarks"></a>Açıklamalar

Silme işlemi tarafından gerçekleştirilen `Clear` çağrılarak alınabilir [geri](#undo) üye işlevi.

Geçerli seçimi Sil ve Silinen içeriği panoya Yerleştir için çağrı [Kes](#cut) üye işlevi.

Daha fazla bilgi için [WM_CLEAR](/windows/desktop/dataxchg/wm-clear) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]

##  <a name="copy"></a>  CEdit::Copy

Geçerli seçimi, bu işleve coy CF_TEXT biçiminde panoya düzenleme denetiminde (varsa) çağırın.

```
void Copy();
```

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [WM_COPY](/windows/desktop/dataxchg/wm-copy) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]

##  <a name="create"></a>  CEdit::Create

Windows düzenleme denetimi oluşturur ve ona ekler `CEdit` nesne.

```
virtual BOOL Create(
    DWORD dwStyle,
    const RECT& rect,
    CWnd* pParentWnd,
    UINT nID);
```

### <a name="parameters"></a>Parametreler

*dwStyle*<br/>
Düzenleme denetiminin stilini belirtir. Herhangi bir birleşimini uygulamak [düzenleme stilleri](styles-used-by-mfc.md#edit-styles) denetimi.

*Rect*<br/>
Düzenleme denetiminin boyutunu ve konumunu belirtir. Olabilir bir `CRect` nesne veya `RECT` yapısı.

*pParentWnd*<br/>
Düzenleme denetiminin üst penceresine belirtir (genellikle bir `CDialog`). NULL olmamalıdır.

*nID*<br/>
Düzenleme denetiminin kimliğini belirtir.

### <a name="return-value"></a>Dönüş Değeri

Başlatma başarılı olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Oluşturmak bir `CEdit` iki adımda nesne. İlk olarak, çağrı `CEdit` oluşturucusu ve sonra çağrı `Create`, hangi Windows düzenleme denetimi oluşturur ve ona ekler `CEdit` nesne.

Zaman `Create` yürütür, Windows gönderir [WM_NCCREATE](/windows/desktop/winmsg/wm-nccreate), [WM_NCCALCSIZE](/windows/desktop/winmsg/wm-nccalcsize), [WM_CREATE](/windows/desktop/winmsg/wm-create), ve [WM_GETMINMAXINFO](/windows/desktop/winmsg/wm-getminmaxinfo) Düzenle denetim iletileri.

Bu iletiler tarafından varsayılan olarak işlenir [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), ve [Ongetminmaxınfo](cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CEdit`, yeni sınıfa ileti eşlemesi ekleyin ve yukarıdaki ileti işleyicisi üye işlevleri geçersiz kılar. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.

Aşağıdaki uygulama [pencere stilleri](styles-used-by-mfc.md#window-styles) bir düzenleme denetimi.

- WS_CHILD her zaman

- Ws_vısıble genellikle

- Ws_dısabled nadiren

- WS_GROUP grup denetimleri için

- WS_TABSTOP sekme sırasını düzenleme denetimi eklemek için

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]

##  <a name="cut"></a>  CEdit::Cut

(Kes) silmek için bu işlevi düzenleme denetimine geçerli seçimi (varsa) çağırın ve silinen metin CF_TEXT biçiminde panoya kopyalayın.

```
void Cut();
```

### <a name="remarks"></a>Açıklamalar

Silme işlemi tarafından gerçekleştirilen `Cut` çağrılarak alınabilir [geri](#undo) üye işlevi.

Silinen metin panoya koymadan geçerli seçimi silmek için çağrı [Temizle](#clear) üye işlevi.

Daha fazla bilgi için [WM_CUT](/windows/desktop/dataxchg/wm-cut) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]

##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer

Bir düzenleme denetiminin geri alma bayrağı (Sil) sıfırlamak için bu işlevi çağırın.

```
void EmptyUndoBuffer();
```

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimi artık son işlemi geri almak mümkün olmayacaktır. Her bir işlem içinde düzenleme denetiminin geri alınabileceği geri bayrağı ayarlanır.

Otomatik olarak geri bayrağı olduğu zaman temizlenmiş [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) veya [SetHandle](#sethandle) `CWnd` üye işlevleri çağrılır.

Daha fazla bilgi için [EM_EMPTYUNDOBUFFER](/windows/desktop/Controls/em-emptyundobuffer) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]

##  <a name="fmtlines"></a>  CEdit::FmtLines

Yazılım satır sonu karakterleri dahil edilmesi çok satırlı düzenleme denetimi içinde açıp ayarlamak için bu işlevi çağırın.

```
BOOL FmtLines(BOOL bAddEOL);
```

### <a name="parameters"></a>Parametreler

*bAddEOL*<br/>
Eklenecek geçici satır sonu karakteri olup olmadığını belirtir. TRUE değerini karakterler ekler; FALSE değeri bunları kaldırır.

### <a name="return-value"></a>Dönüş Değeri

Varsa sıfır olmayan biçimlendirme oluşur; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Yazılım satır sonu iki satır başları ve sözcük kaydırma nedeniyle bozuk bir satır sonuna eklenen bir satır besleme oluşur. Sabit satır sonu bir satır başı ve satır besleme bir oluşur. Sabit satır sonu ile biten satırları tarafından etkilenmez `FmtLines`.

Windows, yalnızca yanıt `CEdit` birden çok satırlı düzenleme denetimi bir nesnedir.

`FmtLines` yalnızca tarafından döndürülen arabellek etkiler [GetHandle](#gethandle) ve tarafından döndürülen metni [WM_GETTEXT](/windows/desktop/winmsg/wm-gettext). Metin düzenleme denetiminde görüntüleme herhangi bir etkisi yoktur.

Daha fazla bilgi için [EM_FMTLINES](/windows/desktop/Controls/em-fmtlines) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]

##  <a name="getcuebanner"></a>  CEdit::GetCueBanner

Metin işareti ya da Denetim boş olduğunda bir düzenleme denetimindeki ipucu olarak görüntülenir metni alır.

```
BOOL GetCueBanner(
    LPWSTR lpszText,
    int cchText) const;

CString GetCueBanner() const;
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
[out] İşaret metni içeren bir dize işaretçisi.

*cchText*<br/>
[in] Alınabilir karakter sayısı. Bu sondaki boş karakter içerir.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa ilk aşırı yükleme için TRUE; Aksi durumda FALSE.

İkinci aşırı yükleme için bir [CString](../../atl-mfc-shared/using-cstring.md) yöntem başarılı; Aksi takdirde ise işaret metni içeren boş bir dize ("").

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [EM_GETCUEBANNER](/windows/desktop/Controls/em-getcuebanner) Windows SDK'da açıklanan ileti. Daha fazla bilgi için [Edit_GetCueBannerText](/windows/desktop/api/commctrl/nf-commctrl-edit_getcuebannertext) makrosu.

##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine

Bir düzenleme denetimi en üstte görünür satırında belirlemek için bu işlevi çağırın.

```
int GetFirstVisibleLine() const;
```

### <a name="return-value"></a>Dönüş Değeri

En üstte görünür satırın sıfır tabanlı dizini. Tek satırlı düzenleme denetimleri için dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_GETFIRSTVISIBLELINE](/windows/desktop/Controls/em-getfirstvisibleline) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]

##  <a name="gethandle"></a>  CEdit::GetHandle

Şu anda birden çok satırlı düzenleme denetimi için ayrılan bellek için bir tanıtıcı almak için bu işlevi çağırın.

```
HLOCAL GetHandle() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetiminin içeriğini tutan arabellek tanımlayan yerel bellek tanıtıcı. Tek satırlı düzenleme denetimine ileti gönderme gibi bir hata oluşursa, dönüş değeri 0'dır.

### <a name="remarks"></a>Açıklamalar

Tanıtıcı yerel bellek tanıtıcısı ve herhangi bir kullanılabilir **yerel** yerel bellek almayan Windows bellek işlevleri işleyecek bir parametre olarak.

`GetHandle` yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Çağrı `GetHandle` iletişim kutusu DS_LOCALEDIT stili bayrak kümesi ile oluşturulmuşsa bir iletişim kutusunda çok satırlı düzenleme denetimi için. DS_LOCALEDIT stili ayarlı değilse, yine de sıfır dışında bir dönüş değeri alır, ancak döndürülen değer kullanmanız mümkün olmayacaktır.

> [!NOTE]
> `GetHandle` Windows 95/98 ile çalışmaz. Eğer `GetHandle` Windows 95/98'de, NULL döndürür. `GetHandle` Windows NT 3.51 sürümü ve sonraki sürümler altında belirtildiği gibi çalışır.

Daha fazla bilgi için [EM_GETHANDLE](/windows/desktop/Controls/em-gethandle) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]

##  <a name="gethighlight"></a>  CEdit::GetHighlight

Geçerli düzenleme denetimine vurgulanan metnin bir aralıktaki ilk ve son karakter dizinleri alır.

```
BOOL GetHighlight(
    int* pichStart,
    int* pichEnd) const;
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*pichStart*|[out] Vurgulanmış metin aralığını ilk karakter sıfır tabanlı dizini.|
|*pichEnd*|[out] Vurgulanmış metin aralığını son karakter sıfır tabanlı dizini.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [EM_GETHILITE](/windows/desktop/Controls/em-gethilite) Windows SDK'da açıklanan ileti. Her ikisi de `SetHighlight` ve `GetHighlight` yalnızca UNICODE yapıları için şu anda etkin değil.

##  <a name="getlimittext"></a>  CEdit::GetLimitText

Bu metin sınırı almak için bu üye işlevi çağrısı `CEdit` nesne.

```
UINT GetLimitText() const;
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli metin sınırını bayt cinsinden bu `CEdit` nesne.

### <a name="remarks"></a>Açıklamalar

Metin, metin düzenleme denetiminin kabul edebilen bayt cinsinden en uzun süreyi sınırdır.

> [!NOTE]
>  Bu üye işlevi, Windows 95 ve Windows NT 4.0 sürümlerinde kullanılabilir olan.

Daha fazla bilgi için [EM_GETLIMITTEXT](/windows/desktop/Controls/em-getlimittext) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]

##  <a name="getline"></a>  CEdit::GetLine

Bir metin satırı bir düzenleme denetiminden almak için bu işlevi çağırın ve yerleştirir *lpszBuffer*.

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

*nIndex*<br/>
Birden çok satırından almak için satır numarası düzenleme denetimi belirtir. Satır numaraları, sıfır tabanlı olduklarını; 0 değeri, ilk satırı belirtir. Bu parametre, tek satırlı düzenleme denetimi tarafından göz ardı edilir.

*lpszBuffer*<br/>
Satır bir kopyasını alır arabellek işaret eder. İlk sözcük arabellek arabelleğe kopyalanan karakter sayısı belirtmelisiniz.

*nMaxLength*<br/>
En büyük arabellek için kopyalanan bayt sayısını belirtir. `GetLine` Bu değer ilk Word'de yerleştirir *lpszBuffer* Windows çağrısını yapmadan önce.

### <a name="return-value"></a>Dönüş Değeri

Aslında kopyalanan bayt sayısı. Dönüş değeri tarafından belirtilen satır numarası 0 ise *nIndex* düzenleme denetiminde satır sayısı değerinden büyük.

### <a name="remarks"></a>Açıklamalar

Kopyalanan satırın bir sonlandırma boş karakteri içermiyor.

Daha fazla bilgi için [EM_GETLINE](/windows/desktop/Controls/em-getline) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::GetLineCount](#getlinecount).

##  <a name="getlinecount"></a>  CEdit::GetLineCount

Çok satırlı düzenleme denetiminde satır sayısını almak için bu işlevi çağırın.

```
int GetLineCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetimi içeren birden çok satır satır sayısı bir tamsayı. Metin düzenleme denetimine girildiyse, dönüş değeri 1'dir.

### <a name="remarks"></a>Açıklamalar

`GetLineCount` yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için [EM_GETLINECOUNT](/windows/desktop/Controls/em-getlinecount) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]

##  <a name="getmargins"></a>  CEdit::GetMargins

Bu düzenleme denetiminin sol ve sağ kenar boşlukları almak için bu üye işlevini çağırın.

```
DWORD GetMargins() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düşük düzey WORD ve sağ kenar boşluğundaki DWPOİNT genişliğini sol kenar boşluğu genişliği.

### <a name="remarks"></a>Açıklamalar

Kenar boşlukları piksel cinsinden ölçülür.

> [!NOTE]
>  Bu üye işlevi, Windows 95 ve Windows NT 4.0 sürümlerinde kullanılabilir olan.

Daha fazla bilgi için [EM_GETMARGINS](/windows/desktop/Controls/em-getmargins) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="getmodify"></a>  CEdit::GetModify

Bir düzenleme denetimi içeriğini değiştirilmiş olup olmadığını belirlemek için bu işlevi çağırın.

```
BOOL GetModify() const;
```

### <a name="return-value"></a>Dönüş Değeri

Düzenleme denetimi içeriğini değiştirilmiş olursa sıfır dışı; Kalan durumunda 0 değişmedi.

### <a name="remarks"></a>Açıklamalar

Windows düzenleme denetiminin içeriğini değiştirilmiş olup olmadığını belirten bir iç bayrağı tutar. Bu bayrak düzenleme denetiminin ilk oluşturulduğunda ve çağrı yaparak da temizlenmesi temizlenir [SetModify](#setmodify) üye işlevi.

Daha fazla bilgi için [EM_GETMODIFY](/windows/desktop/Controls/em-getmodify) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]

##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar

Kullanıcının metin girdiğinde bir düzenleme denetiminde görüntülenen parola karakteri almak için bu işlevi çağırın.

```
TCHAR GetPasswordChar() const;
```

### <a name="return-value"></a>Dönüş Değeri

Kullanıcı yazılan karakter yerine görüntülenecek karakter belirtir. Dönüş değeri NULL ise hiç parola karakteri yok.

### <a name="remarks"></a>Açıklamalar

ES_PASSWORD stiliyle düzenleme denetiminin oluşturursanız, Denetim DLL varsayılan parola karakteri belirler. Bildirim veya [InitCommonControlsEx](/windows/desktop/api/commctrl/nf-commctrl-initcommoncontrolsex) yöntemi belirleyen DLL destekleyen düzenleme denetimi. User32.dll düzenleme denetimini destekler, varsayılan parola karakteri yıldız işareti ise ('* ', U + 002A). Comctl32.dll sürüm 6 düzenleme denetiminin destekliyorsa, varsayılan karakter ('●', U + 25CF) siyah DAİRE uygulanır. Ortak Denetimler DLL ve sürümünü destekleyen hakkında daha fazla bilgi için bkz [kabuk ve ortak denetimleri sürümleri](https://msdn.microsoft.com/library/windows/desktop/bb776779).

Bu yöntem gönderir [EM_GETPASSWORDCHAR](/windows/desktop/Controls/em-getpasswordchar) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]

##  <a name="getrect"></a>  CEdit::GetRect

Biçimlendirme dikdörtgen bir düzenleme denetimi almak için bu işlevi çağırın.

```
void GetRect(LPRECT lpRect) const;
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret `RECT` biçimlendirme dikdörtgen alan yapısı.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgen metin düzenleme denetiminin penceresinin boyutunu bağımsızdır sınırlayıcı dikdörtgeni ' dir.

Çok satırlı düzenleme denetiminin biçimlendirme dikdörtgen tarafından değiştirilebilir [SetRect](#setrect) ve [SetRectNP](#setrectnp) üye işlevleri.

Daha fazla bilgi için [EM_GETRECT](/windows/desktop/Controls/em-getrect) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::LimitText](#limittext).

##  <a name="getsel"></a>  CEdit::GetSel

Başlangıç ve bitiş dönüş değeri ya da parametreleri kullanarak bir düzenleme denetimindeki geçerli bölüm (varsa) karakter konumlarını almak için bu işlevi çağırın.

```
DWORD GetSel() const;

void GetSel(
    int& nStartChar,
    int& nEndChar) const;
```

### <a name="parameters"></a>Parametreler

*nStartChar*<br/>
Geçerli seçimdeki ilk karakterin konumu alacak bir tamsayı başvuru.

*nEndChar*<br/>
Geçerli seçimi bitişini geçen nonselected ilk karakterin konumu alacak bir tamsayı başvuru.

### <a name="return-value"></a>Dönüş Değeri

DWORD döndürür sürüm dwpoint seçiminde bitişinden sonra düşük düzey Word'ün başlangıç konumunu ve nonselected ilk karakterin konumu içeren bir değer döndürür.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_GETSEL](/windows/desktop/Controls/em-getsel) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]

##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip

Geçerli bir düzenleme denetimi ile ilişkili herhangi bir balon ipucu gizler.

```
BOOL HideBalloonTip();
```

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev gönderir [EM_HIDEBALLOONTIP](/windows/desktop/Controls/em-hideballoontip) Windows SDK'da açıklanan ileti.

##  <a name="limittext"></a>  CEdit::LimitText

Kullanıcının bir düzenleme denetimine girebilirsiniz metnin uzunluğunu sınırlamak için bu işlevi çağırın.

```
void LimitText(int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*nChars*<br/>
Kullanıcının girebileceği metin uzunluğu (bayt cinsinden) belirtir. Bu parametre 0 ise, metin uzunluğu uınt_max bayt olarak ayarlanır. Bu varsayılan davranıştır.

### <a name="remarks"></a>Açıklamalar

Metin sınırı değiştirme yalnızca kullanıcının girebileceği metin kısıtlar. Hiçbir etkisi herhangi bir metin düzenleme denetiminde zaten sahip ya da düzenleme denetimi tarafından kopyalanmasını metnin uzunluğunu etkilemez [SetWindowText](cwnd-class.md#setwindowtext) üye işlevinde `CWnd`. Bir uygulama kullanıyorsa `SetWindowText` işlev çağrısında belirtilen bir düzenleme denetimi daha fazla metin yerleştirin `LimitText`, kullanıcının herhangi bir metin düzenleme denetiminde silebilirsiniz. Ancak, metin sınırı kullanıcı yeni metinle varolan metni değiştirmesini engeller, geçerli seçimi silme sürece metin sınırın altına düşmesine neden olur.

> [!NOTE]
>  Win32'de (Windows NT ve Windows 95/98) [SetLimitText](#setlimittext) bu işlevin yerini alır.

Daha fazla bilgi için [EM_LIMITTEXT](/windows/desktop/Controls/em-limittext) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]

##  <a name="linefromchar"></a>  CEdit::LineFromChar

Belirtilen karakter dizinini içeren satırı satır sayısını almak için bu işlevi çağırın.

```
int LineFromChar(int nIndex = -1) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
-1 içeren veya metin düzenleme denetiminin istediğiniz karakteri sıfır tabanlı dizin değeri içeriyor. Varsa *nIndex* -1, geçerli satırı, diğer bir deyişle, giriş işaretini içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen karakter dizinini içeren satırı sıfır tabanlı satır numarası *nIndex*. Varsa *nIndex* -1 ' dir seçimi ilk karakteri içeren satırı sayısı döndürülür. Herhangi bir seçim yoksa geçerli satırı numarası döndürülür.

### <a name="remarks"></a>Açıklamalar

Bir karakter dizinini düzenleme denetiminin başından itibaren karakter sayısıdır.

Bu üye işlevi, yalnızca birden çok satırlı düzenleme denetimleri tarafından kullanılır.

Daha fazla bilgi için [EM_LINEFROMCHAR](/windows/desktop/Controls/em-linefromchar) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]

##  <a name="lineindex"></a>  CEdit::LineIndex

Çok satırlı düzenleme denetimi içinde bir satırın karakter dizinini almak için bu işlevi çağırın.

```
int LineIndex(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*evrimçi*<br/>
Metin düzenleme denetiminin istenen satır için bir dizin değeri içeriyor veya -1'i içerir. Varsa *evrimçi* -1, geçerli satırı, diğer bir deyişle, giriş işaretini içeren satırı belirtir.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen satırın karakter dizinini *evrimçi* veya belirtilen satır numarası düzenleme denetiminde satırları sayısından büyükse, -1.

### <a name="remarks"></a>Açıklamalar

Karakter dizini belirtilen satırın başına düzenleme denetiminin karakterleri sayısıdır.

Bu üye işlevi, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için [EM_LINEINDEX](https://msdn.microsoft.com/library/windows/desktop/bb761611) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]

##  <a name="linelength"></a>  CEdit::LineLength

Bir satırda bir düzenleme denetimi uzunluğunu alır.

```
int LineLength(int nLine = -1) const;
```

### <a name="parameters"></a>Parametreler

*evrimçi*<br/>
Bir karakter uzunluğunu alınacak bulunduğu satırı, sıfır tabanlı dizini. Varsayılan değer -1'dir.

### <a name="return-value"></a>Dönüş Değeri

Tek satırlı düzenleme denetimleri için dönüş değeri olarak TCHARs, metin düzenleme denetiminde uzunluğudur.

Çok satırlı düzenleme denetimleri için dönüş değeri, TCHARs içinde da tarafından belirtilen satır uzunluğunda *evrimçi* parametresi. ANSI metin için uzunluğu satırında bayt sayısıdır; Unicode metin için satır karakter sayısı uzunluğudur. Uzunluğu, satır başı karakteri içermez.

Varsa *evrimçi* parametre denetimi karakter sayısından daha fazla ise, döndürülen değer sıfırdır.

Varsa *evrimçi* parametresi, -1, dönüş değeri seçili karakterler içeren satırları seçili olmayan karakter sayısı. Örneğin, bir satırın sonraki satırın sonundaki sekizinci karakterinde dördüncü karakter seçimi geçerse, dönüş değeri 10'dur. Diğer bir deyişle, üç ilk satır ve yedi sonraki karakter.

TCHAR satır'tablosundaki TCHAR türü hakkında daha fazla bilgi için bkz. [Windows veri türleri](/windows/desktop/WinProg/windows-data-types).

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından desteklenen [EM_LINELENGTH](/windows/desktop/Controls/em-linelength) Windows SDK'da açıklanan ileti.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::LineIndex](#lineindex).

##  <a name="linescroll"></a>  CEdit::LineScroll

Çok satırlı düzenleme denetiminin metin kaydırma için bu işlevi çağırın.

```
void LineScroll(
    int nLines,
    int nChars = 0);
```

### <a name="parameters"></a>Parametreler

*nLines*<br/>
Dikey olarak kaydırmak için satır sayısını belirtir.

*nChars*<br/>
Yatay kaydırma karakter konumlarının sayısını belirtir. Düzenleme denetimi es_rıght veya ES_CENTER bir stile sahipse, bu değer yoksayılır.

### <a name="remarks"></a>Açıklamalar

Bu üye işlevi, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Düzenleme denetimi dikey metin düzenleme denetiminde son satırının kaydırarak değil. Geçerli satırı tarafından belirtilen artı satır varsa *nLines* düzenleme denetiminde satırların toplam sayısını aşıyor, böylece son satırı düzenleme denetiminin düzenleme denetimi pencerenin üstüne kaydırılan değeri ayarlanır.

`LineScroll` herhangi bir satırın son karakter yatay olarak kaydırmak için kullanılabilir.

Daha fazla bilgi için [EM_LINESCROLL](/windows/desktop/Controls/em-linescroll) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::GetFirstVisibleLine](#getfirstvisibleline).

##  <a name="paste"></a>  CEdit::Paste

Panodan veri eklemek için bu işlevi çağırın `CEdit` ekleme noktasına.

```
void Paste();
```

### <a name="remarks"></a>Açıklamalar

Yalnızca Pano CF_TEXT biçiminde veri içeriyorsa, veriler eklenir.

Daha fazla bilgi için [WM_PASTE](/windows/desktop/dataxchg/wm-paste) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]

##  <a name="posfromchar"></a>  CEdit::PosFromChar

Bu belirli bir karakterin konumu (sol üst köşedeki) almak için bu işlevi çağırın `CEdit` nesne.

```
CPoint PosFromChar(UINT nChar) const;
```

### <a name="parameters"></a>Parametreler

*nChar*<br/>
Belirtilen karakterin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Tarafından belirtilen bir karakterin sol üst köşesinin koordinatlarını *nChar*.

### <a name="remarks"></a>Açıklamalar

Karakter, sıfır tabanlı dizin değerini vererek belirtilir. Varsa *nChar* bu son karakter dizinini büyüktür `CEdit` nesnesi, dönüş değeri bu karakterin konumu yalnızca son son karakter koordinatlarını belirtir `CEdit` nesne.

> [!NOTE]
>  Bu üye işlevi, Windows 95 ve Windows NT 4.0 sürümlerinde kullanılabilir olan.

Daha fazla bilgi için [EM_POSFROMCHAR](/windows/desktop/Controls/em-posfromchar) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::LineFromChar](#linefromchar).

##  <a name="replacesel"></a>  CEdit::ReplaceSel

Bir düzenleme denetimindeki geçerli bölüm tarafından belirtilen metinle değiştirmek için bu işlevi çağırın *lpszNewText*.

```
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszNewText*<br/>
Yerine konacak metin içeren bir boş sonlandırılmış dizeye işaret eder.

*bCanUndo*<br/>
Bu işlev Al. geri alınabilecek belirtmek için bu parametrenin değeri TRUE olarak ayarlayın. Varsayılan değer FALSE olur.

### <a name="remarks"></a>Açıklamalar

Bir düzenleme denetiminde metni yalnızca bir bölümünü değiştirir. Tüm metni değiştirmek istiyorsanız, kullanın [CWnd::SetWindowText](cwnd-class.md#setwindowtext) üye işlevi.

Geçerli seçim yok ise, yerine konacak metin geçerli İmleç konumuna eklenir.

Daha fazla bilgi için [EM_REPLACESEL](/windows/desktop/Controls/em-replacesel) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::LineIndex](#lineindex).

##  <a name="setcuebanner"></a>  CEdit::SetCueBanner

Metin işareti görüntülenen veya ipucu, bir düzen denetimi boş olduğunda denetim metin ayarlar.

```
BOOL SetCueBanner(LPCWSTR lpszText);

BOOL SetCueBanner(
    LPCWSTR lpszText,
    BOOL fDrawWhenFocused = FALSE);
```

### <a name="parameters"></a>Parametreler

*lpszText*<br/>
[in] Düzenleme denetiminde görüntülenecek ipucu içeren bir dize işaretçisi.

*fDrawWhenFocused*<br/>
[in] Kullanıcı düzenleme denetiminde tıkladığı ve denetim odağı yanlışsa, işaret başlığı çizilmiştir değil.

Hatta denetim odağa sahip olduğunda TRUE ise işaret başlığı çizilir. Kullanıcı denetimi türüne başladığında işaret başlığı kaybolur.

Varsayılan değer FALSE olur.

### <a name="return-value"></a>Dönüş Değeri

Yöntem başarılı olursa TRUE; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [EM_SETCUEBANNER](/windows/desktop/Controls/em-setcuebanner) Windows SDK'da açıklanan ileti. Daha fazla bilgi için [Edit_SetCueBannerTextFocused](/windows/desktop/api/commctrl/nf-commctrl-edit_setcuebannertextfocused) makrosu.

### <a name="example"></a>Örnek

Aşağıdaki örnek, gösterir [CEdit::SetCueBanner](#setcuebanner) yöntemi.

[!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]

##  <a name="sethandle"></a>  CEdit::SetHandle

Birden çok satırlı düzenleme denetimi tarafından kullanılacak olan yerel bellek tanıtıcı ayarlamak için bu işlevi çağırın.

```
void SetHandle(HLOCAL hBuffer);
```

### <a name="parameters"></a>Parametreler

*hBuffer*<br/>
Yerel bellek işleyici içerir. Bu işleyici önceki bir çağrı tarafından oluşturulmuş olması gerekir [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc) LMEM_MOVEABLE bayrağını kullanarak Windows işlevi. Bellek null ile sonlandırılmış bir dize içerdiği varsayılır. Durum bu değilse, ayrılan belleğin ilk bayt 0 olarak ayarlanması gerekir.

### <a name="remarks"></a>Açıklamalar

Düzenleme denetimi şu anda görüntülenen metnin yerine kendi arabellek ayırma depolamak için bu arabellek sonra kullanır.

Bu üye işlevi, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Uygulamanın yeni bir bellek tanıtıcı ayarlar önce kullanması gereken [GetHandle](#gethandle) tanıtıcısı geçerli ara belleğe alma ve kullanarak Bellek boşaltmak için üye işlevini `LocalFree` Windows işlevi.

`SetHandle` geri alma arabelleği temizler ( [CanUndo](#canundo) üye işlevi, ardından 0 döndürür) ve iç değişiklik bayrağını ( [GetModify](#getmodify) üye işlevi, ardından 0 döndürür). Düzenleme denetimi penceresi yeniden çizilir.

Yalnızca DS_LOCALEDIT stili bayrak kümesi ile iletişim kutusu oluşturduysanız, iletişim kutusunda çok satırlı düzenleme denetiminde bu üye işlevi kullanabilirsiniz.

> [!NOTE]
> `GetHandle` Windows 95/98 ile çalışmaz. Eğer `GetHandle` Windows 95/98'de, NULL döndürür. `GetHandle` Windows NT 3.51 sürümü ve sonraki sürümler altında belirtildiği gibi çalışır.

Daha fazla bilgi için [EM_SETHANDLE](/windows/desktop/Controls/em-sethandle), [LocalAlloc](/windows/desktop/api/winbase/nf-winbase-localalloc), ve [LocalFree](/windows/desktop/api/winbase/nf-winbase-localfree) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]

##  <a name="sethighlight"></a>  CEdit::SetHighlight

Öne çıkan özellikleri geçerli görüntülenen metin aralığı bir düzenleme denetimi.

```
void SetHighlight(
    int ichStart,
    int ichEnd);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*ichStart*|[in] Vurgulamak için metin aralığını ilk karakter sıfır tabanlı dizini.|
|*ichEnd*|[in] Vurgulamak için metin aralığını son karakter sıfır tabanlı dizini.|

### <a name="remarks"></a>Açıklamalar

Bu yöntem gönderir [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) Windows SDK'da açıklanan ileti.  Bu yöntem gönderir [EM_SETHILITE](/windows/desktop/Controls/em-sethilite) Windows SDK'da açıklanan ileti. Her ikisi de `SetHighlight` ve `GetHighlight` yalnızca UNICODE yapıları için etkinleştirilir.

##  <a name="setlimittext"></a>  CEdit::SetLimitText

Bu metin sınırlamak için bu üye işlevini çağırın `CEdit` nesne.

```
void SetLimitText(UINT nMax);
```

### <a name="parameters"></a>Parametreler

*nMax*<br/>
Karakter cinsinden yeni metin sınırı.

### <a name="remarks"></a>Açıklamalar

Metin, metin düzenleme denetiminin kabul edebilen karakter cinsinden en uzun süreyi sınırdır.

Metin sınırı değiştirme yalnızca kullanıcının girebileceği metin kısıtlar. Hiçbir etkisi herhangi bir metin düzenleme denetiminde zaten sahip ya da düzenleme denetimi tarafından kopyalanmasını metnin uzunluğunu etkilemez [SetWindowText](cwnd-class.md#setwindowtext) üye işlevinde `CWnd`. Bir uygulama kullanıyorsa `SetWindowText` işlev çağrısında belirtilen bir düzenleme denetimi daha fazla metin yerleştirin `LimitText`, kullanıcının herhangi bir metin düzenleme denetiminde silebilirsiniz. Ancak, metin sınırı kullanıcı yeni metinle varolan metni değiştirmesini engeller, geçerli seçimi silme sürece metin sınırın altına düşmesine neden olur.

Bu işlev değiştirir [LimitText](#limittext) Win32'de.

Daha fazla bilgi için [EM_SETLIMITTEXT](/windows/desktop/Controls/em-setlimittext) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="setmargins"></a>  CEdit::SetMargins

Bu düzenleme denetiminin sol ve sağ kenar boşluklarını ayarlamak için bu yöntemi çağırın.

```
void SetMargins(
    UINT nLeft,
    UINT nRight);
```

### <a name="parameters"></a>Parametreler

*nLeft*<br/>
Yeni sol kenar boşluğunun piksel genişliği.

*nRight*<br/>
Yeni sağ kenar piksel cinsinden genişliği.

### <a name="remarks"></a>Açıklamalar

> [!NOTE]
>  Bu üye işlevi, Windows 95 ve Windows NT 4.0 sürümlerinde kullanılabilir olan.

Daha fazla bilgi için [EM_SETMARGINS](/windows/desktop/Controls/em-setmargins) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).

##  <a name="setmodify"></a>  CEdit::SetModify

Ayarlamak veya bir düzenleme denetimi için değiştirilmiş bayrağını temizlemek için bu işlevi çağırın.

```
void SetModify(BOOL bModified = TRUE);
```

### <a name="parameters"></a>Parametreler

*bModified*<br/>
Metin değiştirildi ve değiştirilmemiş FALSE değerini belirtir. TRUE değerini gösterir. Varsayılan olarak, değiştirilen bayrağı ayarlanır.

### <a name="remarks"></a>Açıklamalar

Değiştirilen bayrağı, metin düzenleme denetiminin içinde değiştirilmiş olup olmadığını gösterir. Kullanıcının metni değiştiğinde otomatik olarak ayarlanır. Değeri ile alınabilir [GetModify](#getmodify) üye işlevi.

Daha fazla bilgi için [EM_SETMODIFY](/windows/desktop/Controls/em-setmodify) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::GetModify](#getmodify).

##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar

Kullanıcı, metin yazdığında bir düzenleme denetiminde gösterilen bir parola karakteri kaldırın veya bu işlevi çağırın.

```
void SetPasswordChar(TCHAR ch);
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Kullanıcı tarafından yazılan karakter yerine görüntülenecek karakter belirtir. Varsa *ch* 0 ise, kullanıcı tarafından yazılan karakterlerini görüntülenir.

### <a name="remarks"></a>Açıklamalar

Bir parola karakteri olarak ayarlandığında, kullanıcının yazdığı her karakter için bu karakteri görüntülenir.

Bu üye işlevi düzenleme denetimi birden çok satırlı üzerinde etkisi yoktur.

Zaman `SetPasswordChar` üye işlevi çağrıldığında `CEdit` tarafından belirtilen karakter kullanarak tüm görünür karakterleri yeniden çizer *ch*.

Düzenleme denetimi ile oluşturulursa [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) stili, varsayılan parola karakteri yıldız ayarlanır ( <strong>\*</strong>). Bu stil, kaldırılır `SetPasswordChar` çağrılır *ch* 0 olarak ayarlayın.

Daha fazla bilgi için [EM_SETPASSWORDCHAR](/windows/desktop/Controls/em-setpasswordchar) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]

##  <a name="setreadonly"></a>  CEdit::SetReadOnly

Bir düzenleme denetimi salt okunur durumunu ayarlamak için bu işlevi çağırır.

```
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```

### <a name="parameters"></a>Parametreler

*bReadOnly*<br/>
Ayarlama veya düzenleme denetimi salt okunur durumunu kaldırma belirtir. DOĞRU değeri, durumu, salt okunur olarak ayarlar; FALSE değeri okuma/yazma durumunu ayarlar.

### <a name="return-value"></a>Dönüş Değeri

İşlemi ise sıfır olmayan bir hata başarılı ya da 0 ise oluşur.

### <a name="remarks"></a>Açıklamalar

Geçerli ayarı test ederek bulunabilir [ES_READONLY](styles-used-by-mfc.md#edit-styles) dönüş değerini bayrağı [CWnd::GetStyle](cwnd-class.md#getstyle).

Daha fazla bilgi için [EM_SETREADONLY](/windows/desktop/Controls/em-setreadonly) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]

##  <a name="setrect"></a>  CEdit::SetRect

Belirtilen koordinatların kullanarak dikdörtgen boyutlarını ayarlamak için bu işlevi çağırın.

```
void SetRect(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret `RECT` yapısı veya `CRect` nesnesini biçimlendirme dikdörtgenin yeni boyutlarını belirtir.

### <a name="remarks"></a>Açıklamalar

Bu üye, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Kullanım `SetRect` biçimlendirme ayarlamak için birden çok satırlı dikdörtgen düzenleme denetimi. Biçimlendirme dikdörtgen metin düzenleme denetiminin penceresinin boyutunu bağımsızdır sınırlayıcı dikdörtgeni ' dir. Düzenleme denetiminin ilk oluşturulduğunda biçimlendirme dikdörtgen düzenleme denetimi pencerenin istemci alanının aynıdır. Kullanarak `SetRect` üye işlevi, bir uygulama yapabilir biçimlendirme dikdörtgen düzenleme denetimi penceresi daha büyük veya küçük.

Düzenleme denetiminin, hiçbir kaydırma çubuğu varsa, biçimlendirme dikdörtgen penceresinden daha büyük yapılırsa, metin, sarmalanmış değil kırpılır. Düzenleme denetiminin kenarlık içeriyorsa, biçimlendirme dikdörtgen kenarlığın boyutuyla azaltılır. Tarafından döndürülen dikdörtgene ayarlarsanız `GetRect` üye işlevini kaldırmanız gerekir kenarlığı boyutunu dikdörtgene geçirmeden önce `SetRect`.

Zaman `SetRect` çağrılır, düzenleme denetiminin metin de yeniden biçimlendirildi ve yeniden olduğu.

Daha fazla bilgi için [EM_SETRECT](/windows/desktop/Controls/em-setrect) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]

##  <a name="setrectnp"></a>  CEdit::SetRectNP

Çok satırlı düzenleme denetiminin biçimlendirme dikdörtgen ayarlamak için bu işlevi çağırın.

```
void SetRectNP(LPCRECT lpRect);
```

### <a name="parameters"></a>Parametreler

*lpRect*<br/>
İşaret eden bir `RECT` yapısı veya `CRect` nesnesini dikdörtgenin yeni boyutlarını belirtir.

### <a name="remarks"></a>Açıklamalar

Biçimlendirme dikdörtgen metin düzenleme denetiminin penceresinin boyutunu bağımsızdır sınırlayıcı dikdörtgeni ' dir.

`SetRectNP` aynı `SetRect` düzenleme denetimi penceresi değil çizilme dışında üye işlevi.

Düzenleme denetiminin ilk oluşturulduğunda biçimlendirme dikdörtgen düzenleme denetimi pencerenin istemci alanının aynıdır. Çağırarak `SetRectNP` üye işlevi, bir uygulama yapabilir biçimlendirme dikdörtgen düzenleme denetimi penceresi daha büyük veya küçük.

Düzenleme denetiminin, hiçbir kaydırma çubuğu varsa, biçimlendirme dikdörtgen penceresinden daha büyük yapılırsa, metin, sarmalanmış değil kırpılır.

Bu üye, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

Daha fazla bilgi için [EM_SETRECTNP](/windows/desktop/Controls/em-setrectnp) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::SetRect](#setrect).

##  <a name="setsel"></a>  CEdit::SetSel

Karakter aralığı içinde bir düzenleme denetimi seçmek için bu işlevi çağırın.

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
Düşük düzey Word'ün başlangıç konumunu ve dwpoint bitiş konumunu belirtir. Düşük düzey word 0'dır ve dwpoint -1 ise, tüm metin düzenleme denetiminde seçilir. Düşük düzey word -1 ise, herhangi bir geçerli seçimi kaldırılır.

*bNoScroll*<br/>
Giriş işaretini görünüme kaydırılan olup olmadığını gösterir. Giriş işaretini görünüme kaydırılan FALSE ise. TRUE ise, giriş işaretini görünüme kaydırılan değil.

*nStartChar*<br/>
Başlangıç konumu belirtir. Varsa *nStartChar* 0'dır ve *nEndChar* tüm metin düzenleme denetiminde seçili -1'dir. Varsa *nStartChar* -1, herhangi bir geçerli seçimi kaldırılır.

*nEndChar*<br/>
Bitiş konumu belirtir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [EM_SETSEL](/windows/desktop/Controls/em-setsel) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEdit::GetSel](#getsel).

##  <a name="settabstops"></a>  CEdit::SetTabStops

Sekme duraklarını birden çok satırlı düzenleme denetiminde ayarlamak için bu işlevi çağırın.

```
void SetTabStops();
BOOL SetTabStops(const int& cxEachStop);

BOOL SetTabStops(
    int nTabStops,
    LPINT rgTabStops);
```

### <a name="parameters"></a>Parametreler

*cxEachStop*<br/>
Sekme durakları, ayarlanacak belirtir her *cxEachStop* iletişim kutusu birimleri.

*nTabStops*<br/>
Bulunan bir sekme durağı sayısını belirten *rgTabStops*. Bu sayı 1'den büyük olmalıdır.

*rgTabStops*<br/>
İşaretsiz tamsayı sekmesini belirtme bir dizi noktaları iletişim kutusu birimlerinde durdurur. Yatay ve dikey uzaklığı bir iletişim birimidir. Tek bir yatay iletişim birim dörtte için geçerli iletişim temel genişliği birimi eşittir ve 1 dikey iletişim birim bir sekizinci için geçerli iletişim temel yükseklik biriminin eşittir. İletişim temel birimler geçerli sistem yazı tipi genişliği ve yüksekliği göre hesaplanır. `GetDialogBaseUnits` Windows işlevi temel birimlerinin geçerli iletişim piksel cinsinden döndürür.

### <a name="return-value"></a>Dönüş Değeri

Sekmeleri ayarlanan olursa sıfır dışı; Aksi durumda 0.

### <a name="remarks"></a>Açıklamalar

Metin bir çok satırlı düzenleme denetimine kopyalandığında, metin herhangi bir sekme karakteri alanı kadar sonraki sekme durağı oluşturulmasına neden olur.

Sekme duraklarını 32 iletişim kutusu birimleri varsayılan boyutunu ayarlamak için bu üye işlevi parametresiz sürümünü arayın. Sürümü ile 32 dışındaki bir boyuta sekme durakları ayarlama çağrısı *cxEachStop* parametresi. Bir dizi boyutları için sekme durakları ayarlamak için iki parametre ile sürümü kullanın.

Bu üye işlevi, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.

`SetTabStops` otomatik olarak düzenleme penceresi çizmez. Metin düzenleme denetiminde zaten sekme durakları değiştirirseniz, çağrı [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) düzenleme penceresi yeniden çizmek için.

Daha fazla bilgi için [EM_SETTABSTOPS](/windows/desktop/Controls/em-settabstops) ve [GetDialogBaseUnits](/windows/desktop/api/winuser/nf-winuser-getdialogbaseunits) Windows SDK.

### <a name="example"></a>Örnek

  Örneğin bakın [CEditView::SetTabStops](ceditview-class.md#settabstops).

##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip

Geçerli bir düzenleme denetimi ile ilişkili bir balon ipucu görüntüler.

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
|*pEditBalloonTip*|[in] İşaretçi bir [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) balon ipucu açıklayan yapısı.|
|*lpszTitle*|[in] Balon ipucu başlığını içeren bir Unicode dize işaretçisi.|
|*lpszText*|[in] Balon ipucu metnini içeren bir Unicode dize işaretçisi.|
|*ttiIcon*|[in] Bir **INT** balon ipucu ile ilişkilendirilecek simgesi türünü belirtir. TTI_NONE varsayılan değerdir. Daha fazla bilgi için `ttiIcon` üyesi [EDITBALLOONTIP](/windows/desktop/api/commctrl/ns-commctrl-_tageditballoontip) yapısı.|

### <a name="return-value"></a>Dönüş Değeri

Bu yöntem başarılı olursa TRUE; Aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bu işlev gönderir [EM_SHOWBALLOONTIP](/windows/desktop/Controls/em-showballoontip) Windows SDK'da açıklanan ileti. Daha fazla bilgi için [Edit_ShowBalloonTip](/windows/desktop/api/commctrl/nf-commctrl-edit_showballoontip) makrosu.

### <a name="example"></a>Örnek

Aşağıdaki kod örneği bir değişkene tanımlar `m_cedit`, yani geçerli düzenleme denetiminin erişmek için kullanılır. Bu değişken bir sonraki örnekte kullanılır.

[!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]

### <a name="example"></a>Örnek

Aşağıdaki kod örneği, bir düzenleme denetimi için bir balon ipucu görüntüler. [CEdit::ShowBalloonTip](#showballoontip) yöntemi, bir başlık ve balon ipucu metnini belirtir.

[!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]

##  <a name="undo"></a>  CEdit::Undo

Son düzenleme işlemi geri almak için bu işlevi çağırın.

```
BOOL Undo();
```

### <a name="return-value"></a>Dönüş Değeri

Tek satırlı düzenleme denetimi için dönüş değeri her zaman sıfır olmayan. Dönüş değeri, birden çok satırlı düzenleme denetimi için geri alma işlemi başarılı olursa sıfır ya da geri alma işlemi başarısız olursa 0.

### <a name="remarks"></a>Açıklamalar

Geri alma işlemi geri alınabilir. Örneğin, ilk çağrı ile silinen metin geri yükleyebilirsiniz `Undo`. Müdahalede bulunan hiçbir düzenleme işlemi var olduğu sürece, ikinci çağrı metinle yeniden kaldırabilirsiniz `Undo`.

Daha fazla bilgi için [EM_UNDO](/windows/desktop/Controls/em-undo) Windows SDK.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MFC örnek CALCDRIV](../../visual-cpp-samples.md)<br/>
[MFC örnek CMNCTRL2](../../visual-cpp-samples.md)<br/>
[CWnd Sınıfı](../../mfc/reference/cwnd-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CWnd Sınıfı](cwnd-class.md)<br/>
[CButton Sınıfı](cbutton-class.md)<br/>
[CComboBox Sınıfı](ccombobox-class.md)<br/>
[CListBox Sınıfı](clistbox-class.md)<br/>
[CScrollBar Sınıfı](cscrollbar-class.md)<br/>
[CStatic Sınıfı](cstatic-class.md)<br/>
[CDialog Sınıfı](cdialog-class.md)
