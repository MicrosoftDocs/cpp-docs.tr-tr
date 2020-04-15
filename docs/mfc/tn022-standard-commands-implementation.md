---
title: 'TN022: Standart Komutları Uygulama'
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
ms.openlocfilehash: 5c7041f40c7e30592f642d29d9d02812a9596864
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370391"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Standart Komutları Uygulama

> [!NOTE]
> Aşağıdaki teknik not, çevrimiçi belgelere ilk olarak eklenmediğinden beri güncelleştirilemedi. Sonuç olarak, bazı yordamlar ve konular güncel veya yanlış olabilir. En son bilgiler için, çevrimiçi belge dizini ilgi alanı için arama nız önerilir.

Bu not, MFC 2.0 tarafından sağlanan standart komut uygulamalarını açıklar. Standart komutların çoğunu uygulamak için kullanılan mekanizmaları açıkladığı için önce [Teknik Not 21'i](../mfc/tn021-command-and-message-routing.md) okuyun.

Bu açıklama, MFC mimarileri, API'ler ve yaygın programlama uygulamaları hakkında bilgi varsayar. Belgelenmiş yanı sıra belgesiz "uygulama sadece" API'ler açıklanmıştır. Burası, MFC'de programlanma nın özellikleri veya nasıl programyapılacağı hakkında bilgi edinmek için bir yer değildir. Daha genel bilgiler ve belgelenmiş API'lerin ayrıntıları için Visual C++ bölümüne bakın.

## <a name="the-problem"></a>Sorun

MFC, aFXRES üstbilgi dosyasında birçok standart komut iD'si tanımlar. H. Bu komutlar için çerçeve desteği değişir. Çerçeve sınıflarının bu komutları nerede ve nasıl işleyeceğini anlamak yalnızca çerçevenin dahili olarak nasıl çalıştığını göstermekle birlikte, standart uygulamaları özelleştirmeniz ve kendi komut işleyicilerinizi uygulamak için size birkaç teknik öğretmek hakkında yararlı bilgiler sağlar.

## <a name="contents-of-this-technical-note"></a>Bu Teknik Notun İçeriği

Her komut kimliği iki bölümde açıklanmıştır:

- Başlık: komut kimliğinin sembolik adı (örneğin, ID_FILE_SAVE) ardından komutun amacı (örneğin, "geçerli belgeyi kaydeder") bir üst üste ayrılmıştır.

- Komutu hangi sınıfların uyguladığını ve varsayılan uygulamanın ne işe yaradığı açıklayan bir veya daha fazla paragraf

Varsayılan komut uygulamalarının çoğu, çerçevenin taban sınıf ileti haritasında önceden döşenir. Türemiş sınıfınızda açık kablolama gerektiren bazı komut uygulamaları vardır. Bunlar "Not" altında açıklanmıştır. AppWizard'da doğru seçenekleri seçtiyseniz, bu varsayılan işleyiciler oluşturulan iskelet uygulamasında sizin için bağlanır.

## <a name="naming-convention"></a>Adlandırma Kuralı

Standart komutlar, mümkünse kullanmanızı önerdiğimiz basit bir adlandırma kuralını izler. Standart komutların çoğu, uygulamanın menü çubuğundaki standart yerlerde bulunur. Komutun sembolik adı "ID_" ile başlar ve ardından standart açılır menü adı ve ardından menü öğesi adı gelir. Sembolik adı büyük harfle kelime-break'ler altını çizer. Standart menü öğesi adları olmayan komutlar için "ID_" (örneğin, ID_NEXT_PANE) ile başlayan mantıksal bir komut adı tanımlanır.

Menü öğelerine, araç çubuğu düğmelerine veya diğer komut kullanıcı arabirimi nesnelerine bağlı olacak şekilde tasarlanmış komutları belirtmek için "ID_" önekini kullanırız. "ID_" komutlarını işleyen komut işleyicileri, MFC komut mimarisinin ON_COMMAND ve ON_UPDATE_COMMAND_UI mekanizmalarını kullanmalıdır.

Komut mimarisini izlemeyen ve bunları etkinleştirmek ve devre dışı etmek için menüye özel kodgerektiren menü öğeleri için standart "IDM_" önekini kullanmanızı öneririz. MFC komut mimarisini takip etmek yalnızca komut işleyicilerini daha güçlü hale getirir (araç çubuklarıyla çalışacakları için) komut işleyicisi kodunu yeniden kullanılabilir hale getirir.

## <a name="id-ranges"></a>Kimlik Aralıkları

MFC'deki kimlik aralıklarının kullanımı hakkında daha fazla bilgi için lütfen [Technical Note 20'ye](../mfc/tn020-id-naming-and-numbering-conventions.md) bakın.

