---
title: 'TN028: Bağlama duyarlı Yardım desteği | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.help
dev_langs:
- C++
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 58caed14e6b7080405cceb30cfb90623d28dc83e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Bağlama Duyarlı Yardım Desteği
Bu Not Yardım bağlamları kimlikleri ve diğer Yardım konuları MFC'de atamak için kurallar açıklanmaktadır. Bağlama duyarlı Yardım desteği Visual C++'da kullanılabilir Yardım Derleyici gerektirir.  
  
> [!NOTE]
>  Bağlama duyarlı Yardım WinHelp kullanarak uygulama yanı sıra, MFC da HTML Yardım'ı kullanarak destekler. Bu destek ve HTML Yardımı ile programlama hakkında daha fazla bilgi için bkz: [HTML Yardımı: Context-Sensitive yardımcı olmak için programlarınızı](../mfc/html-help-context-sensitive-help-for-your-programs.md).  
  
## <a name="types-of-help-supported"></a>Desteklenen Yardım türleri  
 Windows uygulamalarında uygulanan bağlama duyarlı Yardım iki tür vardır. İlk ifade için "F1 Yardımı" şu anda etkin bir nesne üzerinde göre uygun bağlamına sahip WinHelp başlatma içermesidir. İkinci "Shift + F1" modudur. Bu modda, fare imleci Yardım imleci değiştirir ve kullanıcı bir nesne üzerinde tıklattığınızdan devam eder. Bu noktada, WinHelp kullanıcı tıklattınız nesne için Yardım vermek için başlatılır.  
  
 Microsoft temel sınıfları bu formların Yardım'ın her ikisi de uygulayın. Ayrıca, iki basit Yardım komutu, Yardım dizini ve Yardım kullanma framework destekler.  
  
## <a name="help-files"></a>Yardım dosyaları  
 Microsoft Foundation sınıfları tek bir Yardım dosyasında varsayalım. Yardım dosyası aynı adı ve yolu uygulamanızın olması gerekir. Örneğin, yürütülebilir dosya C:\MyApplication\MyHelp.exe ise Yardım dosyasını C:\MyApplication\MyHelp.hlp olması gerekir. Yolundan ayarladığınız `m_pszHelpFilePath` üye değişken [CWinApp sınıfı](../mfc/reference/cwinapp-class.md).  
  
## <a name="help-context-ranges"></a>Yardım içeriği aralıkları  
 MFC varsayılan uygulaması kimlikleri Yardım içeriğinin atama hakkında bazı kurallar izlemeniz gereken bir program gerektirir. Bu kurallar bir aralığı, belirli denetimlere ayrılan Kimlikleridir. Çeşitli Yardım ilgili üye işlevleri farklı uygulamaları sağlayarak bu kuralları geçersiz kılabilirsiniz.  
  
```  
0x00000000 - 0x0000FFFF : user defined  
0x00010000 - 0x0001FFFF : commands (menus/command buttons)  
0x00010000 + ID_  
(note: 0x18000-> 0x1FFFF is the practical range since command IDs are>=0x8000)  
0x00020000 - 0x0002FFFF : windows and dialogs  
0x00020000 + IDR_  
(note: 0x20000-> 0x27FFF is the practical range since IDRs are <= 0x7FFF)  
0x00030000 - 0x0003FFFF : error messages (based on error string ID)  
0x00030000 + IDP_  
0x00040000 - 0x0004FFFF : special purpose (non-client areas)  
0x00040000 + HitTest area  
0x00050000 - 0x0005FFFF : controls (those that are not commands)  
0x00040000 + IDW_  
```  
  
## <a name="simple-help-commands"></a>Basit "Yardım" komutları  
 Microsoft temel sınıfları tarafından uygulanan iki basit Yardım komutları şunlardır:  
  
-   Tarafından uygulanan ıd_help_ındex [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)  
  
-   Tarafından uygulanan ıd_help_usıng [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)  
  
 İlk komut, uygulama için Yardım dizinini gösterir. İkincisi WinHelp programını kullanarak kullanıcı Yardımı gösterir.  
  
