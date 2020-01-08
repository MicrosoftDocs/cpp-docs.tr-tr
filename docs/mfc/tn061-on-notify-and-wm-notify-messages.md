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
ms.openlocfilehash: aa1efb628ee45be3dfaee320cf64c4b2cbb91f04
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302243"
---
# <a name="tn061-on_notify-and-wm_notify-messages"></a>TN061: ON_NOTIFY ve WM_NOTIFY İletileri

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu teknik notta, yeni WM_NOTIFY iletisi hakkında arka plan bilgileri sağlanır ve MFC uygulamanızda WM_NOTIFY iletileri işlemenin önerilen (ve en yaygın) yolu açıklanmaktadır.

**Windows 3. x ' de bildirim Iletileri**

Windows 3. x ' de, denetimler, fare tıklamaları, içerik ve seçimdeki değişiklikler ve üst öğeye bir ileti göndererek arka plan boyamayı denetleme gibi olayların üst öğelerini bilgilendirir. Basit bildirimler, bildirim kodu (BN_CLICKED gibi) ve *wParam* içine PAKETLENMIŞ denetim kimliği ve *lParam*içindeki denetim tanıtıcısı ile özel WM_COMMAND iletileri olarak gönderilir. *WParam* ve *lParam* 'nin dolu olduğundan, ek veri iletmenin bir yolu yoktur; bu iletiler yalnızca basit bildirim olabilir. Örneğin, BN_CLICKED bildiriminde, düğme tıklandığında fare imlecinin konumu hakkında bilgi göndermenin bir yolu yoktur.

Windows 3. x ' teki denetimlerin ek verileri içeren bir bildirim iletisi gönderilmesi gerektiğinde, WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ gibi çeşitli özel amaçlı mesajlar kullanır CHARTOITEM, WM_VKEYTOITEM vb. Bu iletiler, bunları gönderen denetime geri yansıtılabilir. Daha fazla bilgi için bkz. [TN062: Windows denetimleri Için Ileti yansıtma](../mfc/tn062-message-reflection-for-windows-controls.md).

**Win32 içindeki bildirim Iletileri**

Windows 3,1 ' de var olan denetimlerde Win32 API, Windows 3. x ' de kullanılan bildirim iletilerinin çoğunu kullanır. Ancak, Win32 ayrıca Windows 3. x ' de desteklenenlere birçok karmaşık ve karmaşık denetim ekler. Genellikle, bu denetimlerin bildirim iletileriyle birlikte ek veriler gönderebilmesi gerekir. Ek verilere ihtiyacı olan her yeni bildirim için yeni bir **WM_** <strong>\*</strong> iletisi eklemek yerine, Win32 API tasarımcıları yalnızca bir ileti eklemeyi tercih WM_NOTIFY, bu da herhangi bir miktarda ek veriyi standartlaştırılmış bir biçimde geçirebilir.

WM_NOTIFY iletiler, iletiyi *wParam* içinde gönderen denetimin kimliğini ve *lParam*içindeki bir yapıya yönelik bir işaretçi içerir. Bu yapı, bir **nmhdr** yapısına veya ilk üyesi olarak bir **nmhdr** yapısına sahip olan bir daha büyük yapıya sahiptir. **Nmhdr** üyesi ilk kez olduğundan, bu yapıya yönelik bir Işaretçi bir **nmhdr** işaretçisi olarak ya da onu nasıl bir yere göre daha büyük yapıya işaretçi olarak kullanılabileceğini unutmayın.

Çoğu durumda, işaretçi daha büyük bir yapıya işaret eder ve bunu kullandığınızda onu dönüştürmeniz gerekir. Yalnızca yaygın bildirimler (adları **nm_** ile başlayan) ve araç ipucu denetiminin TTN_SHOW ve ttn_pop bildirimleri gibi bazı bildirimlerde, gerçekten kullanılan bir **nmhdr** yapısı vardır.

