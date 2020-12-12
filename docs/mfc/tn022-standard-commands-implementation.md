---
description: 'Hakkında daha fazla bilgi edinin: TN022: standart komutlar uygulama'
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
ms.openlocfilehash: 7c8540dcf0e41e5f6d5f00a4f22568c4df0fcdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215813"
---
# <a name="tn022-standard-commands-implementation"></a>TN022: Standart Komutları Uygulama

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta, MFC 2,0 tarafından sunulan standart komut uygulamaları açıklanmaktadır. Standart komutların çoğunu uygulamak için kullanılan mekanizmaların açıklandığı için öncelikle [Teknik not21](../mfc/tn021-command-and-message-routing.md) ' i okuyun.

Bu açıklama MFC mimarileri, API 'Ler ve ortak programlama uygulaması hakkında bilgi sahibi olduğunu varsayar. Ayrıca belgelenmiş "yalnızca uygulama" API 'Leri açıklanır. Bu, MFC 'nin özellikleri veya programlama hakkında bilgi edinmeye başlamak için bir yer değildir. Daha fazla genel bilgi edinmek ve belgelenen API 'lerin ayrıntıları için Visual C++ bakın.

## <a name="the-problem"></a>Sorun

MFC, AFXRES. H başlık dosyasında birçok standart komut kimliği tanımlar. Bu komutlar için çerçeve desteği farklılık gösterir. Çerçeve sınıflarının bu komutları nasıl ve ne şekilde işleyeceğini anlamak, yalnızca çerçevenin dahili olarak nasıl çalıştığını göstermez, ancak standart uygulamaları özelleştirmeye ilişkin yararlı bilgiler sağlar ve kendi komut işleyicilerinizi uygulamaya yönelik birkaç teknik öğretir.

## <a name="contents-of-this-technical-note"></a>Bu teknik notun içeriği

Her komut KIMLIĞI iki bölümde açıklanmıştır:

- Başlık: komut KIMLIĞININ sembolik adı (örneğin, ID_FILE_SAVE), komutun amacını (örneğin, "geçerli belgeyi kaydeder") bir iki noktayla ayırarak.

- Komutu hangi sınıfların uygulayacağınızı ve varsayılan uygulamanın ne yaptığını açıklayan bir veya daha fazla paragraf

Çoğu varsayılan komut uygulaması, Framework 'ün temel sınıf ileti eşlemesinde önceden kablolu olarak bulunur. Türetilmiş sınıfınıza açık kablolama gerektiren bazı komut uygulamaları vardır. Bunlar "Note" altında açıklanmaktadır. AppWizard 'da doğru seçenekleri belirlediyseniz, bu varsayılan işleyiciler oluşturulan iskelet uygulamasında sizin için bağlanır.

## <a name="naming-convention"></a>Adlandırma Kuralı

Standart komutlar, mümkünse kullanmanızı önerdiğimiz basit bir adlandırma kuralını izler. Standart komutların çoğu, uygulamanın menü çubuğundaki standart yerlerde bulunur. Komutun sembolik adı "ID_" ile başlar ve ardından standart açılır menü adı ve menü öğesi adı gelir. Sembolik ad, alt çizgi sözcük sonları ile büyük harfle kaydedilir. Standart menü öğesi adlarına sahip olmayan komutlarda, "ID_" (örneğin, ID_NEXT_PANE) ile başlayan bir mantıksal komut adı tanımlanır.

Menü öğelerine, araç çubuğu düğmelerine veya diğer komuta Kullanıcı arabirimi nesnelerine bağlanacak şekilde tasarlanan komutları göstermek için "ID_" önekini kullanırız. Komut işleyicileri işleme "ID_" komutları, MFC komut mimarisinin ON_COMMAND ve ON_UPDATE_COMMAND_UI mekanizmalarını kullanmalıdır.

Komut mimarisini izleyen menü öğeleri için standart "IDM_" önekini kullanmanızı ve bunları etkinleştirmek ve devre dışı bırakmak için menüye özgü koda ihtiyaç duymasını öneririz. Tabii ki, bu yana menü özel komutlarının sayısının küçük olması gerekir, çünkü MFC komut mimarisi, yalnızca komut işleyicilerini daha güçlü hale getirir (Araç çubuklarıyla çalışadıklarından) ancak komut işleyici kodunu yeniden kullanılabilir hale getirir.

## <a name="id-ranges"></a>KIMLIK aralıkları

MFC 'de KIMLIK aralıklarının kullanımı hakkında daha fazla bilgi için lütfen bkz. [teknik nota](../mfc/tn020-id-naming-and-numbering-conventions.md) bakın.

