---
title: 'TN022: Standart komutları uygulama | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.commands
dev_langs:
- C++
helpviewer_keywords:
- ID_PREV_PANE command [MFC]
- ID_APP_EXIT command [MFC]
- ID_NEXT_PANE command [MFC]
- ID_INDICATOR_REC command [MFC]
- ID_WINDOW_SPLIT command [MFC]
- ID_FILE_PRINT_PREVIEW command [MFC]
- ID_WINDOW_CASCADE command [MFC]
- ID_FILE_CLOSE command [MFC]
- ID_FILE_SAVE_COPY_AS command [MFC]
- ID_WINDOW_ARRANGE command [MFC]
- ID_EDIT_FIND command [MFC]
- ID_FILE_OPEN command [MFC]
- ID_FILE_PAGE_SETUP command [MFC]
- ID_OLE_VERB_FIRST command [MFC]
- ID_EDIT_UNDO command [MFC]
- ID_EDIT_CLEAR command [MFC]
- ID_INDICATOR_CAPS command [MFC]
- ID_HELP_INDEX command [MFC]
- commands [MFC], standard
- ID_FILE_PRINT_SETUP command [MFC]
- ID_DEFAULT_HELP command [MFC]
- ID_INDICATOR_SCRL command [MFC]
- ID_FILE_PRINT command [MFC]
- ID_INDICATOR_OVR command [MFC]
- ID_INDICATOR_KANA command [MFC]
- ID_EDIT_COPY command [MFC]
- ID_EDIT_REDO command [MFC]
- ID_EDIT_PASTE command [MFC]
- ID_OLE_INSERT_NEW command [MFC]
- ID_OLE_EDIT_LINKS command [MFC]
- ID_EDIT_PASTE_SPECIAL command [MFC]
- ID_INDICATOR_EXT command [MFC]
- ID_HELP_USING command [MFC]
- standard commands
- ID_VIEW_STATUS_BAR command [MFC]
- ID_FILE_SAVE_AS command [MFC]
- ID_EDIT_CLEAR_ALL command [MFC]
- ID_WINDOW_NEW command [MFC]
- ID_CONTEXT_HELP command [MFC]
- ID_EDIT_REPLACE command [MFC]
- ID_WINDOW_TILE_HORZ command [MFC]
- ID_APP_ABOUT command [MFC]
- TN022
- ID_VIEW_TOOLBAR command [MFC]
- ID_HELP command [MFC]
- ID_WINDOW_TILE_VERT command [MFC]
- ID_EDIT_CUT command [MFC]
- ID_FILE_UPDATE command [MFC]
- ID_EDIT_REPEAT command [MFC]
- ID_FILE_SAVE command [MFC]
- ID_EDIT_PASTE_LINK command [MFC]
- ID_EDIT_SELECT_ALL command [MFC]
- ID_FILE_NEW command [MFC]
- ID_INDICATOR_NUM command
ms.assetid: a7883b46-23f7-4870-ac3a-804aed9258b5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dea42f4bd33281e65696791677bdd81a921a59e6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Standart Komutları Uygulama
> [!NOTE]
>  İlk çevrimiçi belgelerinde eklenmiştir beri aşağıdaki Teknik Not güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konuları güncel veya yanlış olması olabilir. En son bilgiler için çevrimiçi belgeleri dizindeki ilgi konuyu aramak önerilir.  
  
 Bu Not MFC 2.0 tarafından sağlanan standart komut uygulamaları açıklar. Okuma [Teknik Not 21](../mfc/tn021-command-and-message-routing.md) ilk standart komutların çoğu uygulamak için kullanılan mekanizmaları açıkladığı için.  
  
 Bu açıklama MFC mimariler, API ve ortak programlama uygulama bilgisi varsayar. Belgelenen yanı sıra belgelenmemiş "uygulama yalnızca" API'leri açıklanmıştır. Bu özellikleri veya nasıl MFC'de programlanacağı öğrenmeye başlamak için bir yerde değil. Belgelenen API'leri ayrıntılarını ve daha fazla genel bilgi için Visual C++'a bakın.  
  
## <a name="the-problem"></a>Sorun  
 MFC birçok standart komut kimlikleri üstbilgi dosyası AFXRES tanımlar. H. Bu komutlar Framework desteği değişir. Nerede ve nasıl framework sınıflarını bu komutları idare anlama yalnızca size nasıl framework dahili olarak çalışır ancak standart uygulamalarında özelleştirmek ve uygulamak için birkaç teknikleri öğretmek hakkında yararlı bilgiler sağlar gösterilmez Kendi komut işleyicileri.  
  
## <a name="contents-of-this-technical-note"></a>Bu teknik not içeriğini  
 Her komut kimliği iki bölümde açıklanmıştır:  
  
