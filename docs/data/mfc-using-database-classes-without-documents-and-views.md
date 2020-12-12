---
description: 'Daha fazla bilgi edinin: MFC: belgeler ve görünümler olmadan veritabanı sınıflarını kullanma'
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
ms.openlocfilehash: 32b019286a07cacc0c7bf95145d0aedde804ff92
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295165"
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Belgeler ve Görünümler Olmadan Veritabanı Sınıflarını Kullanma

Bazen, veritabanı uygulamalarınızda Framework 'ün belge/görünüm mimarisini kullanmak istemeyebilirsiniz. Bu konuda aşağıdakiler açıklanmaktadır:

- Belge serileştirme gibi [Belgeler kullanmanıza gerek olmadığında](#_core_when_you_don.92.t_need_documents) .

- [Uygulama Sihirbazı](#_core_appwizard_options_for_documents_and_views) ' nı serileştirme ve **Yeni**, **açma**, **kaydetme** ve **farklı kaydet** gibi belge ile ilgili **Dosya** menüsü komutları olmadan uygulamaları desteklemeye yönelik seçenekler.

- [En az bir belge kullanan bir uygulamayla çalışma](#_core_applications_with_minimal_documents).

- [Belge veya görünüm olmadan bir uygulamayı nasıl yapılandıracağınıza](#_core_applications_with_no_document).

## <a name="when-you-do-not-need-documents"></a><a name="_core_when_you_don.92.t_need_documents"></a> Belgelere Ihtiyacınız olmadığında

Bazı uygulamalarda farklı bir belge kavramı vardır. Bu uygulamalar genellikle dosya **Aç** komutuyla bir dosyanın tamamını depolama alanından belleğe yükler. Güncelleştirilmiş dosyayı **Dosya Kaydet** veya **farklı kaydet** komutuyla tek seferde depolama alanına geri yazar. Kullanıcının gördüğü veri dosyası.

Ancak bazı uygulama kategorileri için bir belge gerekmez. Veritabanı uygulamaları işlem koşullarında çalışır. Uygulama bir veritabanından kayıtları seçer ve genellikle bir kerede bir kez kullanıcıya sunar. Kullanıcının gördüğü, genellikle bellekte tek bir geçerli kayıt olabilir.

Uygulamanız veri depolamak için bir belge gerektirmiyorsa, Framework 'ün belge/görünüm mimarisinin bir kısmını veya tamamını kullanabilirsiniz. İle ne kadar çok, tercih ettiğiniz yaklaşıma göre değişir. Şunları yapabilirsiniz:

- Veri kaynağınıza bir bağlantı depolamak için bir yer olarak en az bir belge kullanın, ancak serileştirme gibi normal belge özellikleriyle dağıtılın. Bu, verilerin çeşitli görünümlerini istediğinizde ve tüm görünümleri eşleştirmek, tümünü bir kez güncelleştirmek ve bu şekilde devam etmek istediğinizde yararlı olur.

- Bir görünüm kullanmak yerine doğrudan çizeceğiniz bir çerçeve penceresi kullanın. Bu durumda, belgeyi atlayın ve tüm verileri veya veri bağlantılarını çerçeve pencere nesnesinde depolayamazsınız.

## <a name="application-wizard-options-for-documents-and-views"></a><a name="_core_appwizard_options_for_documents_and_views"></a> Belgeler ve görünümler için uygulama Sihirbazı seçenekleri

MFC Uygulama Sihirbazı ' nda, aşağıdaki tabloda listelenen **veritabanı desteği seçme**' de çeşitli seçenekler bulunur. Bir uygulama oluşturmak için MFC Uygulama Sihirbazı ' nı kullanırsanız, tüm bu seçenekler belgeler ve görünümler ile uygulamalar oluşturur. Bazı seçenekler, gerekli olmayan belge işlevlerini atlayan belgeler ve görünümler sağlar. Daha fazla bilgi için bkz. [veritabanı desteği, MFC Uygulama Sihirbazı](../mfc/reference/database-support-mfc-application-wizard.md).

|Seçenek|Görüntüle|Belge|
|------------|----------|--------------|
|**Hiçbiri**|Öğesinden türetilir `CView` .|Veritabanı desteği sağlamaz. Bu varsayılan seçenektir.<br /><br /> [Uygulama türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **belge/görünüm mimarisi desteği** seçeneğini belirlerseniz, **Dosya** menüsünde serileştirme ve **Yeni**, **açma**, **kaydetme** ve **farklı kaydet** komutları dahil olmak üzere tam belge desteği alırsınız. [Belge Içermeyen uygulamalara](#_core_applications_with_no_document)bakın.|
|**Yalnızca üst bilgi dosyaları**|Öğesinden türetilir `CView` .|Uygulamanız için temel veritabanı desteği düzeyini sağlar.<br /><br /> Afxdb. h 'yi içerir. Bağlantı kitaplıklarını ekler, ancak herhangi bir veritabanına özgü sınıf oluşturmaz. Kayıt kümelerini daha sonra oluşturabilir ve kayıtları incelemek ve güncelleştirmek için kullanabilirsiniz.|
|**Dosya desteği olmadan veritabanı görünümü**|Türeten türetilmiş `CRecordView`|Belge desteği sağlar ancak serileştirme desteği yoktur. Belge, kayıt kümesini saklayabilir ve birden çok görünümü koordine edebilir; serileştirme veya **Yeni**, **Aç**, **Kaydet** ve **farklı kaydet** komutlarını desteklemez. [En az belgeli uygulamalara](#_core_applications_with_minimal_documents)bakın. Bir veritabanı görünümü eklerseniz, verilerin kaynağını belirtmeniz gerekir.<br /><br /> Veritabanı üst bilgi dosyalarını, bağlantı kitaplıklarını, kayıt görünümünü ve bir kayıt kümesini içerir. ( [Uygulama türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında yalnızca **belge/görünüm mimarisi desteği** seçeneği belirlenmiş olan uygulamalar için kullanılabilir.)|
|**Dosya destekli veritabanı görünümü**|Türeten türetilmiş `CRecordView`|Serileştirme ve belgeyle ilgili **Dosya** menüsü komutları dahil olmak üzere tam belge desteği sağlar. Veritabanı uygulamaları genellikle dosya başına değil, kayıt başına temelinde çalışır ve bu nedenle serileştirme gerektirmez. Ancak, serileştirme için özel bir kullanıma sahip olabilirsiniz. [En az belgeli uygulamalara](#_core_applications_with_minimal_documents)bakın. Bir veritabanı görünümü eklerseniz, verilerin kaynağını belirtmeniz gerekir.<br /><br /> Veritabanı üst bilgi dosyalarını, bağlantı kitaplıklarını, kayıt görünümünü ve bir kayıt kümesini içerir. ( [Uygulama türü, MFC Uygulama Sihirbazı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında yalnızca **belge/görünüm mimarisi desteği** seçeneği belirlenmiş olan uygulamalar için kullanılabilir.)|

Serileştirme ve seri hale getirme alternatiflerinin bir tartışması için bkz. [serileştirme: serileştirme ve veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).

## <a name="applications-with-minimal-documents"></a><a name="_core_applications_with_minimal_documents"></a> En az belgeli uygulamalar

MFC Uygulama Sihirbazı, form tabanlı veri erişimi uygulamalarını destekleyen iki seçeneğe sahiptir. Her seçenek, bir `CRecordView` türetilmiş görünüm sınıfı ve bir belge oluşturur. Bunlar, belgenin dışına çıktıklarında farklılık gösterir.

### <a name="document-without-file-support"></a><a name="_core_a_document_without_file_support"></a> Dosya desteği olmayan belge

Belge serileştirmesi gerekmiyorsa, **dosya desteği olmadan** uygulama Sihirbazı veritabanı seçeneği veritabanı görünümü ' nü seçin. Belge, aşağıdaki yararlı amaçlara hizmet eder:

- Bir nesneyi depolamak için kullanışlı bir yerdir `CRecordset` .

   Bu kullanım sıradan belge kavramlarını paraleller: belge, verileri depolar (veya bu durumda bir kayıt kümesi) ve Görünüm belgenin bir görünümüdür.

- Uygulamanız birden çok görünüm (örneğin, birden çok kayıt görünümü) sunduğunda, bir belge görünümlerin eşgüdümünü destekler.

   Birden çok görünüm aynı verileri gösterayarlanırsa, `CDocument::UpdateAllViews` herhangi bir görünüm verileri değiştirdiğinde tüm görünümlere güncelleştirmeleri koordine etmek için üye işlevini kullanabilirsiniz.

Bu seçeneği genellikle basit form tabanlı uygulamalar için kullanırsınız. Uygulama Sihirbazı bu tür uygulamalar için otomatik olarak uygun yapıyı destekler.

### <a name="document-with-file-support"></a><a name="_core_a_document_with_file_support"></a> Dosya desteğiyle belge

Belge ile ilgili **Dosya** menü komutları ve belge serileştirmesi için alternatif bir kullanıma sahip olduğunuzda, dosya desteğiyle uygulama Sihirbazı veritabanı seçeneği **veritabanı görünümü** ' nü seçin. Programınızın veri erişimi bölümü için, belgeyi [dosya desteği olmadan belge](#_core_a_document_without_file_support)içinde açıklananla aynı şekilde kullanabilirsiniz. Kullanıcının tercihlerini veya diğer yararlı bilgileri depolayan serileştirilmiş bir kullanıcı profili belgesi okumak ve yazmak için, belgenin serileştirme özelliğini kullanabilirsiniz. Daha fazla fikir için bkz. [serileştirme: serileştirme ve veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).

Uygulama Sihirbazı bu seçeneği destekler, ancak belgeyi serileştiren kodu yazmanız gerekir. Seri hale getirilmiş bilgileri belge veri üyelerinde depolayın.

## <a name="applications-with-no-document"></a><a name="_core_applications_with_no_document"></a> Belge Içermeyen uygulamalar

Bazen belge veya görünüm kullanmayan bir uygulama yazmak isteyebilirsiniz. Belgeler olmadan, verilerinizi (örneğin, bir `CRecordset` nesnesi) çerçeve pencere sınıfında veya uygulama sınıfınıza depoladığınızda. Ek gereksinimler, uygulamanın bir kullanıcı arabirimi sunmadığına bağlıdır.

### <a name="database-support-with-a-user-interface"></a><a name="_core_database_support_with_a_user_interface"></a> Kullanıcı arabirimiyle veritabanı desteği

Kullanıcı arabiriminiz varsa (örneğin, bir konsol komut satırı arabirimi dışında), uygulamanız bir görünüm yerine doğrudan çerçeve penceresinin istemci alanına çizilir. Bu tür bir uygulama `CRecordView` , `CFormView` `CDialog` ana kullanıcı arabirimi için, veya kullanmaz, ancak normalde normal `CDialog` iletişim kutularında kullanılır.

### <a name="writing-applications-without-documents"></a><a name="_core_writing_applications_without_documents"></a> Belgeleri olmayan uygulamalar yazma

Uygulama Sihirbazı belge olmadan uygulama oluşturmayı desteklemediğinden, kendi `CWinApp` türetilmiş sınıfınızı yazmanız gerekir ve gerekirse, bir `CFrameWnd` veya sınıfı da oluşturabilirsiniz `CMDIFrameWnd` . `CWinApp::InitInstance`Uygulama nesnesini geçersiz kılın ve bildirin:

```cpp
CYourNameApp theApp;
```

Framework, ileti eşleme mekanizmasını ve diğer birçok özelliği de sağlar.

### <a name="database-support-separate-from-the-user-interface"></a><a name="_core_database_support_separate_from_the_user_interface"></a> Kullanıcı arabiriminden ayrı veritabanı desteği

Bazı uygulamaların kullanıcı arabirimi veya yalnızca en az bir tane olması gerekir. Örneğin, yazdığınızı varsayalım:

- Diğer uygulamaların (istemciler), uygulama ve veri kaynağı arasındaki özel veri işlemesi için çağrı yapan bir ara veri erişimi nesnesi.

- Verileri bir veritabanı biçiminden diğerine veya hesaplama yapan ve toplu iş güncelleştirmelerini gerçekleştiren bir uygulama gibi, Kullanıcı müdahalesi olmadan verileri işleyen bir uygulama.

Nesneye sahip bir belge olmadığından `CRecordset` , büyük olasılıkla `CWinApp` türetilmiş uygulama sınıfınıza ekli bir veri üyesi olarak saklamak isteyeceksiniz. Alternatifler şunlardır:

- Kalıcı bir `CRecordset` nesneyi hiç tutmadı. Kayıt kümesi sınıfı oluşturuculara NULL geçirebilirsiniz. Bu durumda Framework, `CDatabase`  kayıt kümesinin üye işlevindeki bilgileri kullanarak geçici bir nesne oluşturur `GetDefaultConnect` . Bu, en olası alternatif yaklaşımdır.

- `CRecordset`Nesne genel bir değişken yapılıyor. Bu değişken, geçersiz kılmanızda dinamik olarak oluşturduğunuz bir kayıt kümesi nesnesi işaretçisi olmalıdır `CWinApp::InitInstance` . Bu, çerçeve başlatılmadan önce nesneyi oluşturmaya çalışıyor.

- Kayıt kümesi nesnelerini bir belge veya görünüm bağlamında yaptığınız gibi kullanma. Uygulamanızın veya çerçeve pencere nesnelerinizin üye işlevlerinde kayıt kümeleri oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[MFC veritabanı sınıfları](../data/mfc-database-classes-odbc-and-dao.md)