MFC standart komutları 0xE000 ile 0xEFFF aralığında yer almalıdır. Kitaplığın sonraki sürümlerinde değişikliğe tabi olduklarından lütfen bu kimliklerin belirli değerlerini kullanmayın.

Uygulamanız, komutunu 0x8000 ile 0xDFFF aralığında tanımlamalıdır.

## <a name="standard-command-ids"></a>Standart komut kimlikleri

Her komut KIMLIĞI için, dosya ISTEMLERINDE bulunan standart bir ileti satırı İstem dizesi vardır. RC. Bu menü istemi için dize KIMLIĞI, komut KIMLIĞIYLE aynı olmalıdır.

- ID_FILE_NEW yeni/boş bir belge oluşturur.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnFileNew` uygulamadaki belge şablonlarının sayısına bağlı olarak bu komutu farklı şekilde uygular. Yalnızca bir tane varsa `CDocTemplate` , `CWinApp::OnFileNew` Bu türden yeni bir belge ve ayrıca uygun çerçeve ve görünüm sınıfı oluşturur.

   Birden fazla varsa `CDocTemplate` , `CWinApp::OnFileNew` kullanıcıya bir iletişim kutusu (AFX_IDD_NEWTYPEDLG) isteyecek ve hangi belge türünün kullanılacağını seçmesine izin verir. Seçilen, `CDocTemplate` belgeyi oluşturmak için kullanılır.

   ID_FILE_NEW ortak özelleştirmesi, farklı bir ve daha fazla grafik seçimi olan belge türlerini sağlamaktır. Bu durumda, kendi uygulamanızı uygulayabilir `CMyApp::OnFileNew` ve yerine ileti eşlemine yerleştirebilirsiniz `CWinApp::OnFileNew` . Temel sınıf uygulamasını çağırmaya gerek yoktur.

   ID_FILE_NEW diğer yaygın özelleştirmesi, her türden bir belge oluşturmak için ayrı bir komut sağlamaktır. Bu durumda, ID_FILE_NEW_CHART ve ID_FILE_NEW_SHEET gibi yeni komut kimliklerini tanımlamanız gerekir.

- ID_FILE_OPEN var olan bir belgeyi açar.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnFileOpen` , öğesini `CWinApp::DoPromptFileName` `CWinApp::OpenDocumentFile` açmak için dosyanın dosya ya da yol adı ile birlikte, çağırmanın çok basit bir uygulamasına sahiptir. `CWinApp`Uygulama yordamı, `DoPromptFileName` Standart FileOpen iletişim kutusunu getirir ve geçerli belge şablonlarından elde edilen dosya uzantılarına göre doldurur.

   ID_FILE_OPEN ortak bir özelleştirmesi, FileOpen iletişim kutusunu özelleştirmek veya ek dosya filtreleri eklemektir. Bunu özelleştirmek için önerilen yol, varsayılan uygulamayı kendi FileOpen iletişim kutusu ile değiştirmek ve `CWinApp::OpenDocumentFile` belgenin dosyası ya da yol adıyla çağırmasıdır. Temel sınıfı çağırmaya gerek yoktur.

- ID_FILE_CLOSE açık olan belgeyi kapatır.

   `CDocument::OnFileClose``CDocument::SaveModified`değiştirildiyse, kullanıcıdan belgeyi kaydetmesi istenir ve ardından çağrı yapılır `OnCloseDocument` . Belgeyi yok etme da dahil olmak üzere tüm kapatma mantığı, `OnCloseDocument` yordamında yapılır.

    > [!NOTE]
    >  ID_FILE_CLOSE, belgeler çerçevesi penceresine gönderilen WM_CLOSE iletisinden veya SC_CLOSE bir sistem komutundan farklı şekilde davranır. Bir pencerenin kapatılması belgeyi yalnızca belgenin gösterdiği son çerçeve penceresi ise kapatır. Belgeyi ID_FILE_CLOSE ile kapatmak yalnızca belgeyi kapatmayacak, ancak belgeyi gösteren tüm çerçeve pencerelerini kapatacak.