-   Başlık: Komut Kimliği simgesel ad (örneğin, **ıd_fıle_save**) amacı virgülle ayrılmış komutu (örneğin, "geçerli belgeyi kaydeder"), ardından.  
  
-   Komut ve varsayılan uygulama yaptığı hangi sınıfların açıklayan bir veya daha fazla paragraf uygular  
  
 Çoğu varsayılan komutu uygulamaları framework'ün temel sınıf ileti eşlemesinde prewired. Türetilmiş sınıfınız içindeki açık kablolama gerektiren bazı komut uygulamaları vardır. Bunlar "Note" altında açıklanmıştır. Bu varsayılan işleyiciler içinde AppWizard sağ seçenekleri seçerseniz, sizin için oluşturulan iskelet uygulamada bağlanır.  
  
## <a name="naming-convention"></a>Adlandırma Kuralı  
 Standart komutlar mümkünse kullanmanızı öneririz basit bir adlandırma kuralını izler. Çoğu standart komutları bir uygulamanın menü çubuğu standart yerde bulunur. Komut simgesel ad "menü öğesi standart açılır menü adından, arkasından ID_" ile başlar. Simgesel Adı alt çizgi kesmeleri ile büyük harflerle ' dir. Standart menü öğesi adları yok komutları için bir mantıksal komut adı "ID_" ile başlayan tanımlanır (örneğin, **ıd_next_pane**).  
  
 Menü öğeleri, araç çubuğu düğmeleri veya diğer komut kullanıcı arabirimi nesneleri bağlanması için tasarlanmış komutları belirtmek için "ID_" önekini kullanın. "ID_" komutları işleme komut işleyicileri kullanması gereken `ON_COMMAND` ve `ON_UPDATE_COMMAND_UI` MFC mekanizmaları mimarisi komutu.  
  
 Komut mimarisini izleyin ve etkinleştirmek ve bunları devre dışı bırakmak için menü özgü kodu gerekli menü öğeleri için standart "IDM_" öneki kullanmanızı öneririz. Elbette MFC komutu mimarisi aşağıdaki yalnızca komut işleyicileri (araç çubukları ile çalışacaktır bu yana) daha güçlü yapar ancak komut işleyici kodu yeniden kullanılabilir hale getirir beri menü belirli komutları sayısı küçük olması gerekir.  
  
## <a name="id-ranges"></a>Kimliği aralıkları  
 Lütfen [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md) MFC kimliği aralıklardaki kullanımı hakkında daha fazla ayrıntı için.  
  
 MFC standart komutlar için 0xE000 0xEFFF aralığında. Kitaplığın gelecekteki sürümlerde değiştirilebilir olduğundan bu kimlikleri belirli değerlerine güvenmeyin.  
  
 Uygulamanız kendi komutları için 0x8000 0xDFFF aralığında tanımlamanız gerekir.  
  
## <a name="standard-command-ids"></a>Standart komut kimlikleri  
 Her komut kimliği için dosya İSTEMLERİ bulunabilir standart ileti satır istem dizesi yok. RC. Bu menü istemi dize kimliği komut kimliği aynı olması gerekir  
  
-   Id_fıle_new yeni veya boş bir belge oluşturur.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnFileNew` Belge şablonları sayısına bağlı olarak farklı şekilde bu komut uygulamada uygular. Varsa yalnızca `CDocTemplate`, `CWinApp::OnFileNew` uygun çerçeve ve görünüm sınıfı yanı sıra, bu tür bir yeni belge oluşturun.  
  
     Varsa birden fazla `CDocTemplate`, `CWinApp::OnFileNew` bir iletişim kutusu ile kullanıcıya sorar (**AFX_IDD_NEWTYPEDLG**) kullanmak için hangi belge türü seç yapmalarına izin. Seçili `CDocTemplate` belge oluşturmak için kullanılır.  
  
     Bir sık kullanılan özelleştirme `ID_FILE_NEW` farklı bir ve daha fazla grafik seçeneği belge türlerinin sağlamaktır. Bu durumda, kendi uygulayabileceğiniz **CMyApp::OnFileNew** ve ileti haritanızı yerine koyun `CWinApp::OnFileNew`. Temel sınıf uygulamasını çağırmak için gerek yoktur.  
  
     Başka bir sık kullanılan özelleştirme `ID_FILE_NEW` ayrı bir komutu her türdeki bir belge oluşturmak için sağlamaktır. Bu durumda yeni bir komut kimlikleri, örneğin ID_FILE_NEW_CHART ve ID_FILE_NEW_SHEET tanımlamanız gerekir.  
  
-   Id_fıle_open var olan bir belgeyi açar.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnFileOpen` çağırma çok basit bir uygulamaya sahip **CWinApp::DoPromptFileName** arkasından `CWinApp::OpenDocumentFile` açmak için dosyaya dosya veya yol adı. `CWinApp` Uygulama yordamı **DoPromptFileName** standart FileOpen iletişim kutusunu açar ve geçerli belge şablonlardan elde dosya uzantıları ile doldurur.  
  
     Bir sık kullanılan özelleştirme `ID_FILE_OPEN` FileOpen iletişim özelleştirme veya ek dosya filtreleri ekleyin. Varsayılan uygulama kendi FileOpen iletişim ve çağrısı ile değiştirmek için bu özelleştirmek için önerilen yöntem olduğu `CWinApp::OpenDocumentFile` belgenin dosya veya yol adı ile. Taban sınıfı çağırmak için gerek yoktur.  
  
