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
ms.openlocfilehash: bdd405bda5c0af9e04a50eee4ef5738f3a53259e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370402"
---
# <a name="tn021-command-and-message-routing"></a>TN021: Komut ve İleti Yönlendirme

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, komut yönlendirme ve gönderme mimarisinin yanı sıra genel pencere ileti yönlendirmesi gelişmiş konuları açıklar.

Burada açıklanan mimariler hakkında genel ayrıntılar, özellikle Windows iletileri, denetim bildirimleri ve komutlar arasındaki ayrım için Visual C++ bölümüne bakın. Bu not, yazdırılan belgelerde açıklanan konulara çok aşina olduğunuzu varsayar ve yalnızca çok gelişmiş konuları ele alar.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Komut Yönlendirme ve Gönderme MFC 1.0 İşlevselliği MFC 2.0 Mimarisine Evrilir

Windows menü komutları, hızlandırıcı anahtarları ve iletişim denetimi bildirimleri bildirimleri sağlamak için aşırı yüklenen WM_COMMAND iletisi vardır.

MFC 1.0, türemiş bir sınıftaki bir komut işleyicinin (örneğin, `CWnd` "OnFileNew") belirli bir WM_COMMAND yanıt olarak çağrılmasını sağlayarak bunun üzerine inşa edilmiştir. Bu, ileti eşlemi adı verilen bir veri yapısıyla birlikte yapıştırılır ve çok yer açısından verimli bir komut mekanizmasıyla sonuçlanır.

MFC 1.0 ayrıca denetim bildirimlerini komut iletilerinden ayırmak için ek işlevsellik de sağladı. Komutlar, bazen Komut Kimliği olarak da bilinen 16 bitlik bir kimlikle temsil edilir. Komutlar normalde bir `CFrameWnd` (yani bir menü seçimi veya çevrilmiş hızlandırıcı) başlar ve diğer pencerelerin çeşitli yönlendirilir olsun.

MFC 1.0, Çoklu Belge Arabiriminin (MDI) uygulanması için sınırlı bir anlamda komut yönlendirmesini kullandı. (MDI çerçeve penceresi temsilcisi etkin MDI Alt penceresine komut verir.)

Bu işlevsellik genelleştirilmiş ve komutların daha geniş bir nesne aralığı (yalnızca pencere nesneleri tarafından değil) tarafından işletilmesine izin vermek için MFC 2.0'da genişletilmiştir. İletileri yönlendirmek için daha resmi ve genişletilebilir bir mimari sağlar ve komutların yalnızca işlenmesi için değil, aynı zamanda bir komutun geçerli kullanılabilirliğini yansıtacak şekilde Kullanıcı Arabirimi nesnelerini (menü öğeleri ve araç çubuğu düğmeleri gibi) güncelleştirmek için komut hedef yönlendirmesini yeniden kullanır.

## <a name="command-ids"></a>Komut Kimlikleri

Komut yönlendirme ve bağlama işleminin açıklaması için Visual C++ bölümüne bakın. [Teknik Not 20,](../mfc/tn020-id-naming-and-numbering-conventions.md) kimlik adlandırma hakkında bilgi içerir.

Komut tanlamaları için genel öneki "ID_" kullanırız. Komut iLikleri >= 0x8000'dir. İleti satırı veya durum çubuğu, komut kimliğiyle aynı kimlikleri içeren bir STRINGTABLE kaynağı varsa komut açıklaması dizesini gösterir.

Uygulamanızın kaynaklarında, komut kimliği çeşitli yerlerde görünebilir:

- İleti satırı istemiyle aynı kıta sahip bir STRINGTABLE kaynağında.

- Muhtemelen aynı komutu çağıran menü öğelerine iliştirilen birçok MENÜ kaynağında.

- (ADVANCED) bir GOSUB komutu için bir iletişim düğmesinde.

Uygulamanızın kaynak kodunda, komut kimliği çeşitli yerlerde görünebilir:

- KAYNAK'ınızda. Uygulamaya özgü komut tanımlarını tanımlamak için H (veya diğer ana sembol üstbilgi dosyası).

- BELKI bir araç çubuğu oluşturmak için kullanılan bir kimlik dizisinde.

- ON_COMMAND bir makroda.

- BELKI bir ON_UPDATE_COMMAND_UI makro.

Şu anda, MFC'de komut iliklerinin >= 0x8000 gerektiren tek uygulama GOSUB iletişim lerinin/komutlarının uygulanmasıdır.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>GOSUB Komutları, İletişimLerde Komut Mimarisini Kullanma

Yönlendirme ve komutları etkinleştirme komut mimarisi çerçeve pencereleri, menü öğeleri, araç çubuğu düğmeleri, iletişim çubuğu düğmeleri, diğer denetim çubukları ve istek ve rota komutları veya denetim düğmeleri bir ana komut hedefi (genellikle ana çerçeve penceresi) için güncellemek için tasarlanmış diğer kullanıcı arabirimi öğeleri ile iyi çalışır. Bu ana komut hedefi, komut veya denetim bildirimlerini uygun şekilde diğer komut hedef nesnelerine yönlendirebilir.

İletişim denetimidenetimini uygun komut kimliğine atarsanız, iletişim kutusu (modal veya modeless) komut mimarisinin bazı özelliklerinden yararlanabilir. İletişim iletişimleri için destek otomatik değildir, bu nedenle bazı ek kod yazmak zorunda klabilirsiniz.

Tüm bu özelliklerin düzgün çalışması için komut larınızın >= 0x8000 olması gerektiğini unutmayın. Birçok iletişim kutusu aynı kareye yönlendirilebildiği için paylaşılan komutlar >= 0x8000, belirli bir iletişim kutusundaki paylaşılmayan IDC'ler ise = 0x7FFF <olmalıdır.

Uygun komut kimliğine ayarlanan düğmenin IDC'si ile normal bir modal iletişim kutusuna normal bir düğme yerleştirebilirsiniz. Kullanıcı düğmeyi seçtiğinde, iletişim kutusunun sahibi (genellikle ana çerçeve penceresi) komutu diğer komutlar gibi alır. Genellikle başka bir iletişim (ilk iletişim bir GOSUB) getirmek için kullanıldığından bu bir GOSUB komutu denir.

Ayrıca iletişim günlüğündeki `CWnd::UpdateDialogControls` işlevi arayabilir ve ana çerçeve pencerenizin adresini geçirebilirsiniz. Bu işlev, iletişim denetimlerinizi çerçevede komut işleyicileri olup olmadığına bağlı olarak etkinleştirebilir veya devre dışı kılır. Bu işlev, uygulamanızın boşta döngüdeki denetim çubukları için otomatik olarak çağrılır, ancak bu özelliğe sahip olmak istediğiniz normal iletişim leri doğrudan aramanız gerekir.

## <a name="when-on_update_command_ui-is-called"></a>ON_UPDATE_COMMAND_UI Çağrıldığında

Bir programın tüm menü öğelerinin etkin/denetlenmiş durumunu her zaman korumak hesaplama açısından pahalı bir sorun olabilir. Yaygın bir teknik, menü öğelerini yalnızca kullanıcı POPUP'ı seçtiğinde etkinleştirmek/denetlemektir. MFC 2.0 uygulaması `CFrameWnd` WM_INITMENUPOPUP iletisini işler ve ON_UPDATE_COMMAND_UI işleyicileri aracılığıyla menülerin durumlarını belirlemek için komut yönlendirme mimarisini kullanır.

`CFrameWnd`ayrıca durum çubuğunda (ileti satırı olarak da bilinir) seçilen geçerli menü öğesini açıklamak için WM_ENTERIDLE iletisini işler.

Visual C++tarafından düzenlenen bir uygulamanın menü yapısı, WM_INITMENUPOPUP anda kullanılabilir olası komutları temsil etmek için kullanılır. ON_UPDATE_COMMAND_UI işleyicileri bir menünün durumunu veya metnini değiştirebilir veya gelişmiş kullanımlar için (File MRU listesi veya OLE Verbs açılır menüsü gibi), menü çizilmeden önce menü yapısını değiştirebilir.

