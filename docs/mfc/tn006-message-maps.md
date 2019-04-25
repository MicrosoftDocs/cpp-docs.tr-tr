---
title: 'TN006: İleti Eşlemeleri'
ms.date: 06/25/2018
f1_keywords:
- vc.messages.maps
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- ON_NOTIFY_RANGE macro [MFC]
- ON_COMMAND macro [MFC]
- ON_CONTROL_RANGE macro [MFC]
- ON_REGISTERED_MESSAGE macro [MFC]
- ON_NOTIFY message [MFC]
- ON_COMMAND_RANGE_EX macro [MFC]
- ON_MESSAGE macro [MFC]
- Windows messages [MFC], message maps
- ON_COMMAND_RANGE macro [MFC]
- TN006
- ON_CONTROL macro [MFC]
- ON_COMMAND_EX macro [MFC]
- message maps [MFC], Windows messaging
ms.assetid: af4b6794-4b40-4f1e-ad41-603c3b7409bb
ms.openlocfilehash: 3536cb215da04fb7114853d3fa5d764585cbb58e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62306155"
---
# <a name="tn006-message-maps"></a>TN006: İleti Eşlemeleri

Bu Not, MFC ileti eşlemesi özelliği açıklar.

## <a name="the-problem"></a>Sorun

Microsoft Windows sanal işlevler, Mesajlaşma olanağı kullanan pencere sınıfları uygular. İletileri dahil çok sayıda nedeniyle, her Windows ileti için ayrı bir sanal işlev sağlayan fazla vakit büyük vtable oluşturursunuz.

Sistem tarafından tanımlanan Windows ileti sayısı zamanla değişir ve uygulamaları kendi Windows iletilerini tanımladığından ileti eşlemeleri arabirimi değişiklikler mevcut kodu Bozulması engellenir yöneltme düzeyi sağlar.

## <a name="overview"></a>Genel Bakış

MFC pencere gönderilen iletileri işlemek için kullanılan geleneksel Windows tabanlı programlar switch ifadesi bir alternatif sunar. Böylece bir pencere tarafından bir ileti alındığında, otomatik olarak uygun yöntemi çağrılır yöntemleri iletileri bir eşleme tanımlanabilir. Bu ileti eşleme özelliği, sanal işlevler benzeyecek şekilde tasarlanmıştır ancak C++ sanal işlevler ile mümkün ek faydası vardır.

## <a name="defining-a-message-map"></a>İleti eşlemesi tanımlama

[DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) makrosu, bir sınıf için üç üye bildirir.

- Özel bir dizi AFX_MSGMAP_ENTRY girdi olarak adlandırılan *_messageEntries*.

- Adlı bir korumalı AFX_MSGMAP yapı *messageMap* işaret eden *_messageEntries* dizisi.

- Korumalı çağrılan sanal işlev `GetMessageMap` adresini döndürür *messageMap*.

Bu makro, ileti eşlemeleri kullanarak herhangi bir sınıf bildiriminde koymanız gerekir. Kural gereği, sınıf bildiriminin sonuna olduğu. Örneğin:

```cpp
class CMyWnd : public CMyParentWndClass
{
    // my stuff...

protected:
    //{{AFX_MSG(CMyWnd)
    afx_msg void OnPaint();
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};
```

Bu yeni sınıflar oluşturduklarında AppWizard ve ClassWizard ile oluşturulan biçimidir. / / {{Ve / /}} köşeli ayraçlar için ClassWizard gereklidir.

İleti haritanın tablo bir kümesi genişletmek için ileti eşlemesi girişleri makrolar kullanılarak tanımlanır. Bir tablo ile başlayan bir [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) sınıf bu ileti eşlemesi tarafından işlenir ve işlenemeyen ileti geçirilir üst sınıfın tanımlayan makro çağrısı. Tablo ile biten [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) makro çağrısı.

Bu iki makro çağrılar arasında bu ileti eşlemesi tarafından işlenmek üzere her ileti için bir girdidir. Her standart Windows ileti ON_WM_ formunun bir makro olan*MESSAGE_NAME* , o ileti için bir giriş oluşturur.