-   Id_fıle_close açık belgeyi kapatır.  
  
     **CDocument::OnFileClose** çağrıları `CDocument::SaveModified` değiştirildi ve daha sonra çağırır belgeyi kaydetmek için kullanıcıdan `OnCloseDocument`. Belge yok etme dahil olmak üzere tüm kapanış mantığını içerir, yapılır `OnCloseDocument` yordamı.  
  
    > [!NOTE]
    >  **Id_fıle_close** öğesinden farklı şekilde davranan bir `WM_CLOSE` ileti veya bir **SC_CLOSE** belge çerçeve penceresi için gönderilen sistem komutu. Yalnızca bu belge gösteren son çerçeve penceresi ise bir pencereyi belgeyi kapatın. Belgeyle kapatma **ıd_fıle_close** yalnızca belge kapanmaz ancak belgenin gösteren tüm çerçeve pencereleri kapanacak.  
  
-   Id_fıle_save geçerli belgeyi kaydeder.  
  
     Uygulama Yardımcısı yordamı kullanır **CDocument::DoSave** kullanılan her ikisi için **OnFileSave** ve **OnFileSaveAs**. Önce kaydedilmemiş olan bir belgeyi kaydederseniz (diğer bir deyişle, bir yol adı olarak dosya yeni olması durumunda yok) veya bir salt okunur belgeden okundu **OnFileSave** mantığı gibi davranacağı **ıd_fıle_save_as** komut ve yeni bir dosya adı girmesini isteyin. Dosyayı açma ve kaydetme yapılması gerçek işlemi sanal işlev yapılır `OnSaveDocument`.  
  
     Özelleştirme için iki ortak nedenleri vardır **ıd_fıle_save**. Kaydetmeyin belgeleri için basitçe kaldırmak **ıd_fıle_save** menü öğeleri ve araç çubuğu düğmelerini kullanarak, kullanıcı arabirimi. Ayrıca belgenizi hiçbir zaman kirli emin olun (diğer bir deyişle, hiçbir zaman çağrı `CDocument::SetModifiedFlag`) ve framework hiçbir zaman belgenin kaydedilmesini neden olur. Ortalarda dışında bir disk dosyasına kaydetmeye belgeler için bu işlem için yeni bir komut tanımlayın.  
  
     Durumunda bir `COleServerDoc`, **ıd_fıle_save** hem dosyayı kaydedin (için normal belgeler) ve dosya güncelleştirmesi (embedded belgeler) için kullanılır.  
  
     Belge verilerinizi tek tek disk dosyalarında depolanır, ancak varsayılan kullanmak istemiyorsanız **CDocument** uygulama seri, geçersiz kılmalısınız `CDocument::OnSaveDocument` yerine **OnFileSave**.  
  
-   Id_fıle_save_as farklı bir dosya adı altında geçerli belgeyi kaydeder.  
  
     **CDocument::OnFileSaveAs** uygulama kullandığı aynı **CDocument::DoSave** yardımcı yordamı olarak **OnFileSave**. **OnFileSaveAs** komutu gibi işlenir **ıd_fıle_save** belgeleri kaydetme önce hiçbir dosya adı olsaydı. **COleServerDoc::OnFileSaveAs** normal belge veri dosyasını kaydetmek veya OLE nesneyi temsil eden bir sunucu belgeyi kaydetmek için mantığı katıştırılmış ayrı bir dosya olarak başka bir uygulama içinde uygular.  
  
     Mantığını özelleştirirseniz **ıd_fıle_save**, özelleştirmek isteyeceksiniz **ıd_fıle_save_as** benzer bir şekilde veya "Farklı Kaydet" işlemi belgeniz için geçerli olmayabilir. Gerekli olmadığından, menü çubuğundan menü öğesi kaldırabilirsiniz.  
  
