---
title: Veritabanı Desteği, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.database
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
ms.openlocfilehash: c13d56d2fee45e130aba81168188bec6d8828d51
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365886"
---
# <a name="database-support-mfc-application-wizard"></a>Veritabanı Desteği, MFC Uygulama Sihirbazı

Bu sayfa, projeniz için veritabanı desteği düzeyini (artı gerekirse bir veri kaynağı) belirtmenize olanak tanıyan seçenekler sağlar.

- **Veritabanı desteği**

   Projeniz için veritabanı desteği düzeyini ayarlar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Yok**|Veritabanı desteği sağlamaz. Bu varsayılan seçenektir.|
   |**Yalnızca üstbilgi dosyaları**|Uygulamanız için temel veritabanı desteği düzeyini sağlar. **İstemci türü**altında ODBC desteğini seçerseniz, MFC Uygulama Sihirbazı projenizde afxdb üstbilgi dosyasını içerir. H. Bağlantı kitaplıkları ekler, ancak veritabanına özgü sınıflar oluşturmaz. Daha sonra kayıt kümeleri oluşturabilir ve bunları kayıtları incelemek ve güncelleştirmek için kullanabilirsiniz. **İstemci türü**altında OLE DB desteğini seçerseniz, aşağıdaki üstbilgi dosyaları dahildir: ATLBASE. H AFXOLEDB. H ATLPLUS. H|
   |**Dosya desteği olmadan veritabanı görünümü**|Veritabanı üstbilgi dosyaları, bağlantı kitaplıkları, bir kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca [Uygulama Türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında **belge/görünüm mimarisi destek** seçeneği olan uygulamalar için kullanılabilir.) Bu seçenek belge desteği içerir, ancak serileştirme desteği içermez. Veritabanı görünümü eklemeyi seçerseniz, verilerin kaynağını belirtmeniz gerekir.|
   |**Dosya desteği ile veritabanı görünümü**|Veritabanı üstbilgi dosyaları, bağlantı kitaplıkları, bir kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca **Uygulama Türü** sayfasında **belge/görünüm mimarisi destek** seçeneği olan uygulamalar için kullanılabilir.) Bu seçenek, örneğin bir kullanıcı profil dosyasını güncelleştirmek için kullanabileceğiniz belge serileştirmesini destekler. Veritabanı uygulamaları genellikle dosya başına değil, kayıt başına bazda çalışır ve bu nedenle serileştirme gerekmez. Ancak, serileştirme için özel bir kullanımınız olabilir. Veritabanı görünümü eklemeyi seçerseniz, verilerin kaynağını belirtmeniz gerekir.|

   > [!NOTE]
   > **Veritabanı Desteği**altında, dosya desteği olmadan **Veritabanı görünümünü** veya dosya desteği ile **Veritabanı görünümünü**seçerseniz, görünüm sınıfı türetme, Istemci **türü** seçiminize bağlı olarak aşağıdaki gibi değişir:

  - **İstemci türü**altında **ODBC'yi** seçerseniz, uygulamanın görünüm sınıfı [CRecordView'dan](../../mfc/reference/crecordview-class.md)türetilmiştir. Bu sınıf, MFC Uygulama Sihirbazı'nın da sizin için oluşturduğu [CRecordset](../../mfc/reference/crecordset-class.md)türetilmiş sınıfla ilişkilidir. Bu seçenek, kayıt görünümünün kayıt kümesi üzerinden kayıtları görüntülemek ve güncelleştirmek için kullanıldığı form tabanlı bir uygulama sağlar.

  - **İstemci türü**altında **OLE DB'yi** seçerseniz, görünüm sınıfı [COleDBRecordView'den](../../mfc/reference/coledbrecordview-class.md)türetilmiştir ve [ctable](../../data/oledb/ctable-class.md) veya [CCommand](../../data/oledb/ccommand-class.md)türetilmiş bir sınıfla ilişkilidir.

- **İstemci türü**

   Projenizin OLE DB veya ODBC sınıfları kullanıp kullanmadığını gösterir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**OLE DB**|Bu seçenek seçildiğinde, **Veri Kaynağı** düğmesini tıklattığınızda, OLE DB veri kaynağına bağlantı oluşturmanıza yardımcı olmak için Veri **Bağlantısı Özellikleri** sihirbazı çağırır.|
   |**ODBC**|Bu seçenek seçildiğinde, **Veri Kaynağı** düğmesini tıklattığınızda, ODBC veri kaynağına bağlantı oluşturmanıza yardımcı olmak için Veri **Kaynağı Seç** sihirbazı çağırır.|

