---
title: 'TN021: Komut ve ileti yönlendirme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.routing
dev_langs:
- C++
helpviewer_keywords:
- TN021
- command routing [MFC], technical note TN021
- Windows messages [MFC], routing
ms.assetid: b5952c8b-123e-406c-a36d-a6ac7c6df307
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5a1061f4a7d4394cb84c26514795c406f78146df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn021-command-and-message-routing"></a>TN021: Komut ve İleti Yönlendirme
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not genel pencere ileti akışında Gelişmiş konular yanı sıra komut Yönlendirme ve gönderme mimarisini açıklar.  
  
 Lütfen Visual C++ için burada açıklanan mimarileri hakkında genel bilgi için özellikle Windows iletiler, Denetim bildirimleri ve komutlar arasında ayrım bakın. Bu Not yazdırılan belgelerinde açıklanan sorunları çok bilginiz ve yalnızca çok Gelişmiş konular ele varsayar.  
  
## <a name="command-routing-and-dispatch-mfc-10-functionality-evolves-to-mfc-20-architecture"></a>Komut Yönlendirme ve gönderme MFC 1.0 işlevselliği dönüşmesi MFC 2.0 mimarisi  
 Windows sahip **WM_COMMAND** menü komutlarını Hızlandırıcı tuşları ve iletişim denetim bildirimleri bildirimleri sağlamak için aşırı ileti.  
  
 MFC 1.0 üzerinde biraz bir komut işleyici (örneğin, "OnFileNew") vererek içinde yerleşik bir **CWnd** türetilmiş sınıf belirli bir yanıt çağrılmadığı **WM_COMMAND**. Bu ileti eşlemesi adlı bir veri yapısı birlikte yapışmış ve çok verimli alanı komutu mekanizması olur.  
  
 MFC 1.0 denetimi bildirimleri komutunun iletilerinde ayırmak için ek işlevler de sağlanır. Komutları bazen bir komut kimliği bilinen bir 16 bit kimliği ile temsil edilir Komutları normal olarak başlatmak bir **CFrameWnd** (diğer bir deyişle, menüsünü seçin veya çevrilmiş Hızlandırıcı) ve diğer windows çeşitli yönlendirilen.  
  
 MFC 1.0 birden çok belge arabirimi (MDI) uygulaması için sınırlı bir fikir komut yönlendirme kullanılır. (Bir MDI çerçeve penceresi temsilci kendi etkin MDI alt pencere komutlarına.)  
  
 Bu işlev genelleştirilmiş ve MFC 2. 0'ı geniş bir grup nesneleri (yalnızca penceresi) tarafından işlenecek komutlarına izin vermek için genişletilmiş. Daha fazla resmi sağlar ve yönlendirme için genişletilebilir mimari iletilerini ve komut hedefi için yalnızca komutların işleme, aynı zamanda bir komutu geçerli kullanılabilirliğini yansıtacak şekilde (örneğin, menü öğeleri ve araç çubuğu düğmeleri) kullanıcı Arabirimi nesnelerini güncelleştirme yönlendirme yeniden kullanır .  
  
## <a name="command-ids"></a>Komut Kimlikleri  
 Visual C++ Yönlendirme ve bağlama işlemi komutu bir açıklaması için bkz. [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md) kimliği adlandırma hakkında bilgi içerir.  
  
 Komut kimlikleri için genel önek "ID_" kullanırız. Komut kimlikleri > = 0x8000. İleti satırı veya durum çubuğunda komut açıklama dizesi Komut kimliği ile aynı kimliğiyle STRINGTABLE kaynak olup olmadığını gösterir  
  
 Uygulamanızı kaynaklarında kimliği için bir komut birçok yerde görüntülenir:  
  
-   İleti satırı istemi aynı Kimliğe sahip bir STRINGTABLE kaynak.  
  
-   Aynı komut çağırma menü öğelerini bağlı büyük olasılıkla birçok menü kaynakları.  
  
-   Aç iletişim düğmesini GOSUB komutu için (Gelişmiş).  
  
 Uygulamanızın kaynak kodunu kimliği için bir komut birçok yerde görüntülenir:  
  
-   KAYNAĞINIZ. Y (veya diğer ana sembol üstbilgi dosyası) uygulamaya özgü komut kimlikleri tanımlamak için.  
  