-   Id_fıle_save_copy_as kopyalama geçerli belgeyi yeni adla kaydeder.  
  
     **COleServerDoc::OnFileSaveCopyAs** uygulamasıdır çok benzer **CDocument::OnFileSaveAs**, ancak bu belge nesnesi "temel alınan dosyaya kaydet sonra bağlı değil". Bellek içi belgenin "kaydetme önce değiştirilmişse", diğer bir deyişle, yine "değişiklik". Ayrıca, bu komut yol adı veya belgede depolanan başlık etkisi yoktur.  
  
-   Id_fıle_update katıştırılmış bir belge kaydetmek için kapsayıcı bildirir.  
  
     `COleServerDoc::OnUpdateDocument` Uygulama yalnızca notifiies katıştırma kaydedilmelidir kapsayıcı. Kapsayıcı sonra uygun OLE API'lerini katıştırılmış nesne kaydetmek için çağırır.  
  
-   Id_fıle_page_setup bir uygulamaya özgü sayfası Kurulum/düzeni iletişim kutusunu çağırır.  
  
     Şu anda bu iletişim kutusu için bir standart yoktur ve bu komutun varsayılan uygulaması framework sahiptir.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_fıle_prınt_setup standart Sayfa Yapısı iletişim kutusu çağırır.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     Bu komut kullanıcının yazıcı özelleştirmek ve yazdırma ayarları için en az izin veren standart yazdırma Kurulumu iletişim kutusunu çağırır bu belge veya en çok tüm belgelerde bu uygulama. Tüm sistemin varsayılan yazıcı ayarlarını değiştirmek için Denetim Masası'nı kullanmanız gerekir.  
  
     `CWinApp::OnFilePrintSetup` çok basit uygulama oluşturma sahip bir `CPrintDialog` nesne ve arama **CWinApp::DoPrintDialog** uygulama işlevi. Bu uygulama varsayılan yazıcı kurulumu ayarlar.  
  
     Bu komut özelleştirmek için ortak Belge kaydedildiğinde depolanması gereken belge başına yazıcı ayarları için izin vermek için gerekiyor. Bunu yapmak için ileti eşlemesi işleyici eklemeniz gerekir, **CDocument** oluşturur sınıfı bir `CPrintDialog` nesne, uygun yazıcı özniteliklerle başlatır (genellikle **hDevMode** ve **hDevNames**), çağrı **CPrintDialog::DoModal,** ve değiştirilen yazıcı ayarlarını kaydedin. İçin sağlam bir uygulama, uygulanması sırasında göz önünde bulundurmanız gerekenler **CWinApp::DoPrintDialog** hataları algılamak ve **CWinApp::UpdatePrinterSelection** duyarlı Varsayılanları ilgilenmek için ve Sistem genelinde yazıcı değişiklikleri izleme.  
  
-   Geçerli belgenin ıd_fıle_prınt standart yazdırma  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CView`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     Bu komut geçerli belgeyi yazdırır ya da daha doğru bir şekilde standart yazdırma iletişim çağırma ve yazdırma altyapısı çalıştıran içerir yazdırma işlemi başlatır.  
  
     **CView::OnFilePrint** bu komut ve ana yazdırma döngü uygular. Sanal çağırır `CView::OnPreparePrinting` yazdırma iletişim kullanıcıyla istemi. Bu ardından yazıcıya gitmek için çıktı DC hazırlar, yazdırma ilerleme durumu iletişim kutusunu açar (**AFX_IDD_PRINTDLG**) ve gönderir `StartDoc` kaçış yazıcı. **CView::OnFilePrint** ana sayfa yönelimli yazdırma döngü de içerir. Her bir sayfa için sanal çağırır `CView::OnPrepareDC` arkasından bir `StartPage` kaçış ve sanal çağırma `CView::OnPrint` bu sayfa için. Tamamlandığında, sanal `CView::OnEndPrinting` denir ve yazdırma ilerleme iletişim kutusu kapatılır.  
  
     MFC yazdırma mimarisi, yazdırmayı ve Baskı Önizleme için birçok farklı yolu için tasarlanmıştır. Normalde çeşitli bulacaksınız `CView` geçersiz kılınabilir işlevler tüm sayfa yönelimli yazdırma görevleri için yeterli. Çıkış, sayfa dışı yönelik için yazıcı bulduğunuz değiştirmek için gereken kullanan bir uygulama durumunda **ıd_fıle_prınt** uygulaması.  
  
-   Id_fıle_prınt_prevıew girin Baskı Önizleme modunu geçerli belge için.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CView`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     **CView::OnFilePrintPreview** belgelenen yardımcı işlevini çağırarak Baskı Önizleme modunu başlatır **CView::DoPrintPreview**. **CView::DoPrintPreview** ana Baskı Önizleme döngünün gibi altyapısıdır **OnFilePrint** yazdırma döngünün ana altyapısıdır.  
  
     Baskı Önizleme işlemi için farklı parametreler geçirerek çeşitli şekillerde özelleştirilebilir **DoPrintPreview**. Lütfen [Teknik Not 30](../mfc/tn030-customizing-printing-and-print-preview.md)Baskı Önizleme ayrıntılarını bazıları açıklanır ve özelleştirmek nasıl.  
  
