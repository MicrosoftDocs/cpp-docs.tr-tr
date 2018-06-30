---
title: 'TN006: İleti eşlemeleri | Microsoft Docs'
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.messages.maps
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2c4bc820c6b54e055235c1bd29bd55ccfc032c92
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121682"
---
# <a name="tn006-message-maps"></a>TN006: İleti Eşlemeleri

Bu Not MFC ileti eşlemesi tesis açıklar.

## <a name="the-problem"></a>Sorun

Microsoft Windows ileti özelliği kullanmanız pencere sınıfları içinde sanal işlevleri uygular. Yer alan iletileri çok sayıda nedeniyle, her Windows ileti için ayrı bir sanal işleve sağlayan bir şekilde basımı karşılamayacak kadar büyük vtable oluşturursunuz.

Zaman içinde sistem tarafından tanımlanan Windows iletilerini sayısını değiştirir ve uygulamaları kendi Windows iletilerini tanımlayabilir olduğundan ileti eşlemeleri arabirimi değişiklikleri var olan kodu bozmasını engeller yöneltme düzeyini belirtin.

## <a name="overview"></a>Genel Bakış

MFC pencere gönderilen iletileri işlemek için kullanılan geleneksel Windows tabanlı programlarda switch deyimi bir alternatif sunar. Böylece bir pencere tarafından bir ileti alındığında, uygun yöntemi otomatik olarak çağrılır iletileri eşlemeyi yöntemlerine tanımlanabilir. Bu ileti eşleme tesis sanal işlevler benzeyecek şekilde tasarlanmıştır ancak C++ sanal işlevleri ile olası ek avantajları vardır.

## <a name="defining-a-message-map"></a>İleti eşlemesi tanımlama

