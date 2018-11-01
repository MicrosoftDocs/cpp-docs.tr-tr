---
title: 'TN021: Komut ve İleti Yönlendirme'
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: 4a0774234e6314ff6811bbeafa11403f19cf568e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50635714"
---
# <a name="tn021-command-and-message-routing"></a>TN021: Komut ve İleti Yönlendirme

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, Gelişmiş konularına genel bir pencere ileti yönlendirme yanı sıra komut Yönlendirme ve gönderme mimarisini açıklar.

Lütfen Visual C++ için genel ayrıntılar için burada açıklanan mimarilerde özellikle Windows iletileri, Denetim bildirimleri ve komutlar arasında ayrım bakın. Bu Not yazdırılan belgelerinde açıklanan sorunları çok aşina olduğu ve yalnızca çok Gelişmiş konular ele varsayar.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Komut Yönlendirme ve gönderme MFC 1.0 işlevselliği geliştikçe MFC'ye 2.0 mimarisi

Windows, menü komutlarını Hızlandırıcı tuşları ve iletişim denetim bildirimleri bildirimleri sağlamak için aşırı yüklenmiş WM_COMMAND ileti vardır.

MFC 1.0 yerleşik üzerinde biraz bir komut işleyici (örneğin, "OnFileNew") sağlayarak bir `CWnd` yanıt olarak belirli bir WM_COMMAND çağrılmadığı türetilmiş. Bu ileti eşlemesi adlı bir veri yapısı ile birlikte yapışmış ve çok verimli alan komut mekanizması sonuçlanır.

MFC 1.0 de komut iletilerini denetim bildirimleri ayırmak için ek işlevler sağlanır. Komutlar, bazen bir komut kimliği bilinen 16-bit kimliği tarafından temsil edilir Komutlar normal şekilde başlatın bir `CFrameWnd` (diğer bir deyişle, bir menü seçeneğini belirleyin veya çevrilmiş bir Hızlandırıcı) ve diğer windows çeşitli yönlendirilir.

MFC 1.0 Çok Belgeli Arabirim (MDI) uygulaması için sınırlı anlamda komut yönlendirme kullanılır. (Bir MDI çerçeve penceresinin temsilci komutları, etkin MDI alt penceresine.)

Bu işlev, genelleştirilmiş ve MFC 2. 0'ı geniş bir grup nesneleri (yalnızca pencere nesneleri) tarafından işlenecek komutlarına izin vermek için genişletilmiş. Daha fazla resmi sağlar ve genişletilebilir mimari Yönlendirme iletilerini ve komut hedef yalnızca komutların işleme için aynı zamanda kullanıcı Arabirimi nesneleri (örneğin, menü öğeleri ve araç çubuğu düğmeleri) bir komut geçerli kullanılabilirliğini yansıtacak şekilde güncelleştirmek için yönlendirme kullanır .

## <a name="command-ids"></a>Komut Kimlikleri

Visual C++, Yönlendirme ve model bağlama işleminden komutu bir açıklaması için bkz. [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md) kimliği adlandırma hakkında bilgi içerir.

Komut kimlikleri için genel ön eki "ID_" kullanırız. Komut kimlikleri > = 0x8000. İleti satırı veya durum çubuğu komut açıklama dizesi olarak komut kimliği. aynı kimlikleri STRINGTABLE kaynak olup olmadığını gösterir

Kaynakları, uygulamanızın kimliği için bir komut çeşitli yerlerde görünür:

- Satır içi iletisi istemi aynı Kimliğe sahip bir STRINGTABLE kaynakta.

- Aynı komutu çağıran menü öğelerine bağlı muhtemelen çoğu menü kaynakları.

- Bir iletişim düğmesinde GOSUB komutu için (Gelişmiş).

Uygulamanızın kaynak kodunda kimliği için bir komut çeşitli yerlerde görünür:

- KAYNAĞINIZDA. Y (veya diğer ana sembol başlık dosyası) uygulamaya özgü komut kimlikleri tanımlamak için.