-   **ID_FILE_MRU_FILE1**... **FILE16** komut kimlikleri dosya MRU için bir aralığı `list`.  
  
     **CWinApp::OnUpdateRecentFileMenu** daha gelişmiş kullanımlarını biri olan bir güncelleştirme komutu UI işleyicisidir `ON_UPDATE_COMMAND_UI` mekanizması. Menü kaynağınız yalnızca bir tek menü öğesi kimliği olan tanımladığınız **ID_FILE_MRU_FILE1**. Bu menü öğesi başlangıçta devre dışı kalır.  
  
     MRU Listesi büyüdükçe, daha fazla menü öğeleri listesine eklenir. Standart `CWinApp` uygulama varsayılanlarını dört en son kullanılan dosyalar standart sınırla. Varsayılan çağırarak değiştirebileceğiniz `CWinApp::LoadStdProfileSettings` daha büyük veya küçük bir değere sahip. MRU Listesi uygulamanın içinde depolanır. INI dosyası. Listenin uygulamanızın yüklenen `InitInstance` çağırırsanız işlev `LoadStdProfileSettings`ve uygulamanızı çıktığında kaydedilir. MRU güncelleştirme komut UI işleyici göreli yollar Dosya menüsünde görüntülenmek için mutlak yollar da dönüştürür.  
  
     **CWinApp::OnOpenRecentFile** olan `ON_COMMAND` gerçek komutu gerçekleştirir işleyici. Yalnızca dosya adı MRU listesi ve çağrıları alır `CWinApp::OpenDocumentFile`, dosyayı açıp MRU listesini güncelleştirmeden tüm işini yapar.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Geçerli seçim ıd_edıt_clear temizler  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Bu komutu kullanarak, bir uygulama sağlar `CEdit::Clear`. Geçerli seçim yoksa komutu devre dışı bırakılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_clear_all tüm belgeyi temizler.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz MFC öğretici örnek bkz [KARALAMA](../visual-cpp-samples.md) örnek uygulama.  
  
-   Id_edıt_copy geçerli Seçimi panoya kopyalar.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Seçili metnin CF_TEXT kullanmakla panoya kopyalar bu komutun bir uygulama sağlar `CEdit::Copy`. Geçerli seçim yoksa komutu devre dışı bırakılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_cut geçerli Seçimi panoya keser.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` bir uygulama CF_TEXT kullanmakla panoya şu anda seçili metni keser bu komutun sağlar `CEdit::Cut`. Geçerli seçim yoksa komutu devre dışı bırakılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_fınd başlar bulma işlemi ve kalıcı olmayan Bul iletişim kutusunu getirir.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Bu komut uygulama yardımcı işlevini çağırır uygulaması sağlar **OnEditFindReplace** kullanın ve özel uygulama değişkenlerde önceki bulun ve değiştirin ayarlarını depolamak için. `CFindReplaceDialog` Sınıfı, kullanıcıdan istemek için kalıcı olmayan iletişim yönetmek için kullanılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_paste geçerli Pano içeriğini ekler.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Seçili metni kullanarak değiştirme geçerli Pano verileri kopyalar bu komutun bir uygulama sağlar `CEdit::Paste`. Varsa komutu devre dışı hiçbir **CF_TEXT** Panodaki.  
  
     **COleClientDoc** yalnızca bu komut için bir güncelleştirme komutu UI işleyicisi sağlar. Pano gömülebilir OLE öğesi/nesnesi içermiyorsa komutu devre dışı bırakılacak. Gerçek yapıştırma yapmak gerçek komut işleyici yazmaktan sorumlu. OLE uygulamanızı de diğer biçimlere yapıştırabilirsiniz, kendi güncelleştirme komut UI işleyici görünümünde veya belge sağlamanız (diğer bir deyişle, herhangi bir yerde önce **COleClientDoc** komutu hedef akışındaki).  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
     Standart OLE uygulaması değiştirmek için kullanmak `COleClientItem::CanPaste`.  
  
-   Id_edıt_paste_lınk geçerli Pano içeriğini bir bağlantı ekler.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `COleDocument` yalnızca bu komut için bir güncelleştirme komutu UI işleyicisi sağlar. Pano linkable OLE öğesi/nesnesi içermiyorsa komutu devre dışı bırakılacak. Gerçek yapıştırma yapmak gerçek komut işleyici yazmaktan sorumlu. OLE uygulamanızı de diğer biçimlere yapıştırabilirsiniz, kendi güncelleştirme komut UI işleyici görünümünde veya belge sağlamanız (diğer bir deyişle, herhangi bir yerde önce `COleDocument` komutu hedef akışındaki).  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
     Standart OLE uygulaması değiştirmek için kullanmak `COleClientItem::CanPasteLink`.  
  
-   Id_edıt_paste_specıal geçerli Pano içeriğini seçenekleriyle ekler.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf. MFC bu iletişim kutusunu sağlamaz.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_repeat son işlem yinelenir.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` son bulma işlemi yinelemek için bu komutu bir uygulamasını sağlar. Son bulma için özel uygulama değişkenleri kullanılır. Bir bulma girişilemiyor komutu devre dışı bırakılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_replace başlar değiştirme işlemi ve kalıcı olmayan Değiştir iletişim kutusunu getirir.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Bu komut uygulama yardımcı işlevini çağırır uygulaması sağlar **OnEditFindReplace** kullanın ve özel uygulama değişkenlerde önceki bulun ve değiştirin ayarlarını depolamak için. `CFindReplaceDialog` Sınıfı kullanıcıdan kalıcı olmayan iletişim yönetmek için kullanılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_select_all tüm belgeyi seçer.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Belgedeki tüm metni seçer bu komutu bir uygulamasını sağlar. Seçilecek hiç metin yoksa komutu devre dışı bırakılır.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_undo son işlemini geri alır.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     `CEditView` Bu bir uygulamasını sağlar komutunu `CEdit::Undo`. Komutu devre dışı bırakılır `CEdit::CanUndo` FALSE değerini döndürür.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_edıt_redo son işlemi yineler.  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_wındow_new etkin belgede başka bir pencere açılır.  
  
     **CMDIFrameWnd::OnWindowNew** geçerli belgenin başka bir görünüm içeren başka bir çerçeve oluşturmak için geçerli belgenin belge şablonu kullanarak bu güçlü bir özellik uygular.  
  
     Hiçbir etkin MDI alt pencere yoksa çoğu birden çok belge arabirimi (MDI) pencere menü komutları gibi komutu devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez. Ek görünümler veya çerçeve pencereleri oluşturan komut sağlamak isterseniz, büyük olasılıkla kendi komut inventing kapalı daha iyi olur. Koddan kopyalayabilirsiniz **CMDIFrameWnd::OnWindowNew** ve belirli çerçeve ve görünüm sınıfları, istediğiniz şekilde değiştirin.  
  
