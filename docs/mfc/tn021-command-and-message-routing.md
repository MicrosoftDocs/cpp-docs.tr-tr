---
description: 'Hakkında daha fazla bilgi edinin: TN021: komut ve Ileti yönlendirme'
title: 'TN021: Komut ve İleti Yönlendirme'
ms.date: 06/28/2018
f1_keywords:
- vc.routing
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
ms.openlocfilehash: 3cc481585fa2f1eacc3deb575e163d5a1644002c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215852"
---
# <a name="tn021-command-and-message-routing"></a>TN021: Komut ve İleti Yönlendirme

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, komut yönlendirme ve dağıtım mimarisinin yanı sıra genel pencere ileti yönlendirmesinde gelişmiş konular açıklanmaktadır.

Burada açıklanan mimarilerde, özellikle Windows iletileri, denetim bildirimleri ve komutlar arasındaki ayrım hakkında genel Ayrıntılar için Visual C++ bakın. Bu notta, yazdırılmış belgelerde açıklanan sorunlar hakkında bilgi sahibi olduğunuz ve yalnızca çok gelişmiş konuların adresleyen varsayılmaktadır.

## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Komut yönlendirme ve dağıtma MFC 1,0 Işlevleri MFC 2,0 mimarisine gelişir

Windows 'un, menü komutları, hızlandırıcı tuşları ve iletişim denetimi bildirimleri bildirimleri sağlamak için aşırı yüklenmiş WM_COMMAND iletisi vardır.

Bir türetilmiş sınıftaki komut işleyicisine (örneğin, "OnFileNew") `CWnd` belirli bir WM_COMMAND yanıt olarak çağrılması için izin vererek oluşturulan MFC 1,0. Bu, ileti eşlemesi olarak adlandırılan bir veri yapısıyla birlikte gruplandırılır ve çok boşluklu bir komut mekanizmasıyla sonuçlanır.

MFC 1,0 ayrıca komut iletilerinden Denetim bildirimlerini ayırmak için ek işlevler sağlamıştır. Komutlar, bazen komut KIMLIĞI olarak da bilinen 16 bit KIMLIK ile temsil edilir. Komutlar normalde bir (yani `CFrameWnd` , bir menü Seç veya çevrilmiş Hızlandırıcı) ile başlar ve diğer birçok Windows 'a yönlendirilir.

MFC 1,0 birden çok belge arabirimi (MDI) uygulamasına yönelik sınırlı bir anlamda komut yönlendirmesi kullandı. (Bir MDI çerçevesi penceresi, etkin MDI alt penceresine komutlar verin.)

Bu işlevsellik,, komutların daha geniş nesneler (yalnızca pencere nesneleri değil) tarafından işlenmesine izin vermek için MFC 2,0 ' de Genelleştirilmiş ve genişletilmiştir. Yönlendirme iletileri için daha resmi ve genişletilebilir bir mimari sağlar ve komut hedef yönlendirmeyi yalnızca komutların işlenmesiyle (menü öğeleri ve araç çubuğu düğmeleri gibi), bir komutun geçerli kullanılabilirliğini yansıtacak şekilde yeniden kullanır.

## <a name="command-ids"></a>Komut Kimlikleri

Komut yönlendirme ve bağlama işleminin açıklaması için bkz. Visual C++. [Teknik notta 20](../mfc/tn020-id-naming-and-numbering-conventions.md) kimlik adlandırmayla ilgili bilgiler yer alır.

Komut kimlikleri için "ID_" genel önekini kullanıyoruz. Komut kimlikleri >= 0x8000 ' dır. Komut KIMLIĞIYLE aynı kimliklere sahip bir STRINGTABLE kaynağı varsa, ileti çizgisi veya durum çubuğu komut açıklama dizesini gösterir.

Uygulamanızın kaynaklarında, bir komut KIMLIĞI birkaç yerde görüntülenebilir:

- İleti satırı istemiyle aynı KIMLIĞE sahip bir STRINGTABLE kaynağında.

- Aynı komutu çağıran menü öğelerine eklenen çok sayıda menü kaynağı.

- (GELIŞMIŞ) GOSUB komutuna ait bir iletişim kutusunda.

