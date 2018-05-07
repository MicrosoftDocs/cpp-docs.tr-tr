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
ms.openlocfilehash: dc8e49ec04e1932c7bac4faa9a8737b480d8ef54
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY ve WM_NOTIFY İletileri
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu teknik Not Yeni arka plan bilgileri sağlar **wm_notıfy** iletisi ve işleme önerilen (ve en yaygın) biçimini tanımlar **wm_notıfy** MFC uygulamanızda iletileri.  
  
 **Windows bildirim iletilerini 3.x**  
  
 Windows 3.x, fare tıklamaları gibi olayların üst denetimleri bildir değişiklikleri içerik ve seçim ve denetim arka plan boyama üst bir ileti göndererek. Basit bildirimler gibi özel gönderilir **WM_COMMAND** iletilerle bildirim kodu (gibi **BN_CLICKED**) ve kimliği içine paketlenmiş denetim `wParam` ve denetimintanıtıcısı`lParam`. Bu yana unutmayın `wParam` ve `lParam` olan herhangi bir ek veriyi geçirmek için bir yolu yoktur tam — bu iletileri yalnızca basit bildirim olabilir. Örneğin, **BN_CLICKED** bildirim, düğme tıklatıldığında fare imlecini konumu hakkında bilgi göndermek için bir yolu yoktur.  
  
 Ek verileri içeren bir bildirim iletisi göndermek için Windows 3.x gerek denetimlerinde, kullandığında dahil olmak üzere, özel amaçlı iletiler çeşitli `WM_CTLCOLOR`, `WM_VSCROLL`, `WM_HSCROLL`, `WM_DRAWITEM`, `WM_MEASUREITEM`, `WM_COMPAREITEM`, `WM_DELETEITEM`, `WM_CHARTOITEM`, `WM_VKEYTOITEM`ve benzeri. Bu iletiler, bunları gönderilen denetim geri yansıtılır. Daha fazla bilgi için bkz: [TN062: Windows denetimleri için ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).  
  
 **Win32 Bildirim iletileri**  
  
 Windows 3.1 var denetimleri için Win32 API kullanılan bildirim iletilerinin çoğu Windows kullanan 3.x. Ancak, Win32 de Gelişmiş, karmaşık denetimleri çeşitli Windows desteklenenler ekler 3.x. Genellikle, bu denetimlerin ek verilerle kendi bildirim iletilerini göndermek gerekir. Yeni bir ekleme yerine **WM_\***  ek veriler, Win32 API tasarımcıları gerektiren her bir yeni bildirim yalnızca tek bir ileti eklemek seçtiğiniz için ileti **wm_notıfy**, hangi iletebilir herhangi standartlaştırılmış bir şekilde ek veri miktarı.  
  
 **Wm_notıfy** iletileri ileti gönderme denetiminin Kimliğini içeren `wParam` ve bir yapı için bir işaretçi `lParam`. Bu yapı olan bir **NMHDR** yapısı veya sahip bazı büyük yapısı bir **NMHDR** yapısı ilk üye olarak. Bu yana unutmayın **NMHDR** üye ilk, bu yapısına yönelik işaretçinin ya da bir işaretçi olarak kullanılabilir bir **NMHDR** veya cast nasıl bağlı olarak büyük yapısına yönelik işaretçinin olarak.  
  
 Çoğu durumda, daha büyük bir yapı işaretçi işaret edecek ve kullandığınız zaman cast gerekir. Ortak bildirimleri gibi yalnızca birkaç bildirim olarak (adları başlayan ile **NM_**) ve araç ipucu denetimin **TTN_SHOW** ve **TTN_POP** bildirimleri olan bir **NMHDR** gerçekten kullanılan yapısı.  
  
 **NMHDR** yapısı veya ilk üye tanıtıcısı ve ileti ve bildirim kodu gönderme denetiminin Kimliğini içerir (gibi **TTN_SHOW**). Biçimi **NMHDR** yapısı aşağıda gösterilmektedir:  
  
```  
typedef struct tagNMHDR {  
    HWND hwndFrom;  
    UINT idFrom;  
    UINT code;  
} NMHDR;  
```  
  
 İçin bir **TTN_SHOW** ileti **kod** üye kümesine **TTN_SHOW**.  
  
 Çoğu bildirimleri bir işaretçi içeren daha büyük bir yapının geçirmek bir **NMHDR** yapısı ilk üye olarak. Örneğin, liste görünümü denetimin tarafından kullanılan yapısı göz önünde bulundurun **LVN_KEYDOWN** liste görünümü denetimi bir tuşuna basıldığında, gönderilen bildirim iletisi. İşaretçi işaret bir **LV_KEYDOWN** aşağıda gösterildiği gibi tanımlanan yapısı:  
  
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
|**NM_CLICK**|Kullanıcı denetimi sol fare düğmesini tıklattıktan|  
|**NM_DBLCLK**|Kullanıcı tıklatıldığında sol fare düğmesi denetimi|  
|**NM_RCLICK**|Kullanıcı denetimi sağ fare düğmesini tıklattıktan|  
|**NM_RDBLCLK**|Kullanıcı tıklatıldığında farenin sağ düğmesiyle denetimi|  
|**NM_RETURN**|Denetim odağı giriş sırada ENTER tuşuna basıldığında kullanıcı|  
|**NM_SETFOCUS**|Giriş odağı denetimi verildi|  
|**NM_KILLFOCUS**|Denetim giriş odağını kaybetmiş|  
|**NM_OUTOFMEMORY**|Çünkü kullanılabilir yeterli bellek yoktu denetim bir işlem tamamlanamadı|  
  