-   MDI pencerenin altındaki simgeleri ıd_wındow_arrange düzenler.  
  
     `CMDIFrameWnd` Bu standart MDI komut bir uygulama Yardımcısı işlevinde uygulayan **OnMDIWindowCmd**. Bu yardımcı komut kimlikleri MDI Windows iletilerini eşler ve bu nedenle çok fazla kod paylaşabilirsiniz.  
  
     Hiçbir etkin MDI alt pencere yoksa çoğu MDI pencere menü komutları gibi komutu devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Bunlar Pencereleri çakışacak şekilde pencereleri ıd_wındow_cascade basamaklar.  
  
     `CMDIFrameWnd` Bu standart MDI komut bir uygulama Yardımcısı işlevinde uygulayan **OnMDIWindowCmd**. Bu yardımcı komut kimlikleri MDI Windows iletilerini eşler ve bu nedenle çok fazla kod paylaşabilirsiniz.  
  
     Hiçbir etkin MDI alt pencere yoksa çoğu MDI pencere menü komutları gibi komutu devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Id_wındow_tıle_horz döşeme windows yatay olarak.  
  
     Bu komut uygulanan `CMDIFrameWnd` olduğu gibi **ıd_wındow_cascade**, farklı bir MDI Windows ileti işlemi için kullanılacak dışında.  
  
     Uygulamanız için varsayılan döşeme yönü seçmeniz gerekir. Bu pencere "Kutucuğuna" menü öğesi için kimliği ya da değiştirerek yapabilirsiniz **ıd_wındow_tıle_horz** veya **ıd_wındow_tıle_vert**.  
  
-   Id_wındow_tıle_vert döşeme windows dikey olarak.  
  
     Bu komut uygulanan `CMDIFrameWnd` olduğu gibi **ıd_wındow_cascade**, farklı bir MDI Windows ileti işlemi için kullanılacak dışında.  
  
     Uygulamanız için varsayılan döşeme yönü seçmeniz gerekir. Bu pencere "Kutucuğuna" menü öğesi için kimliği ya da değiştirerek yapabilirsiniz **ıd_wındow_tıle_horz** veya **ıd_wındow_tıle_vert**.  
  
