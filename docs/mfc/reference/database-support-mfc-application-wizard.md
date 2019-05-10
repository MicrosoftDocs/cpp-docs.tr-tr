---
title: Veritabanı Desteği, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.database
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
ms.openlocfilehash: 94ed75ffd59294d5beb076ef4d66e57ef763f10e
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525462"
---
# <a name="database-support-mfc-application-wizard"></a>Veritabanı Desteği, MFC Uygulama Sihirbazı

Bu sayfa, veritabanının düzeyini belirtmenize olanak sağlayan seçenekler sağlar. projeniz için (veri kaynağı yanı sıra, gerekirse) destekler.

- **Veritabanı desteği**

   Projeniz için veritabanı destek düzeyini ayarlar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Yok.**|Hiçbir veritabanı desteği sağlar. Varsayılan seçenek budur.|
   |**Yalnızca üst bilgi dosyaları**|Uygulamanız için temel düzeyde bir veritabanı desteği sağlar. ODBC desteği altında seçerseniz **istemci türü**, MFC Uygulama Sihirbazı projenizde AFXDB üstbilgi dosyasını içerir. H Bağlantı kitaplıkları ekler, ancak herhangi bir veritabanı özgü sınıflar oluşturmaz. Daha sonra kayıt kümeleri oluşturma ve bunları inceleyin ve kayıtları güncelleştirmek için kullanın. OLE DB desteği altında seçerseniz **istemci türü**, aşağıdaki üst bilgi dosyaları dahil edilir: ATLBASE.H AFXOLEDB.H ATLPLUS.H|
   |**Dosya desteği olmadan veritabanı görünümü**|Veritabanı üst bilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Kullanılabilir olan uygulamalar için **belge/görünüm mimarisi desteği** seçeneğe [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfası.) Bu seçenek, belge desteği, ancak hiçbir serileştirme desteği içerir. Veritabanı görünümü dahil kullanmayı tercih ederseniz, veri kaynağı belirtmeniz gerekir.|
   |**Dosya destekli veritabanı görünümü**|Veritabanı üst bilgi dosyaları, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Kullanılabilir olan uygulamalar için **belge/görünüm mimarisi desteği** seçeneğe **uygulama türü** sayfası.) Bu seçenek, örneğin, bir kullanıcı profili dosyasını güncelleştirmek için kullanabileceğiniz Belge Serileştirme destekler. Yerine dosya ve bu nedenle temel serileştirme gerekmez veritabanı uygulamaları, genellikle kayıt başına temelinde çalışır. Ancak, serileştirme için özel bir kullanım olabilir. Veritabanı görünümü dahil kullanmayı tercih ederseniz, veri kaynağı belirtmeniz gerekir.|

   > [!NOTE]
   > Altında **veritabanı desteği**, ya da seçerseniz **Ritabanı görünümü dosya desteği olmadan** veya **görünümü dosya destekli veritabanı**, görünüm sınıfı türetme, bağlı olarak farklılık gösterir üzerinde **istemci türü** aşağıdaki gibi bir seçimi:

   - Seçerseniz **ODBC** altında **istemci türü**, uygulamanın görünüm sınıfın türetildiği sonra [CRecordView](../../mfc/reference/crecordview-class.md). Bu sınıf ile ilişkili bir [CRecordset](../../mfc/reference/crecordset-class.md)-türetilmiş sınıf, MFC Uygulama Sihirbazı'nı da sizin için oluşturur. Bu seçenek, kayıt görünümü kayıtları, kayıt kümesi aracılığıyla görüntülemek ve güncelleştirmek için kullanılan form tabanlı bir uygulama sağlar.

   - Seçerseniz **OLE DB** altında **istemci türü**, görünüm sınıfın türetildiği sonra [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), ve ilişkili olduğu bir [CTable](../../data/oledb/ctable-class.md) veya [CCommand](../../data/oledb/ccommand-class.md)-türetilmiş sınıf.