-   Araç çubuğu oluşturmak için kullanılan belki de bir kimliği dizide.  
  
-   İçinde bir **ON_COMMAND** makrosu.  
  
-   BELKİ de bir **on_update_command_uı** makrosu.  
  
 Şu anda, yalnızca komut kimlikleri gerektirir MFC uygulamasında olması > = 0x8000 GOSUB iletişim kutuları/komutları uygulamasıdır.  
  
## <a name="gosub-commands-using-command-architecture-in-dialogs"></a>İletişim kutuları komutu mimarisinde kullanarak GOSUB komutları  
 Çerçeve pencereleri, menü öğeleri, araç çubuğu düğmeleri, iletişim çubuğu düğmelerini, diğer denetim çubukları ve isteğe bağlı ve rota komutları güncelleştirmek veya bir ana kimlikleri denetlemek için tasarlanan diğer kullanıcı arabirimi öğeleri ile Yönlendirme ve komutları etkinleştirme komutu mimarisi çalışır komut hedefi (genellikle ana çerçeve penceresi). Ana komutu hedefleyen uygun olarak diğer komutu hedef nesnelere komut veya denetim bildirimleri yol.  
  
 İletişim denetimi denetim kimliği için uygun komut kimliği atadığınızda, bir iletişim kutusu (kalıcı veya geçici) komutu mimarisinin özelliklerinden bazıları yararlanabilir İletişim kutuları için destek otomatik, değil, bu nedenle birkaç ek kod yazmanız gerekir.  
  
 Düzgün çalışması Bu, tüm özellikler için komut kimlikleri olması gerektiğini unutmayın > = 0x8000. Birçok iletişim kutuları için aynı çerçeve yönlendirilen için paylaşılan komutları olmalıdır > 0x8000, belirli bir iletişim kutusu paylaşılmayan IDCs olması gereken sırada = < 0x7FFF =.  
  
 Normal bir modal iletişim için uygun komut kimliği kümesi düğmesini IDC ile normal bir düğme yerleştirin Kullanıcı düğmesini seçtiğinde (genellikle ana çerçeve penceresi) iletişim sahibi diğer komutu gibi komutu alır. (İlk iletişim GOSUB) başka bir iletişim kutusunu açmak için genellikle kullanıldığından bu GOSUB komutu çağrılır.  
  
 Ayrıca işlev çağırıp **CWnd::UpdateDialogControls** , iletişim kutusundaki ve ana çerçeve penceresi adresini geçirin. Bu işlevi etkinleştirmek veya komut işleyicileri çerçevede olup olmadığını göre iletişim kutusu denetimleri devre dışı. Bu işlev otomatik olarak, Denetim çubuklarını uygulamanızın boşta döngü için çağrılır, ancak bu özelliğe sahip olmasını istediğiniz doğrudan normal iletişim kutuları için çağırmanız gerekir.  
  
## <a name="when-onupdatecommandui-is-called"></a>On_update_command_uı olduğunda çağrılır  
 Her zaman bir programın tüm menü öğelerini etkin ve kullanıma durumunu korumak pkı'ya pahalı bir sorun olabilir. Yalnızca kullanıcı açılan seçtiğinde menü öğelerini etkinleştir/denetimi için ortak bir tekniktir. MFC 2.0 uyarlamasını **CFrameWnd** tanıtıcıları **WM_INITMENUPOPUP** iletisi ve menülerde durumunu belirlemek için komut yönlendirme mimarisini kullanır **ON_UPDATE_COMMAND_ UI** işleyicileri.  
  
 **CFrameWnd** aynı zamanda işleyen **WM_ENTERIDLE** durum çubuğunda (ileti satırı olarak da bilinir) öğesinin seçili geçerli menü açıklayan ileti.  
  
 Visual C++ tarafından düzenlenen bir uygulamanın menü yapısı adresinde olası komutları temsil etmek için kullanılan **WM_INITMENUPOPUP** zaman. **On_update_command_uı** işleyicileri durumunda veya menü metnini değiştirebilirsiniz ya da (dosya MRU Listesi veya OLE Fiiller açılır menü) gibi gelişmiş kullanır gerçekten değiştirmek için önce menü yapısı menü çizilir.  
  
 Aynı sıralama **on_update_command_uı** işleme araç çubukları (ve diğer denetim çubukları) yapılır uygulama boşta döngü girdiğinde. Bkz: *sınıf kitaplığı başvurusu* ve [Teknik Not 31](../mfc/tn031-control-bars.md) denetim çubukları hakkında daha fazla bilgi için.  
  