##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> On_notıfy: MFC uygulamalarında wm_notıfy iletileri işleme  
 İşlev `CWnd::OnNotify` bildirim iletilerini işleme. Varsayılan uygulama çağırmak bildirim işleyicileri için ileti eşlemesi denetler. Genel olarak, size geçersiz `OnNotify`. Bunun yerine, bir işleyici işlevi sağlar ve bu işleyici için bir ileti eşleme girişi sahibi pencerenin sınıfı için ileti eşlemesi ekleyin.  
  
 ClassWizard, ClassWizard özellik sayfası oluşturabilirsiniz `ON_NOTIFY` ileti eşleme girişi ve bir iskelet işleyici işlevi ile sağlayın. Bu işlemi kolaylaştırmak için ClassWizard kullanma hakkında daha fazla bilgi için bkz: [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).  
  
 `ON_NOTIFY` İleti eşleme makro aşağıdaki sözdizimi vardır:  
  
```  
 
ON_NOTIFY(
wNotifyCode  ,  
id  ,
    memberFxn)  
 
```  
  
 Burada italik parametreleri ile değiştirilir:  
  
 `wNotifyCode`  
 Bildirim iletisi, gibi ele alınması için kod **LVN_KEYDOWN**.  
  
 `id`  
 Bildirim gönderilen denetim alt tanımlayıcısı.  
  
 `memberFxn`  
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
  
 `pNotifyStruct`  
 Yukarıdaki bölümde açıklandığı gibi bildirim yapısı için bir işaretçi.  
  
 *Sonuç*  
 Sonuç kodu için bir işaretçi dönmek önce ayarlamanız.  
  
## <a name="example"></a>Örnek  
 Üye işlevini istediğinizi belirtmek için `OnKeydownList1` işlemek için **LVN_KEYDOWN** gelen iletileri `CListCtrl` özelliği kimliği `IDC_LIST1`, aşağıdaki ileti haritanızı eklemek için ClassWizard kullanırsınız:  
  
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
  
 Not ClassWizard uygun türde bir işaretçi otomatik olarak sağlar. Bildirim yapısı aracılığıyla erişebilirsiniz `pNMHDR` veya `pLVKeyDow`.  
  
##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE  
 Aynı işlemi gerekiyorsa **wm_notıfy** ileti denetimleri kümesini için kullandığınız **on_notıfy_range** yerine `ON_NOTIFY`. Örneğin, belirli bir bildirim iletisi için aynı eylemi gerçekleştirmek istediğiniz düğmeler kümesi olabilir.  
  
 Kullandığınızda **on_notıfy_range**, bildirim iletisini başına belirtme ve alt tanımlayıcıları aralığın bitiş işlemek üzere alt tanımlayıcıların bitişik bir aralık belirtin.  
  
 ClassWizard işlemiyor **on_notıfy_range**; bunu kullanmak için ileti eşlemesi kendiniz düzenlemeniz gerekir.  
  
 İleti eşleme girişi ve işlev prototipi **on_notıfy_range** aşağıdaki gibidir:  
  
```  
 
ON_NOTIFY_RANGE(
wNotifyCode  ,   
id  ,   
idLast  ,
    memberFxn)  
 
```  
  
 Burada italik parametreleri ile değiştirilir:  
  
 `wNotifyCode`  
 Bildirim iletisi, gibi ele alınması için kod **LVN_KEYDOWN**.  
  
 `id`  
 Tanımlayıcıları bitişik aralığındaki ilk tanımlayıcısı.  
  
 `idLast`  
 Tanımlayıcıların bitişik aralıktaki son tanımlayıcısı.  
  
 `memberFxn`  
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
  
 `id`  
 Bildirimi tarafından gönderilen denetim alt tanımlayıcısı.  
  
 `pNotifyStruct`  
 Yukarıda açıklandığı gibi bildirim yapısı için bir işaretçi.  
  
 *Sonuç*  
 Sonuç kodu için bir işaretçi dönmek önce ayarlamanız.  
  
##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE  
 Bildirim birden fazla nesne istiyorsanız yönlendirme bir ileti işleme, kullanabileceğiniz **on_notıfy_ex** (veya **on_notıfy_ex_range**) yerine `ON_NOTIFY` (veya **on_notıfy_range** ). Arasındaki tek fark **EX** sürümü ve normal sürümü olan üye fonksiyonu için adlı **EX** sürümü döndürür bir **BOOL** belirten olsun veya olmasın ileti işleme devam etmelidir. Döndürme **FALSE** bu işlevden aynı iletiyi birden fazla nesnesindeki işlemenize olanak sağlar.  
  
 ClassWizard işlemiyor **on_notıfy_ex** veya **on_notıfy_ex_range**; bunlardan birini, kullanmak istiyorsanız, ileti eşlemesi kendiniz düzenlemeniz gerekir.  
  
 İleti eşleme girişi ve işlev prototipi **on_notıfy_ex** ve **on_notıfy_ex_range** aşağıdaki gibidir. Parametrelerin anlamları olmayan aynıdır**EX** sürümleri.  
  
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
 Her iki durumda da `id` bildirimi tarafından gönderilen denetim alt tanıtıcısı tutar.  
  
 İşlevinizi döndürmesi gerekir **TRUE** bildirim iletisi tamamen işlendi, veya **FALSE** komut yönlendirme içinde başka nesneler iletiyi işlemek için bir fırsat olması gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