Uygulamanızın kaynak kodunda, bir komut KIMLIĞI birkaç yerde görüntülenebilir:

- . Uygulamaya özgü komut kimliklerini tanımlamak için H (veya diğer ana sembol üstbilgi dosyası).

- BELKI de bir araç çubuğu oluşturmak için kullanılan bir KIMLIK dizisinde.

- ON_COMMAND makroda.

- BELKI de bir ON_UPDATE_COMMAND_UI makrosunda.

Şu anda, MFC 'deki komut kimliklerini gerektiren tek uygulama, GOSUB iletişimleri/komutlarının uygulamasıdır >= 0x8000 olmalıdır.

## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>GOSUB komutları, Iletişim kutularında komut mimarisini kullanma

Yönlendirme ve etkinleştirme komutlarının komut mimarisi, çerçeve pencereleri, menü öğeleri, araç çubuğu düğmeleri, iletişim çubuğu düğmeleri, diğer denetim çubukları ve isteğe bağlı olarak güncelleştirilecek ve komutları veya denetim kimliklerini bir ana komut hedefi (genellikle ana çerçeve penceresi) için tasarlanan diğer kullanıcı arabirimi öğeleriyle sorunsuz bir şekilde çalışabilir. Bu ana komut hedefi, komut veya Denetim bildirimlerini uygun şekilde diğer komut hedefi nesnelerine yönlendirebilir.

İletişim kutusu denetiminin denetim KIMLIĞINI uygun komut KIMLIĞINE atarsanız, bir iletişim kutusu (kalıcı veya kalıcı olmayan), komut mimarisinin bazı özelliklerinden faydalanabilirsiniz. İletişim kutuları için destek otomatik değildir, bu nedenle bazı ek kodlar yazmanız gerekebilir.

Tüm bu özelliklerin düzgün şekilde çalışması için komut kimliklerinizin >= 0x8000 olması gerektiğini unutmayın. Birçok iletişim kutusu aynı çerçeveye yönlendirildiğinden, paylaşılan komutların >= 0x8000 olması gerekir, ancak belirli bir iletişim kutusunda paylaşılmayan IDCs <= 0x7FFF olmalıdır.

Normal bir düğmeyi, Button 'ın IDC öğesinin uygun komut KIMLIĞINE ayarlandığı bir normal kalıcı iletişim kutusuna yerleştirebilirsiniz. Kullanıcı düğmeyi seçtiğinde, iletişim kutusunun sahibi (genellikle ana çerçeve penceresi) komutu diğer tüm komutde olduğu gibi alır. Genellikle başka bir iletişim kutusu (ilk iletişim kutusunun GOSUB) getirmek için kullanıldığından, bu bir GOSUB komutu olarak adlandırılır.

Ayrıca, iletişim kutusunda işlevini çağırıp `CWnd::UpdateDialogControls` ana çerçeve pencerenizin adresini geçirebilirsiniz. Bu işlev, iletişim denetim denetimlerinizi çerçevede komut işleyicileri olup olmadığına göre etkinleştirir veya devre dışı bırakır. Bu işlev, uygulamanızın boşta döngüsünde denetim çubukları için otomatik olarak çağrılır, ancak bu özelliği kullanmak istediğiniz normal iletişim kutuları için doğrudan çağırmanız gerekir.

## <a name="when-on_update_command_ui-is-called"></a>ON_UPDATE_COMMAND_UI çağrıldığında

Tüm bir programın menü öğelerinin etkin/işaretli durumunun sürdürülmesi, her zaman pahalı maliyetli bir sorun olabilir. Ortak bir teknik, menü öğelerini yalnızca Kullanıcı açılan pencereyi seçtiğinde etkinleştirir/denetmektir. MFC 2,0 uygulamasının `CFrameWnd` WM_INITMENUPOPUP iletisini işler ve ON_UPDATE_COMMAND_UI işleyiciler aracılığıyla menülerin durumlarını öğrenmek için komut yönlendirme mimarisini kullanır.

`CFrameWnd` Ayrıca durum çubuğunda seçilen geçerli menü öğesini (ileti satırı olarak da bilinir) tanımlayacak WM_ENTERIDLE iletisini işler.