-   Bölümlendirici ıd_wındow_splıt klavye arabirim.  
  
     `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm Bölümlendirici pencere parçası ise, bu komut uygulama işlevine temsil edecek `CSplitterWnd::DoKeyboardSplit`. Bu bölme klavye kullanıcıların bölme veya Bölümlendirici pencere bölünmesi sağlayacak bir modda yerleştirin.  
  
     Görünüm bir ayırıcı değil, bu komutu devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Id_app_about hakkında iletişim kutusunu çağırır.  
  
     Bir uygulamanın hakkında kutusunu standart uygulaması yoktur. AppWizard oluşturulan varsayılan uygulama, uygulamanız için özel iletişim kutusu sınıfı oluşturma ve hakkında kutu olarak kullanın. AppWizard da iletişim kutusunu çağırır ve bu komutu işler Önemsiz komut işleyici yazacaksınız.  
  
     Bu komut neredeyse her zaman gerçekleştireceksiniz.  
  
-   Id_app_exıt uygulama çıkın.  
  
     **CWinApp::OnAppExit** bu komutu göndererek işleyen bir `WM_CLOSE` uygulamanın ana pencere iletisi. (Kirli dosyaları vb. isteyen) uygulamasının kapatılıyor standart tarafından işlenen `CFrameWnd` uygulaması.  
  
     Bu komut işleyici özelleştirmesini önerilmez. Geçersiz kılma `CWinApp::SaveAllModified` veya `CFrameWnd` mantığı kapatma önerilir.  
  
     Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz  
  
-   Id_help_ındex listeler Yardım konuları. HLP dosyasına bakın.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnHelpIndex` Bu komut trivially çağırarak işleme `CWinApp::WinHelp`.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Yardım'ı kullanma hakkında Yardım ıd_help_usıng görüntüler.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnHelpUsing` Bu komut trivially çağırarak işleme `CWinApp::WinHelp`.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Id_context_help girer SHIFT-F1 Yardımı modu.  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnContextHelp` Bu komut, Yardım modu imleci ayarlama, kalıcı döngü girerek ve Yardım almak için bir pencere seçmek kullanıcı için bekleyen işler. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) MFC Yardım uygulaması hakkında daha fazla ayrıntı için.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Geçerli bağlamda Yardım ıd_help sağlar  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     `CWinApp::OnHelp` Bu komut için geçerli uygulama bağlamı sağ Yardım bağlamı alarak işler. Bu basit F1 Yardımı işlediğinde, ileti kutuları vb. yardımcı olur. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) MFC hakkında daha fazla ayrıntı uygulama yardımcı olmak için.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Bağlam için varsayılan Yardım ıd_default_help görüntüler  
  
    > [!NOTE]
    >  Bunun için bağlanmanız gerekir, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfının türetilmiş.  
  
     Bu komut genellikle eşlenmiş `CWinApp::OnHelpIndex`.  
  
     Varsayılan Yardım ve Yardım dizin arasında bir fark isterseniz farklı komut işleyici sağlanabilir.  
  
-   Id_next_pane gider sonraki bölme  
  
     `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm Bölümlendirici pencere parçası ise, bu komut uygulama işlevine temsil edecek **CSplitterWnd::OnNextPaneCmd**. Bu sonraki Bölümlendirici bölmesinde etkin görünüm taşır.  
  
     Bu komut görünümü bir ayırıcı değil veya yok sonraki bölme gitmek için devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Id_prev_pane gider Önceki Bölme  
  
     `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm Bölümlendirici pencere parçası ise, bu komut uygulama işlevine temsil edecek **CSplitterWnd::OnNextPaneCmd**. Bu önceki Bölümlendirici bölmesinde etkin görünüm taşır.  
  
     Bu komut görünümü bir ayırıcı değil veya gitmek için hiçbir önceki bölmesinde devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   Id_ole_ınsert_new yeni bir OLE nesnesi ekler  
  
     Şu anda bu komut için standart uygulaması yoktur. Bu uygulama, `CView`-türetilen geçerli seçimi daha yeni bir OLE öğesi/nesne eklemek için sınıfı.  
  
     Bu komut tüm OLE istemci uygulamaları uygulamalıdır. AppWizard, OLE seçeneğiyle bir iskelet uygulaması oluşturacak **OnInsertObject** görünüm sınıfınızda tamamlanması gerekir.  
  
     MFC OLE örnek bkz [OCLIENT](../visual-cpp-samples.md) bu komutun tam bir uygulama için örnek.  
  
-   Id_ole_edıt_lınks düzenler OLE bağlantıları  
  
     `COleDocument` Bu komut, standart OLE bağlantıları iletişim sağlanan MFC uygulaması kullanarak işler. Bu iletişim kutusunu uyarlamasını üzerinden erişilen `COleLinksDialog` sınıfı. Geçerli belge tüm bağlantılar içermiyor komutu devre dışı bırakılır.  
  
     Bu komut işleyici özelleştirmesini önerilmez.  
  