MFC standart komutları 0xE000 ile 0xEFFF aralığında düşer. Kitaplığın gelecekteki sürümlerinde değişikliğe tabi olduğundan, lütfen bu ifadelerin belirli değerlerine güvenmeyin.

Uygulamanız 0x8000 ile 0xDFFF aralığındaki komutlarını tanımlamalıdır.

## <a name="standard-command-ids"></a>Standart Komut TIsi

Her komut kimliği için, dosya PROMPTS'da bulunabilecek standart bir ileti satırı istem dizesi vardır. Rc. Bu menü isteminin dize kimliği komut kimliğiyle aynı olmalıdır.

- ID_FILE_NEW Yeni/boş bir belge oluşturur.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnFileNew`bu komutu, uygulamadaki belge şablonlarının sayısına bağlı olarak farklı şekilde uygular. Yalnızca biri `CDocTemplate`varsa, `CWinApp::OnFileNew` bu tür yeni bir belge yanı sıra uygun çerçeve ve görünüm sınıfı oluşturur.

   Birden `CDocTemplate`fazla varsa, `CWinApp::OnFileNew` kullanıcıya bir iletişim kutusu (AFX_IDD_NEWTYPEDLG) ile istenir ve hangi belge türünü kullanacaklarını seçmelerine izin verilir. Seçili `CDocTemplate` belgeyi oluşturmak için kullanılır.

   ID_FILE_NEW yaygın özelleştirmebelge türleri farklı ve daha grafiksel bir seçim sağlamaktır. Bu durumda kendi `CMyApp::OnFileNew` uygulayabilir ve yerine mesaj haritanıza `CWinApp::OnFileNew`yerleştirebilirsiniz. Taban sınıf uygulamasını çağırmaya gerek yoktur.

   ID_FILE_NEW başka bir yaygın özelleştirme, her tür bir belge oluşturmak için ayrı bir komut sağlamaktır. Bu durumda, örneğin ID_FILE_NEW_CHART ve ID_FILE_NEW_SHEET gibi yeni komut tanımlarını tanımlamanız gerekir.

- ID_FILE_OPEN Varolan bir belgeyi açar.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnFileOpen`açmak için dosya veya `CWinApp::DoPromptFileName` yol `CWinApp::OpenDocumentFile` adı ile takip arama çok basit bir uygulama vardır. Uygulama `CWinApp` yordamı `DoPromptFileName` standart FileOpen iletişim kutusunu getirir ve geçerli belge şablonlarından elde edilen dosya uzantılarıyla doldurur.

   ID_FILE_OPEN yaygın özelleştirmelerinden biri, FileOpen iletişim kutusunu özelleştirmek veya ek dosya filtreleri eklemektir. Bunu özelleştirmenin önerilen yolu, varsayılan uygulamayı kendi FileOpen iletişim günlüğünzle `CWinApp::OpenDocumentFile` değiştirmek ve belgenin dosya veya yol adı ile arama yapmaktır. Taban sınıfını aramanız gerekmez.

- ID_FILE_CLOSE Şu anda açık olan belgeyi kapatır.

   `CDocument::OnFileClose``CDocument::SaveModified` değiştirilen ve daha sonra çağırırsa, `OnCloseDocument`kullanıcıdan belgeyi kaydetmesini ister. Belgenin yok edilmesi de dahil olmak üzere `OnCloseDocument` tüm kapanış mantığı rutin olarak yapılır.

    > [!NOTE]
    >  ID_FILE_CLOSE, belgeler çerçeve penceresine gönderilen WM_CLOSE iletisinden veya SC_CLOSE sistem komutundan farklı davranır. Pencereyi kapatmak, yalnızca belgeyi gösteren son çerçeve penceresiyse belgeyi kapatır. Belgeyi ID_FILE_CLOSE ile kapatmak yalnızca belgeyi kapatmakla birlikte, belgeyi gösteren tüm çerçeve pencerelerini de kapatır.

