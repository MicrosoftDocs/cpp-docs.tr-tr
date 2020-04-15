---
title: 'TN061: ON_NOTIFY ve WM_NOTIFY İletileri'
ms.date: 06/28/2018
helpviewer_keywords:
- ON_NOTIFY_EX message [MFC]
- TN061
- ON_NOTIFY message [MFC]
- ON_NOTIFY_EX_RANGE message [MFC]
- ON_NOTIFY_RANGE message [MFC]
- notification messages
- WM_NOTIFY message
ms.assetid: 04a96dde-7049-41df-9954-ad7bb5587caf
ms.openlocfilehash: 845558dad6b9f6e820c759cb83fce2c6cbceaa0c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366592"
---
# <a name="tn061-on_notify-and-wm_notify-messages"></a>TN061: ON_NOTIFY ve WM_NOTIFY İletileri

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu teknik not, yeni WM_NOTIFY iletisi hakkında arka plan bilgileri sağlar ve MFC uygulamanızda WM_NOTIFY iletileri işlemenin önerilen (ve en yaygın) yolunu açıklar.

**Windows 3.x'te Bildirim İletileri**

Windows 3.x'te denetimler, ebeveynlerine fare tıklamaları, içerik ve seçim değişiklikleri gibi olayları bildirir ve üst öğeye ileti göndererek arka plan boyamasını denetler. Basit bildirimler özel WM_COMMAND iletileri olarak gönderilir, bildirim kodu (BN_CLICKED gibi) ve kontrol kimliği *wParam* ve *lParam'da*kontrol tutamacına paketlenmiştir. *WParam* ve *lParam* dolu olduğundan, herhangi bir ek veri aktarmak için bir yol yoktur unutmayın - bu iletiler sadece basit bir bildirim olabilir. Örneğin, BN_CLICKED bildiriminde, düğme tıklatıldığında fare imlecinin konumu hakkında bilgi göndermenin bir yolu yoktur.

Windows 3.x'teki denetimlerin ek veri içeren bir bildirim iletisi göndermesi gerektiğinde, WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_CHARTOITEM, WM_VKEYTOITEM ve benzeri dahil olmak üzere çeşitli özel amaçlı iletiler kullanırlar. Bu iletiler, gönderen denetime geri yansıtılabilir. Daha fazla bilgi için [Bkz. TN062: Windows Denetimleri için İleti Yansıması.](../mfc/tn062-message-reflection-for-windows-controls.md)

**Win32'deki Bildirim Mesajları**

Windows 3.1'de bulunan denetimler için Win32 API, Windows 3.x'te kullanılan bildirim iletilerinin çoğunu kullanır. Ancak Win32, Windows 3.x'te desteklenendenetimlere bir dizi karmaşık denetim de ekler. Sık sık, bu denetimlerin bildirim iletileriyle ek veri göndermesi gerekir. Win32 API tasarımcıları, ek veri gerektiren her yeni bildirim için yeni bir **WM_** <strong>\*</strong> iletisi eklemek yerine, standart laştırılmış bir şekilde herhangi bir miktarda ek veri geçirebilen yalnızca bir ileti WM_NOTIFY eklemeyi tercih etti.

WM_NOTIFY iletileri *wParam* iletisi gönderen denetim kimliği ve *lParam*bir yapıya bir işaretçi içerir. Bu yapı, ilk üyesi olarak NMHDR **yapısına** sahip bir **NMHDR** yapısı veya daha büyük bir yapıdır. **NMHDR** üyesi ilk olduğundan, bu yapıya işaretçi bir **NMHDR** için bir işaretçi veya nasıl döküm bağlı olarak daha büyük yapı için bir işaretçi olarak kullanılabilir unutmayın.

Çoğu durumda, işaretçi daha büyük bir yapıyı işaret eder ve kullanırken onu dökmeniz gerekir. Ortak bildirimler (adları **NM_** ile başlayan) ve araç ipucu denetiminin TTN_SHOW ve TTN_POP bildirimleri gibi yalnızca birkaç bildirimde, gerçekte kullanılan bir **NMHDR** yapısıdır.