[DECLARE_MESSAGE_MAP](reference/message-map-macros-mfc.md#declare_message_map) makrosu bir sınıf için üç üye bildirir.

- Özel bir dizi AFX_MSGMAP_ENTRY girişlerinin adlı *_messageEntries*.

- Korumalı bir AFX_MSGMAP yapısı adlı *messageMap* işaret *_messageEntries* dizi.

- Bir korumalı olarak adlandırılan sanal işlev `GetMessageMap` adresini döndürür *messageMap*.

İleti eşlemeleri kullanarak herhangi bir sınıf bildiriminde bu makrosu koyulmalıdır. Kurala göre bu sınıf bildiriminin sonunda olur. Örneğin:

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

Bu yeni sınıflar oluşturduğunuzda AppWizard ve ClassWizard tarafından oluşturulan biçimidir. / / {{Ve / /}} köşeli ClassWizard için gereklidir.

İleti haritanın tablo genişletmek için ileti eşlemesi girişlerini makroları kümesi kullanılarak tanımlanır. Bir tablo ile başlayan bir [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) bu ileti eşlemesi tarafından işlenen ve işlenmeyen iletileri geçirilir üst sınıf tanımlar makrosu çağrısı. Tablo ile biten [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) makrosu çağrısı.

Bu iki makrosu bu ileti eşlemesi tarafından yönetilecek her ileti için bir giriş çağrıdır. Her standart Windows ileti makrosu ON_WM_ formun sahip*MESSAGE_NAME* ileti için bir giriş oluşturur.

Standart işlev imzası, her Windows ileti parametrelerinin açılmasını ve tür güvenliği sağlamak için tanımlanmış. Bu imzaları bildirimi Afxwin.h dosyasında bulunabilir, [CWnd](../mfc/reference/cwnd-class.md). Her biri anahtar sözcüğü ile işaretlenmiş **afx_msg** kolay bir şekilde tanımlanması için.

> [!NOTE]
> ClassWizard gerektirir, kullandığınız **afx_msg** ileti eşlemesi işleyici bildirimlerinizde anahtar sözcük.

 Bu işlev imzaları basit bir kuralı kullanarak türetilen. İşlevin adı ile her zaman başlayan `"On`". Bu, "kaldırılan WM_" Windows iletisiyle adını ve büyük harfe her sözcüğün ilk harfini tarafından izlenir. Sıralama parametreleri olan *wParam* arkasından `LOWORD`(*lParam*) sonra `HIWORD`(*lParam*). Kullanılmayan parametreleri geçmedi. MFC sınıfları tarafından Sarmalanan tanıtıcıları uygun MFC nesnelerine işaretçiler dönüştürülür. Aşağıdaki örnek WM_PAINT ileti işleme ve neden gösterilmektedir `CMyWnd::OnPaint` çağrılacak işlev:

```cpp
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    //{{AFX_MSG_MAP(CMyWnd)
    ON_WM_PAINT()
    //}}AFX_MSG_MAP
END_MESSAGE_MAP()
```

 İleti eşleme tablosu herhangi bir işlev veya sınıf tanımının kapsamı dışında tanımlanmış olması gerekir. Bu bir extern "C" bloğunda sokulmalıdır değil.

> [!NOTE]
> ClassWizard arasında ortaya ileti eşleme girdilerini Değiştir / / {{ve / /}} açıklama köşeli ayraç.

## <a name="user-defined-windows-messages"></a>Windows iletileri kullanıcı tanımlı

Kullanıcı tanımlı iletiler dahil edilebilir bir ileti eşlemesi kullanarak [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) makrosu. Bu makrosu ileti numarası ve bir yöntem formun kabul eder:

```cpp
    // inside the class declaration
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

    #define WM_MYMESSAGE (WM_USER + 100)

BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass)
    ON_MESSAGE(WM_MYMESSAGE, OnMyMessage)
END_MESSAGE_MAP()
```

Bu örnekte, kullanıcı tanımlı iletiler için standart WM_USER temel türetilmiş bir Windows ileti Kimliğine sahip özel bir ileti için bir işleyici oluşturur. Aşağıdaki örnek, bu işleyici çağrı gösterilmektedir:

```cpp
CWnd* pWnd = ...;
pWnd->SendMessage(WM_MYMESSAGE);
```

Bu yaklaşımı kullanın kullanıcı tanımlı iletilerinin 0x7fff aralıktaki WM_USER arasında olmalıdır.

> [!NOTE]
> ClassWizard ClassWizard kullanıcı arabiriminden girme ON_MESSAGE işleyici yordamları desteklemiyor. Ayrıca Visual C++ Düzenleyicisi'nden bunları el ile girmeniz gerekir. ClassWizard bu girişler ayrıştırabilir ve yalnızca tüm diğer ileti eşleme girdileri gibi Gözat sağlar.

## <a name="registered-windows-messages"></a>Kayıtlı Windows iletileri

[RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) işlevi, sistem genelinde benzersiz olması garanti yeni bir pencere iletisi tanımlamak için kullanılır. On_regıstered_message makrosu bu iletileri işlemek için kullanılır. Bu makro adını kabul eden bir *UINT yakın* kayıtlı windows ileti kimliği içeren değişkeni Örneğin

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

Kayıtlı Windows ileti kimliği (Bu örnekte WM_FIND) değişken olmalıdır bir *NEAR* on_regıstered_message biçimini nedeniyle değişken uygulanır.

Bu yaklaşımı kullanın, kullanıcı tanımlı iletiler aralığını 0xC000-0xFFFF aralığında olacaktır.

> [!NOTE]
> ClassWizard ClassWizard kullanıcı arabiriminden girme on_regıstered_message işleyici yordamları desteklemiyor. Ayrıca metin Düzenleyicisi'nden bunları el ile girmeniz gerekir. ClassWizard bu girişler ayrıştırabilir ve yalnızca tüm diğer ileti eşleme girdileri gibi Gözat sağlar.

## <a name="command-messages"></a>Komut iletileri

Menüleri ve Hızlandırıcıları komut iletileri ileti eşlemeleri ON_COMMAND makrosu ile işlenir. Bu makrosu komut kimliği ve yöntemi kabul eder. Yalnızca belirli WM_COMMAND ekinde bir *wParam* kimliği ileti eşleme girdisinde belirtilen yöntemi tarafından işlenir belirtilen komut eşittir. Komut işleyici üye işlevleri hiç parametre almaz ve dönüş **void**. Makro aşağıdaki biçime sahiptir:

```cpp
ON_COMMAND(id, memberFxn)
```

Komut güncelleştirme iletileri aynı bir mekanizma aracılığıyla yönlendirilir, ancak on_update_command_uı makrosu kullanın. Güncelleştirme işleyici üye işlevlerini ele tek bir parametre için bir işaretçi bir [Ccmduı](../mfc/reference/ccmdui-class.md) nesne ve geri dönüp **void**. Makro bir biçime sahip

```cpp
ON_UPDATE_COMMAND_UI(id, memberFxn)
```

İleri düzey kullanıcılar komutu ileti işleyicileri genişletilmiş bir biçimidir ON_COMMAND_EX makrosu kullanabilirsiniz. Makro ON_COMMAND işlevlerinin bir alt kümesi sağlar. Genişletilmiş komut işleyici üye işlevlerini tek bir parametre ele bir **UINT** , komut Kimliğini içerir ve geri dönüp bir **BOOL**. Dönüş değeri olmalıdır **TRUE** komutu işlendiğini belirtmek için. Aksi takdirde yönlendirme diğer komutu hedef nesnelere devam eder.

Bu form örnekleri:

- İç Resource.h (genellikle Visual C++ tarafından oluşturulan)

    ```cpp
    #define    ID_MYCMD      100
    #define    ID_COMPLEX    101
    ```

- İçinde sınıf bildirimi

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

 İleri düzey kullanıcılar, tek bir komut işleyici kullanarak bir dizi komutları işleyebilir: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) veya ON_COMMAND_RANGE_EX. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