- ID_FILE_SAVE Geçerli belgeyi kaydeder.

   Uygulama hem de `CDocument::DoSave` `OnFileSave` `OnFileSaveAs`kullanılan bir yardımcı yordam kullanır. Daha önce kaydedilmemiş bir belgeyi (diğer bir deyişle, DosyaYeni örneğinde olduğu gibi bir yol adı yoktur) veya salt `OnFileSave` okunur belgeden okunan bir belgeyi kaydederseniz, mantık ID_FILE_SAVE_AS komutu gibi davranır ve kullanıcıdan yeni bir dosya adı sağlamasını ister. Dosyayı açma ve kaydetme yapma fiili işlemi sanal `OnSaveDocument`işlev üzerinden yapılır.

   ID_FILE_SAVE özelleştirmek için iki yaygın neden vardır. Kaydolmayan belgeler için, ID_FILE_SAVE menü öğelerini ve araç çubuğu düğmelerini kullanıcı arabiriminizden kaldırmanız yeterlidir. Ayrıca belgenizi asla kirletmediğinden (diğer bir `CDocument::SetModifiedFlag`zamanda aramayın) ve çerçevenin belgenin kaydedilmesine asla neden olmadığından emin olun. Disk dosyası dışında bir yere kaydeden belgeler için, bu işlem için yeni bir komut tanımlayın.

   Bir `COleServerDoc`, ID_FILE_SAVE durumunda hem dosya kaydetme (normal belgeler için) hem de dosya güncelleştirmesi (katıştırılmış belgeler için) için kullanılır.

   Belge verileriniz tek tek disk dosyalarında depolanıyorsa, ancak `CDocument` varsayılan serileştirme uygulamasını kullanmak `CDocument::OnSaveDocument` istemiyorsanız, '' yerine `OnFileSave`geçersiz kılmanız gerekir.

- ID_FILE_SAVE_AS Geçerli belgeyi farklı bir dosya adı altında kaydeder.

   Uygulama, `CDocument::OnFileSaveAs` `CDocument::DoSave` `OnFileSave`aynı yardımcı yordamı kullanır. Belgelerde `OnFileSaveAs` kayıttan önce dosya adı yoksa komut ID_FILE_SAVE gibi işlenir. `COleServerDoc::OnFileSaveAs`normal bir belge veri dosyasını kaydetmek veya başka bir uygulamaya katıştırılmış bir OLE nesnesini ayrı bir dosya olarak temsil eden bir sunucu belgesini kaydetmek için mantığı uygular.

   ID_FILE_SAVE mantığını özelleştirirseniz, büyük olasılıkla benzer bir şekilde ID_FILE_SAVE_AS özelleştirmek isteyebilirsiniz veya "Farklı Kaydet" işlemi belgeniz için geçerli olmayabilir. Gerekli değilse menü öğenizi menü çubuğunuzdan kaldırabilirsiniz.

- ID_FILE_SAVE_COPY_AS geçerli belgeyi yeni bir ad altında kaydeder.

   `CDocument::OnFileSaveAs`Uygulama, `COleServerDoc::OnFileSaveCopyAs` belge nesnesinin kaydedilmeden sonra temel dosyaya "iliştirilmiş" olmaması dışında çok benzer. Diğer bir deyişle, bellek içi belge kaydedilmeden önce "değiştirildi", yine de "değiştirilir". Ayrıca, bu komutun belgede depolanan yol adı veya başlığı üzerinde hiçbir etkisi yoktur.

- ID_FILE_UPDATE katıştılmış bir belgeyi kaydetmek için kapsayıcıyı not edinir.

   Uygulama, `COleServerDoc::OnUpdateDocument` katıştırma işleminin kaydedilmesi gerektiğini kapsayıcıya belirtir. Kapsayıcı daha sonra katıştırılmış nesneyi kaydetmek için uygun OLE API'lerini çağırır.

- ID_FILE_PAGE_SETUP Uygulamaya özgü bir sayfa kurulumu/düzeni iletişim kutusunu çağırır.

   Şu anda bu iletişim kutusu için bir standart yoktur ve çerçevede bu komutun varsayılan uygulaması yoktur.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_FILE_PRINT_SETUP Standart Yazdırma Kurulumu iletişim kutusunu çağırın.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   Bu komut, kullanıcının yazıcı yı ve yazdırma ayarlarını en azından bu belge veya bu uygulamadaki tüm belgeler için özelleştirmesine olanak tanıyan standart yazdırma kurulumu iletişim kutusunu çağırır. Tüm sistemin varsayılan yazıcı ayarlarını değiştirmek için Denetim Masası'nı kullanmanız gerekir.

   `CWinApp::OnFilePrintSetup`bir nesne oluşturma ve `CPrintDialog` `CWinApp::DoPrintDialog` uygulama işlevini çağıran çok basit bir uygulama vardır. Bu, uygulama varsayılan yazıcı kurulumlarını ayarlar.

   Bu komutu özelleştirmenin yaygın gereksinimi, kaydedildiğinde belgeyle birlikte depolanması gereken belge başına yazıcı ayarlarına izin vermektir. Bunu yapmak için `CDocument` sınıfınızda bir `CPrintDialog` nesne oluşturan bir ileti eşlem işleyicisi eklemeniz, uygun yazıcı öznitelikleriyle (genellikle `CPrintDialog::DoModal` *hDevMode* ve *hDevNames)* başlatılması, değiştirilen yazıcı ayarlarını aramanız ve değiştirilen yazıcı ayarlarını kaydetmeniz gerekir. Sağlam bir uygulama için, hataları algılama `CWinApp::DoPrintDialog` ve mantıklı `CWinApp::UpdatePrinterSelection` varsayılanlarla başa çıkmak ve sistem genelinde yazıcı değişikliklerini izlemek için uygulanmasına bakmalısınız.

