---
title: 'MFC: Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC applications [C++], without views
- documents [C++], applications without
- ODBC applications [C++]
- document/view architecture [C++], in databases
- files [C++], MFC
- database classes [C++], MFC
- CRecordView class, using in database applications
- database applications [C++], without views
- database applications [C++], application wizard options
- application wizards [C++], creating database applications
- ODBC [C++], file support in database applications
- ODBC applications [C++], without documents
- database applications [C++], without documents
- user interface [C++], drawing information
ms.assetid: 15bf52d4-91cf-4b1d-8b37-87c3ae70123a
ms.openlocfilehash: ab9946609fa20c4644873a684a754cbc8a41742f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024640"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma

Bazen, veritabanı uygulamalarında framework'ün belge/görünüm mimarisini kullanan istemeyebilirsiniz. Bu konu şunları açıklar:

- [Ne zaman gereksinim belgeleri kullanmak](#_core_when_you_don.92.t_need_documents) Belge Serileştirme gibi.

- [Uygulama Sihirbazı Seçenekleri](#_core_appwizard_options_for_documents_and_views) serileştirme olmadan ve uygulamaları desteklemek için ilgili **dosya** menü komutları gibi **yeni**, **açık** , **Kaydet**, ve **Kaydet**.

- [En az bir belge kullanan bir uygulama ile çalışma konusunda](#_core_applications_with_minimal_documents).

- [Belge veya görüntüleme olmayan bir uygulama nasıl](#_core_applications_with_no_document).

##  <a name="_core_when_you_don.92.t_need_documents"></a> Ne zaman belge gerekmez

Bazı uygulamalar, ayrı bir belge kavramı vardır. Bu uygulamalar genellikle tüm veya çoğu bir dosya depolama'yı belleğe ile yüklemek bir **Dosya Aç** komutu. Bunlar güncelleştirilmiş dosyayı geri tamamını tek seferde depolama yazma bir **dosyasını kaydedin** veya **Kaydet** komutu. Kullanıcının gördüğü veri dosyasıdır.

Ancak, bazı uygulama kategorileri bir belge gerektirmez. Veritabanı uygulamaları, işlem olarak çalışır. Uygulama kayıtları bir veritabanından seçer ve bunları kullanıcı genellikle teker teker gösterir. Kullanıcının gördüğü genellikle tek bellekte olabilir tek bir geçerli kaydı olur.

Uygulama verilerini depolamak için bir belge gerektirmiyorsa, bazı veya tüm framework'ün belge/görünüm mimarisi ile etiket. Ne dağıtacağınız tercih ettiğiniz yaklaşımı bağlıdır. Şunu yapabilirsiniz:

- En az bir belge, veri kaynağı bağlantısı saklar, ancak seri hale getirme gibi normal belge özelliklerle etiket için bir yer olarak kullanın. Bu, birkaç veri görünümlerini ve tümünü tek seferde ve benzeri güncelleştirme görünümleri eşitlemek istediğiniz istediğinizde kullanışlıdır.

- Çerçeve penceresi içine doğrudan bir görünüm kullanmak yerine çizdiğiniz kullanın. Bu durumda, belgenin çıkarın ve herhangi bir veri veya veri bağlantıları çerçeve pencere nesnesi içinde saklamak.

##  <a name="_core_appwizard_options_for_documents_and_views"></a> Belgeler ve görünümler için Uygulama Sihirbazı Seçenekleri

MFC Uygulama Sihirbazı birkaç seçenek vardır **seçin veritabanı desteği**, aşağıdaki tabloda listelenmiştir. Bir uygulama oluşturmak için MFC Uygulama Sihirbazı'nı kullanırsanız, tüm bu seçenekler belgeler ve görünümler ile uygulamalar oluşturur. Bazı seçenekler, belgeler ve gereksiz belge özelliklerini atlayan görünümler sağlar. Daha fazla bilgi için [veritabanı desteği, MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md).

|Seçenek|Görüntüle|Belge|
|------------|----------|--------------|
|**Yok.**|Türetilmiş `CView`.|Hiçbir veritabanı desteği sağlar. Varsayılan seçenek budur.<br /><br /> Seçerseniz **belge/görünüm mimarisi desteği** seçeneğini [Application Type, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, serileştirme dahil olmak üzere tam belge desteği alın ve **yeni** , **Açık**, **Kaydet**, ve **Kaydet** komutlarını **dosya** menüsü. Bkz: [hiçbir belge uygulamalarla](#_core_applications_with_no_document).|
|**Yalnızca üst bilgi dosyaları**|Türetilmiş `CView`.|Uygulamanız için temel düzeyde bir veritabanı desteği sağlar.<br /><br /> Afxdb.h içerir. Bağlantı kitaplıkları ekler, ancak herhangi bir veritabanı özgü sınıflar oluşturmaz. Daha sonra kayıt kümeleri oluşturma ve bunları inceleyin ve kayıtları güncelleştirmek için kullanın.|
|**Dosya desteği olmadan veritabanı görünümü**|Öğesinden türetilen `CRecordView`|Belge desteği, ancak hiçbir serileştirme desteği sağlar. Belge kayıt depolayabilir ve birden çok görünüm koordine; Seri duruma getirmeyi desteklemeyen veya **yeni**, **açık**, **Kaydet**, ve **Kaydet** komutları. Bkz: [en az Belgeli Uygulamalar](#_core_applications_with_minimal_documents). Bir veritabanı görünümü eklerseniz, veri kaynağı belirtmeniz gerekir.<br /><br /> Veritabanı üst bilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Kullanılabilir olan uygulamalar için **belge/görünüm mimarisi desteği** seçeneği seçili [Application Type, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfası.)|
|**Dosya destekli veritabanı görünümü**|Öğesinden türetilen `CRecordView`|Serileştirme dahil olmak üzere tam belge desteği sağlar ve ilgili **dosya** menü komutları. Yerine dosya ve bu nedenle temel serileştirme gerekmez veritabanı uygulamaları, genellikle kayıt başına temelinde çalışır. Ancak, serileştirme için özel bir kullanım olabilir. Bkz: [en az Belgeli Uygulamalar](#_core_applications_with_minimal_documents). Bir veritabanı görünümü eklerseniz, veri kaynağı belirtmeniz gerekir.<br /><br /> Veritabanı üst bilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Kullanılabilir olan uygulamalar için **belge/görünüm mimarisi desteği** seçeneği seçili [Application Type, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfası.)|

Serileştirme ve seri hale getirme için alternatif alternatifleri için bkz [seri hale getirme: Serileştirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).

##  <a name="_core_applications_with_minimal_documents"></a> En az Belgeli Uygulamalar

MFC Uygulama Sihirbazı, form tabanlı veri erişimi uygulamaları destekleyen iki seçenek vardır. Her seçenek oluşturur bir `CRecordView`-türetilmiş sınıf görünümü ve bir belge. Bunlar, kullanıcılar belgenin dışında bırakın farklı.

###  <a name="_core_a_document_without_file_support"></a> Belge dosya desteği olmadan

Uygulama Sihirbazı'nı veritabanı seçeneğini **Ritabanı görünümü dosya desteği olmadan** Belge Serileştirme gerekmiyorsa. Belge aşağıdaki kullanışlı amaca hizmet eder:

- Depolamak için kullanışlı bir yerdir bir `CRecordset` nesne.

   Sıradan belge kavramlarını bu kullanım paralelleştirir: belge verileri depoları (veya bu durumda, bir kayıt kümesi) ve görünüm belgenin bir görünümüdür.

- Uygulamanız (örneğin, birden çok kayıt görünümleri) birden çok görünüm sunar, görünümlerini koordine bir belge destekler.

   Birden çok görünüm aynı verileri gösterme, kullanabileceğiniz `CDocument::UpdateAllViews` herhangi bir görünüm veriler değiştiğinde tüm görünümlere güncelleştirmelerini koordine etmek için üye işlevi.

Genellikle basit form tabanlı uygulamalar için bu seçeneği kullanın. Uygulama Sihirbazı'nı uygun bir yapı böyle uygulamalar için otomatik olarak destekler.

###  <a name="_core_a_document_with_file_support"></a> Dosya destekli belge

Uygulama Sihirbazı'nı veritabanı seçeneğini **görünümü dosya destekli veritabanı** belgeyle ilgili için alternatif kullanımınız olduğunda **dosya** menü komutları ve Belge Serileştirme. Programınız için veri erişim bölümü, belge aynı şekilde açıklandığı gibi kullanabileceğiniz [dosya desteği olmadan belge](#_core_a_document_without_file_support). Örneğin, okuma ve yazma, kullanıcının tercihlerini veya diğer yararlı bilgileri depolayan bir serileştirilmiş kullanıcı profili belgesini belgenin seri hale getirme özelliği kullanabilirsiniz. Daha fazla fikir için bkz [seri hale getirme: Serileştirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).

Bu seçenek, Uygulama Sihirbazı'nı destekler, ancak belgeyi serileştiren kod yazmanız gerekir. Serileştirilmiş bilgiler belge veri üyelerinde Store.

##  <a name="_core_applications_with_no_document"></a> Belge olmadan uygulamalar

Bazen, belgeler veya görünümleri kullanmayan bir uygulama yazmak isteyebilirsiniz. Belgeler olmadan verilerinizi depolayın (gibi bir `CRecordset` nesne) çerçeve penceresi sınıfınıza ya da, uygulama sınıfı. Tüm ek gereksinimleri, uygulama kullanıcı arabirimi sunar üzerinde bağlıdır.

###  <a name="_core_database_support_with_a_user_interface"></a> Bir kullanıcı arabirimi ile veritabanı desteği

Kullanıcı Arabirimi (örneğin, bir konsolu komut satırı arabirimi, diğer) varsa, doğrudan çerçeve penceresinin istemci alanına yerine bir görünümde, uygulamanızın çizer. Bu tür bir uygulama kullanmaz `CRecordView`, `CFormView`, veya `CDialog` ana kullanıcı arabirimi, ancak için normalde kullandığınız `CDialog` sıradan iletişim kutuları için.

###  <a name="_core_writing_applications_without_documents"></a> Belgeler olmadan uygulamaları yazma

Uygulama Sihirbazı'nı belgeler olmadan uygulama oluşturmayı desteklemediğinden, kendi yazmanız gereken `CWinApp`-türetilmiş sınıf, gerekli olursa, oluşturun ve ayrıca bir `CFrameWnd` veya `CMDIFrameWnd` sınıfı. Geçersiz kılma `CWinApp::InitInstance` ve bir uygulamanın nesne olarak bildirin:

```cpp
CYourNameApp theApp;
```

Framework hala ileti eşleme mekanizması ve diğer birçok özellik sağlar.

###  <a name="_core_database_support_separate_from_the_user_interface"></a> Ayrı kullanıcı arabiriminden veritabanı desteği

Bazı uygulamalar kullanıcı etkileşimi veya en az bir tane gerekir. Örneğin, yazdığınız varsayalım:

- Özel uygulama ve veri kaynağı arasında verilerin işlenmesi için diğer uygulamalara (istemciler) çağrı ara veri erişim nesnesi.

- Başka veya hesaplamalar yapar ve toplu güncelleştirmeler gerçekleştiren bir veritabanı biçiminden veri taşıyan bir uygulama gibi kullanıcı müdahalesi olmadan verileri işleyen bir uygulama.

Belge sahibi olduğundan `CRecordset` nesne büyük olasılıkla istediğiniz bir katıştırılmış veri üyesi olarak depolamak sizin `CWinApp`-uygulama sınıfı türetilmiş. Seçenekler şunlardır:

- Kalıcı bırakmaktan `CRecordset` nesnesi. Kayıt kümesi sınıf yapıcısına NULL geçirebilirsiniz. Bu durumda, geçici bir çerçeve oluşturur `CDatabase` kümenizin bilgileri kullanarak nesne `GetDefaultConnect` üye işlevi. Büyük olasılıkla alternatif bir yaklaşım budur.

- Yapmadan `CRecordset` genel değişkeni nesnesi. Bu değişken, dinamik olarak oluşturduğunuz bir kayıt nesnesine bir işaretçi olmalıdır, `CWinApp::InitInstance` geçersiz kılar. Bu çerçeve başlatılmadan önce nesne oluşturmaya çalışırken önler.

- Bir belge ya da bir görünüm bağlamı içinde olduğu gibi kayıt kümesi nesnelerini kullanma. Kayıt kümeleri, üye işlevleri uygulamanızın veya çerçeve pencere nesneleri oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[MFC veritabanı sınıfları](../data/mfc-database-classes-odbc-and-dao.md)