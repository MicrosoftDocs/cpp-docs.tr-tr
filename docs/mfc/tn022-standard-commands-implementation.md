---
title: 'TN022: Standart komutları uygulama'
ms.date: 11/04/2016
f1_keywords:
- vc.commands
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
ms.openlocfilehash: 8d568760cc75a4c1f2ddb6dd88108cc830783194
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58775837"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Standart komutları uygulama

> [!NOTE]
>  Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not, MFC 2.0 tarafından sağlanan standart komut uygulamaları açıklar. Okuma [Teknik Not 21](../mfc/tn021-command-and-message-routing.md) ilk çünkü birçok standart komutu uygulamak için kullanılan mekanizmalarını açıklar.

Bu açıklama, MFC mimarileri, API ve programlama genellikle bilgi varsayar. Belgelenen yanı sıra belgelenmemiş "uygulamasına yalnızca" API'leri açıklanmıştır. Bu özellikleri veya MFC'de programlamayı öğrenmeye başlamak için bir yer değildir. Belgelenen API'leri ayrıntılarını ve daha fazla genel bilgi için Visual C++'a bakın.

## <a name="the-problem"></a>Sorun

MFC üstbilgi dosyasında AFXRES birçok standart komut kimlikleri tanımlar. H Bu komutlar için Framework desteği değişir. Nerede ve nasıl framework sınıfları bu komutları işlemek anlama yalnızca size nasıl, framework dahili olarak çalışır ancak standart uygulamaları özelleştirmek ve uygulamak için birkaç teknikleri öğretin konusunda faydalı bilgiler sağlayacaktır gösterilmez Kendi komut işleyicileri.

## <a name="contents-of-this-technical-note"></a>Bu teknik Not içeriği

Her komut kimliği iki bölümde açıklanmıştır:

- Başlık: amacı komutu (örneğin, "geçerli bir belgeyi kaydederken"), ardından komut kimliği (örneğin, ıd_fıle_save) simgesel adının bir virgülle ayrılmış.

- Komut ve varsayılan uygulama yaptığı hangi sınıfları tanımlayan bir veya daha fazla paragraflar uygulayın

Çoğu varsayılan komut uygulamaları framework'ün temel sınıf ileti eşlemede prewired. Açık teknik, türetilmiş sınıf içinde gerektiren bazı komut uygulamaları vardır. Bunlar, "Not" açıklanmıştır. Bu varsayılan işleyicileri doğru seçenekleri AppWizard seçerseniz, sizin için iskelet oluşturulan uygulamada bağlanacaksınız.

## <a name="naming-convention"></a>Adlandırma Kuralı

Standart komutlar, mümkünse kullanmanızı öneririz basit bir adlandırma kuralını izler. Çoğu standart komutları uygulama menü çubuğunda standart yerleri bulunur. Simgesel Adı komut "menü öğesi standart açılır menü adından, ardından ID_" ile başlar. Simgesel Adı alt çizgi kesmeleri ile büyük harf kullanılıyor. Standart menü öğesi adları olmayan komutları için mantıksal komut adı "ID_" (örneğin, ıd_next_pane) ile başlayan tanımlanır.

Menü öğeleri, araç çubuğu düğmeleri veya diğer komut kullanıcı arabirimi nesneleri bağlanması için tasarlanmış komutlarını belirtmek için "ID_" önekini kullanın. ON_COMMAND ve on_update_command_uı mekanizmaları MFC komut mimarisi için komut işleyicileri "ID_" komutları işleme kullanmanız gerekir.

Komut mimarisi izleyin ve menü özgü kod etkinleştirmek ve bunları devre dışı bırakmak için gereksinim menü öğeleri için standart "IDM_" öneki kullanmanızı öneririz. Elbette MFC komut mimarisi aşağıdaki yalnızca bu yana (çubuklarıyla çalışacaktır) komut işleyicileri daha güçlü hale getirir ancak komut işleyicinizin kodunu yeniden kullanılabilir hale getirir bu yana komutlarını belirli sayıda küçük olmalıdır.

## <a name="id-ranges"></a>Kimliği aralıkları

Lütfen [Teknik Not 20](../mfc/tn020-id-naming-and-numbering-conventions.md) kimliği aralığı MFC kullanımı hakkında daha fazla ayrıntı için.

MFC standart komutlar için 0xE000 0xEFFF aralığında. Kitaplığı'nın gelecekteki sürümlerde değişebilir olduğundan bu kimliklerinin belirli değerlerine güvenmeyin.