Uygulama boşta döngüye girdiğinde, araç çubukları (ve diğer denetim çubukları) için de aynı tür ON_UPDATE_COMMAND_UI işleme yapılır. Denetim çubukları hakkında daha fazla bilgi için *Sınıf Kitaplığı Başvurusu* ve [Teknik Not 31'e](../mfc/tn031-control-bars.md) bakın.

## <a name="nested-pop-up-menus"></a>İç Içe Açılan Menüler

İç içe bir menü yapısı kullanıyorsanız, açılır menüdeki ilk menü öğesinin ON_UPDATE_COMMAND_UI işleyicisinin iki farklı durumda çağrıldığını fark edeceksiniz.

İlk olarak, açılır menü kendisi için çağrılır. Açılır menülerde kimlik olmadığı için bu gereklidir ve açılan menünün ilk menü öğesinin kimliğini tüm açılır menüye başvurmak için kullanırız. Bu durumda, *m_pSubMenu* nesnenin `CCmdUI` m_pSubMenu üye değişkeni NULL olmayan olacaktır ve açılır menüyü gösterir.

İkinci olarak, açılır menüdeki menü öğeleri çizilmeden hemen önce çağrılır. Bu durumda, kimlik yalnızca ilk menü öğesine *m_pSubMenu* başvurur ve `CCmdUI` nesnenin m_pSubMenu üye değişkeni NULL olacaktır.

Bu, açılır menü öğesini menü öğelerinden farklı olarak etkinleştirmenize olanak tanır, ancak bazı menü farkında kod yazmanızı gerektirir. Örneğin, aşağıdaki yapıya sahip iç içe bir menüde:

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

ID_NEW_SHEET ve ID_NEW_CHART komutları bağımsız olarak etkinleştirilebilir veya devre dışı bırakılır. İkisinden biri etkinse **Yeni** açılır menü etkinleştirilmelidir.

ID_NEW_SHEET için komut işleyicisi (açılır penceredeki ilk komut) aşağıdaki gibi görünür:

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

ID_NEW_CHART için komut işleyicisi normal bir güncelleştirme komut işleyicisi olacaktır ve aşağıdaki gibi bir şey görünür:

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="on_command-and-on_bn_clicked"></a>ON_COMMAND ve ON_BN_CLICKED

**ON_COMMAND** ve **ON_BN_CLICKED** için ileti eşlemi makroları aynıdır. MFC komut ve denetim bildirim yönlendirme mekanizması, nereye yönlendireceğine karar vermek için yalnızca komut kimliğini kullanır. Kontrol bildirim kodu sıfır **(BN_CLICKED)** olan denetim bildirimleri komut olarak yorumlanır.

> [!NOTE]
> Aslında, tüm denetim bildirim iletileri komut işleyicisi zincirinden geçer. Örneğin, teknik olarak belge sınıfınızda **EN_CHANGE** için bir denetim bildirim işleyicisi yazmanız mümkündür. Bu özelliğin pratik uygulamaları az olduğundan, özellik ClassWizard tarafından desteklenmez ve özelliğin kullanımı kırılgan kodneden olabilir, çünkü bu genellikle tavsiye edilmez.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Düğme Kontrollerinin Otomatik Devre Dışı Bırakılması Devre

Bir iletişim çubuğuna veya CWnd'yi aradığınız yeri kullanarak bir iletişim kutusuna bir düğme denetimi **yerseniz::UpdateDialogControls** kendi başına, **ON_COMMAND** veya **ON_UPDATE_COMMAND_UI** işleyicileri olmayan düğmelerin çerçeve tarafından sizin için otomatik olarak devre dışı bırakıldığını fark esiniz. Bazı durumlarda, bir işleyiciniz olması gerekmez, ancak düğmenin etkin kalmasını istersiniz. Bunu başarmanın en kolay yolu, bir kukla komut işleyicisi eklemektir (ClassWizard ile yapması kolay) ve içinde hiçbir şey yapmamaktır.

## <a name="window-message-routing"></a>Pencere İletisi Yönlendirme

Aşağıda, MFC sınıfları ve Windows ileti yönlendirmesi ve diğer konuların bunları nasıl etkilediği ile ilgili daha gelişmiş bazı konular açıklanmaktadır. Buradaki bilgiler yalnızca kısa bir süre açıklanmıştır. Genel API'ler hakkında ayrıntılar için *Sınıf Kitaplığı Başvurusu'na* bakın. Uygulama ayrıntıları hakkında daha fazla bilgi için lütfen MFC kitaplık kaynak koduna bakın.

Tüm **CWnd**türetilmiş sınıflar için çok önemli bir konu olan Pencere temizleme yle ilgili ayrıntılar için lütfen [Teknik Not 17'ye](../mfc/tn017-destroying-window-objects.md) bakın.

## <a name="cwnd-issues"></a>CWnd Sorunları

Uygulama üye işlevi **CWnd::OnChildNotify,** alt pencereler (denetimler olarak da bilinir) için, ebeveynlerine (veya "sahibine" giden iletiler, komutlar ve denetim bildirimleri) kancaya takmak veya başka bir şekilde bilgilendirilmek için güçlü ve genişletilebilir bir mimari sağlar. Alt pencere (/denetim) C++ **CWnd** nesnesinin kendisiyse, sanal işlev **OnChildNotify** ilk olarak özgün iletideki parametrelerle (yani bir **MSG** yapısı) çağrılır. Alt pencere iletiyi rahat bırakabilir, yiyebilir veya üst öğeiçin iletiyi değiştirebilir (nadir).

Varsayılan **CWnd** uygulaması aşağıdaki iletileri işler ve alt pencerelerin (denetimlerin) iletiye ilk erişmesine izin vermek için **OnChildNotify** kancasını kullanır:

- **WM_MEASUREITEM** ve **WM_DRAWITEM** (kendi kendine çizmek için)

- **WM_COMPAREITEM** ve **WM_DELETEITEM** (kendi kendine çizmek için)

- **WM_HSCROLL** ve **WM_VSCROLL**

- **Wm_ctlcolor**

- **WM_PARENTNOTIFY**

**OnChildNotify** kancasının, sahip çizim iletilerini kendi kendine çizilen iletilere dönüştürmek için kullanıldığını fark edeceksiniz.

**OnChildNotify** kancasına ek olarak, kaydırma iletilerinin yönlendirme davranışı daha da vardır. Kaydırma çubukları ve **WM_HSCROLL** kaynakları ve **WM_VSCROLL** mesajları hakkında daha fazla bilgi için lütfen aşağıya bakın.

## <a name="cframewnd-issues"></a>CFrameWnd Sorunları

**CFrameWnd** sınıfı, uygulamanın çoğunu komut yönlendirme ve kullanıcı arabirimi güncelleştirme sağlar. Bu öncelikle uygulamanın ana çerçeve penceresi için kullanılır (**CWinApp::m_pMainWnd**) ancak tüm çerçeve pencereleri için geçerlidir.

Ana çerçeve penceresi menü çubuğunun olduğu penceredir ve durum çubuğunun veya ileti satırının üst öğesidir. Lütfen komut yönlendirme ve WM_INITMENUPOPUP yukarıdaki tartışmaya **bakın.**

**CFrameWnd** sınıfı etkin görünümün yönetimini sağlar. Aşağıdaki iletiler etkin görünüm üzerinden yönlendirilir:

- Tüm komut iletileri (etkin görünüm onlara ilk erişim alır).

- **Kardeş** kaydırma çubuklarından gelen WM_HSCROLL ve **WM_VSCROLL** iletileri (aşağıya bakın).

- **WM_ACTIVATE** (ve MDI için **WM_MDIACTIVATE)** sanal işlev **CView::OnActivateView**aramaları dönüştü olsun.

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/CMDIChildWnd Sorunları

Her iki MDI çerçeve pencere sınıfları **CFrameWnd** türetilmiştir ve bu nedenle her ikisi de **cframeWnd**sağlanan komut yönlendirme ve kullanıcı arabirimi güncelleştirme aynı tür için etkindir. Tipik bir MDI uygulamasında, yalnızca ana çerçeve penceresi (diğer bir deyişle **CMDIFrameWnd** nesnesi) menü çubuğunu ve durum çubuğunu tutar ve bu nedenle komut yönlendirme uygulamasının ana kaynağıdır.

Genel yönlendirme şeması, etkin MDI alt penceresinin komutlara ilk erişimi elde etmesidir. Varsayılan **PreTranslateMessage** işlevleri, hem MDI alt pencereleri (ilk) hem de MDI çerçevesi (ikinci) ve normalde **TranslateMDISysAccel** (son) tarafından işlenen standart MDI sistem komut hızlandırıcıları için hızlandırıcı tablolarını işler.

## <a name="scroll-bar-issues"></a>Kaydırma Çubuğu Sorunları

Kaydırma iletisini **(WM_HSCROLL**/**OnHScroll** ve/veya **WM_VSCROLL**/**OnVScroll)** işlerken, kaydırma çubuğu iletisinin nereden geldiğine dayanmaması için işleyici kodunu yazmayı denemelisiniz. Kaydırma iletileri gerçek kaydırma çubuğu denetimlerinden veya kaydırma çubuğu denetimleri olmayan **WS_HSCROLL**/**WS_VSCROLL** kaydırma çubuklarından gelebileceğinden, bu yalnızca genel bir Windows sorunu değildir.

MFC, kaydırma çubuğu denetimlerinin kaydırılmakta olan pencerenin alt veya kardeşleri olmasına olanak sağlayacak şekilde genişletir (aslında, kaydırma çubuğu ile kaydırılan pencere arasındaki üst/alt ilişkisi herhangi bir şey olabilir). Bu, özellikle splitter pencereli paylaşılan kaydırma çubukları için önemlidir. Paylaşılan kaydırma çubuğu sorunları hakkında daha fazla bilgi de dahil olmak üzere **CSplitterWnd'in** uygulanmasıyla ilgili ayrıntılar için lütfen [Technical Note 29'a](../mfc/tn029-splitter-windows.md) bakın.

Bir yan notta, oluşturma zamanında belirtilen kaydırma çubuğu stillerinin sıkışıp kaldığı ve Windows'a geçirilmediği iki **CWnd** türetilmiş sınıf vardır. Bir oluşturma yordamına geçirildiğinde, **WS_HSCROLL** ve **WS_VSCROLL** bağımsız olarak ayarlanabilir, ancak oluşturmadan sonra değiştirilemez. Tabii ki, doğrudan test etmemelisiniz veya oluşturdukları pencerenin WS_SCROLL stil bitlerini ayarlamak.

**CMDIFrameWnd** için **Oluşturma** veya **LoadFrame** için geçtiğiniz kaydırma çubuğu stilleri MDICLIENT oluşturmak için kullanılır. Kaydırılabilir bir MDICLIENT alanına (Windows Program Yöneticisi gibi) sahip olmak istiyorsanız, **CMDIFrameWnd'i**oluşturmak için kullanılan stil için her iki kaydırma çubuğu stilini (&#124; **WS_VSCROLL****WS_HSCROLL)** ayarladığınızdan emin olun.

**CSplitterWnd** için kaydırma çubuğu stilleri, ayırıcı bölgeleri için özel paylaşılan kaydırma çubuklarına uygulanır. Statik ayırıcı pencereler için normalde kaydırma çubuğu stilini ayarlamazsınız. Dinamik ayırıcı pencereler için, genellikle bölüneceğiniz yön için kaydırma çubuğu stili ni ayarlarsınız, yani satırları bölebiliyorsanız **WS_HSCROLL,** **WS_VSCROLL** sütunları bölebilirseniz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