- Araç çubuğu oluşturmak için kullanılan belki de bir kimliği dizide.

- ON_COMMAND makrosu içinde.

- BELKİ de bir on_update_command_uı makrosu.

Şu anda yalnızca komut kimlikleri gerektiren bir MFC uygulamasında olması > = 0x8000 GOSUB iletişim kutuları/komutları uygulamasıdır.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>İletişim kutularındaki komut mimarisi kullanarak, GOSUB komutları

Çerçeve pencereleri, menü öğeleri, araç çubuğu düğmeleri, iletişim çubuğu düğmelerinin, diğer denetim çubuklarını ve isteğe bağlı ve rota komutları güncelleştirmesi veya bir ana kimlikleri denetlemek için tasarlanmış diğer kullanıcı arabirimi öğeleri ile Yönlendirme ve komutları etkinleştirme komut mimarisi çalışır komut hedefi (genellikle ana çerçeve penceresinin). Komut veya denetim bildirimleri ana komutu hedefleyen diğer komut hedef nesneleri uygun şekilde yönlendirmek.

Denetim Kimliği iletişim denetimi için uygun komut kimliği atarsanız (kalıcı veya kısıtlayıcı olmayan) bir iletişim komutu mimarisinin özelliklerinden bazıları yararlanabilir İletişim kutuları için destek otomatik, değil, birkaç ek kod yazmanız gerekebilir.

Düzgün çalışması tüm bu özellikler için komut kimlikleri olması gerektiğini unutmayın > = 0x8000. Birçok iletişim kutuları için aynı çerçeve yönlendirilen olduğundan, paylaşılan komutları olmalıdır > 0x8000, belirli bir iletişim kutusu paylaşılmayan IDCs olmalıdır ancak = < 0x7FFF =.

IDC için uygun komut Kimliği Ayarla düğmesi ile normal kalıcı iletişim kutusu, normal bir düğme yerleştirebilirsiniz Kullanıcı düğmeyi seçtiğinde, iletişim kutusu (genellikle ana çerçeve penceresinin) sahibi olduğu gibi başka bir komut komutu alır. (İlk iletişim GOSUB) başka bir iletişim kutusunu açmak için genellikle kullanıldığından bu GOSUB komut adı verilir.

İşlevi ayrıca çağırabilir `CWnd::UpdateDialogControls` , iletişim kutusunda, ana çerçeve penceresinin adres geçirin. Bu işlevi etkinleştirmek veya komut işleyicileri çerçevede olup olmadığını göre iletişim kutusu denetimleri devre dışı bırakın. Bu işlev otomatik olarak sizin için uygulamanızın boşta döngü denetim çubukları için çağrılır, ancak bu özelliğe sahip olmasını istediğiniz doğrudan normal iletişim kutuları için çağırmanız gerekir.

## <a name="when-onupdatecommandui-is-called"></a>On_update_command_uı olduğunda çağrılır

Her zaman bir programın tüm menü öğelerini etkin ve kullanıma durumunu korumak için hesaplama açısından pahalı bir sorun olabilir. Yalnızca kullanıcı açılan seçtiğinde menü öğeleri etkinleştirme/denetimi için ortak bir tekniktir. MFC 2.0 uygulamasını `CFrameWnd` WM_INITMENUPOPUP ileti işleme ve komut yönlendirme mimarisi on_update_command_uı işleyicileri menülerde durumlarını belirlemek için kullanır.

`CFrameWnd` Ayrıca durum çubuğunda (ileti satırı olarak da bilinir) seçili öğe geçerli menü açıklamak için WM_ENTERIDLE ileti işler.

Uygulama menüsü yapısı, Visual C++ tarafından düzenlenemez WM_INITMENUPOPUP zaman kullanılabilir olası komutları temsil etmek için kullanılır. On_update_command_uı işleyicileri, durum veya bir menü metnini değiştirme veya menü çizilmeden önce (dosya MRU Listesi veya OLE fiilleri açılan menü gibi) Gelişmiş kullanımları gerçekten menüsü yapısı değiştirin.

