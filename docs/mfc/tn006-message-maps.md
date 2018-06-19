---
title: 'TN006: İleti eşlemeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 160b88a7069ac9a5851c0f472f756d694e59874e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384703"
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
  
-   Özel bir dizi `AFX_MSGMAP_ENTRY` adlı girişleri `_messageEntries`.  
  
-   Korumalı bir `AFX_MSGMAP` adlı yapısı `messageMap` işaret `_messageEntries` dizi.  
  
-   Bir korumalı olarak adlandırılan sanal işlev `GetMessageMap` adresini döndürür `messageMap`.  
  
 İleti eşlemeleri kullanarak herhangi bir sınıf bildiriminde bu makrosu koyulmalıdır. Kurala göre bu sınıf bildiriminin sonunda olur. Örneğin:  
  
```  
class CMyWnd : public CMyParentWndClass  
{ *// my stuff...  
 
protected: *//{{AFX_MSG(CMyWnd)  
    afx_msg void OnPaint();
*//}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
```  
  
 Bu yeni sınıflar oluşturduğunuzda AppWizard ve ClassWizard tarafından oluşturulan biçimidir. / / {{Ve / /}} köşeli ClassWizard için gereklidir.  
  
 İleti haritanın tablo genişletmek için ileti eşlemesi girişlerini makroları kümesi kullanılarak tanımlanır. Bir tablo ile başlayan bir [begın_message_map](reference/message-map-macros-mfc.md#begin_message_map) bu ileti eşlemesi tarafından işlenen ve işlenmeyen iletileri geçirilir üst sınıf tanımlar makrosu çağrısı. Tablo ile biten [END_MESSAGE_MAP](reference/message-map-macros-mfc.md#end_message_map) makrosu çağrısı.  
  
 Bu iki makrosu bu ileti eşlemesi tarafından yönetilecek her ileti için bir giriş çağrıdır. Her standart Windows ileti makrosu ON_WM_ formun sahip*MESSAGE_NAME* ileti için bir giriş oluşturur.  
  
 Standart işlev imzası, her Windows ileti parametrelerinin açılmasını ve tür güvenliği sağlamak için tanımlanmış. Bu imzaları bildirimi Afxwin.h dosyasında bulunabilir, [CWnd](../mfc/reference/cwnd-class.md). Her biri anahtar sözcüğü ile işaretlenmiş `afx_msg` kolay bir şekilde tanımlanması için.  
  
> [!NOTE]
>  ClassWizard gerektirir, kullandığınız `afx_msg` ileti eşlemesi işleyici bildirimlerinizde anahtar sözcük.  
  
 Bu işlev imzaları basit bir kuralı kullanarak türetilen. İşlevin adı ile her zaman başlayan `"On`". Bu, "kaldırılan WM_" Windows iletisiyle adını ve büyük harfe her sözcüğün ilk harfini tarafından izlenir. Sıralama parametreleri olan `wParam` arkasından `LOWORD`(`lParam`) sonra `HIWORD`(`lParam`). Kullanılmayan parametreleri geçmedi. MFC sınıfları tarafından Sarmalanan tanıtıcıları uygun MFC nesnelerine işaretçiler dönüştürülür. Aşağıdaki örnekte nasıl işleneceğini gösterir `WM_PAINT` iletisi ve neden `CMyWnd::OnPaint` çağrılacak işlev:  
  
```  
BEGIN_MESSAGE_MAP(CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    ON_WM_PAINT() *//}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 İleti eşleme tablosu herhangi bir işlev veya sınıf tanımının kapsamı dışında tanımlanmış olması gerekir. Bu bir extern "C" bloğunda sokulmalıdır değil.  
  
> [!NOTE]
>  ClassWizard arasında ortaya ileti eşleme girdilerini Değiştir / / {{ve / /}} açıklama köşeli ayraç.  
  
## <a name="user-defined-windows-messages"></a>Windows iletileri kullanıcı tanımlı  
 Kullanıcı tanımlı iletiler dahil edilebilir bir ileti eşlemesi kullanarak [ON_MESSAGE](reference/message-map-macros-mfc.md#on_message) makrosu. Bu makrosu ileti numarası ve bir yöntem formun kabul eder:  
  
''' * / / sınıf bildirimi içinde  
    afx_msg LRESULT OnMyMessage(WPARAM wParam, LPARAM lParam);

 
 #<a name="define-wmmymessage-wmuser--100"></a>WM_MYMESSAGE tanımlayın (WM_USER + 100)  
 
Begın_message_map (CMyWnd, CMyParentWndClass)  
    ON_MESSAGE (WM_MYMESSAGE, OnMyMessage)  
END_MESSAGE_MAP()  
```  
  
 In this example, we establish a handler for a custom message that has a Windows message ID derived from the standard `WM_USER` base for user-defined messages. The following example shows how to call this handler:  
  
```  
CWnd * pWnd =...;  
pWnd SendMessage(WM_MYMESSAGE) ->;
```  
  
 The range of user-defined messages that use this approach must be in the range `WM_USER` to 0x7fff.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the Visual C++ editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Registered Windows Messages  
 The [RegisterWindowMessage](http://msdn.microsoft.com/library/windows/desktop/ms644947) function is used to define a new window message that is guaranteed to be unique throughout the system. The macro `ON_REGISTERED_MESSAGE` is used to handle these messages. This macro accepts a name of a `UINT NEAR` variable that contains the registered windows message ID. For example  
  
```  
CMyWnd sınıfı: ortak CMyParentWndClass  
{  
Ortak:  
    CMyWnd();

 *//{{AFX_MSG(CMyWnd)  
    afx_msg LRESULT OnFind(WPARAM wParam, LPARAM lParam); * //}}AFX_MSG  
 
    DECLARE_MESSAGE_MAP() 
};  
 
YAKIN statik UINT WM_FIND RegisterWindowMessage("COMMDLG_FIND"); =

 
Begın_message_map (CMyWnd, CMyParentWndClass) *//{{AFX_MSG_MAP(CMyWnd)  
    On_regıstered_message (WM_FIND, OnFind) * //}}AFX_MSG_MAP  
END_MESSAGE_MAP()  
```  
  
 The registered Windows message ID variable (WM_FIND in this example) must be a `NEAR` variable because of the way `ON_REGISTERED_MESSAGE` is implemented.  
  
 The range of user-defined messages that use this approach will be in the range 0xC000 to 0xFFFF.  
  
> [!NOTE]
>  ClassWizard does not support entering `ON_REGISTERED_MESSAGE` handler routines from the ClassWizard user interface. You must manually enter them from the text editor. ClassWizard will parse these entries and let you browse them just like any other message-map entries.  
  
## Command Messages  
 Command messages from menus and accelerators are handled in message maps with the `ON_COMMAND` macro. This macro accepts a command ID and a method. Only the specific `WM_COMMAND` message that has a `wParam` equal to the specified command ID is handled by the method specified in the message-map entry. Command handler member functions take no parameters and return `void`. The macro has the following form:  
  
```  
ON_COMMAND (kimliği, memberFxn)  
```  
  
 Command update messages are routed through the same mechanism, but use the `ON_UPDATE_COMMAND_UI` macro instead. Command update handler member functions take a single parameter, a pointer to a [CCmdUI](../mfc/reference/ccmdui-class.md) object, and return `void`. The macro has the form  
  
```  
On_update_command_uı (kimliği, memberFxn)  
```  
  
 Advanced users can use the `ON_COMMAND_EX` macro, which is an extended form of command message handlers. The macro provides a superset of the `ON_COMMAND` functionality. Extended command-handler member functions take a single parameter, a `UINT` that contains the command ID, and return a `BOOL`. The return value should be `TRUE` to indicate that the command has been handled. Otherwise routing will continue to other command target objects.  
  
 Examples of these forms:  
  
-   Inside Resource.h (usually generated by Visual C++)  
  
 ```  
 #<a name="define----idmycmd------100"></a>ID_MYCMD 100 tanımlayın  
 #<a name="define----idcomplex----101"></a>ID_COMPLEX 101 tanımlayın  
 ```  
  
-   Inside the class declaration  
  
 ```  
    afx_msg void OnMyCommand();
afx_msg void OnUpdateMyCommand (Ccmduı * pCmdUI);

    afx_msg BOOL OnComplexCommand(UINT nID);

 ```  
  
-   Inside the message map definition  
  
 ```  
    ON_COMMAND(ID_MYCMD,
    OnMyCommand)  
    ON_UPDATE_COMMAND_UI(ID_MYCMD,
    OnUpdateMyCommand)  
    ON_COMMAND_EX(ID_MYCMD,
    OnComplexCommand)  
 ```  
  
-   In the implementation file  
  
 ```  
    void CMyClass::OnMyCommand()  
 {* / / komut işleme  
 }  
 
    void CMyClass::OnUpdateMyCommand(CCmdUI* pCmdUI)  
 {* / / pCmdUI UI durumuyla ayarlayın  
 }  
 
    BOOL CMyClass::OnComplexCommand(UINT nID)  
 {* / / komut işleme  
    TRUE döndürür;  
 }  
 ```  
  
 Advanced users can handle a range of commands by using a single command handler: [ON_COMMAND_RANGE](reference/message-map-macros-mfc.md#on_command_range) or `ON_COMMAND_RANGE_EX`. See the product documentation for more information about these macros.  
  
> [!NOTE]
>  ClassWizard supports creating `ON_COMMAND` and `ON_UPDATE_COMMAND_UI` handlers, but it does not support creating `ON_COMMAND_EX` or `ON_COMMAND_RANGE` handlers. However, Class Wizard will parse and let you browse all four command handler variants.  
  
## Control Notification Messages  
 Messages that are sent from child controls to a window have an extra bit of information in their message map entry: the control's ID. The message handler specified in a message map entry is called only if the following conditions are true:  
  
-   The control notification code (high word of `lParam`), such as BN_CLICKED, matches the notification code specified in the message-map entry.  
  
-   The control ID (`wParam`) matches the control ID specified in the message-map entry.  
  
 Custom control notification messages may use the [ON_CONTROL](reference/message-map-macros-mfc.md#on_control) macro to define a message map entry with a custom notification code. This macro has the form  
  
```  
ON_CONTROL (wNotificationCode, kimliği, memberFxn)  
```  
  
 For advanced usage [ON_CONTROL_RANGE](reference/message-map-macros-mfc.md#on_control_range) can be used to handle a specific control notification from a range of controls with the same handler.  
  
> [!NOTE]
>  ClassWizard does not support creating an `ON_CONTROL` or `ON_CONTROL_RANGE` handler in the user interface. You must manually enter them with the text editor. ClassWizard will parse these entries and let you browse them just like any other message map entries.  
  
 The Windows Common Controls use the more powerful [WM_NOTIFY](http://msdn.microsoft.com/library/windows/desktop/bb775583) for complex control notifications. This version of MFC has direct support for this new message by using the `ON_NOTIFY` and `ON_NOTIFY_RANGE` macros. See the product documentation for more information about these macros.  
  
## See Also  
 [Technical Notes by Number](../mfc/technical-notes-by-number.md)   
 [Technical Notes by Category](../mfc/technical-notes-by-category.md)