Uygulamanız kendi komutları 0x8000 ile 0xDFFF aralığında tanımlamanız gerekir.

## <a name="standard-command-ids"></a>Standart komut kimlikleri

Her komut kimliği için dosya İSTEMLERİ bulunabilir standart ileti satır istem dizesi yoktur. RC. Bu menü istem için dize kimliği komut kimliği. aynı olmalıdır.

- Id_fıle_new yeni/olarak boş belge oluşturur.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnFileNew` Bu komut belge şablonları sayısına bağlı olarak farklı uygulama uygular. Varsa yalnızca `CDocTemplate`, `CWinApp::OnFileNew` uygun çerçeve ve görünüm sınıfı yanı sıra, bu tür bir yeni belge oluşturacaksınız.

   Varsa birden fazla `CDocTemplate`, `CWinApp::OnFileNew` bunları izin vererek bir iletişim kutusu (AFX_IDD_NEWTYPEDLG) belge türünü seçin girmesini ister. Seçili `CDocTemplate` belgesi oluşturmak için kullanılır.

   Farklı bir ve daha fazla grafik istediğiniz belge türleri ıd_fıle_new bir sık kullanılan özelleştirme sağlamaktır. Bu durumda, kendi uygulayabileceğiniz `CMyApp::OnFileNew` ve yerine, ileti eşlemesi yerleştirerek `CWinApp::OnFileNew`. Temel sınıf uygulamasını çağıracak şekilde gerek yoktur.

   Id_fıle_new başka bir sık kullanılan özelleştirme, her türden bir belge oluşturmak için ayrı bir komut sağlamaktır. Bu durumda yeni komut kimlikleri, örneğin ID_FILE_NEW_CHART ve ID_FILE_NEW_SHEET tanımlamanız gerekir.

- Id_fıle_open var olan bir belgeyi açar.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnFileOpen` çok basit bir arama uygulaması olan `CWinApp::DoPromptFileName` ardından `CWinApp::OpenDocumentFile` açmak için dosyaya dosya veya yol adı. `CWinApp` Uygulama yordamı `DoPromptFileName` standart FileOpen iletişim kutusunu açar ve geçerli belge şablonlarından alınan dosya uzantıları ile doldurur.

   Bir sık kullanılan özelleştirme ıd_fıle_open FileOpen iletişim özelleştirebilir veya ek dosya filtreleri ekleyin sağlamaktır. Varsayılan uygulama kendi FileOpen iletişim ve çağrı ile değiştirmek için bu özelleştirmek için önerilen yöntem olduğu `CWinApp::OpenDocumentFile` belgenin dosya veya yol ada sahip. Temel sınıf çağırmaya gerek yoktur.

- Id_fıle_close açık belge kapatır.

   `CDocument::OnFileClose` çağrıları `CDocument::SaveModified` değiştirilmiş ve daha sonra çağırır ve belgeyi kaydetmesine kullanıcıdan istemek için `OnCloseDocument`. Belge yok etme dahil olmak üzere tüm kapanış mantığı içerir, yapılabilir `OnCloseDocument` yordamı.

    > [!NOTE]
    >  Farklı bir WM_CLOSE iletisini veya belge çerçeve penceresi için gönderilen bir SC_CLOSE sistem komutunu gelen ıd_fıle_close davranır. Yalnızca bu belgeyi gösteren son çerçeve penceresi olduğu bir pencereyi kapatmak, belgenin sona erecektir. Belgeyi kapatıp ıd_fıle_close yalnızca belgenin kapanmaz ancak belgeyi gösteren tüm çerçeve pencereleri kapanacak.

