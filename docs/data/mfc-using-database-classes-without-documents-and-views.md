---
title: 'MFC: Belgeler ve Görünümler Olmadan Veritabanı Sınıflarını Kullanma'
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
ms.openlocfilehash: c914a449b73e7da876d2e05b894c016b53881c3b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360667"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Belgeler ve Görünümler Olmadan Veritabanı Sınıflarını Kullanma

Bazen veritabanı uygulamalarınızda çerçevenin belge/görünüm mimarisini kullanmak istemeyebilirsiniz. Bu konu açıklar:

- Belge serileştirme gibi [belgeleri kullanmanız gerekmediğinde.](#_core_when_you_don.92.t_need_documents)

- [Uygulama sihirbazı seçenekleri](#_core_appwizard_options_for_documents_and_views) serileştirme olmadan ve belge ile ilgili **Dosya** menüsü komutları olmadan yeni **,** **Aç**, **Kaydet**ve **Farklı Kaydet**gibi uygulamaları desteklemek için .

- [En az belge kullanan bir uygulamayla çalışma](#_core_applications_with_minimal_documents)

- [Belge veya görünüm olmadan bir uygulama yapılandırma.](#_core_applications_with_no_document)

## <a name="when-you-do-not-need-documents"></a><a name="_core_when_you_don.92.t_need_documents"></a>Belgelere İhtiyacınız Olmadığında

Bazı uygulamaların ayrı bir belge kavramı vardır. Bu uygulamalar genellikle dosyanın tamamını veya çoğunu bir **Dosya Aç** komutuyla depolamadan belleğe yükler. Güncelleştirilmiş dosyayı dosya **kaydet** veya **Farklı** Kaydet komutuyla tek seferde depolamaya geri yazarlar. Kullanıcının gördüğü bir veri dosyasıdır.

Ancak, bazı uygulama kategorileri belge gerektirmez. Veritabanı uygulamaları işlemler açısından çalışır. Uygulama, bir veritabanından kayıtları seçer ve bunları kullanıcıya genellikle birer birer sunar. Kullanıcının gördüğü genellikle bellekteki tek kayıt olabilecek tek bir geçerli kayıttır.

Uygulamanız veri depolamak için bir belge gerektirmiyorsa, çerçevenin belge/görünüm mimarisinin bir kısmını veya tamamını dağıtabilirsiniz. Ne kadar dağıttığınız, tercih ettiğiniz yaklaşıma bağlıdır. Şunları düşünebilirsiniz:

- Veri kaynağınıza bağlantı depolamak için en az belgeyi bir yer olarak kullanın, ancak serileştirme gibi normal belge özelliklerinden vazgeçin. Bu, verilerin çeşitli görünümlerini istediğinizde ve tüm görünümleri eşitlemek, hepsini aynı anda güncelleştirerek ve benzeri durumlarda yararlıdır.

- Bir görünüm kullanmak yerine doğrudan çizdiğiniz bir çerçeve penceresi kullanın. Bu durumda, belgeyi atlayın ve çerçeve penceresi nesnesinde herhangi bir veri veya veri bağlantısı depolayın.

## <a name="application-wizard-options-for-documents-and-views"></a><a name="_core_appwizard_options_for_documents_and_views"></a>Belgeler ve Görünümler için Uygulama Sihirbazı Seçenekleri

MFC Uygulama Sihirbazı'nın select **veritabanı desteğinde**aşağıdaki tabloda listelenen birkaç seçenek vardır. Bir uygulama oluşturmak için MFC Uygulama Sihirbazı'nı kullanırsanız, tüm bu seçenekler belge ve görünümiçeren uygulamalar üretir. Bazı seçenekler, gereksiz belge işlevselliğini atlayan belgeler ve görünümler sağlar. Daha fazla bilgi için [Veritabanı Desteği, MFC Uygulama Sihirbazı'na](../mfc/reference/database-support-mfc-application-wizard.md)bakın.

|Seçenek|Görüntüle|Belge|
|------------|----------|--------------|
|**Yok**|`CView`Türetilmiş.|Veritabanı desteği sağlamaz. Bu varsayılan seçenektir.<br /><br /> [Uygulama Türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **Belge/görünüm mimarisi destek** seçeneğini seçerseniz, **Dosya** menüsünde serileştirme ve **Yeni**, **Aç,** **Kaydet**ve **Kaydet** komutları dahil olmak üzere tam belge desteği alırsınız. [Bkz. Belgesiz Uygulamalar](#_core_applications_with_no_document).|
|**Yalnızca üstbilgi dosyaları**|`CView`Türetilmiş.|Uygulamanız için temel veritabanı desteği düzeyini sağlar.<br /><br /> Afxdb.h içerir. Bağlantı kitaplıkları ekler, ancak veritabanına özgü sınıflar oluşturmaz. Daha sonra kayıt kümeleri oluşturabilir ve bunları kayıtları incelemek ve güncelleştirmek için kullanabilirsiniz.|
|**Dosya desteği olmadan veritabanı görünümü**|Türetilen`CRecordView`|Belge desteği sağlar, ancak serileştirme desteği sağlamaz. Belge kayıt kümesini depolayabilir ve birden çok görünümü koordine edebilir; serileştirmeyi veya **Yeni,** **Aç,** **Kaydet**ve **Kaydet** komutlarını desteklemez. [Minimal Belgelerle Uygulamalara](#_core_applications_with_minimal_documents)Bakın. Bir veritabanı görünümü eklerseniz, verilerin kaynağını belirtmeniz gerekir.<br /><br /> Veritabanı üstbilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve kayıt kümesi içerir. (Yalnızca [Uygulama Türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında seçilen **Belge/görünüm mimarisi destek** seçeneği olan uygulamalar için kullanılabilir.)|
|**Dosya desteği ile veritabanı görünümü**|Türetilen`CRecordView`|Serileştirme ve belgeyle ilgili **Dosya** menüsü komutları da dahil olmak üzere tam belge desteği sağlar. Veritabanı uygulamaları genellikle dosya başına değil, kayıt başına bazda çalışır ve bu nedenle serileştirme gerekmez. Ancak, serileştirme için özel bir kullanımınız olabilir. [Minimal Belgelerle Uygulamalara](#_core_applications_with_minimal_documents)Bakın. Bir veritabanı görünümü eklerseniz, verilerin kaynağını belirtmeniz gerekir.<br /><br /> Veritabanı üstbilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve kayıt kümesi içerir. (Yalnızca [Uygulama Türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında seçilen **Belge/görünüm mimarisi destek** seçeneği olan uygulamalar için kullanılabilir.)|

Serileştirme alternatifleri ve serileştirme için alternatif kullanımlar tartışması için [serileştirme: Serileştirme ve Veritabanı Girişi/Çıktısı'na](../mfc/serialization-serialization-vs-database-input-output.md)bakın.

## <a name="applications-with-minimal-documents"></a><a name="_core_applications_with_minimal_documents"></a>Minimal Belgelerle Uygulamalar

MFC Uygulama Sihirbazı'nın form tabanlı veri erişim uygulamalarını destekleyen iki seçeneği vardır. Her seçenek bir `CRecordView`türetilmiş görünüm sınıfı ve bir belge oluşturur. Belgenin dışında bıraktıkları şey de farklılık gösterir.

### <a name="document-without-file-support"></a><a name="_core_a_document_without_file_support"></a>Dosya Desteği Olmayan Belge

Belge serileştirmegerekmez, **dosya desteği olmadan** uygulama sihirbazı veritabanı seçeneği Veritabanı görünümünü seçin. Belge aşağıdaki yararlı amaçlara hizmet eder:

- Bir nesneyi depolamak `CRecordset` için uygun bir yerdir.

   Bu kullanım sıradan belge kavramlarına paraleldir: belge verileri (veya bu durumda bir kayıt kümesi) depolar ve görünüm belgenin görünümüdür.

- Uygulamanız birden çok görünüm (birden çok kayıt görüntülemesi gibi) sunuyorsa, bir belge görünümleri koordine desteklemektedir.

   Birden çok görünüm aynı verileri gösteriyorsa, herhangi bir `CDocument::UpdateAllViews` görünüm verileri değiştirdiğinde güncelleştirmeleri tüm görünümlere koordine etmek için üye işlevini kullanabilirsiniz.

Bu seçeneği genellikle basit form tabanlı uygulamalar için kullanırsınız. Uygulama sihirbazı bu tür uygulamalar için kullanışlı bir yapıyı otomatik olarak destekler.

### <a name="document-with-file-support"></a><a name="_core_a_document_with_file_support"></a>Dosya Destekli Belge

Belgeyle ilgili **Dosya** menüsü komutları ve belge serileştirme için alternatif bir kullanımınız olduğunda **dosya desteğiyle** uygulama sihirbazı veritabanı seçeneği Veritabanı görünümünü seçin. Programınızın verilere erişim bölümü için, belgeyi [Dosya Desteği Olmadan Belge'de](#_core_a_document_without_file_support)açıklandığı şekilde kullanabilirsiniz. Örneğin, kullanıcının tercihlerini veya diğer yararlı bilgileri depolayan serileştirilmiş bir kullanıcı profili belgesini okumak ve yazmak için belgenin serileştirme özelliğini kullanabilirsiniz. Daha fazla fikir için [serileştirme: Serileştirme ve Veritabanı Girişi/Çıktısı'na](../mfc/serialization-serialization-vs-database-input-output.md)bakın.

Uygulama sihirbazı bu seçeneği destekler, ancak belgeyi seri hale getiren kodu yazmanız gerekir. Serileştirilmiş bilgileri belge veri üyelerinde depolayın.

## <a name="applications-with-no-document"></a><a name="_core_applications_with_no_document"></a>Belgesiz Uygulamalar

Bazen belge veya görünüm kullanmayan bir uygulama yazmak isteyebilirsiniz. Belgeler olmadan, verilerinizi `CRecordset` (nesne gibi) çerçeve penceresi sınıfınızda veya uygulama sınıfınızda saklarsınız. Ek gereksinimler, uygulamanın bir kullanıcı arabirimi sunup sunmadığına bağlıdır.

### <a name="database-support-with-a-user-interface"></a><a name="_core_database_support_with_a_user_interface"></a>Kullanıcı Arabirimi ile Veritabanı Desteği

Kullanıcı arabiriminiz (örneğin konsol komut satırı arabirimi dışında) varsa, uygulamanız görünüm yerine doğrudan çerçeve penceresinin istemci alanına çizer. Böyle bir `CRecordView`uygulama, `CFormView`ana `CDialog` kullanıcı arabirimi için veya kullanmaz, ancak normalde sıradan iletişim için kullanır. `CDialog`

### <a name="writing-applications-without-documents"></a><a name="_core_writing_applications_without_documents"></a>Belgesiz Başvuru Yazma

Uygulama sihirbazı belgeleri olmadan uygulama oluşturmayı desteklemediği için, kendi `CWinApp`türetilmiş sınıfınızı `CFrameWnd` yazmanız ve gerekirse bir veya `CMDIFrameWnd` sınıf oluşturmanız gerekir. Geçersiz `CWinApp::InitInstance` kılma ve bir uygulama nesnesi olarak bildirin:

```cpp
CYourNameApp theApp;
```

Çerçeve hala ileti-harita mekanizması ve diğer birçok özellik sağlar.

### <a name="database-support-separate-from-the-user-interface"></a><a name="_core_database_support_separate_from_the_user_interface"></a>Kullanıcı Arabiriminden Ayrı Veritabanı Desteği

Bazı uygulamaların kullanıcı arabirimine veya yalnızca en az bir arabirimine ihtiyacı yoktur. Örneğin, yazdığınızı varsayalım:

- Diğer uygulamaların (istemcilerin) uygulama ve veri kaynağı arasında özel veri işlemesi için çağrıda deyiştileri bir ara veri erişim nesnesi.

- Verileri bir veritabanı biçiminden diğerine aktaran bir uygulama veya hesaplamalar yapan ve toplu güncelleştirmeler gerçekleştiren bir uygulama gibi, verileri kullanıcı müdahalesi olmadan işleyen bir uygulama.

Hiçbir belge nesneye `CRecordset` sahip olmadığından, büyük olasılıkla nesneyi türetilmiş uygulama sınıfınızda katışılmış bir veri üyesi olarak depolamak `CWinApp`istiyorsunuz. Alternatifler şunlardır:

- Kalıcı `CRecordset` bir nesne tutmuyorum. NULL'u kayıt kümesi sınıf oluşturucularınıza geçirebilirsiniz. Bu durumda, çerçeve kayıt kümesinin `CDatabase` `GetDefaultConnect` üye işlevindeki bilgileri kullanarak geçici bir nesne oluşturur. Bu en olası alternatif yaklaşımdır.

- Nesneyi `CRecordset` küresel değişken yapma. Bu değişken, geçersiz kılmanızda `CWinApp::InitInstance` dinamik olarak oluşturduğunuz bir kayıt kümesi nesnesine işaretçi olmalıdır. Bu, çerçeve başharfe atılmadan önce nesneyi oluşturmaya çalışmayı önler.

- Bir belge veya görünüm bağlamında olduğu gibi kayıt kümesi nesneleri kullanma. Uygulamanızın veya çerçeve pencere nesnelerinin üye işlevlerinde kayıt kümeleri oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Veritabanı Sınıfları](../data/mfc-database-classes-odbc-and-dao.md)