**NMHDR** yapısı veya ilk üye, iletiyi gönderen denetimin tutamacını ve kimliğini ve bildirim kodunu (TTN_SHOW gibi) içerir. **NMHDR** yapısının biçimi aşağıda gösterilmiştir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

Bir TTN_SHOW iletiiçin **kod** üyesi TTN_SHOW olarak ayarlanır.

Çoğu bildirim, ilk üyesi olarak **NMHDR** yapısı içeren daha büyük bir yapıya işaretçi geçirir. Örneğin, liste görünümü denetiminde bir tuşa basıldığında gönderilen liste görünümü denetiminin LVN_KEYDOWN bildirim iletisi tarafından kullanılan yapıyı göz önünde bulundurun. İşaretçi, aşağıda gösterildiği gibi tanımlanan **bir LV_KEYDOWN** yapıya işaret eder:

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

**NMHDR** üyesi bu yapıda ilk olduğundan, bildirim iletisinde geçirilen işaretçi bir **NMHDR** işaretçisi veya bir **LV_KEYDOWN**işaretçisi olarak atanabilir.

**Tüm Yeni Windows Denetimlerinde Ortak Bildirimler**

Bazı bildirimler tüm yeni Windows denetimleri için ortaktır. Bu bildirimler bir **NMHDR** yapısına bir işaretçi geçer.

|Bildirim kodu|Çünkü gönderildi|
|-----------------------|------------------|
|NM_CLICK|Kullanıcı denetimde sol fare düğmesini tıklattı|
|NM_DBLCLK|Kullanıcı denetimde sol fare düğmesine çift tıkladı|
|NM_RCLICK|Kullanıcı denetimde sağ fare düğmesini tıklattı|
|NM_RDBLCLK|Kullanıcı denetimde sağ fare düğmesine çift tıkladı|
|NM_RETURN|Denetim giriş odağı varken kullanıcı ENTER tuşuna bastı|
|NM_SETFOCUS|Kontrol girdi odağı verilmiştir|
|NM_KILLFOCUS|Denetim giriş odağı kaybetti|
|NM_OUTOFMEMORY|Yeterli bellek olmadığı için denetim işlemi tamamlayamadı|

## <a name="on_notify-handling-wm_notify-messages-in-mfc-applications"></a><a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a>ON_NOTIFY: MFC Uygulamalarında WM_NOTIFY İletileri Işleme

İşlev `CWnd::OnNotify` bildirim iletilerini işler. Varsayılan uygulaması, bildirim işleyicilerinin araması için ileti eşlemi denetimlerini denetler. Genel olarak, geçersiz kılmazsınız. `OnNotify` Bunun yerine, bir işleyici işlevi sağlar ve bu işleyici için bir ileti eşlemi ekleyin sahibi pencerenizin sınıfının ileti eşlemi.

ClassWizard, ClassWizard özellik sayfası aracılığıyla, ON_NOTIFY ileti-eş-eşgirişi oluşturabilir ve size bir iskelet işleyicisi işlevi sağlayabilir. Bunu kolaylaştırmak için ClassWizard'ı kullanma hakkında daha fazla bilgi için [Bkz.](../mfc/reference/mapping-messages-to-functions.md)

ON_NOTIFY ileti eşlemi makrosu aşağıdaki sözdizimine sahiptir:

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*<br/>
LVN_KEYDOWN gibi işlenecek bildirim iletisinin kodu.

*Kimliği*<br/>
Bildirimin gönderildiği denetimin alt tanımlayıcısı.

*üyeFxn*<br/>
Bu bildirim gönderildiğinde çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple birlikte bildirilmelidir:

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*pNotifyStruct*<br/>
Yukarıdaki bölümde açıklandığı gibi bildirim yapısıiçin bir işaretçi.

*Sonuç*<br/>
Dönmeden önce ayarladığınız sonuç koduiçin bir işaretçi.

