---
title: 'TN061: On_notıfy ve wm_notıfy iletileri | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: 5d2f1259227fa8d27778dbf0e40b13f5460b7041
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218791"
---
# <a name="tn061-onnotify-and-wmnotify-messages"></a>TN061: ON_NOTIFY ve WM_NOTIFY İletileri

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu teknik Not Yeni wm_notıfy iletisi üzerinde arka plan bilgileri sağlar ve wm_notıfy iletileri MFC uygulamanızda işleme önerilen (ve yaygın) biçimini tanımlar.

**Windows bildirim iletilerini 3.x**

Windows içinde 3.x denetimleri fare tıklama gibi olayların ebeveynleri bildirim değişiklikleri içeriği ve seçim ve denetim arka plan boyama üst bir ileti göndererek. Basit bildirimler (örneğin, BN_CLICKED) bildirim kodla özel WM_COMMAND iletileri olarak gönderilir ve halinde paketlenmiş kimliği kontrol *wParam* ve denetimin tanıtıcıda *lParam*. Bu yana unutmayın *wParam* ve *lParam* olan herhangi bir ek veriyi geçirmek için bir yolu yoktur, tam — bu iletileri yalnızca basit bildirim olabilir. Örneğin, BN_CLICKED bildiriminde düğmesine tıklandığında, fare imlecini konumu hakkında bilgi göndermesine izin hiçbir yolu yoktur.

3.x gerek Windows denetimlerinde ek verileri içeren bir bildirim iletisi gönderirken, özel amaçlı iletileri WM_CTLCOLOR, WM_VSCROLL, WM_HSCROLL, WM_DRAWITEM, WM_MEASUREITEM, WM_COMPAREITEM, WM_DELETEITEM, WM_ dahil olmak üzere, çeşitli kullanırlar. CHARTOITEM, wm_vkeytoıtem ve benzeri. Bu iletiler geri onlara gönderdiğiniz denetimine yansıtılır. Daha fazla bilgi için [TN062: Windows denetimleri için ileti yansıması](../mfc/tn062-message-reflection-for-windows-controls.md).

**Win32'de bildirim iletileri**

Windows 3.1 varolan denetimler için Win32 API en çok kullanılan bildirim iletilerinin içinde Windows kullanan 3.x. Ancak, Win32 de birkaç Gelişmiş, karmaşık denetimleri içinde Windows desteklediği ekler 3.x. Genellikle, bu denetimleri ek bildirim iletilerinin verilerle göndermeniz gerekir. Yeni bir eklemek yerine **WM_** <strong>\*</strong> ek veriler, Win32 API tasarımcıları gerektiren her bir yeni bildirim yalnızca bir ileti, tüm geçirebilirsiniz wm_notıfy, eklemek seçtiğiniz ileti standartlaştırılmış bir biçimde ek veri miktarı.

Wm_notıfy iletileri içeren ileti gönderme denetiminin kimliği *wParam* bir yapıya bir işaretçi *lParam*. Bu yapı geçerli bir **NMHDR** yapısı veya olan bazı daha büyük bir yapının bir **NMHDR** yapısı olarak kendi ilk üyesi. Bu yana unutmayın **NMHDR** ilk üyesi olduğundan, bu yapı işaretçisi için bir işaretçi olarak kullanılabilir bir **NMHDR** veya nasıl türüne bağlı olarak daha büyük yapısına bir işaretçi olarak.

Çoğu durumda, işaretçiyi daha büyük bir yapısına işaret edecek ve kullandığınız zaman, dönüştürme yapmak gerekir. Genel bildirimleri gibi yalnızca birkaç bildirimleri içinde (adları ile başlayıp **NM_**) ve araç ipucu denetiminin TTN_SHOW ve TTN_POP bildirimleri, olan bir **NMHDR** gerçekten kullanılan yapısı.

**NMHDR** yapısı veya ilk üye tanıtıcısı ve ileti ve bildirim kodu (örneğin, TTN_SHOW) gönderme denetiminin Kimliğini içerir. Biçimi **NMHDR** yapısı aşağıda gösterilmektedir:

```cpp
typedef struct tagNMHDR {
    HWND hwndFrom;
    UINT idFrom;
    UINT code;
} NMHDR;
```

Bir TTN_SHOW ileti **kod** üye TTN_SHOW için ayarlanması.

