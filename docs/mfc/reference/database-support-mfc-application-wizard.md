---
title: Veritabanı desteği, MFC Uygulama Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.exe.database
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 86c6cd679b69bf84504d6735ca39d572bd48ff07
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="database-support-mfc-application-wizard"></a>Veritabanı Desteği, MFC Uygulama Sihirbazı
Bu sayfayı veritabanının düzeyini belirtmenize olanak sağlayan seçenekler sunar (veri kaynağı, gerekirse) projeniz için destek.  
  
 **Veritabanı desteği**  
 Projeniz için veritabanı desteği düzeyini ayarlar.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Yok**|Hiçbir veritabanı desteği sağlar. Varsayılan seçenek budur.|  
|**Yalnızca üst bilgi dosyaları**|Uygulamanız için temel düzeyde bir veritabanı desteği sağlar. ODBC desteği altında seçerseniz **istemci türü**, MFC Uygulama Sihirbazı'nı projenizde AFXDB üstbilgi dosyası içerir. H. Bağlantı kitaplıkları ekler, ancak herhangi bir veritabanına özel sınıf oluşturmaz. Daha sonra kayıt kümeleri oluşturabilir ve bunları inceleyin ve kayıtlarını güncelleştirmek için kullanın. OLE DB desteği altında seçerseniz **istemci türü**, aşağıdaki üst bilgi dosyaları dahil edilen: ATLBASE. H AFXOLEDB. H ATLPLUS. H|  
|**Dosya desteği olmayan veritabanı görünümü**|Veritabanı başlık dosyalarını, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca uygulamalarla kullanılabilir **belge/görünüm mimarisi desteği** seçeneğe [uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfası.) Bu seçenek, belge desteği, ancak hiçbir serileştirme desteği içerir. Bir veritabanı görünümü dahil etmek isterseniz, veri kaynağı olarak belirtmeniz gerekir.|  
|**Dosya desteği olan veritabanı görünümü**|Veritabanı başlık dosyalarını, bağlantı kitaplıkları, kayıt görünümü ve bir kayıt kümesi içerir. (Yalnızca uygulamalarla kullanılabilir **belge/görünüm mimarisi desteği** seçeneğe **uygulama türü** sayfası.) Bu seçenek, örneğin, bir kullanıcı profili dosyasını güncelleştirmek için kullanabileceğiniz Belge Serileştirme destekler. Bir dosya başına üzerinde temel ve bu nedenle serileştirme gerekmez yerine veritabanı uygulamaları genellikle bir kayıt başına temelinde çalışır. Bununla birlikte, serileştirme için özel bir kullanım olabilir. Bir veritabanı görünümü dahil etmek isterseniz, veri kaynağı olarak belirtmeniz gerekir.|  
  
> [!NOTE]
>  Altında **veritabanı desteği**, ya da seçerseniz **veritabanı görünümü dosya desteği olmadan** veya **veritabanı dosya desteği görünümüyle**, görünüm sınıf türetme, bağlı olarak farklılık gösterir üzerinde **istemci türü** şekilde Seçimi:  
  
-   Seçerseniz **ODBC** altında **istemci türü**, uygulamanın görünüm sınıfı türetilen sonra [CRecordView](../../mfc/reference/crecordview-class.md). Bu sınıf ile ilişkili bir [CRecordset](../../mfc/reference/crecordset-class.md)-türetilen MFC Uygulama Sihirbazı'nı da sizin için oluşturur sınıfı. Bu seçenek, kayıt kümesi aracılığıyla kayıtları görüntülemek ve güncelleştirmek için kayıt görünümü kullanıldığı form tabanlı bir uygulama sağlar.  
  
-   Seçerseniz **OLE DB** altında **istemci türü**, görünüm sınıfı türetilen sonra [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md), ve ile ilişkili bir [CTable](../../data/oledb/ctable-class.md) veya [CCommand](../../data/oledb/ccommand-class.md)-türetilmiş sınıf.  
  
 **İstemci türü**  
 Projenizi OLE DB veya ODBC sınıfları kullanıp kullanmadığını belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**OLE DB**|Bu seçenek belirlendiğinde, tıklatarak **veri kaynağı** düğmesi çağırır **veri bağlantısı özelliklerini** bir OLE DB veri kaynağı için bir bağlantı oluşturmanıza yardımcı olması için Sihirbazı.|  