Araç çubukları (ve diğer denetim çubukları) on_update_command_uı işleme aynı sıralama yapılır, boşta döngü girdiğinde uygulama. Bkz: *sınıf kitaplığı başvurusu* ve [Teknik Not 31](../mfc/tn031-control-bars.md) denetim çubukları hakkında daha fazla bilgi için.

## <a name="nested-pop-up-menus"></a>İç içe açılır menüler

İç içe geçmiş menüsü yapısı kullanıyorsanız, ilk açılan menü öğesi için on_update_command_uı işleyicisi iki farklı durumlarda çağrılır fark edeceksiniz.

İlk olarak, açılan menü için kendisini adlandırılır. Bu, açılır menüler kimliklere sahip olmadığınızdan ve açılır menüsünden ilk menü öğesinin kimliği tüm menüye başvurmak için kullandığımız için gereklidir. Bu durumda, *m_pSubMenu* üye değişkeninin `CCmdUI` nesnesi NULL olmayan olacaktır ve açılır menüyü işaret edecek.

İkinci olarak, yalnızca çizilecek menü öğelerinin açılan menüden çıkmadan önce çağrılır. Bu durumda, kimliği yalnızca ilk menü öğesine başvurur ve *m_pSubMenu* üye değişkeninin `CCmdUI` nesnesi NULL olacaktır.

Bu, açılan menüyü menü öğelerinden farklı etkinleştirmenize izin verir, ancak bazı menü uyumlu kod yazmanız gerekir. Örneğin, bir iç içe geçmiş menüde aşağıdaki yapıya sahip:

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

ID_NEW_SHEET ve ID_NEW_CHART komutlar bağımsız olarak devre dışı bırakabilir veya etkinleştirilebilir. **Yeni** iki ya da etkinse açılır menü'nin etkinleştirilmesi gerekir.

Komut işleyici ID_NEW_SHEET (açılan ilk komut) için şunun gibi görünür:

```cpp
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)
{
    if (pCmdUI->m_pSubMenu != NULL)
    {
        // enable entire pop-up for "New" sheet and chart
        BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;
        // CCmdUI::Enable is a no-op for this case, so we
        // must do what it would have done.
        pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex,
            MF_BYPOSITION |
            (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

        return;
    }
    // otherwise just the New Sheet command
    pCmdUI->Enable(m_bCanCreateSheet);
}
```

Komut işleyici ID_NEW_CHART için normal güncelleştirme komut işleyicisi ve görünüm şuna benzer olacaktır:

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="oncommand-and-onbnclicked"></a>ON_COMMAND ve ON_BN_CLICKED

İleti eşleme makroları için **ON_COMMAND** ve **ON_BN_CLICKED** aynıdır. MFC komut ve denetim bildirimi yönlendirme mekanizması yalnızca yönlendirmek nereye iletileceğine karar veren komut Kimliğini kullanır. Denetim bildirimleri denetim bildirimi koduyla sıfır (**BN_CLICKED**) komutları yorumlanır.

> [!NOTE]
> Aslında, tüm denetimi bildirim iletileri komut işleyicisi domainproperty'leri gidin. Örneğin, bir denetim bildirimi işleyicisi yazmanız için teknik olarak mümkün **EN_CHANGE** belge sınıfınızdaki. Bu pratik uygulamalar, bu özelliğin birkaç özellik ClassWizard tarafından desteklenmez ve kırılgan kodda özelliğinin kullanımına neden olabilir çünkü genellikle önerilmez.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Otomatik düğme denetimleri devre dışı bırakma devre dışı bırakma

