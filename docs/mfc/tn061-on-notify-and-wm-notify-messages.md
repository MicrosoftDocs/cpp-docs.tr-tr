---
title: 'TN061: On_notıfy ve wm_notıfy iletileri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_NOTIFY
- WM_NOTIFY
dev_langs:
- C++
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4afa05fa8bf21b6e324e9ac14a1b092933a99d55
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954428"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY ve WM_NOTIFY İletileri
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu teknik Not Yeni wm_notıfy iletisi arka plan bilgileri sağlar ve MFC uygulamanız wm_notıfy iletileri işleme önerilen (ve en yaygın) yolu açıklar.  
  
 **Windows bildirim iletilerini 3.x**  
  
 Windows 3.x, fare tıklamaları gibi olayların üst denetimleri bildir değişiklikleri içerik ve seçim ve denetim arka plan boyama üst bir ileti göndererek. Basit bildirimleri (örneğin, BN_CLICKED) bildirim koduyla özel WM_COMMAND iletileri olarak gönderilir ve içine paketlenmiş kimliği kontrol *wParam* ve denetimin işleyicisi *lParam*. Bu yana unutmayın *wParam* ve *lParam* olan herhangi bir ek veriyi geçirmek için bir yolu yoktur tam — bu iletileri yalnızca basit bildirim olabilir. Örneğin, BN_CLICKED bildiriminde düğme tıklatıldığında fare imlecini konumu hakkında bilgi göndermek için yolu yoktur.  
  
 3.x gereken Windows denetimlerinde ek verileri içeren bir bildirim iletisi gönderdiğinizde, özel amaçlı iletileri WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ dahil olmak üzere, çeşitli kullanırlar. CHARTOITEM, WM_VKEYTOITEM ve benzeri. Bu iletiler, bunları gönderilen denetim geri yansıtılır. Daha fazla bilgi için bkz: [TN062: Windows denetimleri için ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
 **Win32 Bildirim iletileri**  
  
 Windows 3.1 var denetimleri için Win32 API kullanılan bildirim iletilerinin çoğu Windows kullanan 3.x. Ancak, Win32 de Gelişmiş, karmaşık denetimleri çeşitli Windows desteklenenler ekler 3.x. Genellikle, bu denetimlerin ek verilerle kendi bildirim iletilerini göndermek gerekir. Yeni bir ekleme yerine **WM_\***  ek veriler, Win32 API tasarımcıları gerektiren her bir yeni bildirim yalnızca bir ileti, ek veriler herhangi bir sayıdaki geçirebilirsiniz wm_notıfy eklemek seçtiğiniz için ileti bir standartlaştırılmış bir şekilde.  
  
 Wm_notıfy iletileri ileti gönderme denetiminin Kimliğini içeren *wParam* ve bir yapı için bir işaretçi *lParam*. Bu yapı olan bir **NMHDR** yapısı veya sahip bazı büyük yapısı bir **NMHDR** yapısı ilk üye olarak. Bu yana unutmayın **NMHDR** üye ilk, bu yapısına yönelik işaretçinin ya da bir işaretçi olarak kullanılabilir bir **NMHDR** veya cast nasıl bağlı olarak büyük yapısına yönelik işaretçinin olarak.  
  
 Çoğu durumda, daha büyük bir yapı işaretçi işaret edecek ve kullandığınız zaman cast gerekir. Ortak bildirimleri gibi yalnızca birkaç bildirim olarak (adları başlayan ile **NM_**) ve araç ipucu denetimin TTN_SHOW ve TTN_POP bildirimleri bir **NMHDR** gerçekten kullanılan yapısı.  
  
 **NMHDR** yapısı veya ilk üye tanıtıcısı ve ileti ve (örneğin, TTN_SHOW) bildirim kodu gönderme denetiminin Kimliğini içerir. Biçimi **NMHDR** yapısı aşağıda gösterilmektedir:  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 Bir TTN_SHOW ileti **kod** üye, TTN_SHOW için ayarlanmış olması.  
  
 Çoğu bildirimleri bir işaretçi içeren daha büyük bir yapının geçirmek bir **NMHDR** yapısı ilk üye olarak. Örneğin, bir liste görünümü denetiminde bir tuşuna basıldığında, gönderilen liste görünümü denetimin LVN_KEYDOWN bildirim iletisi tarafından kullanılan yapısı göz önünde bulundurun. İşaretçi işaret bir **LV_KEYDOWN** aşağıda gösterildiği gibi tanımlanan yapısı:  
  
```  
typedef struct tagLV_KEYDOWN {  
    NMHDR hdr;     
    WORD wVKey;    
    UINT flags;    
} LV_KEYDOWN;  
```  
  
 Bu yana unutmayın **NMHDR** üye bu yapısı içinde ilk, bildirim iletisinde geçirilen işaretçi için bir işaretçi atanabilecek bir **NMHDR** veya gösteren bir işaretçi bir **LV_KEYDOWN** .  
  
 **Bildirimleri ortak tüm yeni Windows denetimleri için**  
  
 Bazı bildirimler tüm yeni Windows denetimleri için yaygındır. Bu bildirimler geçirmek için bir işaretçi bir **NMHDR** yapısı.  
  
|Bildirim kodu|Çünkü gönderilen|  
|-----------------------|------------------|  
|NM_CLICK|Kullanıcı denetimi sol fare düğmesini tıklattıktan|  
|NM_DBLCLK|Kullanıcı tıklatıldığında sol fare düğmesi denetimi|  
|NM_RCLICK|Kullanıcı denetimi sağ fare düğmesini tıklattıktan|  
|NM_RDBLCLK|Kullanıcı tıklatıldığında farenin sağ düğmesiyle denetimi|  
|NM_RETURN|Denetim odağı giriş sırada ENTER tuşuna basıldığında kullanıcı|  
|NM_SETFOCUS|Giriş odağı denetimi verildi|  
|NM_KILLFOCUS|Denetim giriş odağını kaybetmiş|  
|NM_OUTOFMEMORY|Çünkü kullanılabilir yeterli bellek yoktu denetim bir işlem tamamlanamadı|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> On_notıfy: MFC uygulamalarında wm_notıfy iletileri işleme  
 İşlev `CWnd::OnNotify` bildirim iletilerini işleme. Varsayılan uygulama çağırmak bildirim işleyicileri için ileti eşlemesi denetler. Genel olarak, size geçersiz `OnNotify`. Bunun yerine, bir işleyici işlevi sağlar ve bu işleyici için bir ileti eşleme girişi sahibi pencerenin sınıfı için ileti eşlemesi ekleyin.  
  
 ClassWizard özellik sayfasını, aracılığıyla ClassWizard on_notıfy ileti eşleme girişi oluşturmak ve bir iskelet işleyici işlevi ile sağlayın. Bu işlemi kolaylaştırmak için ClassWizard kullanma hakkında daha fazla bilgi için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
 On_notıfy iletisi eşleme makrosu sözdizimi aşağıdaki gibidir:  
  
```  
 
ON_NOTIFY(
wNotifyCode  ,  
id  ,
    memberFxn)  
 
```  
  
 Burada italik parametreleri ile değiştirilir:  
  
 *wNotifyCode*  
 LVN_KEYDOWN gibi ele bildirim iletisi kodu.  
  
 *id*  
 Bildirim gönderilen denetim alt tanımlayıcısı.  
  
 *memberFxn*  
 Bu bildirim gönderildiğinde çağrılacak üye işlevi.  
  
 Üye işlevi ile aşağıdaki prototip bildirilmesi gerekir:  
  
```  
 
afx_msg void  
memberFxn  
(NMHDR* 
pNotifyStruct  , LRESULT* result);

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada italik Parametreler şunlardır:  
  
 *pNotifyStruct*  
 Yukarıdaki bölümde açıklandığı gibi bildirim yapısı için bir işaretçi.  
  
 *Sonuç*  
 Sonuç kodu için bir işaretçi dönmek önce ayarlamanız.  
  
## <a name="example"></a>Örnek  
 Üye işlevini istediğinizi belirtmek için `OnKeydownList1` LVN_KEYDOWN iletileri işlemek için `CListCtrl` özelliği kimliği `IDC_LIST1`, aşağıdaki ileti haritanızı eklemek için ClassWizard kullanırsınız:  
  
```  
ON_NOTIFY(LVN_KEYDOWN,
    IDC_LIST1,
    OnKeydownList1)  
```  
  
 Yukarıdaki örnekte, ClassWizard tarafından sağlanan işlevi şu şekildedir:  
  
```  
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)  
{  
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR; *// TODO: Add your control notification handler *//       code here  
 
 *pResult = 0;  
}  
```  
  
 Not ClassWizard uygun türde bir işaretçi otomatik olarak sağlar. Bildirim yapısı aracılığıyla erişebilirsiniz *pNMHDR* veya *pLVKeyDow*.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE  
 Denetimleri kümesini için aynı wm_notıfy iletisi işleyemedi gerekiyorsa, on_notıfy yerine on_notıfy_range kullanabilirsiniz. Örneğin, belirli bir bildirim iletisi için aynı eylemi gerçekleştirmek istediğiniz düğmeler kümesi olabilir.  
  
 On_notıfy_range kullandığınızda, bildirim iletisini başına belirtme ve alt tanımlayıcıları aralığın bitiş işlemek üzere alt tanımlayıcıların bitişik bir aralığı belirtin.  
  
 ClassWizard on_notıfy_range işlemez; kullanmak için ileti eşlemesi kendiniz düzenlemeniz gerekir.  
  
 On_notıfy_range işlev prototipi ve ileti eşleme girişi aşağıdaki gibidir:  
  
```  
 