**Nmhdr** yapısı veya ilk üyesi, iletiyi gönderen denetimin TANıTıCıSıNı ve kimliğini ve bildirim kodunu (örneğin, ttn_show) içerir. **Nmhdr** yapısının biçimi aşağıda gösterilmiştir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

TTN_SHOW bir ileti için, **kod** üyesi ttn_show olarak ayarlanır.

Çoğu bildirim, ilk üyesi olarak bir **nmhdr** yapısını içeren daha büyük bir yapıya işaretçi iletir. Örneğin, liste görünümü denetiminin LVN_KEYDOWN bildirim iletisi tarafından kullanılan yapıyı göz önünde bulundurun. Bu, liste görünümü denetiminde bir anahtara basıldığında gönderilir. İşaretçi, aşağıda gösterildiği gibi tanımlanan bir **LV_KEYDOWN** yapısına işaret eder:

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

**Nmhdr** üyesinin bu yapıda ilk kez olduğuna, bildirim iletisinde geçirileceği Işaretçinin bir **nmhdr** işaretçisine veya **LV_KEYDOWN**işaretçisine yayınlanacağını unutmayın.

**Tüm yeni Windows denetimlerinde ortak olan bildirimler**

Bazı bildirimler tüm yeni Windows denetimlerinde ortaktır. Bu bildirimler, bir **nmhdr** yapısına bir işaretçi iletir.

|Bildirim kodu|Gönderildiği için|
|-----------------------|------------------|
|NM_CLICK|Denetimdeki sol fare düğmesine tıklamış Kullanıcı|
|NM_DBLCLK|Denetimdeki sol fare düğmesine kullanıcı çift tıkladı|
|NM_RCLICK|Denetimdeki sağ fare düğmesine tıklamış Kullanıcı|
|NM_RDBLCLK|Denetimdeki sağ tıklatılan Kullanıcı düğmesi|
|NM_RETURN|Denetimde giriş odağı olduğunda kullanıcı ENTER tuşuna basıldı|
|NM_SETFOCUS|Denetime giriş odağı verildi|
|NM_KILLFOCUS|Denetim, giriş odağını kaybetti|
|NM_OUTOFMEMORY|Yeterli kullanılabilir bellek olmadığından denetim bir işlemi tamamlayamadı|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a>ON_NOTIFY: MFC uygulamalarında WM_NOTIFY Iletileri Işleme

İşlevi `CWnd::OnNotify` bildirim iletilerini işler. Varsayılan uygulama, bildirim işleyicilerinin çağrı yapılacak ileti haritasını denetler. Genel olarak, `OnNotify`geçersiz kılmayın. Bunun yerine, bir işleyici işlevi sağlar ve sahip pencerenizin sınıfının ileti eşlemesine Bu işleyici için bir ileti eşleme girişi ekleyin.

Classıntertıon Sihirbazı, ClassWizard Özellik sayfası aracılığıyla ON_NOTIFY ileti eşleme girişi oluşturabilir ve size bir iskelet işleyici işlevi sağlayabilir. Bu daha kolay hale getirmek için ClassWizard kullanma hakkında daha fazla bilgi için bkz. [Iletileri IŞLEVLERE eşleme](../mfc/reference/mapping-messages-to-functions.md).

ON_NOTIFY ileti eşleme makrosu aşağıdaki sözdizimine sahiptir:

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*<br/>
LVN_KEYDOWN gibi işlenecek bildirim iletisi kodu.

*id*<br/>
Bildirimin gönderildiği denetimin alt tanımlayıcısı.

*memberFxn*<br/>
Bu bildirim gönderildiğinde çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple bildirilmelidir:

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*pNotifyStruct*<br/>
Yukarıdaki bölümde açıklandığı gibi, bildirim yapısına yönelik bir işaretçi.

*kaynaklanan*<br/>
Döndürmeden önce ayarladığınız sonuç koduna yönelik bir işaretçi.

## <a name="example"></a>Örnek

