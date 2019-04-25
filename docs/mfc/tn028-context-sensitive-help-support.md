---
title: 'TN028: Bağlama duyarlı Yardım desteği'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 5689e314c2ba94068619a066e5f458e06819b2b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62305989"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Bağlama duyarlı Yardım desteği

Bu Not, Yardım bağlamlarının kimlikleri ve diğer Yardım sorunları MFC'de atamak için kurallar açıklanmaktadır. Bağlama duyarlı Yardım desteği, Visual c++'ta kullanılabilir olan Yardım derleyicisi gerektirir.

> [!NOTE]
>  Bağlama duyarlı Yardım WinHelp kullanan uygulama yanı sıra, MFC de HTML Yardımı kullanılmasını destekler. Bu desteği ve HTML Yardımı ile programlama hakkında daha fazla bilgi için bkz. [HTML Yardımı: Programlarınız için bağlama duyarlı Yardım](../mfc/html-help-context-sensitive-help-for-your-programs.md).

## <a name="types-of-help-supported"></a>Desteklenen Yardım türleri

Bağlama duyarlı Yardım Windows uygulamalarında gerçekleştirilen iki tür vardır. İlk ifade "F1 Yardımı" etkin nesneye bağlı olarak uygun bağlamla WinHelp başlatma içerir. İkinci "üst karakter + F1" modudur. Bu modda, fare imleci Yardım imlecine dönüşür ve kullanıcı bir nesnesine tıklayarak devam eder. Bu noktada, WinHelp tıklattığı nesne için yardımcı olmak için başlatılır.

Microsoft Foundation sınıfları biçimlerinden birini Yardım hem de uygulayın. Ayrıca, iki basit Yardım komutları, Yardım dizin ve Sorgularınızla framework destekler.

## <a name="help-files"></a>Yardım dosyaları

Microsoft Foundation sınıfları, tek bir Yardım dosyası varsayılır. Yardım dosyası, bir uygulama olarak aynı adı ve yolu olmalıdır. Örneğin, Yardım dosyası yürütülebilir C:\MyApplication\MyHelp.exe ise C:\MyApplication\MyHelp.hlp olması gerekir. Yolundan ayarladığınız *m_pszHelpFilePath* üye değişkeninin [CWinApp sınıfı](../mfc/reference/cwinapp-class.md).

## <a name="help-context-ranges"></a>Yardım içeriği aralıkları

MFC varsayılan uygulaması bir program kimlikleri Yardım içeriğinin atama hakkında bazı kurallara uymanız gerektirir. Bu bir aralığı olan belirli denetimler için ayrılan kimlikleri kurallardır. Çeşitli yardımla ilgili üye işlevleri farklı uygulamaları sağlayarak bu kurallar geçersiz kılabilirsiniz.

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

Microsoft Foundation sınıfları tarafından uygulanan iki basit Yardım komutları şunlardır:

- Tarafından uygulanan ıd_help_ındex [CWinApp::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- Tarafından uygulanan ıd_help_usıng [CWinApp::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

İlk komut, uygulama için Yardım dizinini gösterir. İkinci WinHelp programı kullanarak kullanıcı Yardımı gösterir.

## <a name="context-sensitive-help-f1-help"></a>Bağlama duyarlı Yardım (F1 Yardımı)

F1 tuşuna genellikle, bir kimliği ıd_help komutu için ana pencerenin Hızlandırıcı tablosu yerleştirilen bir Hızlandırıcı olarak çevrilir. Id_help komutu, bir kimliği ıd_help ana pencerede veya iletişim kutusunda, bir düğme olarak da oluşturulabilir.

Bir komut işleyici ulaşana kadar ıd_help komutu nasıl oluşturulduğunu bağımsız olarak, normal bir komut olarak yönlendirilir. Komut yönlendirme MFC mimarisi hakkında daha fazla bilgi için [Teknik Not 21](../mfc/tn021-command-and-message-routing.md). Uygulamanın etkin Yardım varsa ıd_help komutu tarafından ele alınacaktır [CWinApp::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Uygulama nesnesi yardım iletisini alır ve sonra komut uygun şekilde yönlendirir. Varsayılan komut yönlendirme en belirgin bağlamı belirlemek için yeterli olmadığından, bu gereklidir.

`CWinApp::OnHelp` WinHelp şu sırayla başlatmak çalışır:

1. Denetimleri için etkin bir `AfxMessageBox` çağırmak bir yardımcı kimliği ile Bir ileti kutusu şu anda etkin olursa, o ileti kutusu için uygun bağlamla WinHelp başlatılır.

1. Etkin pencereyi WM_COMMANDHELP ileti gönderir. WinHelp başlatarak o pencereyi yanıt vermezse, aynı iletinin ileti işlenir veya geçerli bir üst düzey penceresidir kadar sonra o pencereyi öncüleri gönderilir.

1. Id_default_help komutu ana penceresine gönderir. Bu, varsayılan Yardım çağırır. Bu komut genellikle eşlenmiş `CWinApp::OnHelpIndex`.

Genel varsayılan kimliği temel değerleri (örneğin 0x10000 komutları için ve iletişim kutuları gibi kaynaklar için 0x20000) geçersiz kılmak için uygulama geçersiz kılmalıdır [CWinApp::WinHelp](../mfc/reference/cwinapp-class.md#winhelp).

Bu işlev ve Yardım içeriğini belirlenir yolu geçersiz kılmak için WM_COMMANDHELP iletiyi işlemesi gerekir. Framework sağladığından, yalnızca geçerli MDI alt penceresi olarak derin gider gibi daha ayrıntılı yardım yönlendirme sağlamak isteyebilirsiniz. Belirli bir pencere veya belki de söz konusu nesne veya iletişim kutusu içindeki etkin denetim geçerli iç durumunu temel iletişim kutusunda, daha ayrıntılı yardım sağlamak isteyebilirsiniz.

## <a name="wmcommandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP Yardım istendiğinde, etkin pencere tarafından alınan özel bir Windows MFC iletisidir. Pencere Bu ileti aldığında, çağırabilir `CWinApp::WinHelp` bağlamla eşleşen pencere iç durumu.

*lParam*<br/>
Şu anda kullanılabilir Yardım bağlamı içerir. *lParam* Yardım içeriği yok belirlendiyse sıfırdır. Uygulanışı `OnCommandHelp` bağlam Kimliğini kullanabilirsiniz *lParam* için farklı bir bağlama belirlemek ya da yalnızca geçirebileceğiniz `CWinApp::WinHelp`.

*wParam*<br/>
Kullanılmayan ve sıfır olur.

Varsa `OnCommandHelp` işlev çağrılarında `CWinApp::WinHelp`, döndürmelidir **TRUE**. Döndüren **TRUE** bu komut, diğer sınıfların ve diğer windows yönlendirmeyi durdurur.

## <a name="help-mode-shiftf1-help"></a>Yardım modu (Shift + F1 Yardımı)

Bu bağlama duyarlı Yardım ikinci biçimidir. Genellikle, bu mod, üst karakter + F1 tuşuna basarak veya menü/araç aracılığıyla girilir. Bu komut (ıd_context_help) olarak uygulanır. Bu komutun kalıcı bir iletişim kutusu sırasında çevirmek için İleti Filtresi kanca kullanılmaz veya menü etkin olduğu, uygulama ana ileti pompası yürütülürken bu nedenle bu komut yalnızca kullanıcı tarafından kullanılabilir (`CWinApp::Run`).

Bu mod girdikten sonra bile uygulama normal şekilde (örneğin, pencerenin boyutlandırma kenarlık) o alan için kendi imleç görüntüler Yardım fare imleci uygulamanın tüm alanlar üzerinde görüntülenir. Kullanıcı, bir komut seçin, klavye ve fare kullanmanız mümkün değil. Komut yürütmenin yerine bu komut hakkında Yardım görüntülenir. Ayrıca, araç çubuğunda düğme gibi bir ekran görünür bir nesnede kullanıcının tıklayabileceği ve bu nesne için Yardım görüntülenir. Bu mod Yardım tarafından sağlanan `CWinApp::OnContextHelp`.

Bu döngü yürütülmesi sırasında tüm giriş klavye menüye erişmek anahtarları dışında etkin değil. Ayrıca, komut çeviri hala aracılığıyla gerçekleştirilen `PreTranslateMessage` bir kısayol tuşuna basın ve bu komutla ilgili Yardım almak izin vermek için.

Varsa belirli çevirileri veya Eylemler alma yerleştirin `PreTranslateMessage` yerde denetlemeniz gereken üst karakter + F1 Yardım modunda sürmez işlevi *m_bHelpMode* üyesi `CWinApp` bu uygulamadan önce işlemler. `CDialog` Uygulaması `PreTranslateMessage` çağırmadan önce denetler `IsDialogMessage`, örneğin. Bu kalıcı olmayan iletişim kutuları hakkında "iletişim gezinti" anahtarları üst karakter + F1 modunda devre dışı bırakır. Ayrıca, `CWinApp::OnIdle` yine de bu döngüsü sırasında çağrılır.

Kullanıcı menüsünden bir komut seçerse, bu komut hakkında Yardım olarak işlenir (WM_COMMANDHELP, aşağıya bakın). Kullanıcının görünen bir alanın uygulama penceresi tıklarsa, bir istemci olmayan ya da bir istemci tıklatın olmasına dair bir belirleme yapılır. `OnContextHelp` İstemci olmayan işler eşleme otomatik olarak istemci tıklamalarına tıklar. İstemci tıklama ise, ardından pencerenin tıklandığını bir WM_HELPHITTEST gönderir. Bu pencere sıfır olmayan bir değer döndürürse, bu değer için Yardım bağlamı olarak kullanılır. Sıfır döndürürse `OnContextHelp` üst pencere çalışır (ve başarısız, üst ve benzeri). Yardım içeriğini belirlenemiyorsa, daha sonra (genellikle) eşleştirilir ana pencereyi ıd_default_help komutu göndermek için varsayılan değer `CWinApp::OnHelpIndex`.

## <a name="wmhelphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

SHIFT + F1 Yardımı modunda tıklanan etkin pencere tarafından alınan bir MFC özel windows iletisi WM_HELPHITTEST var. Pencere Bu ileti aldığında, döndürür bir **DWORD** WinHelp tarafından kullanılmak üzere Yardım kimliği.

LOWORD(lParam) penceresinin istemci alanına göre fare burada tıklandığını x ekseni cihaz koordinat içeriyor.

Y ekseni koordinatı HIWORD(lParam) içerir.

*wParam*<br/>
Kullanılmayan ve sıfır olur. Dönüş değeri sıfır değilse, bu bağlamla WinHelp çağrılır. Dönüş değeri sıfır ise, ana pencereyi Yardım için sorgulanır.

Çoğu durumda, isabet testi kodu zaten olabilir yararlanabilirsiniz. Bkz: `CToolBar::OnHelpHitTest` WM_HELPHITTEST mesajı işleyen bir örneği (düğme ve araç ipuçlarında kullanılan isabet testi kodu kod yararlanır `CControlBar`).

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC Uygulama Sihirbazı desteği ve MAKEHM

MFC Uygulama Sihirbazı, bir Yardım dosyası (.cnt ve .hpj dosyaları) oluşturmak için gerekli dosyaları oluşturur. Ayrıca, Microsoft Yardım Derleyici tarafından kabul edilen önceden oluşturulmuş .rtf dosyaları sayısını içerir. Konu başlıklarından birçoğu tamamlandı, ancak bazı belirli uygulamanız için değiştirilmesi gerekebilir.

Bir "eşleştirme help" dosyası otomatik olarak oluşturulmasını MAKEHM adlı bir yardımcı programı tarafından desteklenir. MAKEHM yardımcı programı, bir uygulamanın kaynak çevirebilir. Bir Yardım eşleme dosyası için H dosyası. Örneğin:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

çevrileceğini:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

Bu biçim, içerik kimlikleri (sağ taraftaki sayı) konu adları (sol tarafındaki simge) ile eşler Yardım derleyicinin tesisi ile uyumludur.

MAKEHM için kaynak kodu MFC programlama yardımcı programları örnek kullanılabilir [MAKEHM](../overview/visual-cpp-samples.md).

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı çalıştırdıktan sonra Yardım desteği ekleme

Yardım uygulamanıza eklemek için en iyi yolu, uygulamanızı oluşturmadan önce "Context-sensitive Help" seçeneği MFC Uygulama Sihirbazı'nın Gelişmiş Özellikler sayfasında denetlemektir. Bu şekilde MFC Uygulama Sihirbazı gerekli ileti eşlemesi girişleri için otomatik olarak ekler, `CWinApp`-türetilmiş sınıf Yardım desteklemek için.

## <a name="help-on-message-boxes"></a>İleti kutuları Yardım

İleti kutuları (Uyarılar da denir) Yardım aracılığıyla desteklenir `AfxMessageBox` işlevi, için sarmalayıcı `MessageBox` Windows API.

İki sürümü vardır `AfxMessageBox`, bir dizeye bir işaretçi ile kullanmak için bir dize kimliği ve başka kullanım (`LPCSTR`):

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

Her iki durumda olduğu bir isteğe bağlı yardımcı kimliği

Bu durumda, bu ileti kutusu için Yardım'ı gösteren 0 nIDHelp için varsayılandır. Kullanıcı F1 bastığında gibi bir ileti kutusu etkin olduğu sırada (Yardım uygulamanın desteklediği durumlarda bile) kullanıcı Yardım almaz. Bu uygun değilse, bir Yardım kimliği için nIDHelp sağlanmalıdır.

İkinci durumda, nIDHelp için varsayılan değer yardımcı kimliği nIDPrompt aynıdır gösterir -1 ' dir. Yalnızca uygulama Elbette Yardım etkin olduğunda Yardım çalışmaz). İleti kutusu Yardım desteği yok istiyorsanız 0 için nIDHelp sağlamanız gerekir. İletinin Yardım etkin, ancak nIDPrompt farklı Yardım Kimliğinden bağlamasına, nIDHelp nIDPrompt farklı yalnızca pozitif bir değer sağlayın istediğiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