## <a name="nested-pop-up-menus"></a>İç içe geçmiş açılır menüler  
 İç içe geçmiş menü yapısı kullanıyorsanız, göreceksiniz **on_update_command_uı** işleyicisi açılır menüde ilk menü öğesi için iki farklı durumlarda çağrılır.  
  
 İlk olarak, bu açılır menü için kendisini adı verilir. Açılır menüler kimlikleri yoktur ve tüm açılır menüyü başvurmak için açılır menüyü ilk menü öğesi Kimliğini kullanırız olduğundan bu işlem gereklidir. Bu durumda, **m_pSubMenu** üye değişken **Ccmduı** nesnesi NULL olmamalıdır ve açılır menüyü işaret edecek.  
  
 İkinci olarak, yalnızca açılır menüde menü öğeleri çizilecek önce çağrılır. Bu durumda, yalnızca ilk menü öğesine Kimliğine başvuruyor ve **m_pSubMenu** üye değişken **Ccmduı** nesnesi, NULL olur.  
  
 Bu açılır menü menü öğelerinden farklı etkinleştirmenize olanak sağlar, ancak bazı menü kullanan kodlar yazmak gerektirir. Örneğin, bir iç içe geçmiş menüde şu yapıda:  
  
```  
File>  
    New> 
    Sheet (ID_NEW_SHEET)  
    Chart (ID_NEW_CHART)  
```  
  
 ID_NEW_SHEET ve ID_NEW_CHART komutlar bağımsız olarak devre dışı veya etkinleştirilebilir. **Yeni** iki ya da etkinse açılır menü'nin etkinleştirilmesi gerekir.  
  
 Komut işleyici ID_NEW_SHEET (açılan ilk komutu) için şöyle görünür:  
  
```  
void CMyApp::OnUpdateNewSheet(CCmdUI* pCmdUI)  
{  
    if (pCmdUI->m_pSubMenu != NULL)  
 { *// enable entire pop-up for "New" sheet and chart  
    BOOL bEnable = m_bCanCreateSheet || m_bCanCreateChart;  
 *// CCmdUI::Enable is a no-op for this case,
    so we *//   must do what it would have done.  
    pCmdUI->m_pMenu->EnableMenuItem(pCmdUI->m_nIndex, 
    MF_BYPOSITION |   
 (bEnable  MF_ENABLED : (MF_DISABLED | MF_GRAYED)));

    return; 
 } *// otherwise just the New Sheet command  
    pCmdUI->Enable(m_bCanCreateSheet);

} 
```  
  
 ID_NEW_CHART komut işleyici normal güncelleştirme komut işleyici ve görünüm şuna benzer olacaktır:  
  
```  
void CMyApp::OnUpdateNewChart(CCmdUI* pCmdUI)  
{  
    pCmdUI->Enable(m_bCanCreateChart);

} 
```  
  
## <a name="oncommand-and-onbnclicked"></a>ON_COMMAND ve ON_BN_CLICKED  
 İleti eşleme makroları için **ON_COMMAND** ve **ON_BN_CLICKED** aynıdır. MFC komut ve denetim bildirim yönlendirme yalnızca komut kimliği yönlendirmek yere karar verme için mekanizması kullanır. Denetim bildirimleri denetim bildirim koduyla sıfır (**BN_CLICKED**) komutları olarak yorumlanır.  
  
> [!NOTE]
>  Aslında, tüm denetimi bildirim iletileri komut işleyici zinciri gidin. Örneğin, bir denetim bildirim işleyicisi yazmanız için teknik olarak olası olmakla **EN_CHANGE** belge sınıfınızda. Bu, bu özelliğin pratik uygulamalar birkaç olduğundan, özelliği ClassWizard tarafından desteklenmez ve özelliğinin kırılacak kodda sonuçlanabilir genellikle önerilmez.  
  