Üye işlevi `OnKeydownList1` KIMLIĞI `IDC_LIST1`olan `CListCtrl` LVN_KEYDOWN iletileri işlemesini istediğinizi belirtmek için, aşağıdaki ileti eşlemine eklemek üzere ClassWizard 'ı kullanabilirsiniz:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

Yukarıdaki örnekte, ClassWizard tarafından sunulan işlev:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;

    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

ClassWizard 'ın doğru türe otomatik olarak bir işaretçi sağladığını unutmayın. Bildirim yapısına *pNMHDR* veya *plvkeyde*aracılığıyla erişebilirsiniz.

##  <a name="_mfcnotes_on_notify_range"></a>ON_NOTIFY_RANGE

Bir denetim kümesi için aynı WM_NOTIFY iletisini işlebilmeniz gerekirse, ON_NOTIFY yerine ON_NOTIFY_RANGE kullanabilirsiniz. Örneğin, belirli bir bildirim iletisi için aynı eylemi gerçekleştirmek istediğiniz bir düğme kümesine sahip olabilirsiniz.

ON_NOTIFY_RANGE kullandığınızda, aralığın başlangıç ve bitiş alt tanımlayıcılarını belirterek bildirim iletisini işleyecek bitişik bir alt tanımlayıcı aralığı belirtirsiniz.

ClassWizard ON_NOTIFY_RANGE işlemez; Bunu kullanmak için ileti eşlemenizi kendiniz düzenlemeniz gerekir.

ON_NOTIFY_RANGE için ileti eşleme girişi ve işlev prototipi aşağıdaki gibidir:

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*<br/>
LVN_KEYDOWN gibi işlenecek bildirim iletisi kodu.

*id*<br/>
Bitişik tanımlayıcı aralığındaki ilk tanımlayıcı.

*ıdlast*<br/>
Bitişik tanımlayıcıların aralıktaki son tanımlayıcı.

*memberFxn*<br/>
Bu bildirim gönderildiğinde çağrılacak üye işlevi.

Üye işleviniz aşağıdaki prototiple bildirilmelidir:

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*id*<br/>
Bildirimi gönderen denetimin alt tanımlayıcısı.

*pNotifyStruct*<br/>
Yukarıda açıklandığı gibi, bildirim yapısına yönelik bir işaretçi.

*kaynaklanan*<br/>
Döndürmeden önce ayarladığınız sonuç koduna yönelik bir işaretçi.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a>ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

Bildirim yönlendirmesinde bir iletiyi işlemek için birden fazla nesne istiyorsanız, ON_NOTIFY (veya ON_NOTIFY_RANGE) yerine ON_NOTIFY_EX (veya ON_NOTIFY_EX_RANGE) kullanabilirsiniz. **Ex** sürümü ve normal sürüm arasındaki tek fark, **ex** sürümü için çağrılan üye işlevinin, ileti işlemenin devam edip etmediğini belirten bir **bool** döndürmesinin ne olduğunu gösterir. Bu işlevden **false** döndürmek, birden fazla nesnede aynı iletiyi işlebırakmanıza olanak tanır.

ClassWizard ON_NOTIFY_EX veya ON_NOTIFY_EX_RANGE işlemez; Bunlardan birini kullanmak istiyorsanız, ileti eşlemenizi kendiniz düzenlemeniz gerekir.

ON_NOTIFY_EX ve ON_NOTIFY_EX_RANGE için ileti eşleme girişi ve işlev prototipi aşağıdaki gibidir. Parametrelerin anlamları,**ex** olmayan sürümlerle aynıdır.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

Yukarıdaki her ikisinin de prototipi aynıdır:

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

Her iki durumda da *ID* , bildirimi gönderen denetimin alt tanımlayıcısını barındırır.

Uyarı iletisi tamamen işlenirse işlevinizin **doğru** olması gerekir veya komut akışındaki diğer nesnelerin iletiyi işlemek için bir şansına sahip olması gerekiyorsa **false** değeri döndürmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