|**ODBC**|Bu seçenek belirlendiğinde, tıklatarak **veri kaynağı** düğmesi çağırır **veri kaynağı Seç** bir ODBC veri kaynağı için bir bağlantı oluşturmanıza yardımcı olması için Sihirbazı.|  
  
 **Veri kaynağı**  
 Tıklatın **veri kaynağı** belirtilen sürücü ya da sağlayıcı ve veritabanını kullanarak bir veri kaynağı ayarlamak için düğmeyi. OLE DB'de seçtiyseniz **istemci türü** seçeneği, bu düğme görüntüler **veri bağlantısı özelliklerini** iletişim kutusu. ODBC seçtiyseniz **istemci türü** seçeneği, bu düğme sağlar **veri kaynağı Seç** iletişim kutusu. Bu seçenek, bir veritabanı görünümü uygulamanıza dahil seçerseniz kullanılabilir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Veri bağlama özellikleri** (OLE DB)|Belirtilen OLE DB Sağlayıcısı'nı kullanarak belirtilen veri kaynağı oluşturur. OLE DB sağlayıcısı, verileri, veri kaynağı, oturum açma kimliği ve (isteğe bağlı) parola konumunu belirtmelisiniz. Bu iletişim kutusu hakkında daha fazla bilgi için bkz: **veri kaynağı** içinde [ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md).|  
|**Veri kaynağını seçin** (ODBC)|Belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağı oluşturur. Veri kaynağı için bir tablo seçmek için bir veri kaynağı adı seçmeniz gerekir. Sihirbaz tablodaki tüm sütunların için üye değişkenleri bağlar bir `CRecordset`-türetilmiş sınıf. Bu iletişim kutusu hakkında daha fazla bilgi için bkz: **veri kaynağı** içinde [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/mfc-odbc-consumer-wizard.md).|  
  
> [!NOTE]
>  Önceki sürümlerde, SHIFT tuşunu **veri kaynağı** düğmesi, bir veri bağlantısı (UDL) dosyasını seçmek izin vermek için bir dosya Aç iletişim kutusu açılır. Bu işlev artık desteklenmemektedir.  
  
 **Öznitelikli veritabanı sınıfı oluşturma**  
 OLE DB istemci yalnızca için kullanılabilir. Veritabanı sınıfları oluşturulan projesinde öznitelikleri kullanıp kullanmadığını belirtir.  
  
 **Tüm sütunları bağlayın**  
 Yalnızca ODBC istemcisi için kullanılabilir. Seçili tablodaki tüm sütunları bağlı olup olmadığını belirtir. Bu kutusunu seçerseniz, tüm sütunlar bağlıdır; Bu kutuyu işaretlemeyin, hiçbir sütun bağlı olan ve, bunları el ile kayıt kümesi sınıfında bağlamanız gerekir.  
  
 **Türü**  
 Yalnızca ODBC istemcisi için kullanılabilir. Aşağıdaki tabloda açıklandığı gibi kayıt kümesinin bir dynaset veya bir anlık görüntü olup olmadığını belirtir.  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|**Dynaset**|Kayıt kümesi bir dynaset olduğunu belirtir. Bir dinamik bir dizini oluşturulmuş görünüm sorgulanan veritabanının veri sağlayan bir sorgu sonucudur. Dinamik küme özgün veriler yalnızca bir tam sayı dizine önbelleğe alır ve bu nedenle bir anlık görüntü üzerinde bir performans sunar elde. Dizin noktalarına doğrudan her kayıt bir sorgu sonucunda bulunan ve bir kaydı kaldırılırsa, gösterir. Ayrıca güncelleştirilmiş bilgilere sorgulanan kayıtları erişebilirsiniz.|  
|Anlık Görüntü|Kayıt kümesi bir anlık görüntü olduğunu belirtir. Bir anlık görüntü sorgu sonucu ve bir noktada bir veritabanı içine bir görünüm saattir. Sorgu sonucu olarak bulunan tüm kayıtları önbelleğe alınmış özgün kayıtlarının değişiklikleri görmezsiniz.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