Bir iletişim çubuğu üzerindeki bir düğme denetimi getirin ya da nereye kullanarak iletişim kutusunda, aradığınız **CWnd::UpdateDialogControls** sizin olmayan düğmeler görürsünüz **ON_COMMAND** veya **On_update_command_uı** işleyicileri otomatik olarak devre dışı bırakılacak sizin için framework tarafından. Bazı durumlarda, bir işleyici olması gerekmez, ancak etkin kalmaya devam düğmesine isteyeceksiniz. Bunu yapmanın en kolay yolu (ClassWizard ile kolayca) bir işlevsiz bir komut işleyici eklemektir ve boş yapın.

## <a name="window-message-routing"></a>Pencere ileti yönlendirme

Aşağıdaki MFC sınıflarını ve nasıl Windows ileti yönlendirme ve diğer konular etkileyen bazı daha ileri seviyeli konulara açıklar. Buradaki bilgiler yalnızca kısaca açıklanmıştır. Başvurmak *sınıf kitaplığı başvurusu* genel API'ler ile ilgili ayrıntılar için. MFC Kitaplığı kaynak kodunu uygulama ayrıntıları hakkında daha fazla bilgi için bkz.

Lütfen [Teknik Not 17](../mfc/tn017-destroying-window-objects.md) penceresi temizleme hakkında ayrıntılı bilgi, tüm için çok önemli bir konu **CWnd**-türetilmiş sınıflar.

## <a name="cwnd-issues"></a>CWnd sorunları

Uygulama üye işlevi **CWnd::OnChildNotify** kanca veya iletileri, komutlar ve denetim Aksi takdirde bilgilendirilmek alt pencereler (denetimleri olarak da bilinir) için güçlü ve Genişletilebilir bir mimari sağlar. kendi üst (veya "sahip") Git bildirimleri. Varsa alt penceresi (/ Denetim) bir c++ **CWnd** kendisi, sanal işlev nesnesi **OnChildNotify** parametrelerle özgün iletiden önce çağırılır (diğer bir deyişle, bir **MSG**yapısı). Alt pencere iletiyi bırakır, Yemek veya üst (nadir) iletiyi değiştirin.

Varsayılan **CWnd** uygulama aşağıdaki iletileri işler ve kullandığı **OnChildNotify** kanca alt iletiye ilk erişmek için windows (denetimler) izin vermek için:

- **WM_MEASUREITEM** ve **WM_DRAWITEM** (için kendi kendine çizmek)

- **WM_COMPAREITEM** ve **WM_DELETEITEM** (için kendi kendine çizmek)

- **WM_HSCROLL** ve **WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

Fark edeceksiniz **OnChildNotify** kanca, sahip çizim iletileri kendi kendine çizmek iletilere değiştirmek için kullanılır.

Ek olarak **OnChildNotify** kanca, kaydırma iletileriniz davranışını daha fazla yönlendirme. Lütfen aşağıda kaydırma çubukları ve kaynakları hakkında daha fazla bilgi için bkz **WM_HSCROLL** ve **WM_VSCROLL** iletileri.

## <a name="cframewnd-issues"></a>CFrameWnd sorunları

**CFrameWnd** SAX komut Yönlendirme ve kullanıcı arabirimi çoğu uygulama güncelleştiriliyor. Bu uygulamanın ana çerçeve penceresi için öncelikli olarak kullanılır (**CWinApp::m_pMainWnd**) ancak tüm çerçeve pencereleri için geçerlidir.

Ana çerçeve penceresinin menü çubuğunu penceresiyle ve durum çubuğunun üst veya ileti satır. Komut yönlendirme yukarıdaki bilgi edinmek ve **WM_INITMENUPOPUP.**

**CFrameWnd** sınıfı etkin görünüm yönetimini sağlar. Şu iletilerden etkin görünüm yönlendirilir:

- Tüm komut iletileri (ilk erişim sağlaması için etkin görünüm alır).

- **WM_HSCROLL** ve **WM_VSCROLL** eşdüzey iletilerden kaydırma çubukları (aşağıya bakın).

- **WM_ACTIVATE** (ve **WM_MDIACTIVATE** MDI için) sanal işlev için çağrılar içine açık **CView::OnActivateView**.

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/Cmdıchildwnd sorunları