- ID_FILE_SAVE geçerli belgeyi kaydeder.

   Uygulama, ve için kullanılan bir yardımcı yordamı kullanır `CDocument::DoSave` `OnFileSave` `OnFileSaveAs` . Daha önce kaydedilmemiş bir belgeyi kaydederseniz (yani, dosya yeni bir durumda olduğu gibi bir yol adına sahip değildir) veya salt okunurdur bir belgeden okunmışsa, `OnFileSave` mantık ID_FILE_SAVE_AS komutu gibi davranır ve kullanıcıdan yeni bir dosya adı sağlamasını ister. Dosyayı açma ve kaydetmeyi yapma işleminin gerçek süreci, sanal işlev aracılığıyla yapılır `OnSaveDocument` .

   ID_FILE_SAVE özelleştirmenin iki yaygın nedeni vardır. Kaydetmeyin belgeler için, ID_FILE_SAVE menü öğelerini ve araç çubuğu düğmelerini kullanıcı arayüzünden kaldırmanız yeterlidir. Ayrıca, belgenizi hiçbir şekilde görmeyin (yani hiçbir şekilde çağırmayın `CDocument::SetModifiedFlag` ) ve çerçeve belgenin kaydedilmesine hiçbir şekilde neden olmaz. Bir disk dosyası dışında başka bir yere kaydedilmiş belgeler için, bu işlem için yeni bir komut tanımlayın.

   Bir durumunda `COleServerDoc` ID_FILE_SAVE, hem dosya kaydetme (normal belgeler için) hem de dosya güncelleştirmesi (katıştırılmış belgeler için) için kullanılır.

   Belge verileriniz ayrı disk dosyalarında depolanıyorsa, ancak varsayılan `CDocument` serileştirme uygulamasını kullanmak istemiyorsanız, yerine geçersiz kılmanız gerekir `CDocument::OnSaveDocument` `OnFileSave` .

- ID_FILE_SAVE_AS geçerli belgeyi farklı bir dosya adı altına kaydeder.

   `CDocument::OnFileSaveAs`Uygulama, `CDocument::DoSave` ile aynı yardımcı yordamı kullanır `OnFileSave` . `OnFileSaveAs`Belgeler, kaydetmeden önce dosya adı yoksa, bu komut ID_FILE_SAVE olarak işlenir. `COleServerDoc::OnFileSaveAs` normal bir belge veri dosyasını kaydetme veya başka bir uygulamaya katıştırılmış OLE nesnesini temsil eden bir sunucu belgesini ayrı bir dosya olarak kaydetme mantığını uygular.

   ID_FILE_SAVE mantığını özelleştirirseniz, büyük olasılıkla ID_FILE_SAVE_AS benzer bir biçimde özelleştirmek isteyeceksiniz veya "farklı kaydet" işlemi belgeniz için uygulanmayabilir. Menü öğesini gerekli değilse menü çubuğundan kaldırabilirsiniz.

- ID_FILE_SAVE_COPY_AS geçerli belgeyi yeni bir adla kaydeder.

   `COleServerDoc::OnFileSaveCopyAs`Uygulama, `CDocument::OnFileSaveAs` kayıt sonrasında temel alınan dosyaya "iliştirilmemiş" değil, öğesine benzer. Diğer bir deyişle, bellek içi belge, kaydetmeden önce "değiştirilmiştir" ise, hala "değiştirilmiştir". Ayrıca, bu komutun belge içinde depolanan yol adı veya başlığı üzerinde hiçbir etkisi yoktur.

- ID_FILE_UPDATE, kapsayıcıyı gömülü bir belgeyi kaydedecek şekilde bildirir.

   `COleServerDoc::OnUpdateDocument`Uygulama, gömmenin kaydedilmesi gereken kapsayıcıyı önemli bir şekilde tespit etmelidir. Daha sonra kapsayıcı, katıştırılmış nesneyi kaydetmek için uygun OLE API 'Lerini çağırır.

- ID_FILE_PAGE_SETUP uygulamaya özgü sayfa kurulumu/düzeni iletişim kutusunu çağırır.

   Şu anda bu iletişim kutusu için standart yoktur ve Framework bu komutun varsayılan uygulamasına sahip değildir.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- Standart yazdırma ayarı iletişim kutusunu ID_FILE_PRINT_SETUP çağırın.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   Bu komut, kullanıcının yazıcı ve yazdırma ayarlarını en az bu belgeyle veya bu uygulamadaki tüm belgelerde özelleştirmesini sağlayan standart yazdırma ayarı iletişim kutusunu çağırır. Tüm sistem için varsayılan yazıcı ayarlarını değiştirmek üzere Denetim Masası ' nı kullanmanız gerekir.

   `CWinApp::OnFilePrintSetup` , bir `CPrintDialog` nesnesi oluşturan ve uygulama işlevini çağıran çok basit bir uygulamaya sahiptir `CWinApp::DoPrintDialog` . Bu, uygulamanın varsayılan yazıcı kurulumunu ayarlar.

   Bu komutu özelleştirmenin yaygın olması, belge başına yazıcı ayarlarına izin vermasıdır ve bu, kaydedildiğinde belgeye depolanmalıdır. Bunu yapmak için `CDocument` , sınıfınıza bir `CPrintDialog` nesne oluşturan, uygun yazıcı öznitelikleri (genellikle *hDevMode* ve *hDevNames*) başlatan bir ileti eşleme işleyicisi eklemeniz, öğesini çağırıp, `CPrintDialog::DoModal` değiştirilen yazıcı ayarlarını kaydetmeniz gerekir. Sağlam bir uygulama için, hataları tespit etmek `CWinApp::DoPrintDialog` ve güvenilir `CWinApp::UpdatePrinterSelection` Varsayılanlar ile ilgilenmek ve sistem genelinde yazıcı değişikliklerini izlemek için uygulamasının uygulamasına bakmanız gerekir.