-   ID_OLE_VERB_FIRST... OLE fiiller için son bir kimlik aralığı  
  
     `COleDocument` Bu komut kimliği aralığı seçili OLE öğesi/nesnesi tarafından desteklenen fiiller için kullanır. Belirli bir OLE öğesi/nesnesi türde sıfır veya daha fazla özel fiiller destekleyebilir beri bu aralığı olmalıdır. Uygulamanızın menüde bir menü öğesi kimliği olmalıdır **ıd_ole_verb_fırst**. Programını çalıştırdığınızda, menü uygun menü fiil açıklaması (veya birçok fiiller ile açılır menüsünden) ile güncelleştirilir. OLE menü Yönetimi tarafından işlenen `AfxOleSetEditMenu`, bu komut için güncelleştirme komut UI işleyicisi Bitti'yi.  
  
     Her komut kimliği bu aralıktaki işlemek için hiçbir açık komut işleyicileri vardır. **COleDocument::OnCmdMsg** bu aralıktaki tüm komut kimlikleri tuzak, sıfır tabanlı fiil sayılara açın ve sunucu bu fiil için başlatma için geçersiz kılındı (kullanarak `COleClientItem::DoVerb`).  
  
     Özelleştirme veya bu komut kimliği aralığı diğer kullanımı önerilmez.  
  
-   Id_vıew_toolbar araç çubuğunu açar ve kapatır  
  
     `CFrameWnd` Bu komut ve güncelleştirme komutu UI işleyicisi araç görünür durumunu değiştirme için işler. Araç çubuğu çerçeve alt pencere kimliğine sahip olan bir alt pencere olmalıdır `AFX_IDW_TOOLBAR`. Komut işleyici gerçekte araç penceresi görünürlüğünü değiştirir. `CFrameWnd::RecalcLayout` çerçeve penceresi araç ile yeni durumundayken yeniden çizmek için kullanılır. Araç çubuğu görünür olduğunda menü öğesi güncelleştirme komutu UI işleyicisi denetler.  
  
     Bu komut işleyici özelleştirmesini önerilmez. Ek araç çubukları eklemek isterseniz, kopyalama ve komut işleyici ve güncelleştirme komut UI işleyici bu komut için değiştirmek istediğiniz.  
  
-   Id_vıew_status_bar durum çubuğunu açar ve kapatır  
  
     Bu komut uygulanan `CFrameWnd` olduğu gibi **ıd_vıew_toolbar**, hariç farklı alt pencere kimliği (**AFX_IDW_STATUS_BAR**) kullanılır.  
  
## <a name="update-only-command-handlers"></a>Yalnızca güncelleştirme komut işleyicileri  
 Birkaç standart komut kimlikleri, durum çubukları göstergeleri olarak kullanılır. Bunlar aynı güncelleştirme komutu UI işleme mekanizması geçerli visual durumlarına uygulama boşta kalma süresi sırasında görüntülemek için kullanın. Kullanıcı tarafından seçilemez bu yana (diğer bir deyişle, bir durum çubuğu bölmesinin gönderemezsiniz), için hiçbir mantıklıdır sonra bir `ON_COMMAND` bu komut kimlikleri için işleyici.  
  
-   **Id_ındıcator_caps** : CAP kilit göstergesi.  
  
-   **Id_ındıcator_num** : NUM kilit göstergesi.  
  
-   **Id_ındıcator_scrl** : SCRL kilit göstergesi.  
  
-   **Id_ındıcator_kana** : KANA kilit göstergesi (yalnızca Japonca sistemler için geçerlidir).  
  
 Bu üç uygulanır **CFrameWnd::OnUpdateKeyIndicator**, uygun sanal anahtarına eşlemek için komut Kimliğini kullanan bir uygulama Yardımcısı. Yaygın olarak görülen bir uygulama etkinleştirir veya devre dışı bırakır (devre dışı durum bölmeleri için metin yok =) `CCmdUI` uygun sanal anahtar şu anda kilitli bağlı olarak nesne.  
  
 Bu komut işleyici özelleştirmesini önerilmez.  
  
-   **Id_ındıcator_ext: EXT**sona erdi select göstergesi.  
  
-   **Id_ındıcator_ovr: OV**e**R**göstergesi üstünü.  
  
-   **Id_ındıcator_rec: REC**ording göstergesi.  
  
 Şu anda bu göstergeleri için standart hiç uygulaması yoktur.  
  
 Bu göstergeler uygulamak isterseniz bu gösterge kimlikleri ve durum çubuğu göstergeleri sıralama koruma kullanmanız önerilir (diğer bir deyişle, bu sırada: EXT, büyük harf, sayı, SCRL, OVR, REC).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)   
 [Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)