## <a name="example"></a>Örnek

Üye işlevin `OnKeydownList1` `CListCtrl` kimliği LVN_KEYDOWN iletileri işlemesini istediğinizi `IDC_LIST1`belirtmek için, ileti haritanıza aşağıdakileri eklemek için ClassWizard'ı kullanırsınız:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

Yukarıdaki örnekte, ClassWizard tarafından sağlanan işlev:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard'ın uygun türde bir işaretçiyi otomatik olarak sağladığını unutmayın. Bildirim yapısına *pNMHDR* veya *pLVKeyDow*üzerinden erişebilirsiniz.

## <a name="on_notify_range"></a><a name="_mfcnotes_on_notify_range"></a>ON_NOTIFY_RANGE

Denetimler kümesi için aynı WM_NOTIFY iletisini işlemeniz gerekiyorsa, ON_NOTIFY yerine ON_NOTIFY_RANGE kullanabilirsiniz. Örneğin, belirli bir bildirim iletisi için aynı eylemi gerçekleştirmek istediğiniz bir düğme kümeniz olabilir.

ON_NOTIFY_RANGE kullandığınızda, aralığın başlangıç ve bitiş alt tanımlayıcılarını belirterek bildirim iletisini işleyeceğiniz bitişik bir alt tanımlayıcı aralığı belirtirsiniz.

ClassWizard ON_NOTIFY_RANGE işlemez; kullanmak için ileti haritanızı kendiniz yapmanız gerekir.

ON_NOTIFY_RANGE için mesaj-harita girişi ve işlev prototipi aşağıdaki gibidir:

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*<br/>
LVN_KEYDOWN gibi işlenecek bildirim iletisinin kodu.

*Kimliği*<br/>
Bitişik tanımlayıcı aralığındaki ilk tanımlayıcı.

*idSon*<br/>
Bitişik tanımlayıcı aralığındaki son tanımlayıcı.

*üyeFxn*<br/>
Bu bildirim gönderildiğinde çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple birlikte bildirilmelidir:

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*Kimliği*<br/>
Bildirimi gönderen denetimin alt tanımlayıcısı.

*pNotifyStruct*<br/>
Yukarıda açıklandığı gibi bildirim yapısına bir işaretçi.

*Sonuç*<br/>
Dönmeden önce ayarladığınız sonuç koduiçin bir işaretçi.

## <a name="on_notify_ex-on_notify_ex_range"></a><a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a>ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

Bildirim yönlendirmesinde bir iletiyi işlemek için birden fazla nesne istiyorsanız, ON_NOTIFY (veya ON_NOTIFY_RANGE) yerine ON_NOTIFY_EX (veya ON_NOTIFY_EX_RANGE) kullanabilirsiniz. **EX** sürümü ile normal sürüm arasındaki tek fark, **EX** sürümü için çağrılan üye işlevin ileti işlemenin devam edip etmeyeceğini belirten bir **BOOL** döndürmesidir. Bu işlevden **FALSE'yi** döndürmek, aynı iletiyi birden fazla nesnede işlemenizi sağlar.

ClassWizard ON_NOTIFY_EX veya ON_NOTIFY_EX_RANGE işlemez; bunlardan birini kullanmak istiyorsanız, ileti haritanızı kendiniz yapmanız gerekir.

ON_NOTIFY_EX ve ON_NOTIFY_EX_RANGE için mesaj-harita girişi ve işlev prototipi aşağıdaki gibidir. Parametrelerin anlamları**EX** olmayan sürümlerle aynıdır.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

Yukarıdakilerin her ikisi için de prototip aynıdır:

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

Her iki durumda *da, kimlik* bildirimi gönderen denetimin alt tanımlayıcısını tutar.

Bildirim iletisi tamamen işlendiyse **veya** komut yönlendirmesindeki diğer nesneler iletiyi işlemek için bir şansa sahipse, işleviniz **DOĞRU** döndürilmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