Visual C++ tarafından düzenlenen bir uygulamanın menü yapısı, WM_INITMENUPOPUP zamanında kullanılabilir olan olası komutları temsil etmek için kullanılır. ON_UPDATE_COMMAND_UI işleyicileri, bir menünün durumunu veya metnini değiştirebilir veya gelişmiş kullanımlar için (dosya MRU listesi veya OLE fiilleri açılır menüsü gibi), menü yapısını menü çizilmeden önce değiştirir.

Uygulama boşta döngüsünü girdiğinde araç çubukları (ve diğer denetim çubukları) için aynı ON_UPDATE_COMMAND_UI işleme sıralaması yapılır. Denetim çubukları hakkında daha fazla bilgi için bkz. *sınıf kitaplığı başvurusu* ve [teknik notta 31](../mfc/tn031-control-bars.md) .

## <a name="nested-pop-up-menus"></a>İç içe açılır menüler

İç içe geçmiş bir menü yapısı kullanıyorsanız, açılır menüdeki ilk menü öğesi için ON_UPDATE_COMMAND_UI işleyicisinin iki farklı durumda çağrıldığını görürsünüz.

İlk olarak, açılır menünün kendisi için çağrılır. Bu, Açılır menülerin kimlikleri olmadığından ve açılan menünün tamamına başvurmak için açılır menünün ilk menü öğesinin KIMLIĞINI kullandığımızda gereklidir. Bu durumda, nesnenin *m_pSubMenu* üye değişkeni `CCmdUI` null değil ve açılır menüyü işaret edecektir.

İkinci olarak, açılır menüdeki menü öğeleri çizilmeden hemen önce çağrılır. Bu durumda, KIMLIK yalnızca ilk menü öğesine başvurur ve nesnenin *m_pSubMenu* üye değişkeni `CCmdUI` null olur.

Bu, menü öğelerinden farklı açılır menüyü etkinleştirmenizi sağlar, ancak bazı menü duyarlı kodlar yazmanızı gerektirir. Örneğin, aşağıdaki yapıyla iç içe geçmiş bir menüde:

```Output
File>
    New>
    Sheet (ID_NEW_SHEET)
    Chart (ID_NEW_CHART)
```

ID_NEW_SHEET ve ID_NEW_CHART komutları bağımsız olarak etkinleştirilebilir veya devre dışı bırakılabilir. İki ikisinden biri etkinse **Yeni** açılır menü etkinleştirilmelidir.

ID_NEW_SHEET için komut işleyicisi (açılır pencere içindeki ilk komut) şöyle görünür:

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

ID_NEW_CHART için komut işleyicisi, normal bir güncelleştirme komut işleyicisi olur ve şunun gibi görünür:

```cpp
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)
{
    pCmdUI->Enable(m_bCanCreateChart);
}
```

## <a name="on_command-and-on_bn_clicked"></a>ON_COMMAND ve ON_BN_CLICKED

**ON_COMMAND** ve **ON_BN_CLICKED** için ileti eşleme makroları aynıdır. MFC komutu ve denetim bildirimi yönlendirme mekanizması, yalnızca yönlendirileceğine karar vermek için komut KIMLIĞINI kullanır. Sıfır (**BN_CLICKED**) denetim bildirimi koduyla denetim bildirimleri komut olarak yorumlanır.

> [!NOTE]
> Aslında, tüm denetim bildirim iletileri komut işleyici zinciri aracılığıyla gider. Örneğin, belge sınıfınıza **EN_CHANGE** için bir denetim bildirim işleyicisi yazmanız Teknik olarak mümkündür. Bu özellik genellikle önerilmez, çünkü bu özelliğin pratik uygulamalarının çok az olması, özelliğin ClassWizard tarafından desteklenmediği ve özelliğinin kullanılması, kırarak koda neden olabilir.

## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Düğme denetimlerinin otomatik olarak devre dışı bırakılmasını devre dışı bırakma