- Geçerli belgeyi ıd_fıle_save kaydeder.

   Uygulama Yardımcısı yordamını kullanır `CDocument::DoSave` her ikisi için kullanıldığı `OnFileSave` ve `OnFileSaveAs`. Önce kaydedilmemiş bir belge kaydettiğinizde, (diğer bir deyişle, bir yol adı olarak dosya yeni söz konusu olduğunda yok) veya salt okunur bir belgeden okundu `OnFileSave` mantıksal ıd_fıle_save_as komutu ve kullanıcıdan yeni bir dosya adı sağlayın gibi davranır . Dosyayı açıp tasarruf yapmak gerçek işlemi sanal işlev yapılır `OnSaveDocument`.

   Id_fıle_save özelleştirmek için sık karşılaşılan iki nedeni vardır. Kaydetme belgeler için yalnızca, kullanıcı arabiriminden ıd_fıle_save menü öğeleri ve araç çubuğu düğmeleri kaldırın. Ayrıca belgenizi hiçbir zaman kirli emin olun (diğer bir deyişle, hiçbir zaman çağrı `CDocument::SetModifiedFlag`) ve framework hiçbir zaman kaydedilecek belge neden olur. Bu işlem için yeni bir komut ortalarda dışındaki bir disk dosyasına kaydedin belgeleri tanımlayın.

   Durumunda, bir `COleServerDoc`, ıd_fıle_save hem dosyasını kaydedin (normal belgeleri için) ve dosya güncelleştirmesi (ekli belgelerin) için kullanılır.

   Belge verilerinizi tek bir disk dosyalarında depolanır, ancak varsayılan kullanmak istemiyorsanız `CDocument` uygulama seri hale getirmek, geçersiz kılmalıdır `CDocument::OnSaveDocument` yerine `OnFileSave`.

- Id_fıle_save_as farklı bir dosya adı altında geçerli belgeyi kaydeder.

   `CDocument::OnFileSaveAs` Uygulama kullandığı aynı `CDocument::DoSave` Yardımcısı yordam olarak `OnFileSave`. `OnFileSaveAs` Belgeleri kaydetme önce dosya adı varsa, komut yalnızca ıd_fıle_save işlenir. `COleServerDoc::OnFileSaveAs` bir normal belge veri dosyasını kaydedilmesini veya başka bir uygulama ayrı bir dosya olarak katıştırılmış bir OLE nesnesi temsil eden bir sunucu belgesinin kaydetmek için mantığı uygular.

   Id_fıle_save mantığını özelleştirirseniz, büyük olasılıkla ıd_fıle_save_as benzer şekilde özelleştirmek istersiniz veya "Farklı Kaydet" işlemi belgenize geçerli olmayabilir. Gerekli olmadığından, menü çubuğundan menü öğesi kaldırabilirsiniz.

- Id_fıle_save_copy_as kopyalama geçerli belgeye yeni bir adla kaydeder.

   `COleServerDoc::OnFileSaveCopyAs` Uygulamasıdır çok benzer `CDocument::OnFileSaveAs`dışında belge nesnesi "için temel alınan dosya kaydetme işleminden sonra bağlı değil". Bellek içi "kaydetme önce değiştirilmiş. belgeyi," diğer bir deyişle, yine de "değişiklik". Ayrıca, bu komut yol adı veya belge içinde depolanan başlık üzerinde etkisi yoktur.

- Id_fıle_update ekli belge kaydetmek için kapsayıcı bildirir.

   `COleServerDoc::OnUpdateDocument` Uygulama notifiies katıştırma kaydedilmesi gereken kapsayıcı yeterlidir. Kapsayıcı sonra katıştırılmış nesneyi kaydetmek için uygun OLE API'lerini çağırır.

- Bir uygulamaya özgü sayfa Kurulum/düzeni iletişim ıd_fıle_page_setup çağırır.

   Şu anda bu iletişim kutusu için standart yoktur ve bu komutun varsayılan uygulaması framework vardır.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_fıle_prınt_setup standart Sayfa Yapısı iletişim kutusu çağırma.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   Bu komut kullanıcının özelleştirme yazıcı ve yazdırma ayarları için en az izin veren standart yazdırma ayarları iletişim kutusunu çağırır bu belge veya en fazla tüm belgelerde bu uygulama. Tüm sistemin varsayılan yazıcı ayarlarını değiştirmek için Denetim Masası'nı kullanmanız gerekir.

   `CWinApp::OnFilePrintSetup` olan bir çok basit uygulama oluşturma bir `CPrintDialog` nesne ve arama `CWinApp::DoPrintDialog` uygulama işlevi. Bu, uygulama varsayılan yazıcı kurulumu ayarlar.

   Bu komut özelleştirmeye yönelik ortak gereken Belge kaydedildiğinde depolanması gereken belge başına yazıcı ayarları için izin vermektir. Bunu yapmak için ileti eşlemesi işleyici eklemeniz gerekir, `CDocument` oluşturan sınıf bir `CPrintDialog` nesne, uygun yazıcı özniteliklerle başlatır (genellikle *hDevMode* ve *hDevNames*), çağrı `CPrintDialog::DoModal`ve değiştirilen yazıcı ayarlarını kaydedin. Sağlam bir uygulama için uygulanması görünmelidir `CWinApp::DoPrintDialog` hataları algılamak ve `CWinApp::UpdatePrinterSelection` mantıklı varsayılanlar ile ilgilenen ve sistem genelinde yazıcı değişiklikleri izlemek için.