- Geçerli belgenin standart yazdırma ID_FILE_PRINT

    > [!NOTE]
    >  Bu `CView` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   Bu komut, geçerli belgeyi veya daha doğru bir şekilde yazdırır, standart yazdırma iletişim kutusunu çağırmayı ve yazdırma altyapısını çalıştırmayı içeren yazdırma işlemini başlatır.

   `CView::OnFilePrint` Bu komutu ve ana yazdırma döngüsünü uygular. `CView::OnPreparePrinting`Kullanıcının Yazdır iletişim kutusuyla ilgili olarak sorması için sanal ' i çağırır. Ardından çıkış DC 'sini yazıcıya gitmek için hazırlar, yazdırma ilerleme durumu iletişim kutusunu (AFX_IDD_PRINTDLG) getirir ve `StartDoc` Çıkış yazıcıya gönderilir. `CView::OnFilePrint` Ayrıca Ana sayfa odaklı yazdırma döngüsünü içerir. Her sayfa için, `CView::OnPrepareDC` bir kaçış tarafından izlenen `StartPage` ve Bu sayfa için sanal olarak çağıran bir sanal disk çağırır `CView::OnPrint` . İşlem tamamlandığında, sanal `CView::OnEndPrinting` çağrılır ve yazdırma ilerleme durumu iletişim kutusu kapatılır.

   MFC yazdırma mimarisi, yazdırma ve baskı önizleme için birçok farklı yolla bir kanca olacak şekilde tasarlanmıştır. Normalde `CView` herhangi bir sayfa odaklı yazdırma görevi için uygun olan çeşitli geçersiz kılınabilir işlevleri bulabilirsiniz. Yalnızca sayfa odaklı olmayan çıkış için yazıcıyı kullanan bir uygulama söz konusu olduğunda, ID_FILE_PRINT uygulamasını değiştirme gereksinimini bulmalısınız.

- ID_FILE_PRINT_PREVIEW geçerli belge için Baskı Önizleme modunu girin.

    > [!NOTE]
    >  Bu `CView` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CView::OnFilePrintPreview` belgelenmiş yardımcı işlevini çağırarak Baskı Önizleme modunu başlatır `CView::DoPrintPreview` . `CView::DoPrintPreview` , yazdırma önizlemesi döngüsünün ana altyapısıdır ve tıpkı `OnFilePrint` yazdırma döngüsünün ana altyapısıdır.

   Yazdırma önizlemesi işlemi, farklı parametreleri öğesine geçirerek çeşitli yollarla özelleştirilebilir `DoPrintPreview` . Lütfen Baskı önizlemenin bazı ayrıntılarını ve bunu nasıl özelleştireceğinizi açıklayan [teknik nota 30](../mfc/tn030-customizing-printing-and-print-preview.md)' a bakın.

- ID_FILE_MRU_FILE1... Dosya MRU **listesi** için bir dizi komut kimliği FILE16.

   `CWinApp::OnUpdateRecentFileMenu` , ON_UPDATE_COMMAND_UI mekanizmasının daha gelişmiş kullanımından biri olan bir Update komutu UI işleyicisidir. Menü kaynağınız içinde yalnızca KIMLIĞI ID_FILE_MRU_FILE1 olan tek bir menü öğesi tanımlamanız gerekir. Bu menü öğesi başlangıçta devre dışı kalır.

   MRU listesi büyüdükçe, listeye daha fazla menü öğesi eklenir. Standart `CWinApp` uygulama varsayılan olarak en son kullanılan dört dosyanın standart sınırına göre yapılır. `CWinApp::LoadStdProfileSettings`Daha büyük veya daha küçük bir değerle çağırarak varsayılan değeri değiştirebilirsiniz. MRU listesi uygulamanın konumunda depolanır. INı dosyası. Bu liste `InitInstance` , çağrısı yaparsanız uygulamanızın işlevine yüklenir `LoadStdProfileSettings` ve uygulamanız çıktığında kaydedilir. MRU güncelleştirme komutu UI işleyicisi Ayrıca, Dosya menüsünde görüntülenmek üzere mutlak yolları göreli yollara dönüştürür.

   `CWinApp::OnOpenRecentFile` , gerçek komutu gerçekleştiren ON_COMMAND işleyicisidir. Dosya adını yalnızca MRU listesinden ve çağrılarından alır. Bu, `CWinApp::OpenDocumentFile` dosyayı açan ve MRU listesini güncelleştiren tüm işleri yapar.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_EDIT_CLEAR geçerli seçimi temizler

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` kullanılarak bu komutun bir uygulamasını sağlar `CEdit::Clear` . Geçerli seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_CLEAR_ALL tüm belgeyi temizler.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz. Örnek bir uygulama için MFC öğretici örneği [karalama](../overview/visual-cpp-samples.md) bölümüne bakın.