Bir iletişim çubuğuna düğme denetimi yerleştirirseniz veya kendi oluşturduğunuz **CWnd:: UpdateDialogControls** öğesini kullanarak bir iletişim kutusunda, **ON_COMMAND** veya **ON_UPDATE_COMMAND_UI** işleyicileri olmayan düğmelerin, çerçeve tarafından sizin için otomatik olarak devre dışı bırakılacağını görürsünüz. Bazı durumlarda, bir işleyiciniz olması gerekmez, ancak düğmenin etkin kalmasını isteyeceksiniz. Bunu başarmanın en kolay yolu, bir kukla komut işleyicisi eklemektir (ClassWizard ile kolayca yapılır) ve içinde hiçbir şey yapmaz.

## <a name="window-message-routing"></a>Pencere Iletisi yönlendirme

Aşağıda, MFC sınıfları ve Windows ileti yönlendirmenin ve diğer konuların bunları nasıl etkilediği hakkında daha gelişmiş konular açıklanmaktadır. Buradaki bilgiler yalnızca kısaca açıklanmıştır. Ortak API 'Ler hakkında ayrıntılı bilgi için *sınıf kitaplığı başvurusuna* bakın. Uygulama ayrıntıları hakkında daha fazla bilgi için lütfen MFC kitaplığı kaynak koduna bakın.

Tüm **CWnd**-türetilmiş sınıflar için çok önemli bir konu olan pencere temizleme hakkındaki ayrıntılar Için lütfen [teknik nota](../mfc/tn017-destroying-window-objects.md) bakın.

## <a name="cwnd-issues"></a>CWnd sorunları

Uygulama üyesi işlevi **CWnd:: Onchildnotıfy** , ana pencereler için (denetimler olarak da bilinir), üst öğe (veya "sahip") giden iletileri, komutları ve Denetim bildirimlerini bağlamak veya bunlarla haberdar olmak için güçlü ve genişletilebilir bir mimari sağlar. Alt pencere (/Control) bir C++ **CWnd** nesnesinin kendisi Ise, **onchildnotıfy** sanal işlevi ilk iletiden (yani, bir **msg** yapısı) parametreler ile önce çağırılır. Alt pencere iletiyi tek başına bırakabilir, bir şekilde bırakabilir veya üst öğe (nadir) için iletiyi değiştirebilir.

Varsayılan **CWnd** uygulamasının aşağıdaki iletileri işler ve alt pencerelerin (denetimlerin) ileti üzerinde ilk erişimine izin vermek Için **OnChildNotify** kancasını kullanır:

- **WM_MEASUREITEM** ve **WM_DRAWITEM** (kendi kendine çizim için)

- **WM_COMPAREITEM** ve **WM_DELETEITEM** (kendi kendine çizim için)

- **WM_HSCROLL** ve **WM_VSCROLL**

- **WM_CTLCOLOR**

- **WM_PARENTNOTIFY**

**Onchildnotıfy** kancasını, sahip çizim iletilerini otomatik çizim iletilerine dönüştürmek için kullanıldığını fark edeceksiniz.

**OnChildNotify** kancalarına ek olarak, kaydırma iletilerinin daha fazla yönlendirme davranışı vardır. Kaydırma çubukları ve **WM_HSCROLL** ve **WM_VSCROLL** iletilerinin kaynakları hakkında daha fazla bilgi için lütfen aşağıya bakın.

## <a name="cframewnd-issues"></a>CFrameWnd sorunları

**CFrameWnd** sınıfı, komut yönlendirme ve Kullanıcı arabirimi güncelleştirme uygulamasının çoğunu sağlar. Bu, öncelikle uygulamanın ana çerçeve penceresi (**CWinApp:: m_pMainWnd**) için kullanılır, ancak tüm çerçeve pencereleri için geçerlidir.

Ana çerçeve penceresi, menü çubuğunu içeren pencere ve durum çubuğunun veya ileti hattının üst öğesidir. Lütfen komut yönlendirme ve WM_INITMENUPOPUP yukarıdaki tartışmaya bakın **.**

**CFrameWnd** sınıfı, etkin görünümün yönetimini sağlar. Aşağıdaki iletiler etkin görünüm aracılığıyla yönlendirilir:

- Tüm komut iletileri (etkin görünüm bunlara ilk erişimi alır).

- Eşdüzey kaydırma çubuklarındaki iletileri **WM_HSCROLL** ve **WM_VSCROLL** (aşağıya bakın).