Çoğu bildirimleri bir işaretçi içeren daha büyük yapısı için geçirin. bir **NMHDR** yapısı olarak kendi ilk üyesi. Örneğin, bir liste görünümü denetimi içinde bir tuşa basıldığında, gönderilen liste görünüm denetiminin LVN_KEYDOWN bildirim iletisi tarafından kullanılan yapısı göz önünde bulundurun. İşaretçi işaret bir **LV_KEYDOWN** yapısı, aşağıda gösterildiği gibi tanımlanır:

```cpp
typedef struct tagLV_KEYDOWN {
    NMHDR hdr;
    WORD wVKey;
    UINT flags;
} LV_KEYDOWN;
```

Bu yana unutmayın **NMHDR** üye bu yapıda ilk, bildirim iletisini geçirilen işaretçi için bir işaretçi atanabilecek bir **NMHDR** ya da bir işaretçi bir **LV_KEYDOWN** .

**Tüm yeni Windows denetimleri için bildirimleri ortak**

Bazı bildirimler tüm yeni Windows denetimleri için ortaktır. Bu bildirimleri geçirmek için bir işaretçi bir **NMHDR** yapısı.

|Bildirim kodu|İçin gönderildi|
|-----------------------|------------------|
|NM_CLICK|Kullanıcının sol fare düğmesine denetimde tıkladığını|
|NM_DBLCLK|Kullanıcı çift sol fare düğmesine denetimde|
|NM_RCLICK|Kullanıcının sağ fare düğmesine denetimde tıkladığını|
|NM_RDBLCLK|Kullanıcı çift sağ fare düğmesine denetimde|
|NM_RETURN|Denetim odağı giriş ancak kullanıcı ENTER tuşuna basıldı|
|NM_SETFOCUS|Denetimin Girintiyi verildi|
|NM_KILLFOCUS|Denetim, giriş odağını kaybetmiş|
|NM_OUTOFMEMORY|Denetim bir işlem tamamlanamadı, çünkü kullanılabilir yeterli bellek yoktu|

##  <a name="_mfcnotes_on_notify.3a_.handling_wm_notify_messages_in_mfc_applications"></a> On_notıfy: MFC uygulamaları wm_notıfy iletileri işleme

İşlev `CWnd::OnNotify` bildirim iletilerini işleme. Varsayılan uygulaması çağırmak bildirim işleyicileri için mesaj haritasını denetler. Genel olarak, size geçersiz `OnNotify`. Bunun yerine, bir işleyici işlevi sağlar ve sahibi pencerenin sınıfı için ileti eşlemesi, işleyici için bir ileti eşleme girişi ekleyin.

ClassWizard, ClassWizard özellik sayfası aracılığıyla on_notıfy iletisi eşleme girişi oluşturabilir ve bir çatı işleyicisi işlevini sağlar. Bunu kolaylaştırmak için ClassWizard kullanma hakkında daha fazla bilgi için bkz. [iletileri işlevlere eşleme](../mfc/reference/mapping-messages-to-functions.md).

İleti eşleme on_notıfy makrosu sözdizimi aşağıdaki gibidir:

```cpp
ON_NOTIFY(wNotifyCode, id, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*  
 Bildirim iletisi LVN_KEYDOWN gibi ele kodu.

*id*  
 Bildirimin gönderildiği denetim alt tanımlayıcısı.

*memberFxn*  
 Bu bildirimi gönderirken çağrılacak üye işlevi.

Aşağıdaki prototip ile üye işlevi bildirilmelidir:

```cpp
afx_msg void memberFxn(NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*pNotifyStruct*  
 Yukarıdaki bölümde açıklandığı gibi bildirim yapısı işaretçisi.

*Sonuç*  
 Sonuç kodu için bir işaretçi, dönmeden önce ayarlarsınız.

## <a name="example"></a>Örnek

Üye işlevi istediğinizi belirtmek için `OnKeydownList1` LVN_KEYDOWN iletileri işlemek için `CListCtrl` ayarlanmış kimliği `IDC_LIST1`, aşağıdaki ileti haritanıza eklemek için ClassWizard kullanırsınız:

```cpp
ON_NOTIFY(LVN_KEYDOWN, IDC_LIST1, OnKeydownList1)
```

Yukarıdaki örnekte, ClassWizard tarafından sağlanan bir işlevdir:

```cpp
void CMessageReflectionDlg::OnKeydownList1(NMHDR* pNMHDR, LRESULT* pResult)
{
    LV_KEYDOWN* pLVKeyDow = (LV_KEYDOWN*)pNMHDR;
    
    // TODO: Add your control notification handler
    //       code here

    *pResult = 0;
}
```

Not ClassWizard otomatik olarak uygun türde bir işaretçi sağlar. Bildirim yapısı üzerinden erişebilirsiniz *pNMHDR* veya *pLVKeyDow*.

##  <a name="_mfcnotes_on_notify_range"></a> ON_NOTIFY_RANGE

Bir dizi denetimi için aynı wm_notıfy iletisi işlenemedi gerekiyorsa on_notıfy yerine on_notıfy_range kullanabilirsiniz. Örneğin, belirli bir bildirim iletisi için aynı eylemi gerçekleştirmek istediğiniz düğme kümesi olabilir.

On_notıfy_range kullandığınızda, alt tanımlayıcıları başına belirtme ve alt tanımlayıcıları aralığın bitiş bildirim iletisini işlemek üzere bitişik aralığını belirtin.

ClassWizard on_notıfy_range işlemedi.; kullanmak için ileti eşlemesi kendiniz düzenlemeniz gerekir.

İleti eşleme girişi ve işlev prototipi on_notıfy_range için aşağıdaki gibidir:

```cpp
ON_NOTIFY_RANGE(wNotifyCode, id, idLast, memberFxn)
```

burada parametreler şunlardır:

*wNotifyCode*  
 Bildirim iletisi LVN_KEYDOWN gibi ele kodu.

*id*  
 Tanımlayıcıların bitişik aralıktaki ilk tanımlayıcısı.

*idLast*  
 Tanımlayıcıların bitişik aralıktaki son tanımlayıcısı.

*memberFxn*  
 Bu bildirimi gönderirken çağrılacak üye işlevi.

Aşağıdaki prototip ile üye işlevi bildirilmelidir:

```cpp
afx_msg void memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

burada parametreler şunlardır:

*id*  
 Bildirim gönderilen denetim alt tanımlayıcısı.

*pNotifyStruct*  
 Yukarıda açıklandığı gibi bildirim yapısı işaretçisi.

*Sonuç*  
 Sonuç kodu için bir işaretçi, dönmeden önce ayarlarsınız.

##  <a name="_mfcnotes_tn061_on_notify_ex.2c_.on_notify_ex_range"></a> ON_NOTIFY_EX, ON_NOTIFY_EX_RANGE

İsterseniz birden fazla nesne bir iletisini işlemek için yönlendirme bildirim on_notıfy (veya on_notıfy_range) yerine on_notıfy_ex (veya on_notıfy_ex_range) kullanabilirsiniz. Arasındaki tek fark **EX** sürümü ve normal sürümü olduğu için adlı üye işlevi **EX** sürüm döndürür bir **BOOL** belirtir olup olmadığı ileti işleme devam etmeniz gerekir. Döndüren **FALSE** bu işlevden birden fazla nesnede aynı iletiyi işlemesini sağlar.

ClassWizard on_notıfy_ex veya on_notıfy_ex_range işlemedi.; bunlardan birini kullanmak isterseniz, ileti eşlemesi kendiniz düzenlemeniz gerekir.

İleti eşleme girişi ve işlev prototipi on_notıfy_ex ve on_notıfy_ex_range aşağıdaki gibidir. Parametreleri anlamı olmayan aynıdır**EX** sürümleri.

```cpp
ON_NOTIFY_EX(nCode, id, memberFxn)
ON_NOTIFY_EX_RANGE(wNotifyCode, id, idLast, memberFxn)
```

Prototip Yukarıdakilerin ikisi için de aynıdır:

```cpp
afx_msg BOOL memberFxn(UINT id, NMHDR* pNotifyStruct, LRESULT* result);
```

Her iki durumda da *kimliği* bildirimi tarafından gönderilen denetim alt tanımlayıcısını tutar.

İşlevinizi döndürmelidir **TRUE** bildirim iletisini tamamen işlenmişse veya **FALSE** komut yönlendirme diğer nesnelerinin iletisini işlemek için bir fırsat olup olmadığını.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
