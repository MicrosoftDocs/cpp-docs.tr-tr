---
description: 'Hakkında daha fazla bilgi edinin: TN028: Context-Sensitive yardım desteği'
title: 'TN028: Bağlama Duyarlı Yardım Desteği'
ms.date: 11/04/2016
f1_keywords:
- vc.help
helpviewer_keywords:
- context-sensitive Help [MFC], MFC applications
- TN028
- resource identifiers, context-sensitive Help
ms.assetid: 884f1c55-fa27-4d4c-984f-30907d477484
ms.openlocfilehash: 96dd1d4356ac226d9377e14985de46e3d0f680ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215657"
---
# <a name="tn028-context-sensitive-help-support"></a>TN028: Bağlama Duyarlı Yardım Desteği

Bu notta, MFC 'de yardım bağlamları kimlikleri ve diğer yardım sorunları atamaya yönelik kurallar açıklanmaktadır. Bağlama duyarlı yardım desteği, Visual C++ bulunan yardım derleyicisini gerektirir.

> [!NOTE]
> MFC kullanılarak bağlama duyarlı yardım uygulamaya ek olarak, MFC HTML Yardımı kullanmayı da destekler. Bu destek ve HTML Yardımı ile programlama hakkında daha fazla bilgi için bkz. [HTML Yardımı: programlarınıza yönelik yardım Context-Sensitive](../mfc/html-help-context-sensitive-help-for-your-programs.md).

## <a name="types-of-help-supported"></a>Desteklenen yardım türleri

Windows uygulamalarında uygulanan iki tür bağlama duyarlı yardım vardır. Birincisi, "F1 Help" olarak anılan geçerli etkin nesneyi temel alan uygun bağlamla WinHelp başlatmasını içerir. İkinci değer "SHIFT + F1" modudur. Bu modda, fare imleci Yardım imlecine dönüşür ve Kullanıcı bir nesneye tıklamasını sağlar. Bu noktada, Kullanıcı tıklamış nesne için yardım sağlamak üzere WinHelp başlatılır.

Microsoft Foundation Sınıfları bu yardım biçimlerinin her ikisini de uygular. Ayrıca Framework iki basit Yardım komutunu destekler, Yardım dizini ve yardım kullanımı.

## <a name="help-files"></a>Yardım dosyaları

Microsoft Foundation sınıfları, tek bir yardım dosyasını kabul eder. Bu yardım dosyası uygulamayla aynı ada ve yola sahip olmalıdır. Örneğin, çalıştırılabilir C:\MyApplication\MyHelp.exe, yardım dosyası C:\MyApplication\MyHelp.hlp. olmalıdır Yolu, [CWinApp sınıfının](../mfc/reference/cwinapp-class.md) *m_pszHelpFilePath* üye değişkeni aracılığıyla ayarlarsınız.

## <a name="help-context-ranges"></a>Yardım bağlamı aralıkları

MFC 'nin varsayılan uygulanması, yardım bağlam kimliklerinin atanması hakkında bazı kuralları izlemek için bir program gerektirir. Bu kurallar, belirli denetimlere ayrılan bir kimlik aralığıdır. Bu kuralları, yardım ile ilgili çeşitli üye işlevlerinin farklı uygulamalarını sağlayarak geçersiz kılabilirsiniz.

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

## <a name="simple-help-commands"></a>Basit "yardım" komutları

Microsoft Foundation Sınıfları tarafından uygulanan iki basit yardım komutu vardır:

- [CWinApp:: OnHelpIndex](../mfc/reference/cwinapp-class.md#onhelpindex) tarafından uygulanan ID_HELP_INDEX

- [CWinApp:: OnHelpUsing](../mfc/reference/cwinapp-class.md#onhelpusing) tarafından uygulanan ID_HELP_USING

İlk komut, uygulamanın Yardım dizinini gösterir. İkincisi, WinHelp programını kullanma konusunda Kullanıcı yardımını gösterir.

## <a name="context-sensitive-help-f1-help"></a>Context-Sensitive yardım (F1 yardımı)

F1 tuşu genellikle ana pencerenin Hızlandırıcı tablosuna yerleştirilmiş bir hızlandırıcı tarafından ID_HELP KIMLIĞI olan bir komuta çevrilir. ID_HELP komutu, ana pencerede veya iletişim kutusunda ID_HELP KIMLIKLI bir düğme tarafından da oluşturulabilir.

ID_HELP komutunun nasıl oluşturulduğuna bakılmaksızın, bir komut işleyicisine ulaşıncaya kadar normal komut olarak yönlendirilir. MFC komut yönlendirme mimarisi hakkında daha fazla bilgi için, [Teknik not21](../mfc/tn021-command-and-message-routing.md)' e bakın. Uygulamanın yardımı etkinse, ID_HELP komutu [CWinApp:: OnHelp](../mfc/reference/cwinapp-class.md#onhelp)tarafından işlenir. Uygulama nesnesi yardım iletisini alır ve sonra komutu uygun şekilde yönlendirir. Varsayılan komut yönlendirmesi en belirli bağlamı belirlemek için yeterli olmadığından, bu gereklidir.

`CWinApp::OnHelp` WinHelp 'yi aşağıdaki sırada başlatmaya çalışır:

1. Yardım KIMLIĞIYLE etkin bir çağrı olup olmadığını denetler `AfxMessageBox` . Şu anda bir ileti kutusu etkin ise, WinHelp bu ileti kutusuna uygun olan bağlamla başlatılır.

1. Etkin pencereye bir WM_COMMANDHELP iletisi gönderir. Bu pencere WinHelp 'yi başlatarak yanıt vermezse, ileti işlenene veya geçerli pencere üst düzey bir pencere olana kadar aynı ileti bu pencerenin üst öğelerinden gönderilir.

1. Ana pencereye bir ID_DEFAULT_HELP komutu gönderir. Bu, varsayılan yardımı çağırır. Bu komut genellikle ile eşleştirilir `CWinApp::OnHelpIndex` .

Varsayılan KIMLIK taban değerlerini genel olarak geçersiz kılmak için (örn., komutlar için 0x10000 ve iletişim kutuları gibi kaynaklar için 0x20000), uygulama [CWinApp:: WinHelp](../mfc/reference/cwinapp-class.md#winhelp)' i geçersiz kılmalıdır.

Bu işlevselliği ve bir yardım bağlamının belirlendiği yöntemi geçersiz kılmak için WM_COMMANDHELP iletisini işlemeniz gerekir. Yalnızca geçerli MDI alt penceresi kadar derin olduğu için Framework 'ün sağladığı daha özel yardım yönlendirmesi sağlamak isteyebilirsiniz. Ayrıca, söz konusu nesnenin geçerli iç durumuna veya iletişim kutusundaki etkin denetime bağlı olarak belirli bir pencere veya iletişim için daha özel yardım sağlamak isteyebilirsiniz.

## <a name="wm_commandhelp"></a>WM_COMMANDHELP

```

afx_msg LRESULT CWnd::OnCommandHelp(WPARAM wParam, LPARAM lParam)
```

WM_COMMANDHELP, yardım istendiğinde etkin pencere tarafından alınan özel bir Windows MFC iletisidir. Pencere bu iletiyi aldığında `CWinApp::WinHelp` pencerenin iç durumuyla eşleşen bağlamla çağrı gösterebilir.

*lParam*<br/>
Şu anda kullanılabilir yardım bağlamını içerir. Yardım bağlamı belirlenmiyorsa, *lParam* sıfırdır. Bir uygulanması, `OnCommandHelp` farklı bir bağlam belirleyebilmek Için *lParam* içindeki bağlam kimliğini kullanabilir veya yalnızca öğesine geçirebilir `CWinApp::WinHelp` .

*wParam*<br/>
Kullanılmaz ve sıfır olacaktır.

`OnCommandHelp`İşlev çağırırsa `CWinApp::WinHelp` , **true** döndürmelidir. **Doğru** döndürme, bu komutun diğer sınıflara ve diğer pencereler için yönlendirilmesini engeller.

## <a name="help-mode-shiftf1-help"></a>Yardım modu (Shift + F1 Help)

Bu, bağlama duyarlı yardım 'ın ikinci biçimidir. Genellikle, bu mod SHIFT + F1 tuşlarına basarak veya menü/araç çubuğu aracılığıyla girilir. Bir komut (ID_CONTEXT_HELP) olarak uygulanır. İleti filtresi kancası, kalıcı bir iletişim kutusu veya menü etkinken bu komutu çevirmek için kullanılmaz, bu nedenle bu komut yalnızca uygulama ana ileti göndericisinin () yürütüldüğü sırada Kullanıcı tarafından kullanılabilir `CWinApp::Run` .

Bu modu girdikten sonra, uygulama normalde bu alan için kendi imlecini (pencerenin etrafında boyutlandırma kenarlığı gibi) görüntülemesine rağmen yardım fare imleci uygulamanın tüm alanlarında gösterilir. Kullanıcı fare veya klavyeyi kullanarak bir komut seçebilir. Komutu yürütmek yerine bu komutla ilgili yardım görüntülenir. Ayrıca, kullanıcı ekrandaki bir düğme gibi görünür bir nesneye tıklayabilir ve bu nesne için yardım gösterilecektir. Bu Yardım modu tarafından sağlanır `CWinApp::OnContextHelp` .

Bu döngünün yürütülmesi sırasında, menüye erişen anahtarlar hariç tüm klavye girişi etkin değildir. Ayrıca, `PreTranslateMessage` kullanıcının bir Hızlandırıcı tuşuna basması ve bu komutla ilgili yardım almasına izin vermek için ile komut çevirisi de gerçekleştirilir.

`PreTranslateMessage`İşlev ÜZERINDE SHIFT + F1 Yardım modu sırasında gerçekleşmemesi gereken belirli Çeviriler veya eylemler varsa,  `CWinApp` bu işlemleri gerçekleştirmeden önce m_bHelpMode üyesini denetlemeniz gerekir. `CDialog`Uygulamasını `PreTranslateMessage` çağırmadan önce bunu denetler ( `IsDialogMessage` Örneğin,). Bu, SHIFT + F1 modundaki engelleyici olmayan iletişim kutularında "iletişim kutusu gezintisi" tuşlarını devre dışı bırakır. Ayrıca, `CWinApp::OnIdle` Bu döngü sırasında hala çağırılır.

Kullanıcı menüden bir komut seçerse, bu komut için yardım olarak işlenir (WM_COMMANDHELP aracılığıyla, aşağıya bakın). Kullanıcı, uygulamalar penceresinin görünür bir alanına tıklarsa, istemci olmayan tıklama veya istemci tıklamasına bakılmaksızın bir belirleme yapılır. `OnContextHelp` istemci olmayan tıklama eşlemesini istemci otomatik tıklamalarına işler. Bir istemci tıklatıysa, tıklanan pencereye bir WM_HELPHITTEST gönderir. Bu pencere sıfır dışında bir değer döndürürse, bu değer yardım bağlamı olarak kullanılır. Sıfır döndürürse, `OnContextHelp` üst pencereyi dener (ve bunun üst öğesi, onun üstü vb.). Bir yardım bağlamı belirlenemiyorsa, varsayılan olarak, ana pencereye bir ID_DEFAULT_HELP komutu göndermektir ve bu daha sonra (genellikle) ile eşlenir `CWinApp::OnHelpIndex` .

## <a name="wm_helphittest"></a>WM_HELPHITTEST

```

afx_msg LRESULT CWnd::OnHelpHitTest(
WPARAM, LPARAM lParam)
```

WM_HELPHITTEST, SHIFT + F1 Yardım modu sırasında tıklanan etkin pencere tarafından alınan MFC özel bir Windows iletisidir. Pencere bu iletiyi aldığında, WinHelp tarafından kullanılmak üzere bir **DWORD** yardım kimliği döndürür.

LOWORD (lParam), fareyi pencerenin istemci alanına göre tıklandığı X ekseni cihaz koordinatını içerir.

HIWORD (lParam), Y ekseni koordinatlarını içerir.

*wParam*<br/>
kullanılmaz ve sıfır olacaktır. Dönüş değeri sıfır değilse, WinHelp bu bağlamla çağırılır. Dönüş değeri sıfırsa, üst pencere yardım için sorgulanır.

Birçok durumda, zaten sahip olduğunuz isabet sınama kodundan yararlanabilirsiniz. `CToolBar::OnHelpHitTest`WM_HELPHITTEST iletisini işlemeye yönelik bir örnek için uygulamasına bakın (kod, içindeki düğmelerde ve araç ipuçlarında kullanılan isabet sınama kodundan yararlanır `CControlBar` ).

## <a name="mfc-application-wizard-support-and-makehm"></a>MFC Uygulama Sihirbazı desteği ve MAKEHM

MFC Uygulama Sihirbazı bir yardım dosyası (. sayisi ve. hpj dosyaları) oluşturmak için gerekli dosyaları oluşturur. Ayrıca, Microsoft Yardım derleyicisi tarafından kabul edilen bir dizi önceden oluşturulmuş. rtf dosyası da içerir. Konuların birçoğu tamamlanmıştır, ancak belirli uygulamanız için bazı bazı değişiklik yapmanız gerekebilir.

"Yardım eşleme" dosyasının otomatik olarak oluşturulması MAKEHM adlı bir yardımcı program tarafından desteklenir. MAKEHM yardımcı programı bir uygulamanın KAYNAĞıNı çevirebilir. H dosyasına bir yardım eşleme dosyası. Örneğin:

```
#define IDD_MY_DIALOG   2000
#define ID_MY_COMMAND   150
```

Şu şekilde çevrilecek:

```
HIDD_MY_DIALOG    0x207d0
HID_MY_COMMAND    0x10096
```

Bu biçim, içerik kimliklerini (sağ taraftaki sayılar) konu adlarıyla (sol taraftaki simgeler) eşleyen yardım derleyicisinin tesisiyle uyumludur.

MAKEHM kaynak kodu, MFC programlama yardımcı programları örnek [makehm](../overview/visual-cpp-samples.md)içinde bulunabilir.

## <a name="adding-help-support-after-running-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı 'Nı çalıştırdıktan sonra yardım desteği ekleme

Uygulamanıza yardım eklemenin en iyi yolu, uygulamanızı oluşturmadan önce MFC Uygulama Sihirbazı ' nın Gelişmiş Özellikler sayfasında "bağlama duyarlı yardım" seçeneğini deneteklemektir. Bu şekilde, MFC Uygulama Sihirbazı, yardımı desteklemek için, gerekli ileti eşleme girdilerini otomatik olarak `CWinApp` türetilmiş sınıfa ekler.

## <a name="help-on-message-boxes"></a>Ileti kutuları hakkında yardım

Ileti kutuları (bazen uyarılar olarak adlandırılır) hakkında Yardım `AfxMessageBox` , WINDOWS API için bir sarmalayıcı olan işlev aracılığıyla desteklenir `MessageBox` .

Öğesinin iki sürümü vardır `AfxMessageBox` : bir DIZE kimliği ve diğeri bir String () işaretçisi ile kullanım için `LPCSTR` .

```
int AFXAPI AfxMessageBox(LPCSTR lpszText,
    UINT nType,
    UINT nIDHelp);

int AFXAPI AfxMessageBox(UINT nIDPrompt,
    UINT nType,
    UINT nIDHelp);
```

Her iki durumda da isteğe bağlı bir yardım KIMLIĞI vardır.

İlk durumda, nIDHelp için varsayılan değer 0 ' dır ve bu ileti kutusu için yardım yok demektir. İleti kutusu etkinken kullanıcı F1 tuşuna basarsa, Kullanıcı yardım almaz (uygulama yardımı desteklese bile). Bu istenmediğinde, nIDHelp için bir yardım KIMLIĞI sağlanmalıdır.

İkinci durumda, nIDHelp için varsayılan değer-1 ' dir. Bu, yardım KIMLIĞININ nIDPrompt ile aynı olduğunu gösterir. Yardım yalnızca uygulamanın yardım etkin olması durumunda çalışacaktır. İleti kutusunun yardım desteği yoksa, nIDHelp için 0 sağlamanız gerekir. İleti için yardım 'ın etkinleştirilmesini, ancak nIDPrompt 'dan farklı bir yardım KIMLIĞI istesin, nIDPrompt öğesinden farklı nIDHelp için pozitif bir değer sağlamanız gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