- **WM_ACTIVATE** (ve **WM_MDIACTIVATE** MDI), **CView:: OnActivateView** sanal işlevine yönelik çağrılara açıktır.

## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/Cmdicchild Dwnd sorunları

Hem MDI çerçeve pencere sınıfları **CFrameWnd** 'den türetilir ve bu nedenle, **CFrameWnd** içinde sağlanan aynı komut yönlendirme ve Kullanıcı arabirimi güncelleştirmesi sıralaması için her ikisi de etkinleştirilir. Tipik bir MDI uygulamasında, yalnızca ana çerçeve penceresi (yani **Cmdiframewnd** nesnesi) menü çubuğunu ve durum çubuğunu ve bu nedenle komut yönlendirme uygulamasının ana kaynağıdır.

Genel Yönlendirme şeması, etkin MDI alt penceresinin komutlara ilk erişimi aldığından emin olur. Varsayılan **PreTranslateMessage** işlevleri, hem MDI alt pencereleri (ilk) hem de MDI çerçevesi (ikinci) için Hızlandırıcı tablolarını ve normal olarak **Translatemdisyısaccel** (son) tarafından işlenen standart MDI sistem komut hızlandırıcılarını işler.

## <a name="scroll-bar-issues"></a>Kaydırma çubuğu sorunları

Kaydırma iletisi (**WM_HSCROLL** / **OnHScroll** ve/veya **WM_VSCROLL** / **OnVScroll**) işlenirken, kaydırma çubuğu iletisinin geldiği yere dayanmaması için işleyici kodunu yazmayı denemelisiniz. Bu yalnızca genel bir Windows sorunu değildir. çünkü, kaydırma iletileri doğru kaydırma çubuğu denetimlerinden veya  / kaydırma çubuğu denetimleri olmayan ws_hscroll **ws_vscroll** kaydırma çubuklarıyla gelebilir.

MFC, kaydırma çubuğu denetimlerinin kaydırılmakta olan pencerenin alt ya da eşdüzey öğelerinin (Aslında, kaydırma çubuğu ve kaydırılan pencere arasındaki üst/alt ilişki herhangi bir şey olabilir) izin vermek için bunu genişletir. Bu, özellikle bölünmüş pencereler ile paylaşılan kaydırma çubukları için önemlidir. Paylaşılan kaydırma çubuğu sorunları hakkında daha fazla bilgi dahil olmak üzere **CSplitterWnd** uygulamasının ayrıntıları Için lütfen [Teknik notun 29](../mfc/tn029-splitter-windows.md) bölümüne bakın.

Bir yan notta, oluşturma zamanında belirtilen kaydırma çubuğu stillerinin yakalanıp Windows 'a geçirilmediği iki **CWnd** türetilmiş sınıfı vardır. Oluşturma yordamına geçirildiğinde, **ws_hscroll** ve **ws_vscroll** bağımsız olarak ayarlanabilir, ancak oluşturma işleminden sonra değiştirilemez. Kuşkusuz, oluşturdukları pencerenin WS_SCROLL stili bitlerini doğrudan test etmeniz veya ayarlamanız gerekir.

**Cmdiframewnd** Için, **oluşturma** veya **LoadFrame** 'e geçirdiğiniz kaydırma çubuğu stilleri, MDICLIENT oluşturmak için kullanılır. Kaydırılabilir bir MDıCLıENT alanına (Windows Program Yöneticisi gibi) sahip olmak istiyorsanız, **Cmdiframewnd** oluşturmak için kullanılan stil için kaydırma çubuğu stillerini (**ws_hscroll** &#124; **ws_vscroll**) ayarladığınızdan emin olun.

**CSplitterWnd** için kaydırma çubuğu stilleri, Splitter bölgeleri için özel paylaşılan kaydırma çubukları için geçerlidir. Statik Bölümlendirici pencereler için normalde, kaydırma çubuğu stilini ayarlayacaksınız. Dinamik Bölümlendirici pencereleri için genellikle, bölüneceği yönle ilgili kaydırma çubuğu stili ayarlanmış olur, diğer bir deyişle, satırları bölebiliyorsanız **ws_hscroll** , sütunları bölebiliyorsanız **ws_vscroll** .

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
