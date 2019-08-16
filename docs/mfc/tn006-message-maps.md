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
ms.openlocfilehash: 489db046910cc4b44e381b3f9056cfe8f8b7ccfa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69511110"
---
# <a name="tn006-message-maps"></a>TN006: İleti Eşlemeleri

Bu notta MFC ileti eşleme tesisi açıklanmaktadır.

## <a name="the-problem"></a>Sorun

Microsoft Windows, kendi mesajlaşma özelliğini kullanan pencere sınıflarında sanal işlevler uygular. Dahil edilen çok sayıda ileti nedeniyle, her bir Windows iletisi için ayrı bir sanal işlev sağlanması, bir proson canlı büyük vtable oluşturacaktır.

Sistem tanımlı Windows iletilerinin sayısı zaman içinde değiştiği ve uygulamalar kendi Windows iletilerini tanımlayabildiğinden, ileti haritaları, arabirim değişikliklerinin mevcut kodu bozmasını önleyen bir yöneltme düzeyi sağlar.

## <a name="overview"></a>Genel Bakış

MFC, bir pencereye gönderilen iletileri işlemek için geleneksel Windows tabanlı programlarda kullanılan Switch ifadesine bir alternatif sağlar. İletilerden yöntemlere eşleme, bir pencere tarafından bir ileti alındığında, uygun yöntemin otomatik olarak çağrılabilmesi için tanımlanabilir. Bu ileti eşleme tesisi, sanal işlevlere benzeecek ancak sanal işlevlerle ilgili C++ ek avantajlar sunacak şekilde tasarlanmıştır.

## <a name="defining-a-message-map"></a>Ileti eşlemesi tanımlama

[DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) makrosu, bir sınıf için üç üye bildirir.

- *_Messageentries*adlı özel bir AFX_MSGMAP_ENTRY girdileri dizisi.

- *_Messageentries* dizisine Işaret eden *messageMap* adlı korumalı bir AFX_MSGMAP yapısı.

- *MessageMap*adresini döndüren adlı `GetMessageMap` korumalı bir sanal işlev.

Bu makro, ileti haritaları kullanılarak herhangi bir sınıfın bildirimine yerleştirilmelidir. Kurala göre, sınıf bildiriminin sonunda bulunur. Örneğin:

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

Bu, yeni sınıflar oluştururken AppWizard ve ClassWizard tarafından oluşturulan biçimdir. ClassWizard için//{{and//}} ayraçları gereklidir.

