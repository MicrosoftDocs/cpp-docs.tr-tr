---
title: "MFC: Belgeler ve görünümler olmadan veritabanı sınıflarını kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1691d1f90201b25cc53cd07e80626e98c447e66b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-using-database-classes-without-documents-and-views"></a>MFC: Belgeler ve Görünümler Olmadan Veritabanı Sınıflarını Kullanma
Bazen, veritabanı uygulamalarınızda framework'ün belge/görünüm mimarisi istemeyebilirsiniz. Bu konuda açıklanmaktadır:  
  
-   [Ne zaman gereksinim belgeleri kullanmak](#_core_when_you_don.92.t_need_documents) belge seri hale getirme gibi.  
  
-   [Uygulama Sihirbazı Seçenekleri](#_core_appwizard_options_for_documents_and_views) seri hale getirme ve olmadan uygulamaları desteklemek için belgeyle ilgili **dosya** menü komutları gibi **yeni**, **açmak**, **Kaydetmek**, ve **Farklı Kaydet**.  
  
-   [En az bir belge kullanan bir uygulama ile çalışmaya nasıl](#_core_applications_with_minimal_documents).  
  
-   [Belge veya görünümü olmayan bir uygulama nasıl yapılandırılır](#_core_applications_with_no_document).  
  
##  <a name="_core_when_you_don.92.t_need_documents"></a>Belgeleri gerektiğinde değil  
 Bazı uygulamalar ayrı bir belge kavramı vardır. Bu uygulamalar genellikle tüm veya çoğu dosyasının depolama biriminden belleğe ile yük bir **Dosya Aç** komutu. Bunlar güncelleştirilmiş dosya geri tamamını tek seferde depolama yazma bir **dosyasını kaydedin** veya **Kaydet** komutu. Kullanıcının gördüğü veri dosyasıdır.  
  
 Bazı uygulama, kategorileri ancak, bir belge gerek yoktur. Veritabanı uygulamaları işlem olarak çalışır. Uygulama bir veritabanındaki kayıtları seçer ve bunları birer birer kullanıcının genellikle sunar. Kullanıcının gördüğü genellikle tek bellekte olabilir tek bir geçerli kayıt var.  
  
 Uygulamanızın veri depolamak için bir belge gerektirmiyorsa, bazılarını veya tümünü framework'ün belge/görünüm mimarisinin etiket. Ne kadar dağıtacağınız tercih ettiğiniz yaklaşıma bağlıdır. Şunu yapabilirsiniz:  
  
-   En az bir belge, veri kaynağına bağlantı saklar, ancak seri hale getirme gibi normal belge özellikleri dağıtacağınız için bir yer olarak kullanın. Bu, birkaç veri görünümlerini ve aynı anda ve benzeri güncelleştirme görünümleri eşitlemek istediğiniz istediğinizde yararlıdır.  
  
-   İçine doğrudan bir görünüm kullanmak yerine çizim çerçeve penceresi kullanın. Bu durumda, belgeyi yok sayın ve herhangi bir veri veya veri bağlantıları çerçeve penceresi nesnesinde depolar.  
  
##  <a name="_core_appwizard_options_for_documents_and_views"></a>Belgeler ve görünümler için Uygulama Sihirbazı Seçenekleri  
 MFC Uygulama Sihirbazı çeşitli seçenekleri vardır **seçin veritabanı desteği**, aşağıdaki tabloda listelenmiştir. Bir uygulama oluşturmak için MFC Uygulama Sihirbazı'nı kullanırsanız, tüm bu seçenekler belgeler ve görünümler uygulamalarla üretir. Belgeler ve gereksiz belge özelliklerini atlayan görünümler bazı seçenekler sağlar. Daha fazla bilgi için bkz: [veritabanı desteği, MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md).  
  
|Seçenek|Görüntüle|Belge|  
|------------|----------|--------------|  
|**Yok**|Türetilmiş `CView`.|Hiçbir veritabanı desteği sağlar. Varsayılan seçenek budur.<br /><br /> Seçerseniz **belge/görünüm mimarisi desteği** seçeneği [uygulama türü, MFC Uygulama Sihirbazı'nı](../mfc/reference/application-type-mfc-application-wizard.md) sayfasında, serileştirme içeren tam belge desteğini alırsınız ve `New`,  **Açık**, **kaydetmek**, ve **Kaydet** komutlarını **dosya** menüsü. Bkz: [belgesi olmayan uygulamalar](#_core_applications_with_no_document).|  
|**Yalnızca üst bilgi dosyaları**|Türetilmiş `CView`.|Uygulamanız için temel düzeyde bir veritabanı desteği sağlar.<br /><br /> Afxdb.h içerir. Bağlantı kitaplıkları ekler, ancak herhangi bir veritabanına özel sınıf oluşturmaz. Daha sonra kayıt kümeleri oluşturabilir ve bunları inceleyin ve kayıtlarını güncelleştirmek için kullanın.|  
|**Dosya desteği olmayan veritabanı görünümü**|Türetilen`CRecordView`|Belge desteği, ancak hiçbir serileştirme desteği sağlar. Belge kayıt kümesi saklayabilir ve birden çok görünüm koordine; Seri duruma getirmeyi desteklemeyen veya `New`, **açık**, **kaydetmek**, ve **Kaydet** komutları. Bkz: [en az Belgeli Uygulamalar](#_core_applications_with_minimal_documents). Bir veritabanı görünümü eklerseniz, veri kaynağı olarak belirtmeniz gerekir.<br /><br /> Veritabanı başlık dosyalarını, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca uygulamalarla kullanılabilir **belge/görünüm mimarisi desteği** seçeneği seçili [uygulama türü, MFC Uygulama Sihirbazı'nı](../mfc/reference/application-type-mfc-application-wizard.md) sayfası.)|  
|**Dosya desteği olan veritabanı görünümü**|Türetilen`CRecordView`|Seri hale getirme içeren tam belge desteği sağlar ve belge ilgili **dosya** menü komutları. Bir dosya başına üzerinde temel ve bu nedenle serileştirme gerekmez yerine veritabanı uygulamaları genellikle bir kayıt başına temelinde çalışır. Ancak, serileştirme için özel bir kullanım olabilir. Bkz: [en az Belgeli Uygulamalar](#_core_applications_with_minimal_documents). Bir veritabanı görünümü eklerseniz, veri kaynağı olarak belirtmeniz gerekir.<br /><br /> Veritabanı başlık dosyalarını, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca uygulamalarla kullanılabilir **belge/görünüm mimarisi desteği** seçeneği seçili [uygulama türü, MFC Uygulama Sihirbazı'nı](../mfc/reference/application-type-mfc-application-wizard.md) sayfası.)|  
  
 Seri hale getirme ve seri hale getirme alternatif kullanımları alternatifleri tartışma için bkz [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).  
  
##  <a name="_core_applications_with_minimal_documents"></a>En az Belgeli Uygulamalar  
 MFC Uygulama Sihirbazı form tabanlı veri erişimi uygulamaları destekleyen iki seçenek vardır. Her seçenek oluşturur bir `CRecordView`-türetilmiş görünüm sınıfı ve bir belge. Bunlar, bunlar belgenin dışında bırakın içinde farklılık gösterir.  
  
###  <a name="_core_a_document_without_file_support"></a>Dosya desteği olmayan belge  
 Uygulama Sihirbazı veritabanı seçeneğini **veritabanı görünümü dosya desteği olmadan** Belge Serileştirme gerekmiyorsa. Belge aşağıdaki kullanışlı amaca hizmet eder:  
  
-   Depolamak için uygun bir yerdir bir `CRecordset` nesnesi.  
  
     Bu kullanım sıradan belge kavramları ile paraleldir: belge verilerini depolayan (veya bu durumda, bir kayıt kümesi) ve belgenin görünümünü görünümüdür.  
  
-   Uygulamanız (örneğin, birden çok kayıt görünümleri) birden çok görünüm sunar, bir belge görünüm düzenlemeyi destekler.  
  
     Birden çok görünüm aynı veriyi gösterirse, kullanabileceğiniz `CDocument::UpdateAllViews` herhangi bir görünüm veriler değiştiğinde tüm görünümlere güncelleştirmelerini koordine etmek için üye işlevi.  
  
 Genellikle basit form tabanlı uygulamalar için bu seçeneği kullanın. Uygulama Sihirbazı'nı uygun bir yapı bu tür uygulamalar için otomatik olarak destekler.  
  
###  <a name="_core_a_document_with_file_support"></a>Dosya desteği olan belge  
 Uygulama Sihirbazı veritabanı seçeneğini seçin **veritabanı dosya desteği görünümüyle** belgeyle ilgili için alternatif kullanımınız olduğunda **dosya** menü komutları ve belge seri hale getirme. Veri erişimi kısmı, program için belgeyi aynı şekilde açıklandığı gibi kullanabilirsiniz [dosya desteği olmayan belge](#_core_a_document_without_file_support). Örneğin, kullanıcının tercihlerini veya diğer yararlı bilgileri depolayan bir serileştirilmiş kullanıcı profil belgesi okumasına ve yazmasına belgenin serileştirme özelliğini kullanabilirsiniz. Daha fazla fikir için bkz: [seri hale getirme: seri hale getirme vs. Veritabanı giriş/çıkış](../mfc/serialization-serialization-vs-database-input-output.md).  
  
 Bu seçenek Uygulama Sihirbazı'nı destekler, ancak belgeyi serileştiren kod yazmanız gerekir. Serileştirilmiş bilgiler belge veri üyelerinde saklar.  
  
##  <a name="_core_applications_with_no_document"></a>Belgesi olmayan uygulamalar  
 Bazen belgeleri veya görünümler kullanmayan uygulama yazmak isteyebilirsiniz. Belgeler olmadan, verilerinizi depolamak (gibi bir `CRecordset` nesnesi), çerçeve pencere sınıfı ya da uygulama sınıfı. Tüm ek gereksinimleri, uygulama bir kullanıcı arabirimi sunar üzerinde bağlıdır.  
  
###  <a name="_core_database_support_with_a_user_interface"></a>Kullanıcı arabirimi ile veritabanı desteği  
 Kullanıcı Arabirimi (örneğin, bir konsol komut satırı arabirimi, diğer) varsa, uygulamanızın çerçeve penceresinin istemci alanına doğrudan yerine görünüm çizer. Bu tür bir uygulama kullanmayan `CRecordView`, `CFormView`, veya `CDialog` ana kullanıcı arayüzü, ancak için normalde kullandığınız `CDialog` sıradan iletişimler için.  
  
###  <a name="_core_writing_applications_without_documents"></a>Belgeler olmadan uygulamaları yazma  
 Uygulama Sihirbazı belgeler olmadan uygulama oluşturmayı desteklemediğinden, kendi yazmalısınız `CWinApp`-türetilmiş sınıf, gerekirse oluşturun ve ayrıca bir `CFrameWnd` veya `CMDIFrameWnd` sınıfı. Geçersiz kılma `CWinApp::InitInstance` ve bir uygulama nesnesi olarak bildirin:  
  
```  
CYourNameApp theApp;  
```  
  
 Framework hala ileti eşleme mekanizmasını ve diğer birçok özellik sağlar.  
  
###  <a name="_core_database_support_separate_from_the_user_interface"></a>Kullanıcı arabiriminden ayrı veritabanı desteği  
 Bazı uygulamalar, herhangi bir kullanıcı arabirimi veya en az bir tane gerekir. Örneğin, şunu yazdığınızı varsayın:  
  
-   Uygulama ve veri kaynağı arasında veri özel işleme için diğer uygulamaların (istemciler) çağrı ara veri erişim nesnesi.  
  
-   Verileri bir veritabanı biçimden başka veya hesaplamaları yapar ve toplu güncelleştirmeler gerçekleştiren bir taşır bir uygulama gibi kullanıcı müdahalesi olmadan verileri işleyen bir uygulama.  
  
 Bir belge sahibi olduğundan `CRecordset` nesnesi, büyük olasılıkla istediğiniz bir katıştırılmış veri üyesi olarak depolamak, `CWinApp`-türetilen uygulama sınıfı. Alternatifler şunları içerir:  
  
-   Kalıcı olmayan tutma `CRecordset` hiç nesne. Geçirebilirsiniz **NULL** kayıt kümesi sınıf oluşturucuları için. Bu durumda, geçici bir çerçevesini oluşturur `CDatabase` kayıt kümesinin bilgileri kullanarak nesne `GetDefaultConnect` üye işlevi. Bu büyük olasılıkla alternatif yaklaşımdır.  
  
-   Yapma `CRecordset` genel değişkeni nesne. Bu değişken dinamik olarak oluşturduğunuz bir kayıt kümesi nesnesi için bir işaretçi olmalıdır, `CWinApp::InitInstance` geçersiz kılar. Bu framework başlatılmadan önce nesne oluşturmaya çalışırken önler.  
  
-   Bir belge veya Görünüm bağlamı içinde olduğu gibi kayıt kümesi nesnelerini kullanma. Kayıt kümeleri üye işlevleri uygulamanızın veya çerçeve pencere nesneleri oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Veritabanı Sınıfları](../data/mfc-database-classes-odbc-and-dao.md)