- Geçerli belgenin ıd_fıle_prınt standart yazdırma

    > [!NOTE]
    >  Şuna bağlanmak, `CView`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   Bu komut, geçerli belge yazdırır veya daha doğru bir şekilde standart yazdırma iletişim kutusu çağırma ve yazdırma altyapısı çalıştıran yazdırma işlemi başlatır.

   `CView::OnFilePrint` Bu komut ve ana yazdırma döngüsü uygular. Sanal çağrı `CView::OnPreparePrinting` Yazdır iletişim kutusu ile Kullanıcı istemi. Ardından DC çıkış yazıcıya gitmek için hazırlar, (AFX_IDD_PRINTDLG) yazdırma ilerleme durumu iletişim kutusunu açar ve gönderen `StartDoc` kaçış yazıcı. `CView::OnFilePrint` Ayrıca ana sayfa yönelimli yazdırma döngü içeriyor. Her bir sayfa için sanal çağırır `CView::OnPrepareDC` arkasından bir `StartPage` kaçış ve sanal çağırma `CView::OnPrint` o sayfanın. Tamamlandığında, sanal `CView::OnEndPrinting` denir ve yazdırma ilerleme iletişim kutusu kapatılır.

   MFC yazdırma mimarisi, yazdırma ve yazdırma önizleme için birçok farklı yöntem için tasarlanmıştır. Normalde çeşitli bulabilirsiniz `CView` geçersiz kılınabilir işlevler tüm sayfa yönelimli yazdırma görevleri için yeterli. Yazıcı için sayfa olmayan yönlendirilmiş çıkış kullanan yalnızca bir uygulama söz konusu olduğunda, ıd_fıle_prınt uygulamasını değiştirmek için gereken bulmanız gerekir.