Standart işlev imzasına Windows mesajların parametreleri açılmasını ve tür güvenliği sağlamak için tanımlanmış. Bu imza, bildirimi dosyasında Afxwin.h bulunabilir, [CWnd](../mfc/reference/cwnd-class.md). Her biri anahtar sözcüğüyle işaretlenir **afx_msg** kolay bir şekilde tanımlanması için.

> [!NOTE]
> ClassWizard gerektirir kullanmanızı **afx_msg** ileti eşlemesi işleyici bildirimlerinizde anahtar sözcük.

Bu işlev imzası, basit bir kuralı kullanarak elde edilmiştir. İşlev adı ile her zaman başlar `"On`". Bu, "kaldırıldı WM_" Windows iletinin adını ve büyük harfli her sözcüğün ilk harfini tarafından izlenir. Parametreleri sıralamadır *wParam* ardından `LOWORD`(*lParam*) sonra `HIWORD`(*lParam*). Kullanılmayan parametreleri geçmedi. MFC sınıfları tarafından Sarmalanan tanıtıcıları uygun MFC nesne işaretçileri dönüştürülür. Aşağıdaki örnek, WM_PAINT iletisini işlemek ve neden gösterilmektedir `CMyWnd::OnPaint` çağrılacak işlev:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

İleti eşleme tablosu herhangi bir işlev veya sınıf tanımının kapsamı dışında tanımlanmış olması gerekir. Bu bir extern "C" bloğunda sokulmalıdır değil.

> [!NOTE]
> ClassWizard arasında gerçekleşen ileti eşlemesi girişleri Değiştir / / {{ve / /}} açıklama köşeli ayraç.

## <a name="user-defined-windows-messages"></a>Kullanıcı tanımlı Windows iletileri

Kullanıcı tanımlı iletiler eklenebilir bir ileti eşlemede kullanarak [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) makrosu. Bu makro, ileti numarası ve formun yöntemi kabul eder:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

Bu örnekte biz kullanıcı tanımlı iletiler için standart WM_USER temel türetilen Windows iletisi Kimliğine sahip özel bir ileti işleyicisi oluşturur. Aşağıdaki örnek, bu işleyicisi çağırma gösterilmektedir:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Bu yaklaşımı kullanın, kullanıcı tarafından tanımlanan iletilerin WM_USER aralıktaki 0x7fff olmalıdır.

> [!NOTE]
> ClassWizard ClassWizard kullanıcı arabiriminden girme ON_MESSAGE işleyici yordamları desteklemez. Ayrıca Visual C++ Düzenleyicisi'nden bunları el ile girmeniz gerekir. ClassWizard bu girişleri ayrıştırma ve bunları yalnızca herhangi diğer ileti eşlemesi girişleri gibi göz atmanıza olanak tanır.

## <a name="registered-windows-messages"></a>Kayıtlı Windows iletileri

[RegisterWindowMessage](/windows/desktop/api/winuser/nf-winuser-registerwindowmessagea) işlevi, sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır. On_regıstered_message makrosu, bu iletileri işlemek için kullanılır. Bu makro adını kabul eden bir *UINT yakın* kayıtlı windows ileti kimliği içeren değişken Örneğin:

```cpp
class CMyWnd : public CMyParentWndClass
{
public:
    CMyWnd();

    //{{AFX_MSG(CMyWnd)
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam);
    //}}AFX_MSG

    DECLARE_MESSAGE_MAP()
};

static UINT NEAR WM_FIND = RegisterWindowMessage("COMMDLG_FIND");

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_REGISTERED_MESSAGE(WM_FIND, OnFind)
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

Kayıtlı Windows ileti kimliği (Bu örnekte WM_FIND) değişken olmalıdır bir *yakın* on_regıstered_message değişken biçimi nedeniyle uygulanır.

Bu yaklaşımı kullanın, kullanıcı tanımlı iletiler aralığı için 0xC000 0xFFFF aralığında olacaktır.

> [!NOTE]
> ClassWizard ClassWizard kullanıcı arabiriminden girme on_regıstered_message işleyici yordamları desteklemez. Ayrıca bir metin düzenleyicisinde bunları el ile girmeniz gerekir. ClassWizard bu girişleri ayrıştırma ve bunları yalnızca herhangi diğer ileti eşlemesi girişleri gibi göz atmanıza olanak tanır.

## <a name="command-messages"></a>Komut iletileri

Menülerini ve Hızlandırıcı komut iletileri ileti eşlemeleri ON_COMMAND makrosu ile işlenir. Bu makro, komut kimliği ve yöntemi kabul eder. Sahip yalnızca belirli WM_COMMAND ileti bir *wParam* eşit belirtilen komut kimliği, ileti eşleme girişi belirtilen yöntemi tarafından işlenir. Komut işleyici üye işlevleri hiçbir parametre ve dönüş **void**. Makro, aşağıdaki biçime sahiptir:

```cpp
ON_COMMAND(id, memberFxn)
```

Komut güncelleştirme iletileri aynı bir mekanizma aracılığıyla yönlendirilir, ancak on_update_command_uı makrosu kullanın. Güncelleştirme işleyici üye işlevlerini tek bir parametre bir işaretçi olması bir [Ccmduı](../mfc/reference/ccmdui-class.md) nesne ve dönüş **void**. Makro formundadır

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

Gelişmiş kullanıcılar, bir komut ileti işleyicileri genişletilmiş halidir ON_COMMAND_EX makrosu kullanabilirsiniz. Bir işlevselliğin ON_COMMAND makrosu sağlar. Genişletilmiş komut işleyici üye işlevler tek bir parametre alır bir **UINT** komut Kimliğini içerir ve dönüş bir **BOOL**. Dönüş değeri olması gereken **TRUE** komutu işlendiğini göstermek için. Aksi takdirde yönlendirme diğer komut hedef nesnelere devam eder.

Bu formlar örnekleri:

- İç Resource.h (genellikle Visual C++ tarafından oluşturulan)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- Sınıf bildirimi içinde

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- İleti eşleme tanımı içinde

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- V souboru implementace

    ```cpp
    void CMyClass::OnMyCommand()
    {
        // handle the command
    }

    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)
    {
        // set the UI state with pCmdUI
    }

    BOOL CMyClass::OnComplexCommand(UINT nID)
    {
        // handle the command
        return TRUE;
    }
    ```

İleri düzey kullanıcılar tek bir komut işleyicisi kullanarak bir dizi komutları işleyebilir: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) veya ON_COMMAND_RANGE_EX. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

> [!NOTE]
> ClassWizard oluşturma ON_COMMAND ve on_update_command_uı işleyicileri destekler, ancak oluşturma ON_COMMAND_EX veya ON_COMMAND_RANGE işleyicileri desteklemez. Ancak, sınıf Sihirbazı ayrıştırma ve tüm dört komut işleyicisi çeşitleri göz atmanıza olanak tanır.

## <a name="control-notification-messages"></a>Denetimi bildirim iletileri

Bir pencereye alt denetimlerinden sahip ek bit kendi ileti bilgilerinin gönderilen iletileri eşleme girişi: denetimin kimliği. Yalnızca aşağıdaki koşullar doğruysa, bir ileti eşlemesi girdisinde belirtilen ileti işleyicisi adı verilir:

- Denetim bildirimi kodunu (üst sınırı *lParam*), ileti eşleme girişi belirtilen bildirim kodu BN_CLICKED gibi eşleşir.

- Denetim Kimliği (*wParam*) ileti eşleme girdisinde belirtilen denetim kimliği eşleşir.

Özel denetimi bildirim iletileri kullanabilir [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) makrosu özel bildirim kodunu içeren bir ileti eşleme girişi tanımlamak için. Bu makro formundadır

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Gelişmiş kullanım için [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) aynı işleyiciyi denetimlerle çeşitli özel denetim bildirimden işlemek için kullanılabilir.

> [!NOTE]
> ClassWizard, kullanıcı arabiriminde bir ON_CONTROL veya ON_CONTROL_RANGE işleyicisi oluşturmayı desteklemez. Ayrıca bir metin düzenleyicisi ile bunları el ile girmeniz gerekir. ClassWizard bu girişleri ayrıştırma ve bunları yalnızca herhangi diğer ileti eşlemesi girişleri gibi göz atmanıza olanak tanır.

Windows ortak denetimleri daha güçlü kullanın [wm_notıfy](/windows/desktop/controls/wm-notify) karmaşık denetim bildirimleri için. MFC'nin bu sürümünü on_notıfy ve on_notıfy_range makroları kullanarak bu yeni iletiyi doğrudan desteği vardır. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