## <a name="disabling-the-automatic-disabling-of-button-controls"></a>Otomatik düğmesi denetimleri devre dışı bırakma devre dışı bırakma  
 Bir iletişim çubuğu düğme denetimi yerleştirin ya da nerede kullanarak bir iletişim kutusunda, aradığınız **CWnd::UpdateDialogControls** kendi kendinize, olmayan bu düğmeler görürsünüz **ON_COMMAND** veya **On_update_command_uı** işleyicileri otomatik olarak devre dışı bırakılacak sizin için çerçevesi tarafından. Bazı durumlarda, bir işleyiciye sahip gerekmez, ancak etkin kalmaya devam düğmesine isteyeceksiniz. Bunu elde etmenin en kolay yolu (ClassWizard ile yapmak kolay) bir kukla komut işleyici eklemektir ve boş yapın.  
  
## <a name="window-message-routing"></a>Pencere ileti yönlendirme  
 Aşağıdaki MFC sınıfları ve nasıl ileti Windows Yönlendirme ve diğer konular etkileyen bazı daha gelişmiş konular açıklar. Burada yer alan bilgiler yalnızca kısaca açıklanmıştır. Başvurmak *sınıf kitaplığı başvurusu* ortak API'ler hakkında ayrıntılı bilgi için. MFC kitaplık kaynak kodu uygulama ayrıntıları hakkında daha fazla bilgi için lütfen bakın.  
  
 Lütfen [Teknik Not 17](../mfc/tn017-destroying-window-objects.md) penceresi temizleme hakkında ayrıntılar, tüm için çok önemli bir konu için **CWnd**-türetilmiş sınıfları.  
  
## <a name="cwnd-issues"></a>CWnd sorunları  
 Uygulama üye fonksiyonu **CWnd::OnChildNotify** kanca veya aksi halde, iletileri, komutlar ve denetim haberdar olmak alt windows (denetimleri olarak da bilinir) için güçlü ve Genişletilebilir bir mimari sağlar kendi üst (veya "sahip") için gönderilen bildirimler. Varsa alt pencere (/ kontrol) bir C++ olan **CWnd** kendisini sanal işlev nesnesi **OnChildNotify** parametrelerle özgün iletiden önce çağırılır (diğer bir deyişle, bir **MSG**yapısı). Alt pencere ileti bırakır, onu yemek veya üst (nadir) iletiyi değiştirin.  
  
 Varsayılan **CWnd** uygulama kullanır ve aşağıdaki iletileri işler **OnChildNotify** kanca alt windows (denetimler) ilk erişimi iletiye izin ver:  
  
- **WM_MEASUREITEM** ve **WM_DRAWITEM** (için kendi kendine çizin)  
  
- **WM_COMPAREITEM** ve **WM_DELETEITEM** (için kendi kendine çizin)  
  
- **WM_HSCROLL** ve **WM_VSCROLL**  
  
- **WM_CTLCOLOR**  
  
- **WM_PARENTNOTIFY**  
  
 Fark edeceksiniz **OnChildNotify** kanca sahip çizim iletileri kendi kendine çizin iletilere değiştirmek için kullanılır.  
  
 Ek olarak **OnChildNotify** kanca, kaydırma iletileriniz daha fazla davranış yönlendirme. Lütfen aşağıda kaydırma çubukları ve kaynaklarıyla ilgili daha ayrıntılı bilgi için bkz: **WM_HSCROLL** ve **WM_VSCROLL** iletileri.  
  
## <a name="cframewnd-issues"></a>CFrameWnd sorunları  
 **CFrameWnd** SAX komut Yönlendirme ve kullanıcı arabirimi çoğu uygulama güncelleştiriliyor. Bu uygulamanın ana çerçeve penceresi için öncelikle kullanılır (**CWinApp::m_pMainWnd**), ancak tüm çerçeve windows için geçerlidir.  
  
 Ana çerçeve penceresi menü çubuğu penceresiyle ve durum çubuğunun üst ya da ileti satır. Komut yönlendirme yukarıdaki tartışma için lütfen bakın ve **WM_INITMENUPOPUP.**  
  
 **CFrameWnd** sınıfı etkin görünüm yönetimini sağlar. Aşağıdaki iletileri etkin görünüm üzerinden yönlendirilir:  
  
-   Tüm komut iletileri (Etkin görünüm ilk erişmesini alır).  
  