- Id_fıle_prınt_prevıew girin Yazdır-Önizle moduna geçerli belge için.

    > [!NOTE]
    >  Şuna bağlanmak, `CView`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CView::OnFilePrintPreview` Baskı Önizleme modunu belgelenmiş yardımcı işlevini çağırarak başlar `CView::DoPrintPreview`. `CView::DoPrintPreview` Ana baskı önizlemeyi döngünün gibi altyapısıdır `OnFilePrint` yazdırma döngü için ana altyapısıdır.

   Baskı Önizleme işlemi için farklı parametreler geçirerek çeşitli şekillerde özelleştirilebilir `DoPrintPreview`. Lütfen [Teknik Not 30](../mfc/tn030-customizing-printing-and-print-preview.md)baskı önizlemeyi ayrıntılarının bazılarını açıklar ve nasıl özelleştireceğinizi.

- ID_FILE_MRU_FILE1... FILE16 Komut kimlikleri için dosya MRU çeşitli **listesi**.

   `CWinApp::OnUpdateRecentFileMenu` on_update_command_uı mekanizmasının daha gelişmiş kullandığı biri olan bir güncelleştirme komut UI işleyicisidir. Menü kaynağınızı kimliği ID_FILE_MRU_FILE1 ile yalnızca tek bir menü öğesi tanımlamanız gerekir. Bu menü öğesi, başlangıçta devre dışı kalır.

   MRU Listesi büyüdükçe, daha fazla menü öğeleri listesine eklenir. Standart `CWinApp` uygulama varsayılan olarak, dört en son kullanılan dosyaların standart sınırla. Varsayılan çağırarak değiştirebilirsiniz `CWinApp::LoadStdProfileSettings` daha büyük veya küçük bir değere sahip. MRU Listesi içinde uygulamanın depolanır. INI dosyası. Listenin uygulamanızın yüklenen `InitInstance` çağırırsanız işlev `LoadStdProfileSettings`, uygulamanız çıkış yaptığında kaydedilir. MRU komut güncelleştirme kullanıcı Arabirimi işleyicisi de mutlak yolları göreli yollar için Dosya menüsünde görünen dönüştürülecektir.

   `CWinApp::OnOpenRecentFile` Gerçek komutu gerçekleştirir ON_COMMAND işleyicisidir. Yalnızca dosya adını MRU listesi ve çağrıları alır `CWinApp::OpenDocumentFile`, tüm işini dosyasını açma ve MRU Listesi güncelleştiriliyor.

   Bu komut işleyici özelleştirmesini önerilmez.

- Geçerli seçimi ıd_edıt_clear temizler

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Bu komutu kullanarak, bir uygulama sağlar `CEdit::Clear`. Geçerli seçim yok ise, komutu devre dışı bırakıldı.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_clear_all belgenin tamamını temizler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz MFC öğretici örnek görmek [KARALAMA](../overview/visual-cpp-samples.md) örnek uygulama.

- Id_edıt_copy geçerli Seçimi panoya kopyalar.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Seçili durumdaki metni CF_TEXT kullanarak olarak panoya kopyalar. Bu komut bir uygulamasını sağlar `CEdit::Copy`. Geçerli seçim yok ise, komutu devre dışı bırakıldı.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Geçerli seçimi panoya ıd_edıt_cut keser.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` CF_TEXT kullanarak olarak panoya seçili metni keser. Bu komut bir uygulamasını sağlar `CEdit::Cut`. Geçerli seçim yok ise, komutu devre dışı bırakıldı.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_fınd başlar bulma işlemi, kalıcı olmayan Bul iletişim kutusunu getirir.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Bu komutun uygulaması yardımcı işlevini çağıran bir uygulama sağlar `OnEditFindReplace` kullanın ve özel uygulama değişkenlerinde önceki Bul/Değiştir ayarları depolamak için. `CFindReplaceDialog` Sınıfı, kullanıcıdan istemek için kalıcı olmayan iletişim yönetmek için kullanılır.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_paste geçerli Pano içeriklerini ekler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Bu komutu kullanarak seçili metni değiştirme geçerli Pano verileri kopyalayan bir uygulamasını sağlar `CEdit::Paste`. Varsa komutu devre dışı hiçbir **CF_TEXT** Panodaki.

   `COleClientDoc` yalnızca bir güncelleştirme komut UI işleyici bu komut için sağlar. Pano gömülebilir OLE öğesi/nesnesi içermiyorsa komutu devre dışı bırakılır. Gerçek yapıştırma yapmak gerçek komut işleyicisi yazmak için sorumlu olursunuz. OLE uygulamanızın diğer biçimlere de yapıştırabilirsiniz, görünümü veya belgeyi kendi güncelleştirme komut UI işleyici sağlamanız (diğer bir deyişle, bir yere önce `COleClientDoc` komut hedef akışındaki).

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

   Standart OLE uygulaması değiştirmek için kullanın `COleClientItem::CanPaste`.

- Id_edıt_paste_lınk geçerli Pano içeriğini kopyalayıp bir bağlantı ekler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `COleDocument` yalnızca bir güncelleştirme komut UI işleyici bu komut için sağlar. Pano değişkenlerinden OLE öğesi/nesnesine içermiyor, komutu devre dışı bırakılır. Gerçek yapıştırma yapmak gerçek komut işleyicisi yazmak için sorumlu olursunuz. OLE uygulamanızın diğer biçimlere de yapıştırabilirsiniz, görünümü veya belgeyi kendi güncelleştirme komut UI işleyici sağlamanız (diğer bir deyişle, bir yere önce `COleDocument` komut hedef akışındaki).

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

   Standart OLE uygulaması değiştirmek için kullanın `COleClientItem::CanPasteLink`.