- geçerli belgenin standart ID_FILE_PRINT yazdırma

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CView`gerekir.

   Bu komut, geçerli belgeyi yazdırır veya daha doğru bir şekilde, standart yazdırma iletişim kutusunu çağırmak ve yazdırma altyapısını çalıştırmayı içeren yazdırma işlemini başlatır.

   `CView::OnFilePrint`bu komutu ve ana yazdırma döngülerini uygular. Bu yazdırma `CView::OnPreparePrinting` iletişim kutusu ile kullanıcının istemi için sanal çağırır. Daha sonra çıkış DC'yi yazıcıya gitmeye hazırlar, yazdırma ilerleme iletişim kutusunu `StartDoc` (AFX_IDD_PRINTDLG) getirir ve kaçışı yazıcıya gönderir. `CView::OnFilePrint`ana sayfa yönelimli yazdırma döngüsüde de yer alıyor. Her sayfa için, bir `CView::OnPrepareDC` `StartPage` kaçış takip sanal çağırır `CView::OnPrint` ve bu sayfa için sanal arama. Tamamlandığında, sanal `CView::OnEndPrinting` çağrılır ve yazdırma ilerleme iletişim kutusu kapatılır.

   MFC baskı mimarisi, yazdırma ve yazdırma önizlemesi için birçok farklı şekilde kancaya takmak üzere tasarlanmıştır. Normalde sayfa yönelimli `CView` yazdırma görevleri için yeterli olan çeşitli geçersiz işlevleri bulacaksınız. Yalnızca sayfa yönelimli olmayan çıktı için yazıcıyı kullanan bir uygulama söz konusu olduğunda, ID_FILE_PRINT uygulamadeğiştirme gereksinimini bulmanız gerekir.

- ID_FILE_PRINT_PREVIEW Geçerli belgenin yazdırma önizleme modunu girin.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CView`gerekir.

   `CView::OnFilePrintPreview`belgelenen yardımcı işlevini `CView::DoPrintPreview`çağırarak yazdırma önizleme modunu başlatır. `CView::DoPrintPreview`baskı önizleme döngüsü için ana motor, `OnFilePrint` tıpkı yazdırma döngüsü için ana motor olduğu gibi.

   Yazdırma önizleme işlemi, farklı parametreleri `DoPrintPreview`. Lütfen baskı önizlemesinin bazı ayrıntılarını ve nasıl özelleştirilebildiğini anlatan [Teknik Not 30'a](../mfc/tn030-customizing-printing-and-print-preview.md)bakın.

- ID_FILE_MRU_FILE1... FILE MRU **listesi**için bir dizi komut ii.

   `CWinApp::OnUpdateRecentFileMenu`ON_UPDATE_COMMAND_UI mekanizmasının daha gelişmiş kullanımlarından biri olan bir güncelleştirme komutu Kullanıcı GEd işleyicisidir. Menü kaynağınızda, yalnızca kimlik ID_FILE_MRU_FILE1 içeren tek bir menü öğenizi tanımlamanız gerekir. Bu menü öğesi başlangıçta devre dışı kalır.

   MRU listesi büyüdükçe, listeye daha fazla menü öğesi eklenir. Standart `CWinApp` uygulama, en son kullanılan dört dosyanın standart sınırına varsayılan dır. Daha büyük veya daha `CWinApp::LoadStdProfileSettings` küçük bir değerle arayarak varsayılandeğeri değiştirebilirsiniz. MRU listesi uygulamanın . INI dosyası. Liste, ararsanız `LoadStdProfileSettings`uygulamanızın `InitInstance` işlevine yüklenir ve uygulamanız çıktığınızda kaydedilir. MRU güncelleştirme komutu Kullanıcı Arabirimi işleyicisi de dosya menüsünde görüntülenmek üzere göreli yollara mutlak yolları dönüştürür.

   `CWinApp::OnOpenRecentFile`gerçek komutu gerçekleştiren ON_COMMAND işleyicidir. Sadece MRU listesinden dosya adını alır `CWinApp::OpenDocumentFile`ve aramalar , hangi dosyayı açma ve MRU listesini güncelleme tüm işi yapar.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_EDIT_CLEAR Geçerli seçimi temizler

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`kullanarak bu komutun `CEdit::Clear`uygulanmasını sağlar. Geçerli bir seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_CLEAR_ALL tüm belgeyi temizler.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz. Örnek bir uygulama için MFC Tutorial örnek [SCRIBBLE'a](../overview/visual-cpp-samples.md) bakın.

- ID_EDIT_COPY Geçerli seçimi Pano'ya kopyalar.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`bu komutun uygulanmasını sağlar ve bu komut, seçili metni `CEdit::Copy`kullanarak CF_TEXT olarak Pano'ya kopyalar. Geçerli bir seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_CUT Geçerli seçimi Panoya keser.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`kullanarak `CEdit::Cut`CF_TEXT olarak Pano'ya şu anda seçili metni kesen bu komutun uygulanmasını sağlar. Geçerli bir seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_FIND Find işlemini başlayır, modeless bul iletişim kutusunu getirir.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`önceki bul/değiştir ayarlarını özel uygulama değişkenlerinde kullanmak ve depolamak için uygulama yardımcı işlevini `OnEditFindReplace` çağıran bu komutun bir uygulamasını sağlar. Sınıf, `CFindReplaceDialog` kullanıcıyı istenmek için modeless iletişim kutusunu yönetmek için kullanılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_PASTE Geçerli Pano içeriğini ekler.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`kullanarak seçili metni değiştirmek yerine geçerli Pano verilerini kopyalayan bu `CEdit::Paste`komutun uygulanmasını sağlar. Panoda **CF_TEXT** yoksa komut devre dışı bırakılır.

   `COleClientDoc`yalnızca bu komut için bir güncelleştirme komutu Kullanıcı Arabirimi işleyicisi sağlar. Pano katıştırılabilir bir OLE öğesi/nesnesi içermiyorsa, komut devre dışı bırakılır. Gerçek yapıştırma yapmak için gerçek komut için işleyici yazmak için sorumludur. OLE uygulamanız diğer biçimleri de yapıştırabiliyorsa, görünümünüzde veya belgenizde kendi güncelleştirme komutu `COleClientDoc` Kullanıcı Arabirimi işleyicinizi sağlamanız gerekir (diğer bir yerde komut hedef yönlendirmesinde daha önce bir yerde).

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

   Standart OLE uygulamasını değiştirmek için `COleClientItem::CanPaste`kullanın.

- ID_EDIT_PASTE_LINK Geçerli Pano içeriğinden bir bağlantı ekler.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `COleDocument`yalnızca bu komut için bir güncelleştirme komutu Kullanıcı Arabirimi işleyicisi sağlar. Pano bağlanabilir OLE öğesi/nesnesi içermiyorsa, komut devre dışı bırakılır. Gerçek yapıştırma yapmak için gerçek komut için işleyici yazmak için sorumludur. OLE uygulamanız diğer biçimleri de yapıştırabiliyorsa, görünümünüzde veya belgenizde kendi güncelleştirme komutu `COleDocument` Kullanıcı Arabirimi işleyicinizi sağlamanız gerekir (diğer bir yerde komut hedef yönlendirmesinde daha önce bir yerde).

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

   Standart OLE uygulamasını değiştirmek için `COleClientItem::CanPasteLink`kullanın.

- ID_EDIT_PASTE_SPECIAL Geçerli Pano içeriğini seçeneklerle ekler.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir. MFC bu iletişim kutusunu sağlamaz.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_REPEAT Son işlemi yineler.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`son bulma işlemini yinelemek için bu komutun uygulanmasını sağlar. Son bulma için özel uygulama değişkenleri kullanılır. Bir bulgu denenemiyorsa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_REPLACE Değiştirme işlemini başlayır, modeless replace iletişim kutusunu getirir.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`önceki bul/değiştir ayarlarını özel uygulama değişkenlerinde kullanmak ve depolamak için uygulama yardımcı işlevini `OnEditFindReplace` çağıran bu komutun bir uygulamasını sağlar. Sınıf, `CFindReplaceDialog` kullanıcıyı harekete sevk eden modeless iletişim kutusunu yönetmek için kullanılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_SELECT_ALL Belgenin tamamını seçer.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`belgedeki tüm metni seçen bu komutun uygulanmasını sağlar. Seçilecek metin yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_UNDO son işlemi geri alamamış.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   `CEditView`kullanarak `CEdit::Undo`bu komutun uygulanmasını sağlar. FALSE döndürürse `CEdit::CanUndo` komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_EDIT_REDO son operasyonu tekrar yapıyor.

   Şu anda bu komut için standart bir uygulama yoktur. Her `CView`türemiş sınıf için bunu uygulamanız gerekir.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_WINDOW_NEW Etkin belgeüzerinde başka bir pencere açar.

   `CMDIFrameWnd::OnWindowNew`geçerli belgenin başka bir görünümünü içeren başka bir çerçeve oluşturmak için geçerli belgenin belge şablonu kullanarak bu güçlü özelliği uygular.

   Çoğu birden çok belge arabirimi (MDI) Pencere menüsü komutları gibi, etkin MDI alt penceresi yoksa komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir. Ek görünümler veya çerçeve pencereleri oluşturan bir komut sağlamak istiyorsanız, büyük olasılıkla kendi komutunuzu icat etmek daha iyi olacaktır. Kodu klonlayabilir `CMDIFrameWnd::OnWindowNew` ve istediğiniz belirli çerçeve ve görünüm sınıflarına değiştirebilirsiniz.

- ID_WINDOW_ARRANGE MDI penceresinin altındaki simgeleri düzenler.

   `CMDIFrameWnd`bu standart MDI komutunu bir uygulama `OnMDIWindowCmd`yardımcı işlevinde uygular. Bu yardımcı komut işlemlerini MDI Windows iletilerine çizer ve bu nedenle çoğunluğu paylaşabilir.

   Çoğu MDI Penceresi menü komutu gibi, etkin MDI alt penceresi yoksa komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_WINDOW_CASCADE Cascades pencereleri üst üste gelen ler için.

   `CMDIFrameWnd`bu standart MDI komutunu bir uygulama `OnMDIWindowCmd`yardımcı işlevinde uygular. Bu yardımcı komut işlemlerini MDI Windows iletilerine çizer ve bu nedenle çoğunluğu paylaşabilir.

   Çoğu MDI Penceresi menü komutu gibi, etkin MDI alt penceresi yoksa komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_WINDOW_TILE_HORZ Döşemeleri pencereleri yatay olarak.

   Bu komut, işlem `CMDIFrameWnd` için farklı bir MDI Windows iletisi kullanılması dışında, tıpkı ID_WINDOW_CASCADE gibi uygulanır.

   Uygulamanız için varsayılan döşeme yönünü seçmelisiniz. Bunu, Pencere "Döşemesi" menü öğesinin kimliğini ID_WINDOW_TILE_HORZ veya ID_WINDOW_TILE_VERT olarak değiştirerek yapabilirsiniz.

- ID_WINDOW_TILE_VERT Döşemeleri pencereleri dikey olarak.

   Bu komut, işlem `CMDIFrameWnd` için farklı bir MDI Windows iletisi kullanılması dışında, tıpkı ID_WINDOW_CASCADE gibi uygulanır.

   Uygulamanız için varsayılan döşeme yönünü seçmelisiniz. Bunu, Pencere "Döşemesi" menü öğesinin kimliğini ID_WINDOW_TILE_HORZ veya ID_WINDOW_TILE_VERT olarak değiştirerek yapabilirsiniz.

- ID_WINDOW_SPLIT Klavye arabirimi splitter için.

   `CView`uygulama için bu `CSplitterWnd` komutu işler. Görünüm bir ayırıcı penceresinin bir parçasıysa, bu komut `CSplitterWnd::DoKeyboardSplit`uygulama işlevine devreder. Bu, ayırıcıyı klavye kullanıcılarının bir bölücü pencereyi bölmesine veya ayırmasına olanak tanıyan bir moda yerleştirilecektir.

   Görünüm bir ayırıcıda değilse, bu komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_APP_ABOUT Hakkında iletişim kutusunu çağırır.

   Bir uygulamanın About kutusu için standart bir uygulama yoktur. Varsayılan AppWizard oluşturulan uygulama, uygulamanız için özel bir iletişim sınıfı oluşturur ve bunu About kutunuz olarak kullanır. AppWizard ayrıca bu komutu işleyen ve iletişim kutusunu çağıran önemsiz komut işleyicisini de yazar.

   Hemen hemen her zaman bu komutu uygulayacak.

- ID_APP_EXIT Başvurudan çıkın.

   `CWinApp::OnAppExit`uygulamanın ana penceresine WM_CLOSE bir ileti göndererek bu komutu işler. Uygulamanın standart kapatma (kirli dosyalar vb. için isteyen) `CFrameWnd` uygulama tarafından işlenir.

   Bu komut işleyicisi özelleştirme önerilir. Geçersiz `CWinApp::SaveAllModified` kılma `CFrameWnd` veya kapanış mantığı önerilir.

   Bu komutu uygulamayı seçerseniz, bu komut kimliğini kullanmanızı öneririz.

- ID_HELP_INDEX Listeleri Yardım konuları. HLP dosyası.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnHelpIndex`bu komutu önemsiz bir `CWinApp::WinHelp`şekilde arayarak işler.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_HELP_USING Yardım'ın nasıl kullanılacağı nasıI yardımcı olur.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnHelpUsing`bu komutu önemsiz bir `CWinApp::WinHelp`şekilde arayarak işler.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_CONTEXT_HELP SHIFT-F1 yardım moduna girer.

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnContextHelp`yardım modu imlecini ayarlayarak, bir modal döngü girerek ve kullanıcının yardım almak için bir pencere seçmesini bekleyerek bu komutu işler. MFC Yardım uygulaması hakkında daha fazla bilgi için lütfen [Technical Note 28'e](../mfc/tn028-context-sensitive-help-support.md) bakın.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_HELP Geçerli bağlam hakkında yardım verir

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   `CWinApp::OnHelp`geçerli uygulama bağlamı için doğru yardım bağlamını alarak bu komutu işler. Bu basit F1 yardım, mesaj kutuları ve benzeri yardım işler. MFC yardım uygulaması hakkında daha fazla bilgi için lütfen [Technical Note 28'e](../mfc/tn028-context-sensitive-help-support.md) bakın.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_DEFAULT_HELP Bağlam için varsayılan yardımı görüntüler

    > [!NOTE]
    >  Bu işlevselliği etkinleştirmek için bunu türetilmiş sınıfın ileti eşlemasına bağlamanız `CWinApp`gerekir.

   Bu komut genellikle ' `CWinApp::OnHelpIndex`için eşlenir.

   Varsayılan Yardım ve Yardım dizini arasında bir ayrım istenirse farklı bir komut işleyicisi sağlanabilir.

- ID_NEXT_PANE Sonraki bölmeye gider

   `CView`uygulama için bu `CSplitterWnd` komutu işler. Görünüm bir ayırıcı penceresinin bir parçasıysa, bu komut `CSplitterWnd::OnNextPaneCmd`uygulama işlevine devreder. Bu, etkin görünümü ayırıcıdaki bir sonraki bölmeye taşır.

   Görünüm bir ayırıcıda değilse veya bir sonraki bölmeye gitmek yoksa bu komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_PREV_PANE Önceki bölmeye gider

   `CView`uygulama için bu `CSplitterWnd` komutu işler. Görünüm bir ayırıcı penceresinin bir parçasıysa, bu komut `CSplitterWnd::OnNextPaneCmd`uygulama işlevine devreder. Bu, etkin görünümü bölücüdeki önceki bölmeye taşır.

   Görünüm bir ayırıcıda değilse veya gidecek önceki bir bölme yoksa bu komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_OLE_INSERT_NEW Yeni bir OLE nesnesi ekler

   Şu anda bu komut için standart bir uygulama yoktur. Geçerli seçime yeni `CView`bir OLE öğesi/nesnesi eklemek için türetilmiş sınıfınız için bunu uygulamanız gerekir.

   Tüm OLE istemci uygulamaları bu komutu uygulamalıdır. AppWizard, OLE seçeneği ile, görünüm `OnInsertObject` sınıfınızda tamamlamanız gereken bir iskelet uygulaması oluşturur.

   Bu komutun tam olarak uygulanması için MFC OLE örnek [OCLIENT](../overview/visual-cpp-samples.md) örneğine bakın.

- ID_OLE_EDIT_LINKS OLE bağlantılarını edinimi

   `COleDocument`standart OLE bağlantıları iletişim kutusunun MFC tarafından sağlanan uygulamasını kullanarak bu komutu işler. Bu iletişim kutusunun uygulanmasına `COleLinksDialog` sınıf aracılığıyla erişilir. Geçerli belge herhangi bir bağlantı içermiyorsa, komut devre dışı bırakılır.

   Bu komut işleyicisi özelleştirme önerilir.

- ID_OLE_VERB_FIRST... SON OLE fiilleri için bir kimlik aralığı

   `COleDocument`şu anda seçili OLE öğesi/nesnesi tarafından desteklenen fiiller için bu komut kimliği aralığını kullanır. Belirli bir OLE öğesi/nesne türü sıfır veya daha fazla özel fiilleri destekleyediğinden, bu bir aralık olmalıdır. Uygulamanızın menüsünde, ID_OLE_VERB_FIRST kimliği içeren bir menü öğesi olmalıdır. Program çalıştırıldığında, menü uygun menü fiil açıklaması (veya birçok fiiliçeren açılır menü) ile güncellenir. OLE menüsünün `AfxOleSetEditMenu`yönetimi, bu komut için güncelleştirme komutu Kullanıcı Arabirimi işleyicisi tarafından gerçekleştirilir.

   Bu aralıkta komut kimliğinin her birini işlemek için açık komut işleyicileri yoktur. `COleDocument::OnCmdMsg`bu aralıktaki tüm komut kimliklerini tuzağa düşürmek, sıfır tabanlı fiil numaralarına dönüştürmek ve bu `COleClientItem::DoVerb`fiilin sunucuyu başlatmak (kullanarak) geçersiz kılınmış olur.

   Bu komut kimliği aralığının özelleştirilmesi veya başka bir şekilde kullanılması önerilmez.

- ID_VIEW_TOOLBAR araç çubuğunu açık ve kapalı olarak alatır

   `CFrameWnd`bu komutu ve araç çubuğunun görünür durumunu geçişiçin güncelleştirme komutu Kullanıcı Arabirimi işleyicisini işler. Araç çubuğu, AFX_IDW_TOOLBAR alt pencere kimliğine sahip çerçevenin alt penceresi olmalıdır. Komut işleyicisi aslında araç çubuğu penceresinin görünürlüğünü geçiş. `CFrameWnd::RecalcLayout`yeni durumunda araç çubuğu ile çerçeve penceresini yeniden çizmek için kullanılır. Denetim li ui işleyicisi, araç çubuğu görünür olduğunda menü öğesini denetler.

   Bu komut işleyicisi özelleştirme önerilir. Ek araç çubukları eklemek isterseniz, bu komut için komut işleyicisini ve güncelleştirme komutu kullanıcı arasını işleyicisini klonlamak ve değiştirmek istersiniz.

- ID_VIEW_STATUS_BAR Durum çubuğunu açık ve kapalı olarak geçişe çıkarır

   Bu komut, farklı `CFrameWnd` bir alt pencere kimliği (AFX_IDW_STATUS_BAR) kullanılması dışında, ID_VIEW_TOOLBAR gibi uygulanır.

## <a name="update-only-command-handlers"></a>Güncelleştirme-Yalnızca Komut Işleyicileri

Durum çubuklarında gösterge olarak çeşitli standart komut iD'leri kullanılır. Bunlar, uygulama boşta kalma süresi boyunca geçerli görsel durumlarını görüntülemek için aynı güncelleştirme komutu Kullanıcı Arabirimi işleme mekanizmasını kullanır. Kullanıcı tarafından seçilemedikleri için (diğer bir şekilde durum çubuğu bölmesini itemezsiniz), o zaman bu komut iDiler için ON_COMMAND bir işleyiciye sahip olmak mantıklı değildir.

- ID_INDICATOR_CAPS : CAP kilit göstergesi.

- ID_INDICATOR_NUM : NUM kilit göstergesi.

- ID_INDICATOR_SCRL : SCRL kilit göstergesi.

- ID_INDICATOR_KANA : KANA kilit göstergesi (sadece Japon sistemleri için geçerlidir).

Bunların üçü de, `CFrameWnd::OnUpdateKeyIndicator`uygun Sanal Anahtar'a eş sağlamak için komut kimliğini kullanan bir uygulama yardımcısı olarak uygulanır. Ortak bir uygulama, uygun Sanal Anahtarın şu anda kilitli `CCmdUI` olup olmadığına bağlı olarak nesneyi (durum bölmeleri devre dışı = metin yok) sağlar veya devre dışı eder.

Bu komut işleyicisi özelleştirme önerilir.

- ID_INDICATOR_EXT : EXTended select göstergesi.

- ID_INDICATOR_OVR : OVeRstrike göstergesi.

- ID_INDICATOR_REC : RECording göstergesi.

Şu anda bu göstergeler için standart bir uygulama yoktur.

Bu göstergeleri uygulamayı seçerseniz, bu gösterge iStatlarını kullanmanızı ve durum çubuğunuzdaki göstergelerin sırasını korumanızı öneririz (diğer bir deyişle: EXT, CAP, NUM, SCRL, OVR, REC).

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