- ID_EDIT_COPY geçerli seçimi panoya kopyalar.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` Şu anda seçili olan metni pano 'ya CF_TEXT olarak kopyalayan bu komutun bir uygulamasını sağlar `CEdit::Copy` . Geçerli seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_CUT geçerli seçimi panoya keser.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` Bu komutun bir uygulamasını kullanarak şu anda seçili olan metni pano 'ya keser CF_TEXT `CEdit::Cut` . Geçerli seçim yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_FIND, bulma işlemini başlatır ve kalıcı bul iletişim kutusunu açar.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` Bu komutun, kullanılacak uygulama Yardımcısı işlevini çağıran `OnEditFindReplace` ve önceki Bul/Değiştir ayarlarını özel uygulama değişkenlerinde depolayabilen bir uygulamasını sağlar. `CFindReplaceDialog`Sınıfı, kullanıcı istemek için kalıcı olmayan iletişim kutusunu yönetmek için kullanılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_PASTE geçerli Pano içeriğini ekler.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` Bu komutun, seçili metni değiştiren geçerli Pano verilerini kopyalayan bir uygulamasını sağlar `CEdit::Paste` . Panoda **cf_text** yoksa komut devre dışı bırakılır.

   `COleClientDoc` Bu komut için yalnızca bir Update komutu Kullanıcı arabirimi işleyicisi sağlar. Pano, eklenebilir bir OLE öğesi/nesnesi içermiyorsa, komut devre dışı bırakılır. Gerçek yapıştırmayı yapmak için gerçek komutun işleyicisini yazmak sizin sorumluluğunuzdadır. OLE uygulamanız aynı zamanda diğer biçimleri de yapıştırabiliyorsanız, kendi Update komut UI işleyicinizi görünüm veya belgenizde (yani, `COleClientDoc` komut hedef yönlendirmesinde bir yerde) sağlamanız gerekir.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

   Standart OLE uygulamasını değiştirmek için kullanın `COleClientItem::CanPaste` .

- ID_EDIT_PASTE_LINK geçerli pano içeriğinden bir bağlantı ekler.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `COleDocument` Bu komut için yalnızca bir Update komutu Kullanıcı arabirimi işleyicisi sağlar. Pano, erişilebilir OLE öğesi/nesnesi içermiyorsa, komut devre dışı bırakılır. Gerçek yapıştırmayı yapmak için gerçek komutun işleyicisini yazmak sizin sorumluluğunuzdadır. OLE uygulamanız aynı zamanda diğer biçimleri de yapıştırabiliyorsanız, kendi Update komut UI işleyicinizi görünüm veya belgenizde (yani, `COleDocument` komut hedef yönlendirmesinde bir yerde) sağlamanız gerekir.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

   Standart OLE uygulamasını değiştirmek için kullanın `COleClientItem::CanPasteLink` .