> [!NOTE]
> ClassWizard oluşturma ON_COMMAND ve on_update_command_uı işleyicilerini destekler, ancak oluşturma ON_COMMAND_EX veya ON_COMMAND_RANGE işleyicileri desteklemiyor. Ancak, sınıf Sihirbazı ayrıştırma ve tüm dört komut işleyici çeşitleri Gözat olanak verir.

## <a name="control-notification-messages"></a>Denetim bildirimi iletileri

Bir pencere için alt denetimlerinden sahip fazladan bit kendi ileti bilgilerinin gönderilen ileti eşlemesi girişi: denetimin kimliği. Yalnızca aşağıdaki koşullar doğruysa bir ileti eşleme girdisinde belirtilen ileti işleyicisi adı verilir:

- Denetim bildirimi kodu (üst sınırı *lParam*), ileti eşleme girdisinde belirtilen bildirim kodu BN_CLICKED gibi eşleşir.

- Denetim Kimliği (*wParam*) ileti eşleme girdisinde belirtilen denetim kimliği ile eşleşir.

Özel denetimi bildirim iletileri kullanabilir [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) özel bildirim kodu içeren bir ileti eşleme girişi tanımlamak için makrosu. Bu makrosu bir biçime sahip

```cpp
ON_CONTROL(wNotificationCode, id, memberFxn)
```

Gelişmiş kullanım için [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) aynı işleyici denetimleriyle aralığından belirli denetim bildirimini işlemek için kullanılabilir.

> [!NOTE]
> ClassWizard kullanıcı arabiriminde bir ON_CONTROL veya ON_CONTROL_RANGE işleyicisi oluşturulmasını desteklemiyor. Ayrıca bir metin düzenleyicisi ile bunları el ile girmeniz gerekir. ClassWizard bu girişler ayrıştırabilir ve yalnızca tüm diğer ileti eşlemesi girdileri gibi Gözat sağlar.

Windows ortak denetimleri daha güçlü kullanmak [wm_notıfy](http://msdn.microsoft.com/library/windows/desktop/bb775583) karmaşık denetim bildirimleri için. MFC bu sürümü, on_notıfy ve on_notıfy_range makroları kullanarak bu yeni ileti için doğrudan desteğe sahiptir. Bu makrolar hakkında daha fazla bilgi için ürün belgelerine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)  
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)  