- **Veri Kaynağı**

   > [!NOTE]
   > ATL OLE DB Tüketici sihirbazı ve MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. İşlevselliği el ile eklemeye devam edebilirsiniz. Daha fazla bilgi için [bkz.](../../data/oledb/creating-a-consumer-without-using-a-wizard.md)

   Belirtilen sürücü veya sağlayıcı ve veritabanını kullanarak bir veri kaynağı ayarlamak için **Veri Kaynağı** düğmesini tıklatın. **İstemci türü** seçeneğinde OLE DB'yi seçtiyseniz, bu düğme **Veri Bağlantısı Özellikleri** iletişim kutusunu görüntüler. **İstemci türü** seçeneğinde ODBC'yi seçtiyseniz, bu düğme **Veri Kaynağı Seç** iletişim kutusunu sağlar. Bu seçenek, yalnızca uygulamanıza bir veritabanı görünümü eklemeyi seçerseniz kullanılabilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Veri Bağlantısı Özellikleri** (OLE DB)|Belirtilen OLE DB sağlayıcısını kullanarak belirtilen veri kaynağını kurar. OLE DB sağlayıcısını, verilerin konumunu, veri kaynağını, oturum açma kimliğini ve (isteğe bağlı olarak) bir parola belirtmeniz gerekir. Bu iletişim kutusuyla ilgili ayrıntılar için [ATL OLE DB Tüketici Sihirbazı'ndaki](../../atl/reference/atl-ole-db-consumer-wizard.md) **Veri kaynağına** bakın.|
   |**Veri Kaynağı** (ODBC) seçin|Belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını kurar. Veri kaynağı için bir tablo seçmek için bir veri kaynağı adı seçmeniz gerekir. Sihirbaz, tablonun tüm sütunlarını türetilmiş sınıfın `CRecordset`üye değişkenlerine bağlar. Bu iletişim kutusuyla ilgili ayrıntılar için [MFC ODBC Tüketici Sihirbazı'ndaki](../../mfc/reference/mfc-odbc-consumer-wizard.md) **Veri kaynağına** bakın.|

- **Atfedilen veritabanı sınıfOluşturma**

   Yalnızca OLE DB istemcisi için kullanılabilir. Oluşturulan projedeki veritabanı sınıflarının öznitelikleri kullanıp kullanmayacağını belirtir.

- **Tüm sütunları bağlama**

   Yalnızca ODBC istemcisi için kullanılabilir. Seçili tablodaki tüm sütunların bağlı olup olmadığını belirtir. Bu kutuyu seçerseniz, tüm sütunlar bağlanır; Bu kutuyu seçmezseniz, sütun bağlı değildir ve bunları kayıt kümesi sınıfında el ile bağlamanız gerekir.

- **Tür**

   Yalnızca ODBC istemcisi için kullanılabilir. Aşağıdaki tabloda açıklandığı gibi kayıt kümesinin bir dinamit mi yoksa anlık görüntü mü olduğunu belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dynaset**|Kayıt kümesinin bir dinamit olduğunu belirtir. Dynaset, sorgulanan veritabanıverilerine dizinlenmiş görünüm sağlayan bir sorgunun sonucudur. Bir dinamit, özgün verilere yalnızca ayrılmaz bir dizin önbelleğe gelir ve böylece anlık görüntü üzerinden performans artışı sağlar. Dizin, sorgu nun sonucu olarak bulunan her kayda doğrudan işaret ediyor ve bir kaydın kaldırılıp kaldırılmadı olduğunu gösterir. Ayrıca sorgulanmış kayıtlarda güncelleştirilmiş bilgilere erişebilirsiniz.|
   |**Anlık Görüntü**|Kayıt kümesinin anlık görüntü olduğunu belirtir. Anlık görüntü bir sorgunun sonucudur ve bir zaman içinde bir veritabanına bir görünümdür. Sorgu nun sonucu olarak bulunan tüm kayıtlar önbelleğe alınır, bu nedenle özgün kayıtlarda herhangi bir değişiklik görmezsiniz.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
