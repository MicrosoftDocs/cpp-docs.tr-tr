---
title: CEdit sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 72bf4ffb56ad34926b3a47d86d7609aae5dff4f5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cedit-class"></a>CEdit sınıfı
Bir Windows düzenleme denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CEdit : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEdit::CEdit](#cedit)|Oluşturan bir `CEdit` denetim nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CEdit::CanUndo](#canundo)|Bir düzenleme denetimi işlemi alınabilecek olup olmadığını belirler.|  
|[CEdit::CharFromPos](#charfrompos)|Belirtilen bir konuma yakın karakter satır ve karakter dizinlerini alır.|  
|[CEdit::Clear](#clear)|Siler (temizler) düzenleme geçerli seçim (eğer varsa) denetler.|  
|[CEdit::Copy](#copy)|Geçerli seçim (varsa) düzenleme denetimine panoya kopyalar **CF_TEXT** biçimi.|  
|[CEdit::Create](#create)|Windows düzenleme denetimi oluşturur ve ona ekler `CEdit` nesnesi.|  
|[CEdit::Cut](#cut)|Geçerli seçim (eğer varsa) düzenleme siler (keser) denetlemek ve silinen metni panoya kopyalar **CF_TEXT** biçimi.|  
|[CEdit::EmptyUndoBuffer](#emptyundobuffer)|(Temizler) bir düzen geri bayrağı denetim sıfırlar.|  
|[CEdit::FmtLines](#fmtlines)|Eklenmesi yumuşak satır sonu karakterleri, birden çok satırlı düzenleme denetimi içinde açmak veya kapatmak ayarlar.|  
|[CEdit::GetCueBanner](#getcuebanner)|Metin işaret ya da Denetim boş olduğunda ve odağa sahip olmayan bir düzenleme denetimindeki ipucu olarak görüntülenen metni alır.|  
|[CEdit::GetFirstVisibleLine](#getfirstvisibleline)|En üstteki görünür satırın bir düzenleme denetimindeki belirler.|  
|[CEdit::GetHandle](#gethandle)|Birden çok satırlı düzenleme denetimi için ayrılmış bellek için bir tanıtıcı alır.|  
|[CEdit::GetHighlight](#gethighlight)|Başlangıç ve bitiş geçerli düzenleme denetimine vurgulanmış metnin bir aralıktaki karakterleri dizinlerini alır.|  
|[CEdit::GetLimitText](#getlimittext)|Bu metin maksimum miktarını alır `CEdit` içerebilir.|  
|[CEdit::GetLine](#getline)|Metin satırının bir düzenleme denetiminden alır.|  
|[CEdit::GetLineCount](#getlinecount)|Birden çok satırlı düzenleme denetimindeki satırları sayısını alır.|  
|[CEdit::GetMargins](#getmargins)|Bunun için sol ve sağ kenar boşlukları alır `CEdit`.|  
|[CEdit::GetModify](#getmodify)|Bir düzen denetimi içeriğini değiştirilmiş olup olmadığını belirler.|  
|[CEdit::GetPasswordChar](#getpasswordchar)|Kullanıcı metin girdiğinde bir düzen denetiminde gösterilen parola karakteri alır.|  
|[CEdit::GetRect](#getrect)|Bir düzen denetimi biçimlendirme dikdörtgen alır.|  
|[CEdit::GetSel](#getsel)|Bir düzenleme denetimindeki geçerli bölüm ilk ve son karakteri konumunu alır.|  
|[CEdit::HideBalloonTip](#hideballoontip)|Geçerli düzenleme denetimi ile ilişkilendirilmiş tüm balon ipucu gizler.|  
|[CEdit::LimitText](#limittext)|Kullanıcı bir Düzenle denetime girebileceği metin uzunluğu sınırlar.|  
|[CEdit::LineFromChar](#linefromchar)|Belirtilen karakter dizinini içeren satırının satır numarasını alır.|  
|[CEdit::LineIndex](#lineindex)|Birden çok satırlı düzenleme denetimi içinde bir satır karakter dizinini alır.|  
|[CEdit::LineLength](#linelength)|Bir düzenleme denetimindeki bir satır uzunluğunu alır.|  
|[CEdit::LineScroll](#linescroll)|Birden çok satırlı düzenleme denetimi metin kayar.|  
|[CEdit::Paste](#paste)|Verileri düzenleme denetimi geçerli imleç konumundaki panodan ekler. Verileri yalnızca Pano veri içeriyorsa eklenir **CF_TEXT** biçimi.|  
|[CEdit::PosFromChar](#posfromchar)|Belirtilen karakter dizinini sol üst köşesinin koordinatlarını alır.|  
|[CEdit::ReplaceSel](#replacesel)|Bir düzenleme denetimindeki geçerli bölüm belirtilen metinle değiştirir.|  
|[CEdit::SetCueBanner](#setcuebanner)|Metin işaret ya da Denetim boş olduğunda ve odağa sahip olmayan bir düzenleme denetimindeki ipucu olarak görüntülenen metni ayarlar.|  
|[CEdit::SetHandle](#sethandle)|Birden çok satırlı düzenleme denetimi tarafından kullanılan yerel belleğe tanıtıcı ayarlar.|  
|[CEdit::SetHighlight](#sethighlight)|Düzen denetimi geçerli görüntülenen metin aralığını bir vurgular.|  
|[CEdit::SetLimitText](#setlimittext)|En büyük miktarda metin bu ayarlar `CEdit` içerebilir.|  
|[CEdit::SetMargins](#setmargins)|Sol ve sağ kenar boşlukları için bu ayarlar `CEdit`.|  
|[CEdit::SetModify](#setmodify)|Ayarlar veya bir düzenleme denetimi değişikliği bayrağını temizler.|  
|[CEdit::SetPasswordChar](#setpasswordchar)|Ayarlar ya da kullanıcı metin girdiğinde bir düzen denetiminde gösterilen bir parola karakteri kaldırır.|  
|[CEdit::SetReadOnly](#setreadonly)|Bir düzen denetimi salt okunur durumunu ayarlar.|  
|[CEdit::SetRect](#setrect)|Birden çok satırlı düzenleme denetimi biçimlendirme dikdörtgen ayarlar ve denetim güncelleştirir.|  
|[CEdit::SetRectNP](#setrectnp)|Birden çok satırlı düzenleme denetimi biçimlendirme dikdörtgen denetimi penceresi yeniden olmadan ayarlar.|  
|[CEdit::SetSel](#setsel)|Karakter aralığı bir düzenleme denetimini seçer.|  
|[CEdit::SetTabStops](#settabstops)|Düzen denetimi Ayarlar sekmesinde birden çok satırda durdurur.|  
|[CEdit::ShowBalloonTip](#showballoontip)|Geçerli düzenleme denetimi ile ilişkili bir balon ipucu görüntüler.|  
|[CEdit::Undo](#undo)|Son düzenleme denetimi işlem tersine çevirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir düzen denetimi, kullanıcı metin girebilirsiniz dikdörtgen alt bir penceredir.  
  
 Bir iletişim şablonunu ya da kodunuzdaki doğrudan bir düzenleme denetimi oluşturabilirsiniz. Her iki durumda da ilk Oluşturucusu çağrısı `CEdit` oluşturmak için `CEdit` nesne sonra çağırın [oluşturma](#create) Windows oluşturmak için üye işlevi düzenleme denetimi ve ekleyebilir `CEdit` nesnesi.  
  
 Yapım tek adımlı işlem türetilen bir sınıfta olabilir `CEdit`. Çağrı ve türetilmiş sınıf oluşturucu yazma **oluşturma** gelen oluşturucusu içinde.  
  
 `CEdit` önemli işlevsellik devralır `CWnd`. Ayarlamak ve metinden almak için bir `CEdit` nesne, kullanın `CWnd` üye işlevleri [SetWindowText](cwnd-class.md#setwindowtext) ve [GetWindowText](cwnd-class.md#getwindowtext), hangi kümesi veya get bir düzen tüm içeriğini denetlemek, olsa bile, çok satırlı bir denetimdir. Çok satırlı denetiminde metin satırlarını '\r\n' karakter sıraları ile ayrılır. Ayrıca, bir düzenleme denetimi çok satırlı ise, almak ve ayarlamak denetimin metnin bir bölümünü çağırarak `CEdit` üye işlevleri [GetLine](#getline), [SetSel](#setsel), [GetSel](#getsel)ve [ ReplaceSel](#replacesel).  
  
 Üst için bir düzen denetimi tarafından gönderilen Windows bildirim iletilerini işlemek istiyorsanız (öğesinden türetilmiş bir sınıf genellikle `CDialog`), her ileti için üst sınıfı için ileti eşleme girişi ve ileti işleyicisi üye işlevi ekleme.  
  
 Her ileti eşleme girişi aşağıdaki biçimdedir:  
  
 **ON_** bildirim **(** *kimliği, memberFxn ***)**  
  
 Burada `id` bildirim göndererek düzenleme denetimi alt pencere Kimliğini belirtir ve `memberFxn` bildirimini işlemek için yazılmış üst üye işlevi adıdır.  
  
 Üst öğenin işlev prototipi aşağıdaki gibidir:  
  
 **afx_msg** void memberFxn **();**  
  
 Olası ileti eşleme girişleri ve açıklamasını, bunlar üst gönderilecek örneklerinin listesi aşağıdadır:  
  
- **ON_EN_CHANGE** kullanıcı düzenleme denetimi metinde değiştirmiş bir eylem sürdü. Farklı **EN_UPDATE** bildirim iletisi, bu bildirim iletisi Windows görüntü güncelleştirildikten sonra gönderilir.  
  
- **ON_EN_ERRSPACE** düzenleme denetimi belirli bir isteği karşılamak için yeterli bellek ayrılamıyor.  
  
- **ON_EN_HSCROLL** kullanıcı bir Düzenle denetimin yatay kaydırma çubuğu tıklar. Ekran güncelleştirilmeden önce üst pencere bildirilir.  
  
- **On_en_kıllfocus** düzenleme denetimine giriş odağı kaybettiğinde.  
  
- **ON_EN_MAXTEXT** geçerli ekleme belirtilen sayıda karakteri düzenleme denetimi için aştı ve kesildi. Bir düzen denetimi olmadığı zaman da gönderilen **ES_AUTOHSCROLL** stili ve eklenecek karakter sayısını düzenleme denetimi genişliğini aşabilir. Bir düzen denetimi olmadığı zaman da gönderilen **ES_AUTOVSCROLL** stili ve bir metin ekleme kaynaklanan satırların toplam sayısı düzenleme denetimi yüksekliğini aşabilir.  
  
- **ON_EN_SETFOCUS** düzenleme denetimine giriş odağını aldığında gönderilir.  
  
- **ON_EN_UPDATE** düzenleme denetimi hakkında değiştirilen metin görüntülemektir. Denetim biçimlendirilmiş metin sonra ancak pencere boyutu değiştirilebilir böylece, metin gerekirse ekranları önce gönderilir.  
  
- **ON_EN_VSCROLL** kullanıcı bir Düzenle denetimin dikey kaydırma çubuğu tıklar. Ekran güncelleştirilmeden önce üst pencere bildirilir.  
  
 Oluşturursanız, bir `CEdit` nesnesi bir iletişim kutusu içinde `CEdit` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CEdit` iletişim kutusu Düzenleyicisi'ni kullanarak bir iletişim kutusu kaynağı nesnesinden `CEdit` nesne kullanıcı iletişim kutusu kapandığında otomatik olarak yok.  
  
 Oluşturursanız, bir `CEdit` nesne bir pencere içinde de gerekebilir, yok. Oluşturursanız, `CEdit` nesne yığında otomatik olarak yok. Oluşturursanız, `CEdit` nesnesi kullanarak yığında **yeni** işlevini çağırmanız gerekir **silmek** kullanıcı Windows sonlandırıldığında yok etmek için bir nesne üzerinde düzenleme denetimi. Tüm bellekte ayırdığınızda `CEdit` nesne, geçersiz kılma `CEdit` yıkıcı ayrılmasını silmek için.  
  
 Belirli bir düzenleme denetimi stillerde değiştirmek için (gibi **ES_READONLY**) kullanmak yerine denetlemek için belirli iletileri gönder [ModifyStyle](cwnd-class.md#modifystyle). Bkz: [Düzenle denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb775464) Windows SDK.  
  
 Daha fazla bilgi için `CEdit`, bkz:  
  
- [Denetimler](../../mfc/controls-mfc.md)  
  
-   Bilgi Bankası makalesi Q259949: bilgi: SetCaretPos() olan uygun olmayan CEdit veya CRichEditCtrl denetimleri  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](cobject-class.md)  
  
 [CCmdTarget](ccmdtarget-class.md)  
  
 [CWnd](cwnd-class.md)  
  
 `CEdit`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
##  <a name="canundo"></a>  CEdit::CanUndo  
 Son düzenleme işlemi geri olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL CanUndo() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Son düzenleme işlemi için yapılan bir çağrı tarafından alınabilir, sıfır olmayan **geri** üye işlevi; 0 geri alınamaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_CANUNDO](http://msdn.microsoft.com/library/windows/desktop/bb775468) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::Undo](#undo).  
  
##  <a name="cedit"></a>  CEdit::CEdit  
 Oluşturan bir `CEdit` nesnesi.  
  
```  
CEdit();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım [oluşturma](#create) Windows düzen denetimi oluşturulamadı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#1](../../mfc/reference/codesnippet/cpp/cedit-class_1.cpp)]  
  
##  <a name="charfrompos"></a>  CEdit::CharFromPos  
 Sıfır tabanlı satır ve bu belirtilen noktasında en yakın bir karakterin karakter dizinlerini almak için bu işlevi çağırmak `CEdit` denetimi  
  
```  
int CharFromPos(CPoint pt) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `pt`  
 Bu istemci alanında bir noktanın koordinatlarını `CEdit` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düşük düzey karakter dizinde **WORD**ve yüksek sırayla satır dizini **WORD**.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu üye fonksiyonu kullanılabilir başlayarak Windows 95 ve Windows NT 4.0 kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_CHARFROMPOS](http://msdn.microsoft.com/library/windows/desktop/bb761566) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#3](../../mfc/reference/codesnippet/cpp/cedit-class_2.cpp)]  
  
##  <a name="clear"></a>  CEdit::Clear  
 (Temizle) geçerli seçim düzenleme denetimine (varsa) silmek için bu işlevini çağırın.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından gerçekleştirilen silme **Temizle** çağırarak geri [geri](#undo) üye işlevi.  
  
 Geçerli seçimi silin ve silinmiş içeriği panoya yerleştirmek için çağrı [Kes](#cut) üye işlevi.  
  
 Daha fazla bilgi için bkz: [WM_CLEAR](http://msdn.microsoft.com/library/windows/desktop/ms649020) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#4](../../mfc/reference/codesnippet/cpp/cedit-class_3.cpp)]  
  
##  <a name="copy"></a>  CEdit::Copy  
 Bu işleve coy Pano'ya düzenleme denetimindeki (varsa) geçerli seçim çağrısı **CF_TEXT** biçimi.  
  
```  
void Copy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [WM_COPY](http://msdn.microsoft.com/library/windows/desktop/ms649022) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#5](../../mfc/reference/codesnippet/cpp/cedit-class_4.cpp)]  
  
##  <a name="create"></a>  CEdit::Create  
 Windows düzenleme denetimi oluşturur ve ona ekler `CEdit` nesnesi.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Düzenle denetim stilini belirtir. Herhangi bir bileşimini uygulamak [düzenleme stilleri](styles-used-by-mfc.md#edit-styles) denetlemek için.  
  
 `rect`  
 Düzenle denetim boyutunu ve konumunu belirtir. Olabilir bir `CRect` nesne veya `RECT` yapısı.  
  
 `pParentWnd`  
 Düzenle denetim üst pencere belirtir (genellikle bir `CDialog`). Değil olmalıdır **NULL**.  
  
 `nID`  
 Düzenle denetim kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CEdit` iki adımda nesne. İlk olarak, arama `CEdit` oluşturucu ve ardından arama **oluşturma**, hangi Windows düzenleme denetimi oluşturur ve ekler `CEdit` nesnesi.  
  
 Zaman **oluşturma** yürütür, Windows gönderir [WM_NCCREATE](http://msdn.microsoft.com/library/windows/desktop/ms632635), [WM_NCCALCSIZE](http://msdn.microsoft.com/library/windows/desktop/ms632634), [WM_CREATE](http://msdn.microsoft.com/library/windows/desktop/ms632619), ve [WM_ GETMINMAXINFO](http://msdn.microsoft.com/library/windows/desktop/ms632626) düzenleme denetimine iletisi.  
  
 Bu iletiler, varsayılan olarak tarafından işlenen [OnNcCreate](cwnd-class.md#onnccreate), [OnNcCalcSize](cwnd-class.md#onnccalcsize), [OnCreate](cwnd-class.md#oncreate), ve [Ongetminmaxınfo](cwnd-class.md#ongetminmaxinfo) üye işlevleri içinde `CWnd` temel sınıfı. Varsayılan ileti işleme genişletmek için öğesinden bir sınıf türetin `CEdit`ileti eşlemesi için yeni sınıf ekleyin ve yukarıdaki ileti işleyicisi üye işlevlerini geçersiz kılma. Geçersiz kılma `OnCreate`, örneğin, gerekli başlatma için yeni bir sınıf gerçekleştirmek için.  
  
 Aşağıdaki uygulama [pencere stilleri](styles-used-by-mfc.md#window-styles) bir düzenleme denetimine.  
  
- **WS_CHILD** her zaman  
  
- **Ws_vısıble** genellikle  
  
- **Ws_dısabled** nadiren  
  
- **WS_GROUP** grup denetimleri için  
  
- **WS_TABSTOP** sekme sırasını düzenleme denetimi eklemek için  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#2](../../mfc/reference/codesnippet/cpp/cedit-class_5.cpp)]  
  
##  <a name="cut"></a>  CEdit::Cut  
 Düzenleme denetimine (varsa) geçerli seçim (kesme) silmek için bu işlevi çağırmak ve silinen metni panoya kopyalamak **CF_TEXT** biçimi.  
  
```  
void Cut();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından gerçekleştirilen silme **Kes** çağırarak geri [geri](#undo) üye işlevi.  
  
 Geçerli seçim silinen metni panoya koymadan silmek için arama [Temizle](#clear) üye işlevi.  
  
 Daha fazla bilgi için bkz: [WM_CUT](http://msdn.microsoft.com/library/windows/desktop/ms649023) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#6](../../mfc/reference/codesnippet/cpp/cedit-class_6.cpp)]  
  
##  <a name="emptyundobuffer"></a>  CEdit::EmptyUndoBuffer  
 (Sil) sıfırlamak için bu işlev bir düzenleme denetimi geri bayrağı çağırın.  
  
```  
void EmptyUndoBuffer();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Düzenleme denetimi şimdi son işlemi geri yükleyemez. Düzenleme denetimi içinde bir işlem geri alınabilir olduğunda geri alma bayrağını ayarlayın.  
  
 Otomatik olarak geri bayrağı her temizlenmiş [SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext) veya [SetHandle](#sethandle) `CWnd` üye işlevleri çağrılır.  
  
 Daha fazla bilgi için bkz: [EM_EMPTYUNDOBUFFER](http://msdn.microsoft.com/library/windows/desktop/bb761568) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#7](../../mfc/reference/codesnippet/cpp/cedit-class_7.cpp)]  
  
##  <a name="fmtlines"></a>  CEdit::FmtLines  
 Birden çok satırlı düzenleme denetimi içinde yumuşak satır sonu karakterleri dahil edilmesi açmak veya kapatmak ayarlamak için bu işlevini çağırın.  
  
```  
BOOL FmtLines(BOOL bAddEOL);
```  
  
### <a name="parameters"></a>Parametreler  
 *bAddEOL*  
 Yumuşak satır sonu karakterleri eklenecek olup olmadığını belirtir. Değerini **TRUE** ; karakter ekler değerini **FALSE** bunları kaldırır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Varsa sıfır olmayan biçimlendirme oluşur; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 İki satır başı ve sözcük kaydırma nedeniyle bozuk bir satır sonuna eklenen bir satır besleme yumuşak satır sonu oluşur. Bir satır başı ve satır besleme bir sabit satır sonu oluşur. Sabit satır sonu ile son satırları etkilenmez `FmtLines`.  
  
 Windows, yanıt yalnızca `CEdit` birden çok satırlı düzenleme denetimi nesnesidir.  
  
 `FmtLines` yalnızca tarafından döndürülen arabellek etkiler [GetHandle](#gethandle) ve tarafından döndürülen metin [WM_GETTEXT](http://msdn.microsoft.com/library/windows/desktop/ms632627). Düzenle denetim içindeki metnin görüntülenmesi üzerinde hiçbir etkisi olmaz.  
  
 Daha fazla bilgi için bkz: [EM_FMTLINES](http://msdn.microsoft.com/library/windows/desktop/bb761570) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#8](../../mfc/reference/codesnippet/cpp/cedit-class_8.cpp)]  
  
##  <a name="getcuebanner"></a>  CEdit::GetCueBanner  
 Metin işaret ya da Denetim boş olduğunda bir düzenleme denetimindeki ipucu olarak görüntülenen metni alır.  
  
```  
BOOL GetCueBanner(
    LPWSTR lpszText,  
    int cchText) const;  
  
CString GetCueBanner() const;  
```  
  
### <a name="parameters"></a>Parametreler  
 [out] `lpszText`  
 İşaret metin içeren bir dize için bir işaretçi.  
  
 [in] `cchText`  
 Alınabilir karakter sayısı. Bu sayı sonlandırma içerir `NULL` karakter.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk aşırı için `true` yöntemi başarılıysa ise `false`.  
  
 İkinci aşırı yüklemesi için bir [CString](../../atl-mfc-shared/using-cstring.md) yöntemi ise, başarılı, aksi takdirde işaret metni içeren boş dize ("").  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [EM_GETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761572) Windows SDK'ın açıklanan ileti. Daha fazla bilgi için bkz: [Edit_GetCueBannerText](http://msdn.microsoft.com/library/windows/desktop/bb761695) makrosu.  
  
##  <a name="getfirstvisibleline"></a>  CEdit::GetFirstVisibleLine  
 Bir düzen denetimi en üstteki görünür satırında belirlemek için bu işlevini çağırın.  
  
```  
int GetFirstVisibleLine() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 En üstteki görünür satır sıfır tabanlı dizini. Tek satırlı düzenleme denetimlerinde dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_GETFIRSTVISIBLELINE](http://msdn.microsoft.com/library/windows/desktop/bb761574) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#9](../../mfc/reference/codesnippet/cpp/cedit-class_9.cpp)]  
  
##  <a name="gethandle"></a>  CEdit::GetHandle  
 Şu anda birden çok satırlı düzenleme denetimi için ayrılan bellek için bir tanıtıcı almak için bu işlevini çağırın.  
  
```  
HLOCAL GetHandle() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenleme denetimi içeriğini tutan arabellek tanımlayan bir yerel bellek tanıtıcısı. Tek satırlı düzenleme denetimine ileti gönderme gibi bir hata oluşursa, dönüş değeri 0'dır.  
  
### <a name="remarks"></a>Açıklamalar  
 İşleyici yerel bellek tanıtıcısı ve herhangi biri tarafından kullanılabilir **yerel** yerel bellek ele Windows bellek işlevleri parametre olarak işler.  
  
 **GetHandle** yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Çağrı **GetHandle** iletişim kutusu ile oluşturulmuşsa bir iletişim kutusunda birden çok satırlı düzenleme denetimi için **DS_LOCALEDIT** stil bayrağı ayarlanmış. Varsa **DS_LOCALEDIT** stili ayarlı değil, sıfır olmayan bir dönüş değeri almaya devam, ancak döndürülen değer kullanmanız mümkün olmaz.  
  
> [!NOTE]
> **GetHandle** Windows 95/98 ile çalışmaz. Çağırırsanız **GetHandle** Windows 95/98, onu döndürür **NULL**. **GetHandle** 3.51 ve sonraki sürümleri Windows NT altında açıklandığı gibi çalışır.  
  
 Daha fazla bilgi için bkz: [EM_GETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761576) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#10](../../mfc/reference/codesnippet/cpp/cedit-class_10.cpp)]  
  
##  <a name="gethighlight"></a>  CEdit::GetHighlight  
 İlk ve son karakterler dizinleri geçerli düzenleme denetimine vurgulanmış metin aralığını alır.  
  
```  
BOOL GetHighlight(
    int* pichStart,   
    int* pichEnd) const;  
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[out] `pichStart`|İlk karakter vurgulanır metin aralığını, sıfır tabanlı dizini.|  
|[out] `pichEnd`|Vurgulanan metin aralığını son karakter sıfır tabanlı dizini.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [EM_GETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761578) Windows SDK'ın açıklanan ileti.  
  
##  <a name="getlimittext"></a>  CEdit::GetLimitText  
 Bu metin sınırını almak için bu üye işlevini çağırın `CEdit` nesnesi.  
  
```  
UINT GetLimitText() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli metin sınırı, bayt cinsinden bu `CEdit` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin düzenleme denetimi kabul edebilir bayt cinsinden maksimum metin sınırıdır.  
  
> [!NOTE]
>  Bu üye fonksiyonu kullanılabilir başlayarak Windows 95 ve Windows NT 4.0 kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_GETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761582) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#11](../../mfc/reference/codesnippet/cpp/cedit-class_11.cpp)]  
  
##  <a name="getline"></a>  CEdit::GetLine  
 Metin satırının bir düzenleme denetiminden almak için bu işlevi çağırmak ve yerleştirir `lpszBuffer`.  
  
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
 `nIndex`  
 Birden çok satırından almak için satır numarası düzenleme denetimi belirtir. Satır numaraları sıfır tabanlı; 0 değeri ilk satırı belirtir. Bu parametre, tek satırlı düzenleme denetimi tarafından göz ardı edilir.  
  
 `lpszBuffer`  
 Satır kopyasını alan arabellek noktalarına. Arabellek ilk sözcüğün arabelleğe kopyalanabilmesi için karakter üst sınırını belirtmeniz gerekir.  
  
 `nMaxLength`  
 Arabelleğe kopyalanabilir bayt sayısını belirtir. `GetLine` Bu değer ilk Word'de yerleştirir `lpszBuffer` Windows çağrısı yapmadan önce.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerçekte kopyalanan bayt sayısı. Dönüş değeri satır numarası tarafından belirtilen 0 ise `nIndex` düzenleme denetimindeki satırları sayısından büyük.  
  
### <a name="remarks"></a>Açıklamalar  
 Kopyalanan satırın null sonlandırma karakter içermiyor.  
  
 Daha fazla bilgi için bkz: [EM_GETLINE](http://msdn.microsoft.com/library/windows/desktop/bb761584) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::GetLineCount](#getlinecount).  
  
##  <a name="getlinecount"></a>  CEdit::GetLineCount  
 Birden çok satırlı düzenleme denetimindeki satırları sayısını almak üzere bu işlevini çağırın.  
  
```  
int GetLineCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Birden çok satırlı satır sayısını içeren bir tamsayı denetim düzenleyin. Metin düzenleme denetimine girilmemişse dönüş değeri 1'dir.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetLineCount` yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Daha fazla bilgi için bkz: [EM_GETLINECOUNT](http://msdn.microsoft.com/library/windows/desktop/bb761586) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#12](../../mfc/reference/codesnippet/cpp/cedit-class_12.cpp)]  
  
##  <a name="getmargins"></a>  CEdit::GetMargins  
 Sol ve sağ kenar boşluklarının bu düzenleme denetimini almak için bu üye işlevini çağırın.  
  
```  
DWORD GetMargins() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sol kenar boşluğu düşük sırayla genişliğini **WORD** ve sağ kenar boşluğu yüksek sırayla genişliğini **WORD**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kenar boşlukları piksel cinsinden ölçülür.  
  
> [!NOTE]
>  Bu üye fonksiyonu kullanılabilir başlayarak Windows 95 ve Windows NT 4.0 kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_GETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761590) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="getmodify"></a>  CEdit::GetModify  
 Bir düzen denetimi içeriğini değiştirilmiş olup olmadığını belirlemek için bu işlevini çağırın.  
  
```  
BOOL GetModify() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Düzenle denetim içeriği değiştirilirse sıfır olmayan; Bunlar kaldığı yoksa 0 değişmedi.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows düzenleme denetimi içeriğini değiştirilmiş olup olmadığını belirten bir iç bayrağı korur. Bu bayrak düzenleme denetimi ilk oluşturulduğunda ve çağırarak ayrıca temizlenmesi temizlenir [SetModify](#setmodify) üye işlevi.  
  
 Daha fazla bilgi için bkz: [EM_GETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761592) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#13](../../mfc/reference/codesnippet/cpp/cedit-class_13.cpp)]  
  
##  <a name="getpasswordchar"></a>  CEdit::GetPasswordChar  
 Kullanıcı metin girdiğinde, bir düzenleme denetiminde gösterilen parola karakter almak için bu işlevini çağırın.  
  
```  
TCHAR GetPasswordChar() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kullanıcı yazılan karakter yerine görüntülenecek karakteri belirtir. Dönüş değeri `NULL` hiçbir parola karakteri varsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Düzen denetimi ile oluşturursanız **ES_PASSWORD** stilini, Denetim destekler DLL varsayılan parola karakteri belirler. Bildirim veya [InitCommonControlsEx](http://msdn.microsoft.com/library/windows/desktop/bb775697) yöntemi DLL destekleyen belirler düzenleme denetimi. User32.dll düzenleme denetimi destekliyorsa, varsayılan parola yıldız karakterdir ('* ', U + 002A). Comctl32.dll sürüm 6 düzenleme denetimi destekliyorsa, varsayılan siyah DAİRE ('●', U + 25CF) karakterdir. Ortak Denetimler DLL ve sürümünü destekleyen hakkında daha fazla bilgi için bkz [kabuk ve ortak denetimleri sürümleri](http://msdn.microsoft.com/library/windows/desktop/bb776779).  
  
 Bu yöntem gönderir [EM_GETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761594) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#14](../../mfc/reference/codesnippet/cpp/cedit-class_14.cpp)]  
  
##  <a name="getrect"></a>  CEdit::GetRect  
 Bir düzen denetimi biçimlendirme dikdörtgen almak için bu işlevini çağırın.  
  
```  
void GetRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret `RECT` biçimlendirme dikdörtgen alan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirme dikdörtgen düzenleme denetimi penceresi boyutunu bağımsızdır metin sınırlayan dikdörtgen ' dir.  
  
 Birden çok satırlı düzenleme denetimi biçimlendirme dikdörtgen tarafından değiştirilebilir [SetRect](#setrect) ve [SetRectNP](#setrectnp) üye işlevleri.  
  
 Daha fazla bilgi için bkz: [EM_GETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761596) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::LimitText](#limittext).  
  
##  <a name="getsel"></a>  CEdit::GetSel  
 Başlangıç ve bitiş dönüş değeri veya parametrelerini kullanarak bir düzenleme denetimindeki geçerli bölüm (varsa) karakter konumlarını almak için bu işlevini çağırın.  
  
```  
DWORD GetSel() const;  
  
void GetSel(
    int& nStartChar,  
    int& nEndChar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nStartChar`  
 İlk karakterin geçerli seçim alacak bir tamsayı başvuru.  
  
 `nEndChar`  
 İlk karakterin nonselected geçerli seçimin sonundan sonraya alacak bir tamsayı başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür sürüm bir `DWORD` yüksek düzey word seçim sonunda düşük düzey Word'de başlangıç konumu ve ilk karakterin nonselected içeren bir değer döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_GETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761598) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#15](../../mfc/reference/codesnippet/cpp/cedit-class_15.cpp)]  
  
##  <a name="hideballoontip"></a>  CEdit::HideBalloonTip  
 Geçerli düzenleme denetimi ile ilişkilendirilmiş tüm balon ipucu gizler.  
  
```  
BOOL HideBalloonTip();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev gönderir [EM_HIDEBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761604) Windows SDK'ın açıklanan ileti.  
  
##  <a name="limittext"></a>  CEdit::LimitText  
 Kullanıcı bir Düzenle denetime girebilirsiniz metnin uzunluğunu sınırlamak için bu işlevini çağırın.  
  
```  
void LimitText(int nChars = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nChars`  
 Kullanıcının girebileceği metin uzunluğu (bayt cinsinden) belirtir. Bu parametre 0 ise, metin uzunluğu kümesine **uınt_max** bayt sayısı. Bu varsayılan davranıştır.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin sınırı değiştirme yalnızca kullanıcının girebileceği metin kısıtlar. Düzenleme denetimine herhangi bir metin üzerinde hiçbir etkisi zaten var veya düzenleme denetimi tarafından kopyalanmasını metnin uzunluğunu etkilemez [SetWindowText](cwnd-class.md#setwindowtext) üye işlevinde `CWnd`. Bir uygulama kullanıyorsa, `SetWindowText` işlev çağrısında belirtilen bir düzenleme denetimi daha fazla metin yerleştirin `LimitText`, kullanıcının herhangi bir düzenleme denetimi içindeki metnin silebilirsiniz. Ancak, metin sınırı kullanıcı varolan metni yeni metinle değiştirmesini önlemek için geçerli seçim silme sürece metni metin sınırın altına düşmesine neden olur.  
  
> [!NOTE]
>  Win32 içinde (Windows NT ve Windows 95/98) [SetLimitText](#setlimittext) bu işlevin yerini alır.  
  
 Daha fazla bilgi için bkz: [EM_LIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761607) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#17](../../mfc/reference/codesnippet/cpp/cedit-class_16.cpp)]  
  
##  <a name="linefromchar"></a>  CEdit::LineFromChar  
 Belirtilen karakter dizinini içeren satırının satır numarasını almak için bu işlevini çağırın.  
  
```  
int LineFromChar(int nIndex = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 İstenen karakter düzenleme denetimi metninde sıfır tabanlı dizin değeri içeriyor veya -1 içerir. Varsa `nIndex` -1 ' dir geçerli satır, diğer bir deyişle, düzeltme işareti içeren satırı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen karakter dizinini içeren satırı sıfır tabanlı satır sayısı `nIndex`. Varsa `nIndex` -1 ' dir seçimi ilk karakteri içeren satırı sayısını döndürülür. Herhangi bir seçim geçerli satır numarasını döndürülür.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter dizini düzenleme denetimi başından itibaren karakter sayısıdır.  
  
 Bu üye işlevi yalnızca birden çok satırlı düzenleme denetimleri tarafından kullanılır.  
  
 Daha fazla bilgi için bkz: [EM_LINEFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761609) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#18](../../mfc/reference/codesnippet/cpp/cedit-class_17.cpp)]  
  
##  <a name="lineindex"></a>  CEdit::LineIndex  
 Birden çok satırlı düzenleme denetimi içinde bir satır karakter dizinini almak için bu işlevini çağırın.  
  
```  
int LineIndex(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nLine`  
 Düzenle denetim metin istenen satır için bir dizin değeri içeriyor veya -1 içerir. Varsa `nLine` -1 ' dir geçerli satır, diğer bir deyişle, düzeltme işareti içeren satırı belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen satır karakter dizinini `nLine` veya belirtilen satır numarası düzenleme denetimindeki satırları sayısından büyükse, -1.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter dizini belirtilen satır başına düzenleme denetimi karakterleri sayısıdır.  
  
 Bu üye işlevi yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Daha fazla bilgi için bkz: [EM_LINEINDEX](http://msdn.microsoft.com/library/windows/desktop/bb761611) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#19](../../mfc/reference/codesnippet/cpp/cedit-class_18.cpp)]  
  
##  <a name="linelength"></a>  CEdit::LineLength  
 Bir düzenleme denetimindeki bir satır uzunluğunu alır.  
  
```  
int LineLength(int nLine = -1) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nLine`  
 Bir karakter uzunluğunu alınacak bulunduğu satırı sıfır tabanlı dizini. Varsayılan değer -1'dir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek satırlı düzenleme denetimlerinde dönüş değeri olarak uzunluğudur `TCHAR`düzenleme denetimindeki metnin s.  
  
 Çok satırlı düzenleme denetimleri için dönüş değeri olarak uzunluğudur `TCHAR`tarafından belirtilen satırının s `nLine` parametresi. İçin [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)] metin, uzunluk satırına bayt sayısı; Unicode metin için satır karakter sayısını uzunluğudur. Uzunluk satırın sonuna satır başı karakteri içermez.  
  
 Varsa `nLine` parametresi birden çok denetim karakter sayısı, dönüş değeri sıfır değil.  
  
 Varsa `nLine` parametre -1, dönüş değeri seçili karakterler içeren satırları seçili olmayan karakter sayısı. Örneğin, seçimi satırın sonuna kadar sonraki sekiz karakter arasında bir satırın dördüncü karakter geçerse, dönüş değeri 10'dur. Diğer bir deyişle, üç ilk satır ve yedi sonraki karakter.  
  
 Hakkında daha fazla bilgi için `TCHAR` yazın, bkz: `TCHAR` tablosunda satır [Windows veri türleri](http://msdn.microsoft.com/library/windows/desktop/aa383751).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tarafından desteklenen [EM_LINELENGTH](http://msdn.microsoft.com/library/windows/desktop/bb761613) Windows SDK'ın açıklanan ileti.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::LineIndex](#lineindex).  
  
##  <a name="linescroll"></a>  CEdit::LineScroll  
 Birden çok satırlı metin kaydırma için bu işlevi düzenleme denetimi çağrısı.  
  
```  
void LineScroll(
    int nLines,  
    int nChars = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nLines`  
 Dikey olarak kaydırmak için satır sayısını belirtir.  
  
 `nChars`  
 Yatay kaydırma için karakter konumlarını sayısını belirtir. Düzenleme denetimi ya da varsa bu değer yoksayılır **es_rıght** veya **ES_CENTER** stili.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye işlevi yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Düzenleme denetimi dikey metin düzenleme denetimindeki son satırının kaydırarak değil. Tarafından belirtilen satır sayısı artı geçerli satır varsa `nLines` düzenleme denetimindeki satırları toplam sayısını aşıyor, böylece düzenleme denetimi son satırının düzenleme denetimi pencerenin üstündeki kaydırılan değere ayarlanır.  
  
 `LineScroll` her satırın son karakter yatay kaydırma için kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_LINESCROLL](http://msdn.microsoft.com/library/windows/desktop/bb761615) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::GetFirstVisibleLine](#getfirstvisibleline).  
  
##  <a name="paste"></a>  CEdit::Paste  
 Panodan veri eklemek için bu işlevi çağırmak `CEdit` ekleme noktasına.  
  
```  
void Paste();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Verileri yalnızca Pano veri içeriyorsa eklenir **CF_TEXT** biçimi.  
  
 Daha fazla bilgi için bkz: [WM_PASTE](http://msdn.microsoft.com/library/windows/desktop/ms649028) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#20](../../mfc/reference/codesnippet/cpp/cedit-class_19.cpp)]  
  
##  <a name="posfromchar"></a>  CEdit::PosFromChar  
 Bu içinde belirli bir karakter (sol üst köşesinde) konumunu almak için bu işlevi çağırmak `CEdit` nesnesi.  
  
```  
CPoint PosFromChar(UINT nChar) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nChar`  
 Belirtilen karakter sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından belirtilen bir karakterin sol üst köşesinin koordinatlarını `nChar`.  
  
### <a name="remarks"></a>Açıklamalar  
 Karakter, sıfır tabanlı dizin değerini vererek belirtilir. Varsa `nChar` bu son karakter dizinini değerinden daha büyük `CEdit` nesnesi, dönüş değeri bu karakterin yalnızca son karakter geçmiş koordinatlarını belirtir `CEdit` nesnesi.  
  
> [!NOTE]
>  Bu üye fonksiyonu kullanılabilir başlayarak Windows 95 ve Windows NT 4.0 kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_POSFROMCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761631) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::LineFromChar](#linefromchar).  
  
##  <a name="replacesel"></a>  CEdit::ReplaceSel  
 Bir düzenleme denetimindeki geçerli bölüm tarafından belirtilen metin değiştirmek için bu işlevi çağırmak `lpszNewText`.  
  
```  
void ReplaceSel(LPCTSTR lpszNewText, BOOL bCanUndo = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszNewText`  
 Değiştirme metnini içeren null ile sonlandırılmış bir dize noktalarına.  
  
 `bCanUndo`  
 Bu işlev alınabilecek belirtmek için bu parametrenin değerini ayarlayın **doğru** . Varsayılan değer **FALSE**.  
  
### <a name="remarks"></a>Açıklamalar  
 Yalnızca bir düzenleme denetimindeki metnin bir bölümünü değiştirir. Tüm metni değiştirmek istiyorsanız, kullanmak [CWnd::SetWindowText](cwnd-class.md#setwindowtext) üye işlevi.  
  
 Geçerli seçim ise değiştirme metnini geçerli İmleç konumuna eklenir.  
  
 Daha fazla bilgi için bkz: [EM_REPLACESEL](http://msdn.microsoft.com/library/windows/desktop/bb761633) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::LineIndex](#lineindex).  
  
##  <a name="setcuebanner"></a>  CEdit::SetCueBanner  
 Metin ipucu olarak görüntülenir veya ipucu, Denetim boş olduğunda bir düzen denetim metin ayarlar.  
  
```  
BOOL SetCueBanner(LPCWSTR lpszText);

 
BOOL SetCueBanner(
    LPCWSTR lpszText,   
    BOOL fDrawWhenFocused = FALSE);
```  
  
### <a name="parameters"></a>Parametreler  
 [in] `lpszText`  
 Düzenleme denetimine görüntülenecek ipucu içeren bir dize işaretçi.  
  
 [in] `fDrawWhenFocused`  
 Varsa `false`, kullanıcı düzenleme denetimine tıkladığında ve denetim odağı işaret başlık çizilir değil.  
  
 Varsa `true`, hatta denetimi odağa sahip olduğunda işaret başlık çizilir. Kullanıcı denetim türü başladığında işaret başlık kaybolur.  
  
 Varsayılan değer `false` şeklindedir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [EM_SETCUEBANNER](http://msdn.microsoft.com/library/windows/desktop/bb761639) Windows SDK'ın açıklanan ileti. Daha fazla bilgi için bkz: [Edit_SetCueBannerTextFocused](http://msdn.microsoft.com/library/windows/desktop/bb761703) makrosu.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki örnekte gösterilmiştir [CEdit::SetCueBanner](#setcuebanner) yöntemi.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#2](../../mfc/reference/codesnippet/cpp/cedit-class_20.cpp)]  
  
##  <a name="sethandle"></a>  CEdit::SetHandle  
 Birden çok satırlı düzenleme denetimi tarafından kullanılan yerel belleğe tanıtıcı ayarlamak için bu işlevini çağırın.  
  
```  
void SetHandle(HLOCAL hBuffer);
```  
  
### <a name="parameters"></a>Parametreler  
 *hBuffer*  
 Yerel bellek için bir tanıtıcı içerir. Bu işleme için önceki bir çağrı tarafından oluşturulmuş olması gerekir [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723) Windows işlevini kullanarak **LMEM_MOVEABLE** bayrağı. Bellek null ile sonlandırılan bir karakter dizesi varsayılır. Bu durumda değilse, ayrılan belleğin ilk baytı 0 olarak ayarlanması gerekir.  
  
### <a name="remarks"></a>Açıklamalar  
 Düzenleme denetimi şu anda görüntülenen metnin yerine kendi arabellek ayırma depolamak için bu arabellek sonra kullanır.  
  
 Bu üye işlevi yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Bir uygulamanın yeni bir bellek tanıtıcısı ayarlamadan önce kullanması gereken [GetHandle](#gethandle) tanıtıcı geçerli ara belleğe alma ve o belleğini kullanan boş üye işlevi **LocalFree** Windows işlevi.  
  
 `SetHandle` geri alma arabelleği temizler ( [CanUndo](#canundo) üye işlevi sonra 0 döndürür) ve iç değişikliği bayrağı ( [GetModify](#getmodify) üye işlevi sonra 0 döndürür). Düzenleme denetimi penceresi çizilir.  
  
 Yalnızca iletişim kutusuyla oluşturduysanız bu üye işlevi birden çok satırlı düzenleme denetimindeki bir iletişim kutusunda kullanabilirsiniz **DS_LOCALEDIT** stil bayrağı ayarlanmış.  
  
> [!NOTE]
> **GetHandle** Windows 95/98 ile çalışmaz. Çağırırsanız **GetHandle** Windows 95/98, onu döndürür **NULL**. **GetHandle** 3.51 ve sonraki sürümleri Windows NT altında açıklandığı gibi çalışır.  
  
 Daha fazla bilgi için bkz: [EM_SETHANDLE](http://msdn.microsoft.com/library/windows/desktop/bb761641), [LocalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366723), ve [LocalFree](http://msdn.microsoft.com/library/windows/desktop/aa366730) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#22](../../mfc/reference/codesnippet/cpp/cedit-class_21.cpp)]  
  
##  <a name="sethighlight"></a>  CEdit::SetHighlight  
 Düzen denetimi geçerli görüntülenen metin aralığını bir vurgular.  
  
```  
void SetHighlight(
    int ichStart,   
    int ichEnd);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|[in] `ichStart`|İlk karakter vurgulamak için metin aralığını, sıfır tabanlı dizini.|  
|[in] `ichEnd`|Vurgulamak için metin aralığını son karakter sıfır tabanlı dizini.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem gönderir [EM_SETHILITE](http://msdn.microsoft.com/library/windows/desktop/bb761643) Windows SDK'ın açıklanan ileti.  
  
##  <a name="setlimittext"></a>  CEdit::SetLimitText  
 Bu metin sınırlamak için bu üye işlevini çağırın `CEdit` nesnesi.  
  
```  
void SetLimitText(UINT nMax);
```  
  
### <a name="parameters"></a>Parametreler  
 `nMax`  
 Yeni metin sınırı karakter.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin düzenleme denetimi kabul edebileceği karakter cinsinden maksimum metin sınırıdır.  
  
 Metin sınırı değiştirme yalnızca kullanıcının girebileceği metin kısıtlar. Düzenleme denetimine herhangi bir metin üzerinde hiçbir etkisi zaten var veya düzenleme denetimi tarafından kopyalanmasını metnin uzunluğunu etkilemez [SetWindowText](cwnd-class.md#setwindowtext) üye işlevinde `CWnd`. Bir uygulama kullanıyorsa, `SetWindowText` işlev çağrısında belirtilen bir düzenleme denetimi daha fazla metin yerleştirin `LimitText`, kullanıcının herhangi bir düzenleme denetimi içindeki metnin silebilirsiniz. Ancak, metin sınırı kullanıcı varolan metni yeni metinle değiştirmesini önlemek için geçerli seçim silme sürece metni metin sınırın altına düşmesine neden olur.  
  
 Bu işlev değiştirir [LimitText](#limittext) Win32 içinde.  
  
 Daha fazla bilgi için bkz: [EM_SETLIMITTEXT](http://msdn.microsoft.com/library/windows/desktop/bb761647) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmargins"></a>  CEdit::SetMargins  
 Sol ve sağ kenar boşluklarının bu düzenleme denetimi ayarlamak için bu yöntemi çağırın.  
  
```  
void SetMargins(
    UINT nLeft,  
    UINT nRight);
```  
  
### <a name="parameters"></a>Parametreler  
 *nLeft*  
 Yeni sol kenar piksel cinsinden genişliği.  
  
 *nRight*  
 Yeni sağ kenar piksel cinsinden genişliği.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Bu üye fonksiyonu kullanılabilir başlayarak Windows 95 ve Windows NT 4.0 kullanılabilir.  
  
 Daha fazla bilgi için bkz: [EM_SETMARGINS](http://msdn.microsoft.com/library/windows/desktop/bb761649) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEditView::GetEditCtrl](ceditview-class.md#geteditctrl).  
  
##  <a name="setmodify"></a>  CEdit::SetModify  
 Ayarlayın veya bir düzenleme denetimi için değiştirilmiş bayrağı temizlemek için bu işlevini çağırın.  
  
```  
void SetModify(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bModified`  
 Değerini **TRUE** metin değiştirildiğini gösterir ve değerini **FALSE** onu değiştirilmemiş olduğunu gösterir. Varsayılan olarak, değiştirilmiş bayrağı ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Değiştirilen bayrağı metin düzenleme denetimi içinde değişiklik olup olmadığını gösterir. Kullanıcı metni değiştiğinde otomatik olarak ayarlanır. Değeri ile alınabilir [GetModify](#getmodify) üye işlevi.  
  
 Daha fazla bilgi için bkz: [EM_SETMODIFY](http://msdn.microsoft.com/library/windows/desktop/bb761651) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::GetModify](#getmodify).  
  
##  <a name="setpasswordchar"></a>  CEdit::SetPasswordChar  
 Ayarlamak veya kullanıcı metin yazdığında bir düzen denetiminde gösterilen bir parola karakteri kaldırmak için bu işlevini çağırın.  
  
```  
void SetPasswordChar(TCHAR ch);
```  
  
### <a name="parameters"></a>Parametreler  
 *ch*  
 Kullanıcı tarafından yazılan karakter yerine görüntülenecek karakteri belirtir. Varsa *ch* 0 ise, kullanıcı tarafından yazılan gerçek karakterler görüntülenir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir parola karakteri olarak ayarlandığında, her karakter için kullanıcı türleri bu karakteri görüntülenir.  
  
 Bu üye işlevi düzenleme denetimi birden çok satırlı üzerinde hiçbir etkisi yoktur.  
  
 Zaman `SetPasswordChar` üye işlevi çağrıldığında `CEdit` tarafından belirlenen karakteri kullanarak tüm görünür karakterleri yeniden çizer *ch*.  
  
 Düzenleme denetimi ile oluşturulursa [ES_PASSWORD](styles-used-by-mfc.md#edit-styles) stili, varsayılan parola karakteri olarak ayarlanmış bir yıldız işareti ( **\***). Bu stili kaldırılır `SetPasswordChar` çağrılır *ch* 0 olarak ayarlayın.  
  
 Daha fazla bilgi için bkz: [EM_SETPASSWORDCHAR](http://msdn.microsoft.com/library/windows/desktop/bb761653) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#16](../../mfc/reference/codesnippet/cpp/cedit-class_22.cpp)]  
  
##  <a name="setreadonly"></a>  CEdit::SetReadOnly  
 Bir düzen denetimi salt okunur durumunu ayarlamak için bu işlevi çağırır.  
  
```  
BOOL SetReadOnly(BOOL bReadOnly = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `bReadOnly`  
 Ayarlama veya kaldırma düzenleme denetimi salt okunur durumunu belirtir. Değerini **TRUE** durumunu ayarlar salt okunur; değerini **FALSE** durumunu okuma/yazma olarak ayarlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İşlemi ise sıfır olmayan başarılı ya da 0 ise bir hata oluşur.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli ayarı test ederek bulunabilir [ES_READONLY](styles-used-by-mfc.md#edit-styles) dönüş değerini bayrağı [CWnd::GetStyle](cwnd-class.md#getstyle).  
  
 Daha fazla bilgi için bkz: [EM_SETREADONLY](http://msdn.microsoft.com/library/windows/desktop/bb761655) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#23](../../mfc/reference/codesnippet/cpp/cedit-class_23.cpp)]  
  
##  <a name="setrect"></a>  CEdit::SetRect  
 Belirtilen koordinatları kullanarak dikdörtgen boyutlarını ayarlamak için bu işlevini çağırın.  
  
```  
void SetRect(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret `RECT` yapısı veya `CRect` biçimlendirme dikdörtgen yeni boyutlarını belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu üye, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Kullanım `SetRect` biçimlendirme ayarlamak için birden çok satırlı dikdörtgen düzenleme denetimi. Biçimlendirme dikdörtgen düzenleme denetimi penceresi boyutunu bağımsızdır metin sınırlayan dikdörtgen ' dir. Düzenleme denetimi ilk oluşturulduğunda biçimlendirme dikdörtgen istemci alanını düzenleme denetimi penceresi ile aynıdır. Kullanarak `SetRect` üye işlevi, bir uygulama yapabilir biçimlendirme dikdörtgen düzenleme denetimi penceresi daha büyük veya küçük.  
  
 Kaydırma çubuğu düzenleme denetimi varsa, biçimlendirme dikdörtgen penceresinden daha büyük yapılırsa, metin, Sarmalanan değil, kırpılır. Düzenleme denetimi kenarlık içeriyorsa, biçimlendirme Dikdörtgen kenarlık boyutuyla azalır. Tarafından döndürülen dikdörtgen ayarlarsanız `GetRect` üye işlevi kaldırmalısınız kenarlığın boyutunu dikdörtgene geçirmeden önce `SetRect`.  
  
 Zaman `SetRect` çağrılır, düzenleme denetimi metin de yeniden biçimlendirilen ve görünürler olduğu.  
  
 Daha fazla bilgi için bkz: [EM_SETRECT](http://msdn.microsoft.com/library/windows/desktop/bb761657) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#24](../../mfc/reference/codesnippet/cpp/cedit-class_24.cpp)]  
  
##  <a name="setrectnp"></a>  CEdit::SetRectNP  
 Birden çok satırlı düzenleme denetimi biçimlendirme dikdörtgen ayarlamak için bu işlevini çağırın.  
  
```  
void SetRectNP(LPCRECT lpRect);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpRect`  
 İşaret eden bir `RECT` yapısı veya `CRect` dikdörtgen yeni boyutlarını belirtir nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Biçimlendirme dikdörtgen düzenleme denetimi penceresi boyutunu bağımsızdır metin sınırlayan dikdörtgen ' dir.  
  
 `SetRectNP` aynıdır `SetRect` üye gördüğünü düzenleme denetimi penceresi değil çizilme dışında.  
  
 Düzenleme denetimi ilk oluşturulduğunda biçimlendirme dikdörtgen istemci alanını düzenleme denetimi penceresi ile aynıdır. Çağırarak `SetRectNP` üye işlevi, bir uygulama yapabilir biçimlendirme dikdörtgen düzenleme denetimi penceresi daha büyük veya küçük.  
  
 Kaydırma çubuğu düzenleme denetimi varsa, biçimlendirme dikdörtgen penceresinden daha büyük yapılırsa, metin, Sarmalanan değil, kırpılır.  
  
 Bu üye, yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 Daha fazla bilgi için bkz: [EM_SETRECTNP](http://msdn.microsoft.com/library/windows/desktop/bb761659) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::SetRect](#setrect).  
  
##  <a name="setsel"></a>  CEdit::SetSel  
 Bir düzen denetiminde bir aralıktaki karakterleri seçmek için bu işlevini çağırın.  
  
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
 *dwSelection*  
 Düşük düzey Word'de başlangıç konumu ve yüksek düzey Word'de bitiş konumu belirtir. Düşük düzey word 0'dır ve yüksek düzey word -1 ise, düzenleme denetimindeki tüm metin seçilir. Düşük düzey word -1 ise, herhangi bir geçerli seçimi kaldırılır.  
  
 *bNoScroll*  
 Şapka görünüme kaydırılan olup olmadığını gösterir. Varsa **yanlış**, düzeltme işareti görünüme kaydırılan. Varsa **doğru**, düzeltme işareti görünüme kaydırılan değil.  
  
 `nStartChar`  
 Başlangıç konumu belirtir. Varsa `nStartChar` 0'dır ve `nEndChar` tüm metin düzenleme denetimindeki seçili -1'dir. Varsa `nStartChar` -1 ' dir herhangi bir geçerli seçimi kaldırılır.  
  
 `nEndChar`  
 Bitiş konumu belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [EM_SETSEL](http://msdn.microsoft.com/library/windows/desktop/bb761661) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEdit::GetSel](#getsel).  
  
##  <a name="settabstops"></a>  CEdit::SetTabStops  
 Birden çok satırlı düzenleme denetiminde sekme durakları ayarlamak için bu işlevini çağırın.  
  
```  
void SetTabStops();  
BOOL SetTabStops(const int& cxEachStop);

 
BOOL SetTabStops(
    int nTabStops,  
    LPINT rgTabStops);
```  
  
### <a name="parameters"></a>Parametreler  
 `cxEachStop`  
 Sekme durakları adresindeki ayarlanacak belirtir her `cxEachStop` iletişim kutusu birimleri.  
  
 `nTabStops`  
 Sekme durakları içinde yer alan sayısını belirtir `rgTabStops`. Bu sayı 1'den büyük olmalıdır.  
  
 `rgTabStops`  
 Bir dizi noktalarına sekmesini belirtme imzasız tamsayılar iletişim kutusu birimleri durdurur. Yatay ve dikey uzaklık bir iletişim birimdir. Bir yatay iletişim biriminin geçerli iletişim temel genişliği biriminin bir-dördüncü için eşit ve 1 dikey iletişim birim geçerli iletişim temel yükseklik biriminin bir-sekizinci için eşit olur. İletişim kutusu temel birimleri geçerli sistem yazı tipi genişliği ve yüksekliği göre hesaplanır. **GetDialogBaseUnits** Windows işlevi temel birimleri geçerli iletişim piksel cinsinden döndürür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sekmeleri ayarlarsanız sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Metin birden çok satırlı düzenleme denetimine kopyalandığında, herhangi bir metin sekmesini karaktere kadar sonraki sekme durağı oluşturulacak alanı neden olur.  
  
 Sekme durakları 32 iletişim kutusu birimleri varsayılan boyutunu ayarlamak için bu üye işlevi parametresiz sürümü çağırın. Sürümüyle 32 dışındaki bir boyuta sekme durakları ayarlama çağrısı `cxEachStop` parametresi. Bir dizi boyutları için sekme durakları ayarlamak için iki parametre ile sürümü kullanın.  
  
 Bu üye işlevi yalnızca birden çok satırlı düzenleme denetimleri tarafından işlenir.  
  
 `SetTabStops` otomatik olarak düzenleme penceresi çizmez. Düzenleme denetimi zaten metinde sekme durakları değiştirirseniz, çağrı [CWnd::InvalidateRect](cwnd-class.md#invalidaterect) düzenleme penceresini yeniden boyutlandırmaya için.  
  
 Daha fazla bilgi için bkz: [EM_SETTABSTOPS](http://msdn.microsoft.com/library/windows/desktop/bb761663) ve [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CEditView::SetTabStops](ceditview-class.md#settabstops).  
  
##  <a name="showballoontip"></a>  CEdit::ShowBalloonTip  
 Geçerli düzenleme denetimi ile ilişkili bir balon ipucu görüntüler.  
  
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
|[in] `pEditBalloonTip`|İşaretçi bir [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) balon ipucu açıklar yapısı.|  
|[in] `lpszTitle`|Balon ipucu başlığını içeren bir UNICODE dizesi işaretçi.|  
|[in] `lpszText`|Balon ipucu metnini içeren bir UNICODE dizesi işaretçi.|  
|[in] `ttiIcon`|Bir `INT` balon ipucu ile ilişkilendirilecek simgesi türünü belirtir. Varsayılan değer `TTI_NONE` şeklindedir. Daha fazla bilgi için bkz: `ttiIcon` üyesi [EDITBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb775466) yapısı.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true` Bu yöntem başarılı olursa; Aksi takdirde `false`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev gönderir [EM_SHOWBALLOONTIP](http://msdn.microsoft.com/library/windows/desktop/bb761668) Windows SDK'ın açıklanan ileti. Daha fazla bilgi için bkz: [Edit_ShowBalloonTip](http://msdn.microsoft.com/library/windows/desktop/bb761707) makrosu.  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir değişken tanımlar `m_cedit`, yani geçerli düzenleme denetimi erişmek için kullanılır. Bu değişken, sonraki örnekte kullanılır.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#1](../../mfc/reference/codesnippet/cpp/cedit-class_25.h)]  
  
### <a name="example"></a>Örnek  
 Aşağıdaki kod örneği, bir düzenleme denetimi için balon ipucu görüntüler. [CEdit::ShowBalloonTip](#showballoontip) yöntemi bir başlık ve balon ipucu metnini belirtir.  
  
 [!code-cpp[NVC_MFC_CEdit_s1#3](../../mfc/reference/codesnippet/cpp/cedit-class_26.cpp)]  
  
##  <a name="undo"></a>  CEdit::Undo  
 Son düzenleme denetimi işlemi geri almak için bu işlevini çağırın.  
  
```  
BOOL Undo();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek satırlı düzenleme denetimi için dönüş değeri her zaman sıfır olmayan bir değer. Birden çok satırlı düzenleme denetimi için dönüş değerini geri alma işlemi başarılıysa sıfır olmayan veya geri alma işlemi başarısız olursa 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir geri alma işlemi geri alınabilir. Örneğin, ilk çağrıda silinen metinle geri yükleyebilirsiniz **geri**. Müdahalede bulunan hiçbir düzenleme işlemi var olduğu sürece ikinci çağrı metinle yeniden kaldırabilirsiniz **geri**.  
  
 Daha fazla bilgi için bkz: [EM_UNDO](http://msdn.microsoft.com/library/windows/desktop/bb761670) Windows SDK'sındaki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFC_CEdit#25](../../mfc/reference/codesnippet/cpp/cedit-class_27.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CALCDRIV](../../visual-cpp-samples.md)   
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CWnd sınıfı](cwnd-class.md)   
 [CButton sınıfı](cbutton-class.md)   
 [CComboBox sınıfı](ccombobox-class.md)   
 [CListBox sınıfı](clistbox-class.md)   
 [CScrollBar sınıfı](cscrollbar-class.md)   
 [CStatic sınıfı](cstatic-class.md)   
 [CDialog Sınıfı](cdialog-class.md)