- Id_edıt_paste_specıal seçeneklerle geçerli Pano içeriklerini ekler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf. MFC iletişim sağlamaz.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_repeat son işlemi yineler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` son bulma işlemi yinelemek için bu komutu bir uygulamasını sağlar. Son bulma özel uygulama değişkenleri kullanılır. Bir bulma denenirse komutu devre dışı bırakıldı.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_replace başlar değiştirme işlemi, kalıcı olmayan Değiştir iletişim kutusunu getirir.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Bu komutun uygulaması yardımcı işlevini çağıran bir uygulama sağlar `OnEditFindReplace` kullanın ve özel uygulama değişkenlerinde önceki Bul/Değiştir ayarları depolamak için. `CFindReplaceDialog` Sınıfı kullanıcıdan kalıcı olmayan iletişim yönetmek için kullanılır.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_select_all tüm belgeyi seçer.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Belgedeki tüm metni seçer bu komut bir uygulamasını sağlar. Seçilecek hiçbir metin ise komutu devre dışı bırakıldı.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_undo son işlemi iptal eder.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   `CEditView` Bu bir uygulamasını sağlar komutu `CEdit::Undo`. Komutu, devre dışı bırakılır `CEdit::CanUndo` false değerini döndürür.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_edıt_redo son işlemi yineler.

   Şu anda bu komut için standart uygulaması yoktur. Bu her biri için uygulamanız gereken `CView`-türetilmiş sınıf.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_wındow_new etkin belgede başka bir pencere açılır.

   `CMDIFrameWnd::OnWindowNew` Bu güçlü bir özellik, geçerli belgenin başka bir görünüm içeren başka bir kare oluşturmak için geçerli belgenin belge şablonu kullanarak uygular.

   Etkin MDI alt penceresi yok ise, çoğu birden çok belge arabirimi (MDI) pencere menü komutları gibi komutu devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez. Ek görünümler veya çerçeve pencereleri oluşturan komut sağlamak istiyorsanız, büyük olasılıkla kendi komut inventing kapalı daha iyi olacaktır. Koddan kopyalayabilirsiniz `CMDIFrameWnd::OnWindowNew` ve dilediğiniz gibi belirli çerçeve ve görünüm sınıfları için değiştirin.

- Bir MDI pencerenin altındaki simgeleri ıd_wındow_arrange düzenler.

   `CMDIFrameWnd` Bu standart MDI komut bir uygulama Yardımcısı işlevi uygulayan `OnMDIWindowCmd`. Bu yardımcı, komut kimlikleri MDI Windows iletilerini eşler ve bu nedenle çok fazla kod paylaşabilirsiniz.

   Etkin MDI alt penceresi yok ise, çoğu MDI pencere menü komutları gibi komutu devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez.

- Örtüşecek şekilde pencereleri ıd_wındow_cascade basamaklar.

   `CMDIFrameWnd` Bu standart MDI komut bir uygulama Yardımcısı işlevi uygulayan `OnMDIWindowCmd`. Bu yardımcı, komut kimlikleri MDI Windows iletilerini eşler ve bu nedenle çok fazla kod paylaşabilirsiniz.

   Etkin MDI alt penceresi yok ise, çoğu MDI pencere menü komutları gibi komutu devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_wındow_tıle_horz kutucukları windows yatay olarak.

   Bu komut, uygulanan `CMDIFrameWnd` olduğu gibi ıd_wındow_cascade, farklı bir MDI Windows ileti işlemi için kullanılacak dışında.

   Uygulamanız için varsayılan kutucuk yönlendirmesini seçmeniz gerekir. Id_wındow_tıle_horz ya da ıd_wındow_tıle_vert pencereyi "Kutucuğunu" menü öğesi Kimliğini değiştirerek bunu yapabilirsiniz.

- Id_wındow_tıle_vert kutucukları windows dikey.

   Bu komut, uygulanan `CMDIFrameWnd` olduğu gibi ıd_wındow_cascade, farklı bir MDI Windows ileti işlemi için kullanılacak dışında.

   Uygulamanız için varsayılan kutucuk yönlendirmesini seçmeniz gerekir. Id_wındow_tıle_horz ya da ıd_wındow_tıle_vert pencereyi "Kutucuğunu" menü öğesi Kimliğini değiştirerek bunu yapabilirsiniz.

- Id_wındow_splıt klavye arabirimine ayırıcı.

   `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm bir ayırıcı penceresi parçası ise, bu komut uygulama işlevine temsil edecek `CSplitterWnd::DoKeyboardSplit`. Bu bölme, klavye kullanıcıların bölebilir veya sayfanın toplamında bir ayırıcı penceresi sağlayacak bir modda yerleştirmeniz gerekir.

   Bu komut, görünümü içinde bir ayırıcı değilse devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_app_about hakkında iletişim kutusunu çağırır.

   Bir uygulamanın hakkında kutusu için standart uygulaması yok. AppWizard ile oluşturulan varsayılan uygulama, uygulamanız için özel bir iletişim kutusu sınıfı oluşturma ve hakkında box'ınızı kullanabilirsiniz. AppWizard Ayrıca bu komutu işler ve iletişim kutusunu çağırır Önemsiz komut işleyici yazılacaktır.

   Bu komut, hemen her zaman uygular.

