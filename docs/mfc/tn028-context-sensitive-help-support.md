---
title: 'TN028: Bağlama Duyarlı Yardım Desteği'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 502edc837d7886dd60ab5107fb194c1490a76928
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370325"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Bağlama Duyarlı Yardım Desteği

Bu not, MFC'deki Yardım bağlarını ve diğer yardım sorunlarını atama kurallarını açıklar. İçeriğe duyarlı yardım desteği, Visual C++'da kullanılabilen yardım derleyicisini gerektirir.

> [!NOTE]
> MFC, WinHelp'i kullanarak içeriğe duyarlı yardım uygulamanın yanı sıra HTML Yardımı'nı da destekler. HTML Yardımı ile bu destek ve programlama hakkında daha fazla bilgi için [HTML Yardımı: Programlarınız için İçeriğe Duyarlı Yardım'a](../mfc/html-help-context-sensitive-help-for-your-programs.md)bakın.

## <a name="types-of-help-supported"></a>Desteklenen Yardım Türleri

Windows uygulamalarında uygulanan içeriğe duyarlı iki tür yardım vardır. "F1 Yardımı" olarak adlandırılan ilk, winhelp'i şu anda etkin olan nesneye dayalı uygun bağlamla başlatmayı içerir. İkincisi "Shift+ F1" modudur. Bu modda, fare imleci yardım imlecini değiştirir ve kullanıcı bir nesneyi tıklatmaya devam eder. Bu noktada, WinHelp kullanıcının tıkladığı nesne için yardım vermek için başlatılır.

Microsoft Hazırlık Sınıfları, bu yardım biçimlerinin her ikisini de uygular. Buna ek olarak, çerçeve iki basit yardım komutları destekler, Yardım Dizini ve Yardım kullanma.

## <a name="help-files"></a>Yardım Dosyaları

Microsoft Foundation sınıfları tek bir Yardım dosyası varsayar. Bu Yardım dosyası, uygulamayla aynı ada ve yola sahip olmalıdır. Örneğin, yürütülebilir C:\MyApplication\MyHelp.exe ise yardım dosyası C:\MyApplication\MyHelp.hlp olmalıdır. [CWinApp Sınıfı'nın](../mfc/reference/cwinapp-class.md) *m_pszHelpFilePath* üye değişkenine giden yolu ayarlarsınız.

## <a name="help-context-ranges"></a>Yardım Bağlam Aralıkları

MFC'nin varsayılan uygulaması, Yardım bağlamı iI'lerinin atanması ile ilgili bazı kuralları izlemesi için bir program gerektirir. Bu kurallar, belirli denetimlere ayrılmış bir dizi addır. Yardımla ilgili çeşitli üye işlevlerin farklı uygulamalarını sağlayarak bu kuralları geçersiz kılabilirsiniz.

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

## <a name="simple-help-commands"></a>Basit "Yardım" Komutları

Microsoft Hazırlık Sınıfları tarafından uygulanan iki basit Yardım komutu vardır:

- ID_HELP_INDEX Hangi [CWinApp tarafından uygulanan::OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex)

- ID_HELP_USING hangi [CWinApp tarafından uygulanan::OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing)

İlk komut, uygulama için Yardım dizini gösterir. İkincisi, WinHelp programını kullanma konusunda kullanıcı yayardımını gösterir.

## <a name="context-sensitive-help-f1-help"></a>İçeriğe Duyarlı Yardım (F1 Yardımı)

F1 tuşu genellikle ana pencerenin hızlandırıcı tablosuna yerleştirilen bir hızlandırıcı tarafından ID_HELP kimliğine sahip bir komuta çevrilir. ID_HELP komutu, ana pencerede veya iletişim kutusunda ID_HELP kimliği olan bir düğme tarafından da oluşturulabilir.

komut ID_HELP nasıl oluşturulursa oluşturulsın, bir komut işleyicisi ulaşana kadar normal bir komut olarak yönlendirilir. MFC komut yönlendirme mimarisi hakkında daha fazla bilgi için [Teknik Not 21'e](../mfc/tn021-command-and-message-routing.md)bakın. Uygulama Yardım etkinse, ID_HELP komutu CWinApp tarafından ele [alınacaktır::OnHelp](../mfc/reference/cwinapp-class.md#onhelp). Uygulama nesnesi yardım iletisini alır ve komutu uygun şekilde yönlendirir. Varsayılan komut yönlendirmesi en özel bağlamı belirlemek için yeterli olmadığından bu gereklidir.

`CWinApp::OnHelp`Aşağıdaki sırada WinHelp başlatmak için çalışır:

1. Yardım Kimliği `AfxMessageBox` ile etkin bir aramayı denetler. İleti kutusu şu anda etkinse, WinHelp bu ileti kutusuna uygun bağlamla başlatılır.

1. Etkin pencereye WM_COMMANDHELP iletisi gönderir. Bu pencere WinHelp başlatılarak yanıt vermezse, ileti işlenene veya geçerli pencere üst düzey bir pencere olana kadar aynı ileti bu pencerenin atalarına gönderilir.

1. Ana pencereye ID_DEFAULT_HELP komutu gönderir. Bu varsayılan Yardım çağırır. Bu komut genellikle ' için `CWinApp::OnHelpIndex`eşlenir.

Varsayılan kimlik temel değerlerini (örn. komutlar için 0x10000 ve iletişim kutuları gibi kaynaklar için 0x20000) genel olarak geçersiz kılmak için uygulama [CWinApp::WinHelp'i](../mfc/reference/cwinapp-class.md#winhelp)geçersiz kılmalıdır.

Bu işlevselliği ve Yardım bağlamını niçin belirlediğini geçersiz kılmak için WM_COMMANDHELP iletisini işlemeniz gerekir. Yalnızca geçerli MDI alt penceresi kadar derin olduğundan, çerçevenin sağladığından daha spesifik Yardım yönlendirmesi sağlamak isteyebilirsiniz. Ayrıca, belirli bir pencere veya iletişim kutusu için, belki de o nesnenin geçerli iç durumuna veya iletişim kutusundaki etkin denetime bağlı olarak daha özel yardım sağlamak isteyebilirsiniz.

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP, Yardım istendiğinde etkin pencere tarafından alınan özel bir Windows MFC iletisidir. Pencere bu iletiyi aldığında, `CWinApp::WinHelp` pencerenin iç durumuyla eşleşen bağlamla çağrılayabilir.

*Lparam*<br/>
Şu anda kullanılabilir Yardım bağlamını içerir. *lParam,* Yardım bağlamı belirlenmemişse sıfırdır. Bir uygulama `OnCommandHelp` farklı bir bağlam belirlemek için *lParam* bağlam kimliği kullanabilirsiniz ya da sadece `CWinApp::WinHelp`geçirebilirsiniz .

*Wparam*<br/>
Kullanılmaz ve sıfır olur.

Fonksiyon `OnCommandHelp` çağırırsa, `CWinApp::WinHelp` **TRUE**döndürmelidir. **TRUE'yu** döndürmek, bu komutun diğer sınıflara ve diğer pencerelere yönlendirmesini durdurur.

## <a name="help-mode-shiftf1-help"></a>Yardım Modu (Shift+F1 Yardım)

Bu, içeriğe duyarlı Yardım'ın ikinci biçimidir. Genellikle bu mod SHIFT+F1 tuşuna basılarak veya menü/araç çubuğu üzerinden girilir. Bir komut (ID_CONTEXT_HELP) olarak uygulanır. Bir modal iletişim kutusu veya menü etkin ken ileti filtresi kancası bu komutu çevirmek için kullanılmaz, bu nedenle bu`CWinApp::Run`komut yalnızca uygulama ana ileti pompasını çalıştırırken kullanıcı tarafından kullanılabilir ( ).

Bu modu girdikten sonra, uygulama normalde o alan için kendi imlecini (pencerenin etrafındaki boyutlandırma kenarlığı gibi) görüntülese bile, Yardım faresi imleci uygulamanın tüm alanlarında görüntülenir. Kullanıcı bir komut seçmek için fareyi veya klavyeyi kullanabilir. Komutu yürütmek yerine, bu komuta yardım görüntülenir. Ayrıca, kullanıcı araç çubuğundaki düğme gibi ekranda görünür bir nesneyi tıklatabilir ve bu nesne için Yardım görüntülenir. Bu Yardım `CWinApp::OnContextHelp`modu.

Bu döngünün yürütülmesi sırasında, menüye erişen tuşlar dışında tüm klavye girişi etkin değildir. Ayrıca, komut çevirisi, `PreTranslateMessage` kullanıcının bir hızlandırıcı tuşuna basması ve bu komut hakkında yardım alması için hala gerçekleştirilir.

SHIFT+F1 Yardım modunda gerçekleşmemesi gereken işlevde belirli çeviriler veya eylemler varsa, bu işlemleri gerçekleştirmeden önce *m_bHelpMode* üyesini `CWinApp` kontrol etmelisiniz. `PreTranslateMessage` Örneğin, `CDialog` `PreTranslateMessage` aramadan `IsDialogMessage`önce bunu denetler. Bu, SHIFT+F1 modu sırasında modeless iletişim kutularındaki "iletişim gezintisi" tuşlarını devre dışı kılabilir. Buna ek `CWinApp::OnIdle` olarak, hala bu döngü sırasında denir.

Kullanıcı menüden bir komut seçerse, bu komuta yardımcı olarak işlenir (WM_COMMANDHELP yoluyla aşağıya bakın). Kullanıcı uygulama penceresinin görünür bir alanını tıklatıyorsa, istemci olmayan bir tıklama mı yoksa istemci tıklaması mı olduğuna ilişkin bir belirleme yapılır. `OnContextHelp`istemci olmayan tıklamaların eşleneme işlemlerini istemci tıklamalarına otomatik olarak işler. İstemci tıklaması ysa, tıklatılan pencereye bir WM_HELPHITTEST gönderir. Bu pencere sıfır olmayan bir değer döndürürse, bu değer yardım bağlamı olarak kullanılır. Sıfır dönerse, `OnContextHelp` üst pencereyi dener (ve başarısız, üst, vb). Yardım bağlamı belirlenemiyorsa, varsayılan olarak ana pencereye bir ID_DEFAULT_HELP komutu göndermektir, `CWinApp::OnHelpIndex`bu komut daha sonra (genellikle) eşlenir.

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST SHIFT+F1 Yardım modu sırasında tıklanan etkin pencere tarafından alınan bir MFC özel windows iletisidir. Pencere bu iletiyi aldığında, WinHelp tarafından kullanılmak üzere bir **DWORD** Yardım Kimliği döndürür.

LOWORD(lParam), farenin pencerenin istemci alanına göre tıklatıldığı X ekseni aygıt koordinatını içerir.

HIWORD(lParam) Y ekseni koordinatını içerir.

*Wparam*<br/>
kullanılmaz ve sıfır olur. İade değeri sıfır değilse, WinHelp bu bağlamla çağrılır. İade değeri sıfırsa, üst pencere yardım için sorgulanır.

Çoğu durumda, zaten sahip olabileceğiniz isabet testi kodundan yararlanabilirsiniz. WM_HELPHITTEST iletisini `CToolBar::OnHelpHitTest` işleme örneğinin uygulanmasına bakın (kod düğmelerde ve araç uçlarında kullanılan `CControlBar`hit test kodundan yararlanır).

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC Uygulama Sihirbazı Desteği ve MAKEHM

MFC Uygulama Sihirbazı, Yardım dosyası (.cnt ve .hpj dosyaları) oluşturmak için gerekli dosyaları oluşturur. Ayrıca, Microsoft Yardım Derleyicisi tarafından kabul edilen önceden oluşturulmuş .rtf dosyaları da içerir. Konuların çoğu tamamlandı, ancak bazı özel uygulama için değiştirilmesi gerekebilir.

"Yardım eşleme" dosyasının otomatik olarak oluşturulması MAKEHM adlı bir yardımcı program tarafından desteklenir. MAKEHM yardımcı programı bir uygulamanın KAYNAK çevirebilirsiniz. Bir Yardım eşleme dosyasına H dosyası. Örneğin:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

şu şekilde tercüme edilecektir:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

Bu biçim, bağlam lı lık adlarını (sağ taraftaki sayılar) konu adlarıyla (sol taraftaki semboller) eşleyen Yardım derleyicisi tesisiyle uyumludur.

MAKEHM için kaynak kodu MFC Programlama Utilities örnek [MAKEHM](../overview/visual-cpp-samples.md)mevcuttur.

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı Çalıştırdıktan Sonra Yardım Desteği Ekleme

Uygulamanıza Yardım eklemenin en iyi yolu, uygulamanızı oluşturmadan önce MFC Uygulama Sihirbazı'nın Gelişmiş Özellikler sayfasındaki "İçeriğe Duyarlı Yardım" seçeneğini denetlemektir. Bu şekilde MFC Uygulama Sihirbazı, Yardım'ı `CWinApp`desteklemek için türetilmiş sınıfınıza gerekli ileti eşlemi girişlerini otomatik olarak ekler.

## <a name="help-on-message-boxes"></a>İleti Kutularına Yardım

İleti Kutuları'ndaki yardım (bazen uyarı olarak `AfxMessageBox` da adlandırılır), Windows `MessageBox` API'sının bir paketleyicisi olan işlev aracılığıyla desteklenir.

İki sürümü vardır `AfxMessageBox`, bir dize kimliği ile kullanmak için ve`LPCSTR`başka bir dize için bir işaretçi ile kullanmak için ( ): :

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

Her iki durumda da isteğe bağlı bir Yardım Kimliği vardır.

İlk durumda, nIDHelp için varsayılan 0, bu ileti kutusu için hiçbir Yardım gösterir. Kullanıcı ileti kutusu gibi ileti kutusu etkinken F1 tuşuna basıyorsa, kullanıcı Yardım almaz (uygulama Yardım'ı desteklese bile). Bu istif edilmezse, nIDHelp için bir Yardım Kimliği sağlanmalıdır.

İkinci durumda, nIDHelp için varsayılan değer -1'dir ve Yardım Kimliği nIDPrompt ile aynı dır. Yardım yalnızca uygulama Yardım etkinse, elbette çalışır). İleti kutusunun yardım desteği olmamasını istiyorsanız nIDHelp için 0 sağlamalısınız. İletinin Yardım'ın etkin olmasını, ancak nIDPrompt'dan farklı bir yardım kimliği istemesini istiyorsanız, nIDPrompt'dan farklı nIDHelp için olumlu bir değer sağlamanız yeterlidir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