İleti eşlemesi tablosu, ileti eşleme girişlerine Genişlet bir makro kümesi kullanılarak tanımlanır. Bir tablo, bu ileti eşlemesi tarafından işlenen sınıfı ve işlenmemiş iletilerin geçirildiği üst sınıfı tanımlayan bir [BEGIN_MESSAGE_MAP](reference/message-map-macros-mfc.md#begin_message_map) makro çağrısıyla başlar. Tablo, [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) makro çağrısıyla biter.

Bu iki makro çağrısı arasında, bu ileti eşlemesi tarafından işlenecek her ileti için bir giriştir. Her standart Windows iletisinde, bu ileti için bir giriş üreten ON_WM_*MESSAGE_NAME* biçiminde bir makro bulunur.

Her bir Windows iletisinin parametrelerini açmak ve tür güvenliği sağlamak için standart bir işlev imzası tanımlanmıştır. Bu imzalar, [CWnd](../mfc/reference/cwnd-class.md)bildiriminde Afxwin. h dosyasında bulunabilir. Her biri kolay tanımlama için **afx_msg** anahtar sözcüğüyle işaretlenir.

> [!NOTE]
> ClassWizard, ileti eşleme işleyicisi bildirimlerinde **afx_msg** anahtar sözcüğünü kullanmanızı gerektirir.

Bu işlev imzaları basit bir kural kullanılarak türetilmişdi. İşlevin adı her zaman "ile `"On`başlar. Bu, "WM_" kaldırılan Windows iletisinin adı ve her sözcüğün ilk harfini büyük harfle izler. Parametrelerin sıralaması *wParam* ve sonrasında `LOWORD` `HIWORD`(*lParam*), (lParam). Kullanılmayan parametreler geçirilmiyor. MFC sınıfları tarafından Sarmalanan tüm tutamaçlar uygun MFC nesnelerine işaretçilere dönüştürülür. Aşağıdaki örnek WM_PAINT iletisini nasıl işleyeceğinizi ve `CMyWnd::OnPaint` işlevin çağrılmasına neden olduğunu gösterir:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

İleti eşleme tablosu herhangi bir işlev veya sınıf tanımının kapsamı dışında tanımlanmalıdır. Bu, extern bir "C" bloğuna yerleştirmemelidir.

> [!NOTE]
> ClassWizard//{{and//}} Açıklama ayracı arasında gerçekleşen ileti eşleme girdilerini değiştirecek.

## <a name="user-defined-windows-messages"></a>Kullanıcı tanımlı Windows Iletileri

Kullanıcı tanımlı iletiler, [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) makrosunu kullanarak bir ileti eşlemesine dahil edilebilir. Bu makro bir ileti numarası ve şu biçimdeki bir yöntemi kabul eder:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

Bu örnekte, Kullanıcı tanımlı iletiler için standart WM_USER temelden türetilmiş bir Windows ileti KIMLIĞI olan özel bir ileti için işleyici oluşturacağız. Aşağıdaki örnek, bu işleyicinin nasıl çağrılacağını göstermektedir:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Bu yaklaşımı kullanan kullanıcı tanımlı ileti aralığı WM_USER aralığında olmalıdır.

> [!NOTE]
> ClassWizard, ClassWizard kullanıcı arabiriminden ON_MESSAGE Handler yordamlarını girmeyi desteklemez. Bunları görsel C++ düzenleyiciden el ile girmeniz gerekir. ClassWizard, bu girdileri ayrıştırır ve diğer tüm ileti eşleme girdileri gibi onlara gözatmanıza imkan tanır.

## <a name="registered-windows-messages"></a>Kayıtlı Windows Iletileri

[RegisterWindowMessage](/windows/win32/api/winuser/nf-winuser-registerwindowmessagew) işlevi, sistem genelinde benzersiz olması garanti edilen yeni bir pencere iletisi tanımlamak için kullanılır. Bu iletileri işlemek için Makro ON_REGISTERED_MESSAGE kullanılır. Bu makro, kayıtlı Windows ileti KIMLIĞINI içeren bir *UINT yakınında* bir ad kabul eder. Örneğin:

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

Kayıtlı Windows ileti KIMLIĞI değişkeni (Bu örnekte WM_FIND), ON_REGISTERED_MESSAGE 'in uygulanma biçimi nedeniyle *yakın* bir değişken olmalıdır.

Bu yaklaşımı kullanan kullanıcı tanımlı ileti aralığı, 0xC000 ile 0xFFFF aralığında olacaktır.

> [!NOTE]
> ClassWizard, ClassWizard kullanıcı arabiriminden ON_REGISTERED_MESSAGE Handler yordamlarını girmeyi desteklemez. Bunları metin düzenleyicisinden el ile girmeniz gerekir. ClassWizard, bu girdileri ayrıştırır ve diğer tüm ileti eşleme girdileri gibi onlara gözatmanıza imkan tanır.

## <a name="command-messages"></a>Komut Iletileri

Menüler ve Hızlandırıcılar 'daki komut iletileri, ON_COMMAND makrosu ile ileti eşlemelerinde işlenir. Bu makro bir komut KIMLIĞI ve bir yöntemi kabul eder. Yalnızca belirtilen komut KIMLIĞINE eşit bir *wParam* öğesine sahıp belirli WM_COMMAND iletisi ileti eşleme girişinde belirtilen yöntem tarafından işlenir. Komut işleyici üye işlevleri parametre almaz ve **void**döndürür. Makro aşağıdaki biçimdedir:

```cpp
ON_COMMAND(id, memberFxn)
```

Komut güncelleştirme iletileri aynı mekanizmaya yönlendirilir, ancak bunun yerine ON_UPDATE_COMMAND_UI makrosunu kullanır. Komut güncelleştirme işleyicisi üye işlevleri tek bir parametre, bir [Ccmdui](../mfc/reference/ccmdui-class.md) nesnesine yönelik bir işaretçi alır ve **void**döndürür. Makro şu biçimdedir

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

Gelişmiş kullanıcılar, komut iletisi işleyicilerinin genişletilmiş biçimi olan ON_COMMAND_EX makrosunu kullanabilir. Makro ON_COMMAND işlevselliğinin bir üst kümesini sağlar. Genişletilmiş komut işleyici üye işlevleri tek bir parametre, komut KIMLIĞINI içeren bir **UINT** alır ve **bool**döndürür. Komutun işlendiğini göstermek için dönüş değeri **true** olmalıdır. Aksi takdirde yönlendirme diğer komut hedef nesnelerine devam eder.

Bu formların örnekleri:

- Resource. h içinde (genellikle görsel C++tarafından oluşturulur)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- Sınıf bildiriminin içinde

    ```cpp
    afx_msg void OnMyCommand();
    afx_msg void OnUpdateMyCommand(CCmdUI* pCmdUI);
    afx_msg BOOL OnComplexCommand(UINT nID);
    ```

- İleti eşleme tanımının içinde

    ```cpp
    ON_COMMAND(ID_MYCMD, OnMyCommand)
    ON_UPDATE_COMMAND_UI(ID_MYCMD, OnUpdateMyCommand)
    ON_COMMAND_EX(ID_MYCMD, OnComplexCommand)
    ```

- Uygulama dosyasında

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

İleri düzey kullanıcılar tek bir komut işleyicisini kullanarak bir dizi komut işleyebilir: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) veya ON_COMMAND_RANGE_EX. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

> [!NOTE]
> ClassWizard, ON_COMMAND ve ON_UPDATE_COMMAND_UI işleyicilerini oluşturmayı destekler, ancak ON_COMMAND_EX veya ON_COMMAND_RANGE işleyicilerini oluşturmayı desteklemez. Ancak, sınıf Sihirbazı ayrıştırılacak ve dört komut işleyici çeşitlerine gözatmanıza imkan tanır.

## <a name="control-notification-messages"></a>Denetim bildirim Iletileri

Bir pencereye alt denetimlerden gönderilen iletiler, ileti eşleme girişinde ek bir bilgi sağlar: denetimin KIMLIĞI. İleti eşleme girişinde belirtilen ileti işleyicisi, yalnızca aşağıdaki koşullar doğruysa çağrılır:

- BN_CLICKED gibi denetim bildirim kodu ( *lParam*'nin yüksek sözcüğü), ileti eşleme girişinde belirtilen bildirim koduyla eşleşir.

- Denetim KIMLIĞI (*wParam*), ileti eşleme girişinde BELIRTILEN denetim kimliğiyle eşleşiyor.

Özel denetim bildirim iletileri, özel bildirim koduna sahip bir ileti eşleme girişi tanımlamak için [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) makrosunu kullanabilir. Bu makro şu biçimdedir

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Gelişmiş kullanım için [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) , aynı işleyiciyle bir denetim aralığından belirli bir denetim bildirimini işlemek için kullanılabilir.

> [!NOTE]
> ClassWizard, Kullanıcı arabiriminde ON_CONTROL veya ON_CONTROL_RANGE işleyicisi oluşturmayı desteklemez. Metin düzenleyicisine el ile girmeniz gerekir. Classınterm Sihirbazı bu girdileri ayrıştırır ve diğer tüm ileti eşleme girdileri gibi onlara gözatmanıza imkan tanır.

Windows ortak denetimleri karmaşık denetim bildirimleri için daha güçlü [WM_NOTIFY](/windows/win32/controls/wm-notify) kullanır. Bu MFC sürümü, ON_NOTIFY ve ON_NOTIFY_RANGE makrolarını kullanarak bu yeni ileti için doğrudan desteğe sahiptir. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