- Id_app_exıt uygulama çıkın.

   `CWinApp::OnAppExit` Bu komut, uygulamanın ana pencere için bir WM_CLOSE iletisini göndererek işler. Standart (bozuk dosyalar için vb. isteyen) kapatılması tarafından işlenir `CFrameWnd` uygulaması.

   Bu komut işleyici özelleştirmesini önerilmez. Geçersiz kılma `CWinApp::SaveAllModified` veya `CFrameWnd` mantıksal kapatma önerilir.

   Bu komut uygulamak seçerseniz, bu komut kimliği kullanmanızı öneririz

- Id_help_ındex listeler Yardım konuları. HLP dosyasına bakın.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnHelpIndex` Bu komut, basit bir şekilde çağırarak işler `CWinApp::WinHelp`.

   Bu komut işleyici özelleştirmesini önerilmez.

- Yardım'ı kullanma hakkında Yardım ıd_help_usıng görüntüler.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnHelpUsing` Bu komut, basit bir şekilde çağırarak işler `CWinApp::WinHelp`.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_context_help girer SHIFT-F1 Yardım modu.

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnContextHelp` Bu komut, imleci Yardım modu ayarı, kalıcı bir döngünün girip hakkında Yardım almak için bir pencere seçmek kullanıcı için bekleyen işler. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) MFC yardımcı uygulama hakkında daha fazla bilgi.

   Bu komut işleyici özelleştirmesini önerilmez.

- Geçerli bağlamda yardımcı ıd_help sağlar

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   `CWinApp::OnHelp` Bu komut, geçerli uygulama içeriği için doğru Yardım bağlamında alarak işler. Bu basit F1 Yardımı işlediğinde, ileti kutularını vb. yardımcı olur. Lütfen [Teknik Not 28](../mfc/tn028-context-sensitive-help-support.md) MFC hakkında daha fazla ayrıntı uygulamasına yardımcı olmak için.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_default_help görüntüler varsayılan bağlamı için bir Yardım

    > [!NOTE]
    >  Şuna bağlanmak, `CWinApp`-bu işlevselliği etkinleştirmek için ileti eşlemesi sınıfın türetilmiş.

   Bu komut genellikle eşlenmiş `CWinApp::OnHelpIndex`.

   Varsayılan Yardım ve Yardım dizin arasında bir ayrım isterseniz farklı komut işleyici sağlanabilir.

- Id_next_pane gider sonraki bölme

   `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm bir ayırıcı penceresi parçası ise, bu komut uygulama işlevine temsil edecek `CSplitterWnd::OnNextPaneCmd`. Bölümlendirici sonraki bölmesine etkin görünüm taşınır.

   Bu komut görünümü içinde bir ayırıcı değil ya da gitmek için hiçbir sonraki bölme devre dışı bırakılır.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_prev_pane gider Önceki Bölme

   `CView` Bu komut için işleme `CSplitterWnd` uygulaması. Görünüm bir ayırıcı penceresi parçası ise, bu komut uygulama işlevine temsil edecek `CSplitterWnd::OnNextPaneCmd`. Bölümlendirici önceki bölmesine etkin görünüm taşınır.

   Bu komut, görünümü içinde bir ayırıcı değil veya yok önceki bölme gitmek için devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez.

- Id_ole_ınsert_new yeni bir OLE nesnesi ekler

   Şu anda bu komut için standart uygulaması yoktur. Bu uygulama, `CView`-türetilmiş sınıf geçerli seçimi daha yeni bir OLE öğesi/nesne eklemek için.

   Bu komut tüm OLE istemci uygulamaları uygulamalıdır. AppWizard OLE seçeneğiyle bir çatı uygulaması oluşturacaktır `OnInsertObject` görünümü sınıfınızda, tamamlanması gerekir.

   MFC OLE örnek görmek [OCLIENT](../overview/visual-cpp-samples.md) bu komut, tam bir uygulama için örnek.

- Id_ole_edıt_lınks düzenler OLE bağlantılar

   `COleDocument` Bu komut, standart OLE bağlantılar iletişim sağlanan MFC uygulamasını kullanarak işler. Bu iletişim kutusunu uygulaması aracılığıyla erişilir `COleLinksDialog` sınıfı. Geçerli belge bağlantıları içermiyorsa komutu devre dışı bırakıldı.

   Bu komut işleyici özelleştirmesini önerilmez.