ON_NOTIFY_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 Burada italik parametreleri ile değiştirilir:  
  
 *wNotifyCode*  
 LVN_KEYDOWN gibi ele bildirim iletisi kodu.  
  
 *id*  
 Tanımlayıcıları bitişik aralığındaki ilk tanımlayıcısı.  
  
 *idLast*  
 Tanımlayıcıların bitişik aralıktaki son tanımlayıcısı.  
  
 *memberFxn*  
 Bu bildirim gönderildiğinde çağrılacak üye işlevi.  
  
 Üye işlevi ile aşağıdaki prototip bildirilmesi gerekir:  
  
```  
 
afx_msg void  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Burada italik Parametreler şunlardır:  
  
 *id*  
 Bildirimi tarafından gönderilen denetim alt tanımlayıcısı.  
  
 *pNotifyStruct*  
 Yukarıda açıklandığı gibi bildirim yapısı için bir işaretçi.  
  
 *Sonuç*  
 Sonuç kodu için bir işaretçi dönmek önce ayarlamanız.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE  
 Bir iletiyi işlemek için yönlendirme bildirim birden fazla nesne istiyorsanız, on_notıfy (veya on_notıfy_range) yerine on_notıfy_ex (veya on_notıfy_ex_range) kullanabilirsiniz. Arasındaki tek fark **EX** sürümü ve normal sürümü olan üye fonksiyonu için adlı **EX** sürümü döndürür bir **BOOL** belirten olsun veya olmasın ileti işleme devam etmelidir. Döndürme **FALSE** bu işlevden aynı iletiyi birden fazla nesnesindeki işlemenize olanak sağlar.  
  
 ClassWizard on_notıfy_ex veya on_notıfy_ex_range işlemez; bunlardan birini kullanmak istiyorsanız, ileti eşlemesi kendiniz düzenlemeniz gerekir.  
  
 İleti eşleme girişi ve işlev prototipi on_notıfy_ex ve on_notıfy_ex_range için aşağıdaki gibidir. Parametrelerin anlamları olmayan aynıdır**EX** sürümleri.  
  
```  
 
ON_NOTIFY_EX(
nCode  ,  
id  ,
    memberFxn) ON_NOTIFY_EX_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 Her ikisi için yukarıdaki prototip aynıdır:  
  
```  
 
afx_msg BOOL  
memberFxn  
(UINT   
id  ,
    NMHDR* 
pNotifyStruct  ,
    LRESULT* result);

 
```  
  
## <a name="remarks"></a>Açıklamalar  
 Her iki durumda da *kimliği* bildirimi tarafından gönderilen denetim alt tanıtıcısı tutar.  
  
 İşlevinizi döndürmesi gerekir **TRUE** bildirim iletisi tamamen işlendi, veya **FALSE** komut yönlendirme içinde başka nesneler iletiyi işlemek için bir fırsat olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