Her iki MDI çerçeve penceresi sınıfları türetilmesi **CFrameWnd** ve bu nedenle her ikisi de aynı sıralama komut yönlendirme etkinleştirilir ve kullanıcı arabirimi güncelleştirilirken karşılaşılan **CFrameWnd**. Tipik bir MDI uygulamasında yalnızca ana çerçeve penceresi (diğer bir deyişle, **CMDIFrameWnd** nesnesi) menü çubuğu ve durum çubuğu tutar ve bu nedenle komut yönlendirme uygulamasının ana kaynağı.

Genel Yönlendirme etkin MDI alt penceresine ilk komutlarına erişimi alır düzenidir. Varsayılan **PreTranslateMessage** işlevleri işlemek için her iki MDI alt pencereleri Hızlandırıcı tabloları (ilk) ve MDI çerçeve tarafından normal olarak ele standart MDI sistem komutu Hızlandırıcıları yanı sıra (saniye)  **TranslateMDISysAccel** (son).

## <a name="scroll-bar-issues"></a>Kaydırma çubuğu sorunları

Kaydırma iletisi işlenirken (**WM_HSCROLL**/**OnHScroll** ve/veya **WM_VSCROLL**/**OnVScroll**), burada kaydırma çubuğu iletinin geldiği kullanmayan şekilde işleyicisi kodu yazmak çalışmanız gerekir. Kaydırma iletileri doğru kaydırma çubuğu denetimleri veya gelen gelebilir olduğundan bu yalnızca bir genel Windows sorunu değildir **WS_HSCROLL**/**WS_VSCROLL** kaydırma çubuğu denetimleri olmayan Çubukları'e gidin.

MFC, alt veya eşdüzey kaydırılan pencerenin gibi kaydırma çubuğu denetimleri için izin verecek şekilde genişletir (aslında, üst/alt ilişkisi kaydırılan penceresi ve kaydırma çubuğu arasında herhangi bir şey olabilir). Bu, özellikle Bölümlendirici pencereler ile paylaşılan kaydırma çubukları için önemlidir. Lütfen [Teknik Not 29](../mfc/tn029-splitter-windows.md) uygulanışı hakkında ayrıntılı bilgi için **CSplitterWnd** paylaşılan kaydırma çubuğu sorunları dahil daha fazla bilgi.

Yan Not üzerinde var olan iki **CWnd** durum belirtilen kaydırma çubuğu stilleri oluşturduğunuz zaman türetilen sınıfların yakalanan ve Windows için geçmedi. Bir oluşturma yordamına geçirildiğinde **WS_HSCROLL** ve **WS_VSCROLL** bağımsız olarak ayarlanabilir, ancak oluşturulduktan değiştirilemez. Elbette, doğrudan test veya gerekir oluşturdukları penceresinin WS_SCROLL stili BITS ayarlayın.

İçin **CMDIFrameWnd** kaydırma çubuğu stilleri, için geçirdiğiniz **Oluştur** veya **LoadFrame** MDICLIENT oluşturmak için kullanılır. Ayarladığınızdan emin olun kaydırılabilir bir MDICLIENT alanı (gibi Windows programı Yöneticisi) sahip olmasını isterseniz, her ikisi de kaydırma stilleri (**WS_HSCROLL** &#124; **WS_VSCROLL**) oluşturmakiçinkullanılanstil**CMDIFrameWnd**.

İçin **CSplitterWnd** kaydırma çubuğu stilleri özel paylaşılan kaydırma çubuklarının Bölümlendirici bölgeleri için geçerlidir. Statik Bölümlendirici pencereler için ya da kaydırma çubuğu stili olarak normalde. Dinamik Bölümlendirici pencereler için kaydırma çubuğunu stil kümesi ikiye bölerek, diğer bir deyişle, yön için genellikle olacaktır **WS_HSCROLL** satır bölmeniz **WS_VSCROLL** sütunları bölmeniz.

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