- ID_EDIT_PASTE_SPECIAL geçerli Pano içeriğini seçeneklerle ekler.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız. MFC bu iletişim kutusunu sağlamaz.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_REPEAT son işlemi yineler.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` son bulma işlemini yinelemek için bu komutun bir uygulamasını sağlar. Son bulma için özel uygulama değişkenleri kullanılır. Bir bul denendiğinde komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_REPLACE değiştirme işlemine başladıktan sonra modsuz değiştirme iletişim kutusunu açar.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` Bu komutun, kullanılacak uygulama Yardımcısı işlevini çağıran `OnEditFindReplace` ve önceki Bul/Değiştir ayarlarını özel uygulama değişkenlerinde depolayabilen bir uygulamasını sağlar. `CFindReplaceDialog`Sınıfı, kullanıcıya isteyen engelleyici olmayan iletişim kutusunu yönetmek için kullanılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_SELECT_ALL tüm belgeyi seçer.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` belgedeki tüm metni seçen bu komutun bir uygulamasını sağlar. Seçilecek metin yoksa komut devre dışı bırakılır.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_UNDO son işlemi geri alır.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   `CEditView` kullanılarak bu komutun bir uygulamasını sağlar `CEdit::Undo` . FALSE döndürürse komut devre dışı bırakılır `CEdit::CanUndo` .

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_EDIT_REDO son işlemi yeniden yapar.

   Şu anda bu komut için standart bir uygulama yok. Bunu, her `CView` türetilmiş sınıf için uygulamalısınız.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_WINDOW_NEW etkin belgede başka bir pencere açar.

   `CMDIFrameWnd::OnWindowNew` Geçerli belgenin belge şablonunu kullanarak geçerli belgenin başka bir görünümünü içeren başka bir çerçeve oluşturmak için bu güçlü özelliği uygular.

   Çoğu birden çok belge arabirimi (MDI) pencere menü komutu gibi, etkin bir MDI alt penceresi yoksa, komut devre dışı bırakılır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez. Ek görünümler veya çerçeve pencereleri oluşturan bir komut sağlamak istiyorsanız, muhtemelen kendi Komutunuz için daha iyi bir işlem yapmanız gerekir. Kodu konumundan kopyalayabilir `CMDIFrameWnd::OnWindowNew` ve belirli çerçeveye değiştirebilir ve istediğiniz sınıfları görüntüleyebilirsiniz.

- ID_WINDOW_ARRANGE MDI penceresinin alt kısmındaki simgeleri yerleştirir.

   `CMDIFrameWnd` Bu standart MDI komutunu bir uygulama yardımcı işlevinde uygular `OnMDIWindowCmd` . Bu yardımcı, komut kimliklerini MDI Windows iletileriyle eşleştirir ve bu nedenle çok sayıda kodu paylaşabilir.

   Birçok MDI penceresi menü komutu gibi, etkin bir MDI alt penceresi yoksa, komut devre dışı bırakılır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- Windows 'un örtüşmesini sağlamak ID_WINDOW_CASCADE.

   `CMDIFrameWnd` Bu standart MDI komutunu bir uygulama yardımcı işlevinde uygular `OnMDIWindowCmd` . Bu yardımcı, komut kimliklerini MDI Windows iletileriyle eşleştirir ve bu nedenle çok sayıda kodu paylaşabilir.

   Birçok MDI penceresi menü komutu gibi, etkin bir MDI alt penceresi yoksa, komut devre dışı bırakılır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- Pencereleri yatay olarak ID_WINDOW_TILE_HORZ döşer.

   Bu komut `CMDIFrameWnd` , işlem için farklı bır MDI Windows iletisi kullanılması dışında, tıpkı ID_WINDOW_CASCADE gibi uygulanır.

   Uygulamanız için varsayılan kutucuk yönünü seçmeniz gerekir. Bunu, pencere "kutucuğu" menü öğesinin KIMLIĞINI ID_WINDOW_TILE_HORZ veya ID_WINDOW_TILE_VERT olarak değiştirerek yapabilirsiniz.

- Pencereleri dikey olarak ID_WINDOW_TILE_VERT.

   Bu komut `CMDIFrameWnd` , işlem için farklı bır MDI Windows iletisi kullanılması dışında, tıpkı ID_WINDOW_CASCADE gibi uygulanır.

   Uygulamanız için varsayılan kutucuk yönünü seçmeniz gerekir. Bunu, pencere "kutucuğu" menü öğesinin KIMLIĞINI ID_WINDOW_TILE_HORZ veya ID_WINDOW_TILE_VERT olarak değiştirerek yapabilirsiniz.

- Klavye arabirimini bölümlendiricinize ID_WINDOW_SPLIT.

   `CView` Bu komutu uygulama için işler `CSplitterWnd` . Görünüm bir splitter penceresinin parçasıysa, bu komut uygulama işlevine temsilci eklenecektir `CSplitterWnd::DoKeyboardSplit` . Bu, ayırıcıyı klavye kullanıcılarına Bölümlendirici pencereyi bölme veya bölme izni veren bir moda yerleştirir.

   Görünüm bir Bölümlendirici içinde değilse, bu komut devre dışı bırakılır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_APP_ABOUT hakkında iletişim kutusunu çağırır.

   Uygulamanın Ilgili kutusu için standart bir uygulama yoktur. Varsayılan AppWizard tarafından oluşturulan uygulama, uygulamanız için özel bir iletişim kutusu sınıfı oluşturacak ve bunu hakkında kutusu olarak kullanacaktır. AppWizard Ayrıca, bu komutu işleyen ve iletişim kutusunu çağıran basit komut işleyicisini yazar.

   Bu komutu neredeyse her zaman uygulayacaksınız.

- Uygulamadan çıkın ID_APP_EXIT.

   `CWinApp::OnAppExit` Bu komutu, uygulamanın ana penceresine bir WM_CLOSE iletisi göndererek işler. Uygulamayı standart olarak kapatma (kirli dosyalar ve benzeri için istem) uygulama tarafından işlenir `CFrameWnd` .

   Bu komut işleyicisinin özelleştirilmesi önerilmez. Geçersiz kılma `CWinApp::SaveAllModified` veya `CFrameWnd` kapatma mantığı önerilir.

   Bu komutu uygulamayı seçerseniz, bu komut KIMLIĞINI kullanmanızı öneririz.

- ID_HELP_INDEX, ' dan yardım konuları listeler. HLP dosyası.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnHelpIndex` Bu komutu, sıradan çağırarak işler `CWinApp::WinHelp` .

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_HELP_USING yardım 'ı kullanma hakkında yardım görüntüler.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnHelpUsing` Bu komutu, sıradan çağırarak işler `CWinApp::WinHelp` .

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_CONTEXT_HELP SHIFT-F1 Yardım moduna girer.

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnContextHelp` Yardım modu imlecini ayarlayarak, kalıcı bir döngü girerek ve kullanıcının yardım almak üzere bir pencere seçmesini bekleyerek bu komutu işler. MFC yardım uygulamasıyla ilgili daha fazla bilgi için lütfen [Teknik notun 28](../mfc/tn028-context-sensitive-help-support.md) bölümüne bakın.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_HELP geçerli bağlamda yardım verir

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   `CWinApp::OnHelp` geçerli uygulama bağlamı için doğru yardım bağlamını alarak bu komutu işler. Bu, basit F1 yardımını, ileti kutuları hakkında yardımı ve benzerlerini işler. MFC yardım uygulamasıyla ilgili daha fazla bilgi için lütfen [Teknik notun 28](../mfc/tn028-context-sensitive-help-support.md) bölümüne bakın.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_DEFAULT_HELP bağlam için varsayılan yardımı görüntüler

    > [!NOTE]
    >  Bu `CWinApp` işlevi etkinleştirmek için bunu türetilmiş sınıfınızın ileti eşlemesine bağlamanız gerekir.

   Bu komut genellikle ile eşleştirilir `CWinApp::OnHelpIndex` .

   Varsayılan yardım ve Yardım dizini arasındaki ayrım isteniyorsa, farklı bir komut işleyici sağlayabilirsiniz.

- ID_NEXT_PANE sonraki bölmeye gider

   `CView` Bu komutu uygulama için işler `CSplitterWnd` . Görünüm bir splitter penceresinin parçasıysa, bu komut uygulama işlevine temsilci eklenecektir `CSplitterWnd::OnNextPaneCmd` . Bu işlem, etkin görünümü Bölümlendirici içindeki bir sonraki bölmeye taşır.

   Görünüm bir Bölümlendirici içinde değilse veya gidilecek sonraki bölme yoksa bu komut devre dışıdır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_PREV_PANE önceki bölmeye gider

   `CView` Bu komutu uygulama için işler `CSplitterWnd` . Görünüm bir splitter penceresinin parçasıysa, bu komut uygulama işlevine temsilci eklenecektir `CSplitterWnd::OnNextPaneCmd` . Bu işlem, etkin görünümü bölümlendiriconun önceki bölmesine taşır.

   Görünüm bir Bölümlendirici içinde değilse veya gidilecek bir önceki bölme yoksa bu komut devre dışıdır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_OLE_INSERT_NEW yeni bir OLE nesnesi ekler

   Şu anda bu komut için standart bir uygulama yok. `CView`Geçerli seçime yeni BIR ole öğesi/nesnesi eklemek için bunu türetilmiş sınıfa uygulamanız gerekir.

   Tüm OLE istemci uygulamaları bu komutu uygulamalıdır. AppWizard, OLE seçeneğiyle birlikte, `OnInsertObject` görüntülemeniz gereken görünüm sınıfınıza bir iskelet uygulaması oluşturur.

   Bu komutun tamamen uygulanması için MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md) örneğine bakın.

- OLE bağlantılarını ID_OLE_EDIT_LINKS düzenleme

   `COleDocument` Bu komutu, standart OLE bağlantıları iletişim kutusunun MFC tarafından sağlanmış uygulamasını kullanarak işler. Bu iletişim kutusunun uygulamasına sınıfı aracılığıyla erişilir `COleLinksDialog` . Geçerli belge herhangi bir bağlantı içermiyorsa, komut devre dışı bırakılır.

   Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_OLE_VERB_FIRST... OLE fiilleri için son bir KIMLIK aralığı

   `COleDocument` Şu anda seçili olan OLE öğesi/nesnesi tarafından desteklenen fiiller için bu komut KIMLIĞI aralığını kullanır. Belirli bir OLE öğesi/nesne türü sıfır veya daha fazla özel fiil destekleyediğinden bu bir Aralık olmalıdır. Uygulamanızın menüsünde, ID_OLE_VERB_FIRST KIMLIĞI olan bir menü öğesi olması gerekir. Program çalıştırıldığında menü, uygun menü fiili açıklaması (veya birçok fiil içeren açılır menü) ile güncelleştirilir. OLE menüsünün Yönetimi `AfxOleSetEditMenu` , bu komut için Update komutu UI işleyicisinde yapılır tarafından işlenir.

   Bu aralıktaki komut KIMLIĞININ her birini işlemek için açık bir komut işleyici yok. `COleDocument::OnCmdMsg` , bu aralıktaki tüm komut kimliklerini yakalamak, sıfır tabanlı fiil numaralarına dönüştürmek ve bu fiil için sunucuyu (kullanarak) başlatmak için geçersiz kılınır `COleClientItem::DoVerb` .

   Bu komut KIMLIĞI aralığının özelleştirilmesi veya diğer kullanımı önerilmez.

- ID_VIEW_TOOLBAR araç çubuğunu açar ve kapatır

   `CFrameWnd` araç çubuğunun görünür durumunu değiştirmek için bu komutu ve Update-Command UI işleyicisini işler. Araç çubuğu, AFX_IDW_TOOLBAR alt pencere KIMLIĞI olan çerçevenin bir alt penceresi olmalıdır. Komut işleyici aslında araç çubuğu penceresinin görünürlüğünü değiştirir. `CFrameWnd::RecalcLayout` , yeni durumundaki araç çubuğuyla çerçeve penceresini yeniden çizmek için kullanılır. Update-Command UI işleyicisi, araç çubuğu görünür olduğunda menü öğesini denetler.

   Bu komut işleyicisinin özelleştirilmesi önerilmez. Ek araç çubukları eklemek istiyorsanız, bu komut için komut işleyicisini ve Update-Command UI işleyicisini klonlamak ve değiştirmek isteyeceksiniz.

- ID_VIEW_STATUS_BAR durum çubuğunu açar ve kapatır

   Bu komut `CFrameWnd` , farklı bir alt pencere kimliği (AFX_IDW_STATUS_BAR) kullanıldığı sürece ID_VIEW_TOOLBAR benzer şekilde uygulanır.

## <a name="update-only-command-handlers"></a>Update-Only komut Işleyicileri

Birkaç standart komut kimliği, durum çubuklarındaki göstergeler olarak kullanılır. Bu, uygulama boşta kalma süresi boyunca geçerli görsel durumlarını göstermek için aynı Update-Command Kullanıcı arabirimi işleme mekanizmasını kullanır. Kullanıcı tarafından seçileolmadıkları için (yani bir durum çubuğu bölmesi gönderemezsiniz), bu komut kimlikleri için ON_COMMAND işleyicisine sahip olmak mantıklı değildir.

- ID_INDICATOR_CAPS: uç kilit göstergesi.

- ID_INDICATOR_NUM: NUM LOCK göstergesi.

- ID_INDICATOR_SCRL: SCRL kilit göstergesi.

- ID_INDICATOR_KANA: KANA kilit göstergesi (yalnızca Japonca sistemler için geçerlidir).

Bunlardan üçü `CFrameWnd::OnUpdateKeyIndicator` , uygun sanal anahtarla eşlemek için komut kimliğini kullanan bir uygulama Yardımcısı olan ' de uygulanır. Ortak bir uygulama, `CCmdUI` uygun sanal anahtarın kilitli olup olmadığına bağlı olarak nesne için (durum bölmeleri devre dışı = metin yok) etkinleştirilir veya devre dışı bırakır.

Bu komut işleyicisinin özelleştirilmesi önerilmez.

- ID_INDICATOR_EXT: Genişletilmiş seçim göstergesi.

- ID_INDICATOR_OVR: fazla çizili gösterge.

- ID_INDICATOR_REC: kayıt göstergesi.

Şu anda bu göstergeler için standart bir uygulama yoktur.

Bu göstergeleri uygulamayı seçerseniz, bu gösterge kimliklerini kullanmanızı ve durum çubuğunuzun göstergelerini sıralamayı (bu sırayla: EXT, CAP, NUM, SCRL, OVR, REC) yapmanızı öneririz.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