- **WM_HSCROLL** ve **WM_VSCROLL** eşdüzey iletilerden kaydırma çubukları (aşağıya bakın).  
  
- **WM_ACTIVATE** (ve **WM_MDIACTIVATE** MDI için) sanal işlev çağrıları içine açık **CView::OnActivateView**.  
  
## <a name="cmdiframewndcmdichildwnd-issues"></a>CMDIFrameWnd/Cmdıchildwnd sorunları  
 Her iki MDI çerçeve penceresi sınıfları türetin **CFrameWnd** ve bu nedenle her ikisi de aynı sıralama komut yönlendirme etkinleştirilir ve kullanıcı arabirimi güncelleştirme sağlanan **CFrameWnd**. Bir uygulamada tipik MDI, yalnızca ana çerçeve penceresi (diğer bir deyişle, **CMDIFrameWnd** nesnesi) menü çubuğu ve durum çubuğu tutar ve bu nedenle ana komut yönlendirme uygulama kaynağıdır.  
  
 Genel Yönlendirme etkin MDI alt pencere komutları ilk erişim alır düzenidir. Varsayılan **PreTranslateMessage** işlevleri işlemek için her iki MDI alt pencereleri Hızlandırıcı tabloları (ilk) ve MDI çerçevesi tarafından normal olarak ele standart MDI sistem komutu Hızlandırıcıları yanı sıra (ikinci)  **TranslateMDISysAccel** (son).  
  
## <a name="scroll-bar-issues"></a>Kaydırma çubuğu sorunları  
 Kaydırma iletiyi işlerken (**WM_HSCROLL**/**OnHScroll** ve/veya **WM_VSCROLL**/**OnVScroll**), burada kaydırma çubuğu iletinin geldiği kalmaz şekilde işleyici kod yazmaya denemelisiniz. Kaydırma iletileri doğru kaydırma çubuğu denetimleri ya da gelebilir beri bu yalnızca bir genel Windows sorun değil **WS_HSCROLL**/**WS_VSCROLL** kaydırma çubuğu denetimleri olmayan Çubukları'e gidin.  
  
 MFC genişletir, alt veya eşdüzey kaydırılan penceresinin kaydırma çubuğu denetimleri için izin vermek için (aslında, kaydırma çubuğu ve pencere kaydırılan üst/alt ilişkisi herhangi bir şey olabilir). Bu, özellikle Bölümlendirici pencereler ile paylaşılan kaydırma çubukları için önemlidir. Lütfen [Teknik Not 29](../mfc/tn029-splitter-windows.md) uygulanması hakkında ayrıntılı bilgi için **CSplitterWnd** daha fazla bilgi dahil olmak üzere paylaşılan kaydırma çubuğu sorunları.  
  
 Yan Not üzerinde var olan iki **CWnd** burada konumunda belirtilen kaydırma çubuğu stilleri oluşturma süresi türetilen sınıflar yakalanan ve Windows geçmedi. Oluşturma yordamına geçirildiğinde **WS_HSCROLL** ve **WS_VSCROLL** bağımsız olarak ayarlanabilir, ancak oluşturma değiştirilemez. Elbette, doğrudan test veya gerekir oluşturuldukları penceresinin WS_SCROLL stili biti ayarlanmış.  
  
 İçin **CMDIFrameWnd** kaydırma çubuğu stilleri için ilettiğiniz **oluşturma** veya **LoadFrame** MDICLIENT oluşturmak için kullanılır. Ayarladığınızdan emin olun bir kaydırılabilir MDICLIENT alanı (gibi Windows programı Yöneticisi) sahip isterseniz, her ikisi de kaydırma stilleri (**WS_HSCROLL** &#124; **WS_VSCROLL**) oluşturmakiçinkullanılanstiliiçin**CMDIFrameWnd**.  
  
 İçin **CSplitterWnd** Bölümlendirici bölgeler için özel paylaşılan kaydırma çubukları kaydırma çubuğu stilleri uygulamak. Statik Bölümlendirici pencereler için her iki kaydırma çubuğu stilini ayarlamanız normalde değil. Dinamik Bölümlendirici pencereler için kaydırma çubuğu, bölme, diğer bir deyişle, yön için stil kümesi genellikle olacaktır **WS_HSCROLL** satır bölerseniz **WS_VSCROLL** sütunları bölerseniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