## <a name="context-sensitive-help-f1-help"></a>İçeriğe duyarlı Yardımı (F1 Yardımı)  
 Kimliğine sahip bir komut için F1 tuşuna genellikle çevrilen `ID_HELP` ana pencerenin Hızlandırıcı tabloya yerleştirilen Hızlandırıcı tarafından. `ID_HELP` Komutu de oluşturulabilir Kimliğine sahip bir düğmesi `ID_HELP` ana pencereyi veya iletişim kutusundaki.  
  
 Bağımsız olarak nasıl `ID_HELP` komutu oluşturulur, bir komut işleyici ulaşana kadar normal bir komut olarak yönlendirilir. Komut yönlendirme MFC mimarisi hakkında daha fazla bilgi için başvurmak [Teknik Not 21](../mfc/tn021-command-and-message-routing.md). Uygulama etkin Yardım varsa `ID_HELP` komutu tarafından işleneceğini [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Uygulama nesnesi yardım iletisini alır ve komut uygun şekilde yönlendirir. Varsayılan komut yönlendirme en özel bağlamı belirlemek için yeterli olmadığından, bu gereklidir.  
  
 `CWinApp::OnHelp` WinHelp aşağıdaki sırayla başlatmak çalışır:  
  
1.  Denetler için etkin bir `AfxMessageBox` çağrısı bir Yardım kimliği ile Bir ileti kutusu şu anda etkin ise, bu ileti kutusu uygun bağlamına sahip WinHelp başlatılır.  
  
2.  Etkin pencereyi WM_COMMANDHELP ileti gönderir. Bu pencere WinHelp başlatarak yanıt vermezse, aynı iletiyi ileti işleme veya geçerli bir üst düzey penceresidir kadar sonra penceresinin üst için gönderilir.  
  
3.  Id_default_help komutu ana pencereyi gönderir. Bu varsayılan Yardım çağırır. Bu komut genellikle eşlenmiş `CWinApp::OnHelpIndex`.  
  
 Genel varsayılan kimliği temel değerleri (örneğin 0x10000 komutlar için ve iletişim kutuları gibi kaynakları için 0x20000) geçersiz kılmak için uygulama kılmalıdır [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp).  
  
 Bu işlevsellik ve Yardım içeriği belirlenir yolu geçersiz kılmak için WM_COMMANDHELP iletiyi işlemesi gerekir. Framework sağladığından, yalnızca geçerli MDI alt pencere olarak derin gidiyor gibi daha özel Yardım yönlendirme sağlamak isteyebilirsiniz. Belirli penceresi veya belki söz konusu nesne veya iletişim kutusu içindeki etkin denetim geçerli iç durumu göre iletişim için daha özel Yardım sağlamak isteyebilirsiniz.  
  
## <a name="wmcommandhelp"></a>WM_COMMANDHELP  
  
```  
 
afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)  
 
```  
  
 WM_COMMANDHELP Yardım istendiğinde, etkin pencere tarafından alınan özel bir Windows MFC iletisidir. Pencerenin bu ileti aldığında, çağırabilir `CWinApp::WinHelp` pencerenin iç durum eşleşen bağlamına sahip.  
  
 `lParam`  
 Şu anda kullanılabilir Yardım bağlamı içerir. `lParam` Yardım içeriği yok belirlendiyse sıfır olur. Uygulaması `OnCommandHelp` bağlamı Kimliğinde kullanabilirsiniz `lParam` için farklı bir bağlam belirlemek ya da yalnızca geçirebileceğiniz `CWinApp::WinHelp`.  
  
 `wParam`  
 Kullanılmaz ve sıfır olur.  
  
 Varsa `OnCommandHelp` işlev çağrıları `CWinApp::WinHelp`, döndürme zorunluluğu `TRUE`. Döndürme `TRUE` bu komut diğer sınıflar ve diğer windows yönlendirmeyi durdurur.  
  
## <a name="help-mode-shiftf1-help"></a>Yardım modu (Shift + F1 Yardımı)  
 Bu bağlama duyarlı Yardım ikinci biçimidir. Genellikle, bu mod SHIFT + F1 tuşuna basarak veya menüsü/araç aracılığıyla girilir. Bir komut olarak uygulanan (**ıd_context_help**). İleti Filtresi kanca modal bir iletişim kutusu yüklenirken bu komut çevirmek için kullanılan değil veya menü etkin olduğu, uygulama ana ileti göndericisi yürütülürken bu nedenle bu komut yalnızca kullanıcı için kullanılabilir (`CWinApp::Run`).  
  
 Uygulamanın normal olarak bu alanı (örneğin, pencerenin boyutlandırma kenarlığın) için kendi imleç görüntüleyecektir olsa bile bu mod girdikten sonra tüm uygulama Yardım fare imleci görüntülenir. Kullanıcı komut seçmek için fareyi veya klavyeyi kullanmanız mümkün değil. Komutu yürütmek yerine bu komutla ilgili Yardım görüntülenir. Ayrıca, kullanıcı ekranında, araç çubuğunda gibi görünür nesne tıklayabilir ve bu nesne için Yardım görüntülenir. Yardım'ın bu mod tarafından sağlanan `CWinApp::OnContextHelp`.  
  
 Bu döngü yürütülmesi sırasında tüm giriş klavye menü erişim anahtarları dışında etkin değil. Ayrıca, komut çeviri hala aracılığıyla gerçekleştirilir `PreTranslateMessage` bir kısayol tuşuna basın ve bu komutla ilgili Yardım almak izin vermek için.  
  
 Varsa belirli çevirileri veya alma eylemleri yerleştirin `PreTranslateMessage` SHIFT + F1 Yardımı modunda denetlemelisiniz gerçekleşmesi döndürmemelidir işlevi `m_bHelpMode` üyesi `CWinApp` bu işlemleri gerçekleştirmeden önce. `CDialog` Uyarlamasını `PreTranslateMessage` çağırmadan önce denetler `IsDialogMessage`, örneğin. Bu "iletişim gezinti" anahtarları kalıcı olmayan iletişim kutuları hakkında üst karakter + F1 modunda devre dışı bırakır. Ayrıca, `CWinApp::OnIdle` hala bu döngüsü sırasında çağrılır.  
  
 Kullanıcı bir komut menüsünden seçerse bu komutla ilgili Yardım olarak gerçekleştirilir (aracılığıyla **WM_COMMANDHELP**, aşağıya bakın). Kullanıcı uygulamaları penceresinin görünür alanı tıklarsa, bir belirleme bir nonclient veya istemci tıklatın olup için yapılır. `OnContextHelp` işleyici eşlemesi nonclient otomatik olarak istemci tıklamalarına tıklatır. Bir istemci tıklatın ise, ardından gönderir bir **WM_HELPHITTEST** tıklandığını penceresine. Bu pencere sıfır olmayan bir değer döndürürse, bu değer için Yardım bağlamı olarak kullanılır. Sıfır döndürürse `OnContextHelp` üst pencere çalışır (Bu, kendi üst başarısız ve benzeri). Yardım içeriği belirlenemiyorsa göndermek için varsayılan değer bir **ıd_default_help** sonra (genellikle) eşlenmiş ana penceresi komutu `CWinApp::OnHelpIndex`.  
  
## <a name="wmhelphittest"></a>WM_HELPHITTEST  
  
```  
 
afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)  
```  
  
 **WM_HELPHITTEST** SHIFT + F1 Yardımı modunda tıklattınız etkin pencereyi tarafından alınan bir MFC özel windows iletisidir. Pencerenin bu ileti aldığında, bir DWORD Yardım kimliği kullanmak için WinHelp tarafından döndürür.  
  
 LOWORD(lParam)  
 Fare penceresinin istemci alanına göre burada tıklandığını x ekseni cihaz koordinat içerir.  
  
 HIWORD(lParam)  
 y koordinatı içerir.  
  
 `wParam`  
 Kullanılmaz ve sıfır olur. Dönüş değeri sıfır değilse, WinHelp ile bu bağlamın adı verilir. Dönüş değeri sıfır ise, ana pencereyi Yardım için sorgulanır.  
  
 Çoğu durumda, isabet testi kodu zaten olabilir yararlanabilirsiniz. Bkz: **CToolBar::OnHelpHitTest** işleme ilişkin bir örnek **WM_HELPHITTEST** ileti (düğme ve ipuçlarında kullanılan isabet testi kodu kodu yararlanır `CControlBar`).  
  
## <a name="mfc-application-wizard-support-and-makehm"></a>MFC Uygulama Sihirbazı desteği ve MAKEHM  
 MFC Uygulama Sihirbazı'nı Yardım dosyasını (.cnt ve .hpj dosyaları) oluşturmak için gerekli dosyaları oluşturur. Ayrıca, Microsoft Yardım Derleyici tarafından kabul edilen önceden oluşturulmuş .rtf dosyaları sayısını içerir. Konular çoğunu tamamlandı, ancak bazı belirli uygulamanız için değiştirilmesi gerekebilir.  
  
 "Eşleme Yardım" dosya otomatik olarak oluşturulmasını MAKEHM adlı bir yardımcı programı tarafından desteklenir. MAKEHM yardımcı programı bir uygulamanın kaynak çevirebilir. Bir Yardım eşleme dosyası dosyasına H. Örneğin:  
  
```  
#define IDD_MY_DIALOG   2000  
#define ID_MY_COMMAND   150  
```  
  
 içine çevrilir:  
  
```  
HIDD_MY_DIALOG    0x207d0  
HID_MY_COMMAND    0x10096  
```  
  
 Bu biçim, konu adları (sol tarafta sembolleri) ile içerik kimlikleri (sağ taraftaki sayılar) eşlemeleri Yardım derleyicinin tesis ile uyumludur.  
  
 MFC programlama Utilities örnek MAKEHM için kaynak kodunu kullanılabilir [MAKEHM](../visual-cpp-samples.md).  
  
## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı çalıştırdıktan sonra Yardım desteği ekleme  
 Yardım uygulamanıza eklemek için en iyi uygulamanızı oluşturmadan önce "Context-sensitive Yardım" seçeneği MFC Uygulama Sihirbazı Gelişmiş Özellikler sayfasında denetlenecek yoludur. Bu şekilde MFC Uygulama Sihirbazı için gerekli ileti eşleme girdilerini otomatik olarak ekler, `CWinApp`-türetilmiş sınıf Yardım desteği.  
  
## <a name="help-on-message-boxes"></a>İleti kutuları hakkında Yardım  
 İleti kutuları (uyarıları da denir) hakkında Yardım aracılığıyla desteklenir `AfxMessageBox` işlevi, için sarmalayıcı `MessageBox` Windows API.  
  
 İki sürümü vardır `AfxMessageBox`, dize kimliği ve başka bir dize için bir işaretçi ile kullanılmak üzere kullanmak için bir tane (`LPCSTR`):  
  
```  
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```  
  
 Her iki durumda olduğu bir isteğe bağlı Yardım kimliği  
  
 İlk durumda, bu ileti kutusu ilgili Yardım gösterir 0 nIDHelp için varsayılandır. Kullanıcı F1 basarsa gibi ileti kutusu etkinken kullanıcı (Yardım uygulamasının desteklediği olsa bile) Yardım alır değil. Bu arzu değilse, bir yardımcı kimliği için nIDHelp sağlanmalıdır.  
  
 İkinci durumda, varsayılan değer nIDHelp için Yardım kimliği nIDPrompt aynı gösterir -1 ' dir. Yalnızca uygulama Elbette Yardım özellikli Yardım çalışmayacak). İleti kutusu Yardım desteği yok istiyorsanız 0 için nIDHelp sağlamalıdır. Yardım etkin, ancak nIDPrompt farklı Yardım Kimliğinden işlemleriniz, nIDHelp nIDPrompt farklı için pozitif bir değer belirtmeniz yeterlidir iletinin istediğiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