- ID_OLE_VERB_FIRST... OLE fiilleri için son bir kimlik aralığı

   `COleDocument` Bu komut kimliği aralığı şu anda seçili OLE öğesini/nesnesi tarafından desteklenen fiiller için kullanır. Belirli bir OLE öğesi/nesne türü sıfır veya daha fazla özel fiilleri destekleyebilir olduğundan bu aralığı olmalıdır. Uygulama menüsünde, bir menü öğesi, kimliği ıd_ole_verb_fırst sahip olması gerekir. Programını çalıştırdığınızda, menü uygun menü fiili açıklaması (veya açılır menü ile birçok fiilleri) ile güncelleştirilecektir. OLE menüsünün yönetim tarafından işlenen `AfxOleSetEditMenu`, bu komut için güncelleştirme komut UI işleyicisinde bitti.

   Her komut kimliği bu aralıktaki bir işleme için hiçbir açık komut işleyicileri vardır. `COleDocument::OnCmdMsg` Bu aralıktaki tüm komut kimlikleri tuzak, sıfır tabanlı fiili sayılara açmak ve sunucu bu fiil için geçersiz kılındı (kullanarak `COleClientItem::DoVerb`).

   Özelleştirme veya bu komut kimliği aralığı diğer kullanımı önerilmez.

- Id_vıew_toolbar araç açıp kapatır

   `CFrameWnd` Bu komut ve komut güncelleştirme kullanıcı Arabirimi işleyicisi araç çubuğu görünür durumunu değiştirmek için işler. Araç, alt penceresi kimliği, AFX_IDW_TOOLBAR ile alt pencere çerçevesinin olması gerekir. Komut işleyici gerçekten araç penceresi görünürlüğünü açıp kapatır. `CFrameWnd::RecalcLayout` çerçeve penceresi araç çubuğu ile yeni durumunda yeniden çizmek için kullanılır. Araç çubuğu görünür olduğunda komut güncelleştirme kullanıcı Arabirimi işleyicisi menü öğesi denetler.

   Bu komut işleyici özelleştirmesini önerilmez. Ek araç çubukları eklemek istiyorsanız, kopyalama ve komut işleyici ve güncelleştirme komut UI işleyici bu komut için değiştirmek istersiniz.

- Id_vıew_status_bar açar ve durum çubuğu kapatır

   Bu komut, uygulanan `CFrameWnd` olduğu gibi ıd_vıew_toolbar, farklı alt pencere dışında kimliği (AFX_IDW_STATUS_BAR) kullanılır.

## <a name="update-only-command-handlers"></a>Yalnızca güncelleştirme komut işleyicileri

Birçok standart komut kimlikleri, durum çubukları göstergeleri olarak kullanılır. Bunlar aynı işleme mekanizması komut güncelleştirme kullanıcı Arabirimi uygulama boşta kalma süresi sırasında visual bunların geçerli durumunu görüntülemek için kullanın. Kullanıcı tarafından seçilemez bu yana (diğer bir deyişle, bir durum çubuğu bölmesinin gönderemezsiniz), sonra da ON_COMMAND işleyici bu komut kimlikleri için hiçbir mantıklı.

- ID_INDICATOR_CAPS: CAP kilit göstergesi.

- ID_INDICATOR_NUM: NUM lock göstergesi.

- ID_INDICATOR_SCRL: SCRL kilit göstergesi.

- ID_INDICATOR_KANA: KANA göstergesi (yalnızca Japonca sistemleri için geçerlidir) kilitleyin.

Bu üç uygulanan `CFrameWnd::OnUpdateKeyIndicator`, uygun sanal anahtara eşlemek için komut kimliği kullanan bir uygulama Yardımcısı. Sık kullanılan bir uygulamasını etkinleştirir veya devre dışı bırakır (devre dışı durum bölmeleri için metin =) `CCmdUI` bağlı olarak uygun sanal anahtarı şu anda kilitli nesne.

Bu komut işleyici özelleştirmesini önerilmez.

- ID_INDICATOR_EXT: Genişletilmiş göstergesi seçin.

- ID_INDICATOR_OVR: Üzerine yerleştirme göstergesi.

- ID_INDICATOR_REC: Kayıt göstergesi.

Şu anda bu göstergeleri standart uygulaması yoktur.

Bu göstergeler uygulamak seçerseniz, bu göstergesi kimlikleri ve göstergeleri, durum çubuğundaki sırayı korumanın kullanmanız önerilir (diğer bir deyişle, bu sırada: EXT, CAP, NUM, SCRL, OVR, REC).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