- **İstemci türü**

   Projenizi OLE DB veya ODBC sınıfları kullanıp kullanmadığını belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**OLE DB**|Bu seçenek belirlendiğinde, tıklayarak **veri kaynağı** düğmesi çağırır **veri bağlantı özellikleri** bir OLE DB veri kaynağı bağlantısı oluşturmanıza yardımcı olması için Sihirbazı.|
   |**ODBC**|Bu seçenek belirlendiğinde, tıklayarak **veri kaynağı** düğmesi çağırır **veri kaynağı Seç** ODBC veri kaynağı bağlantısı oluşturmanıza yardımcı olması için Sihirbazı.|

- **Veri kaynağı**

   > [!NOTE]
   > ATL OLE DB Tüketicisi Sihirbazı ve MFC ODBC Tüketicisi Sihirbazı'nı Visual Studio 2019 bulunan ve daha sonra değildir. İşlevselliğini el ile eklemeye devam edebilirsiniz. Daha fazla bilgi için [olmadan bir tüketici kullanarak sihirbaz oluşturma](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

   Tıklayın **veri kaynağı** düğmesini belirtilen sürücü ya da sağlayıcı ve veritabanı'nı kullanarak bir veri kaynağını ayarlayın. OLE DB içinde seçtiyseniz **istemci türü** seçeneği, bu düğmeyi görüntüler **veri bağlantı özellikleri** iletişim kutusu. ODBC seçtiyseniz **istemci türü** seçeneği, bu düğmeyi sağlar **veri kaynağı Seç** iletişim kutusu. Bu seçenek, bir veritabanı görünümü uygulamanıza dahil seçerseniz kullanılabilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Veri bağlantı özellikleri** (OLE DB)|Belirtilen OLE DB sağlayıcısı kullanılarak belirtilen veri kaynağı oluşturur. OLE DB sağlayıcısı, veri, veri kaynağı, oturum açma kimliği ve (isteğe bağlı) parola konumunu belirtmelisiniz. Bu iletişim kutusu hakkında daha fazla bilgi için bkz: **veri kaynağı** içinde [ATL OLE DB Tüketicisi Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md).|
   |**Veri kaynağı** (ODBC)|Belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağı oluşturur. Veri kaynağı için bir tablo seçmek için bir veri kaynağı adı seçmeniz gerekir. Sihirbaz için üye değişkenleri tablonun tüm sütunlarını bağlar bir `CRecordset`-türetilmiş sınıf. Bu iletişim kutusu hakkında daha fazla bilgi için bkz: **veri kaynağı** içinde [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/mfc-odbc-consumer-wizard.md).|

- **Öznitelik atanmış veritabanı sınıfı üret**

   OLE DB istemci için kullanılabilir. Veritabanı sınıfları oluşturulan projedeki öznitelikleri kullanıp kullanmadığını belirtir.

- **Tüm sütunları bağlayın**

   ODBC istemci için kullanılabilir. Seçili tablodaki tüm sütunları bağlanıp bağlanmadığını belirtir. Bu kutusunu seçerseniz, tüm sütunları bağlıdır; Bu kutuyu işaretlemeyin, hiçbir sütun bağlı ve el ile kayıt kümesi sınıfında bağlanmalıdır.

- **Tür**

   ODBC istemci için kullanılabilir. Aşağıdaki tabloda açıklandığı gibi kayıt bir dinamik bir anlık görüntü olup olmadığını belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dynaset**|Kayıt kümesi bir dinamik olduğunu belirtir. Bir dinamik sorgulanan veritabanının verilerini dizinli bir görünüm sağlar bir sorgu sonucudur. Bir dinamik özgün verilere yalnızca integral dizin önbelleğe alır ve böylece bir anlık görüntü üzerinde bir performans sunar elde edin. Dizin noktaları doğrudan her kayıt için bir sorgu sonucunda bulunan ve bir kaydı kaldırılırsa, gösterir. Ayrıca güncel bilgilere sorgulanan kayıtlara erişebilirsiniz.|
   |**Anlık Görüntü**|Kayıt kümesi bir anlık görüntü olduğunu belirtir. Bir anlık görüntü sorgu sonucu ve zaman içinde bir noktadaki bir veritabanına görünümüdür. Özgün kayıtlarının değişiklikleri görmek için bir sorgu sonucunda bulunan tüm kayıtları önbelleğe alınır.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
