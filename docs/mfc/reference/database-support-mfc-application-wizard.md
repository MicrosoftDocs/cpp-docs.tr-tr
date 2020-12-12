---
description: 'Daha fazla bilgi edinin: veritabanı desteği, MFC Uygulama Sihirbazı'
title: Veritabanı Desteği, MFC Uygulama Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.exe.database
helpviewer_keywords:
- MFC Application Wizard, database support
ms.assetid: 9ddf4558-fd41-4ac7-8d9b-c93d9c68ab59
ms.openlocfilehash: 4c6f980155e980c772b5ee78f83c80a236998b91
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220311"
---
# <a name="database-support-mfc-application-wizard"></a>Veritabanı Desteği, MFC Uygulama Sihirbazı

Bu sayfa, projeniz için veritabanı desteğinin (Ayrıca gerekirse bir veri kaynağı) düzeyini belirtmenize imkan tanıyan seçenekler sağlar.

- **Veritabanı desteği**

   Projeniz için veritabanı desteğinin düzeyini ayarlar.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Hiçbiri**|Veritabanı desteği sağlamaz. Bu varsayılan seçenektir.|
   |**Yalnızca üst bilgi dosyaları**|Uygulamanız için temel veritabanı desteği düzeyini sağlar. **İstemci türü** altında ODBC desteği ' ni SEÇERSENIZ, MFC Uygulama Sihirbazı projenize Afxdb. H başlık dosyasını içerir. Bağlantı kitaplıklarını ekler, ancak veritabanına özgü hiçbir sınıf oluşturmaz. Kayıt kümelerini daha sonra oluşturabilir ve kayıtları incelemek ve güncelleştirmek için kullanabilirsiniz. **İstemci türü** altında OLE DB desteği ' ni seçerseniz, aşağıdaki üst bilgi dosyaları bulunur: ATLBASE. H AFXOLEDB. H ATLPLUS. Olsun|
   |**Dosya desteği olmadan veritabanı görünümü**|Veritabanı üst bilgi dosyalarını, bağlantı kitaplıklarını, bir kayıt görünümünü ve bir kayıt kümesini içerir. ( [Uygulama türü](../../mfc/reference/application-type-mfc-application-wizard.md) sayfasında yalnızca **belge/görünüm mimarisi desteği** seçeneğinin seçildiği uygulamalar için kullanılabilir.) Bu seçenek belge desteğini içerir ancak serileştirme desteği yoktur. Bir veritabanı görünümü eklemeyi seçerseniz, verilerin kaynağını belirtmeniz gerekir.|
   |**Dosya destekli veritabanı görünümü**|Veritabanı üst bilgi dosyalarını, bağlantı kitaplıklarını, bir kayıt görünümünü ve bir kayıt kümesini içerir. ( **Uygulama türü** sayfasında yalnızca **belge/görünüm mimarisi desteği** seçeneğinin seçildiği uygulamalar için kullanılabilir.) Bu seçenek, örneğin, bir kullanıcı profili dosyasını güncelleştirmek için kullanabileceğiniz belge serileştirmesini destekler. Veritabanı uygulamaları genellikle dosya başına değil, kayıt başına temelinde çalışır ve bu nedenle serileştirme gerektirmez. Ancak, serileştirme için özel bir kullanıma sahip olabilirsiniz. Bir veritabanı görünümü eklemeyi seçerseniz, verilerin kaynağını belirtmeniz gerekir.|

   > [!NOTE]
   > **Veritabanı desteği** altında, **dosya desteği olmadan veritabanı görünümü** veya **Dosya desteğiyle veritabanı görünümü** seçeneğini belirlerseniz, görünüm sınıfı elde etme, **istemci türü** seçiminize bağlı olarak aşağıdaki gibi farklılık gösterir:

  - **İstemci türü** altında **ODBC** ' yi seçerseniz, uygulamanın görünüm sınıfı [CRecordView](../../mfc/reference/crecordview-class.md)'den türetilir. Bu sınıf, MFC Uygulama Sihirbazı 'nın sizin için de oluşturduğu bir [CRecordset](../../mfc/reference/crecordset-class.md)ile türetilmiş sınıf ile ilişkilendirilir. Bu seçenek, kayıt görünümünün kayıt kümesi aracılığıyla kayıtları görüntülemek ve güncelleştirmek için kullanıldığı form tabanlı bir uygulama sağlar.

  - **İstemci türü** altında **OLE DB** ' yi seçerseniz, görünüm sınıfı [COleDBRecordView](../../mfc/reference/coledbrecordview-class.md)öğesinden türetilir ve bir [CTable](../../data/oledb/ctable-class.md) veya [CCommand](../../data/oledb/ccommand-class.md)ile türetilmiş sınıf ile ilişkilendirilir.

- **İstemci türü**

   Projenizin OLE DB veya ODBC sınıfları kullanıp kullanmadığını belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**OLE DB**|Bu seçenek belirlendiğinde, veri **kaynağı** düğmesine tıklamak **veri bağlantısı özellikleri** sihirbazını çağırır ve bir OLE DB veri kaynağına bağlantı oluşturmanıza yardımcı olur.|
   |**ODBC**|Bu seçenek belirlendiğinde, **veri kaynağı** düğmesine TıKLADıĞıNıZDA bir ODBC veri kaynağıyla bağlantı oluşturmanıza yardımcı olması Için **veri kaynağı seçme** Sihirbazı ' nı çağırır.|

- **Veri Kaynağı**

   > [!NOTE]
   > ATL OLE DB Tüketici Sihirbazı ve MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](../../data/oledb/creating-a-consumer-without-using-a-wizard.md).

   Belirtilen sürücüyü veya sağlayıcıyı ve veritabanını kullanarak bir veri kaynağı ayarlamak için **veri kaynağı** düğmesine tıklayın. **İstemci türü** seçeneğinde OLE DB ' yi seçtiyseniz, bu düğme **veri bağlantısı özellikleri** iletişim kutusunu görüntüler. **İstemci türü** seçeneğinde ODBC ' yi seçtiyseniz, bu düğme **veri kaynağı seç** iletişim kutusunu sağlar. Bu seçenek yalnızca uygulamanıza bir veritabanı görünümü eklemeyi tercih ediyorsanız kullanılabilir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Veri bağlantısı özellikleri** (OLE DB)|Belirtilen OLE DB sağlayıcıyı kullanarak belirtilen veri kaynağını oluşturur. OLE DB sağlayıcıyı, verilerin konumunu, veri kaynağını, oturum açma KIMLIĞINI ve (isteğe bağlı olarak) bir parolayı belirtmeniz gerekir. Bu iletişim kutusu hakkında daha fazla bilgi için bkz. [ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md)'nda **veri kaynağı** .|
   |**Veri kaynağını seçin** (ODBC)|Belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını oluşturur. Veri kaynağı için bir tablo seçmek üzere bir veri kaynağı adı seçmeniz gerekir. Sihirbaz, tablonun tüm sütunlarını, bir türetilmiş sınıfın üye değişkenlerine bağlar `CRecordset` . Bu iletişim kutusu hakkında daha fazla bilgi için bkz. [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/mfc-odbc-consumer-wizard.md)'nda **veri kaynağı** .|

- **Öznitelikli veritabanı sınıfı oluştur**

   Yalnızca OLE DB istemcisi için kullanılabilir. Oluşturulan projede veritabanı sınıflarının öznitelikleri kullanıp kullanmadığını belirtir.

- **Tüm sütunları bağla**

   Yalnızca ODBC istemcisi için kullanılabilir. Seçili tablodaki tüm sütunların bağlanıp bağlanmadığını belirtir. Bu kutuyu seçerseniz, tüm sütunlar bağlanır; Bu kutuyu seçmezseniz, hiçbir sütun bağlı değildir ve bunları kayıt kümesi sınıfında el ile bağlamanız gerekir.

- **Tür**

   Yalnızca ODBC istemcisi için kullanılabilir. Aşağıdaki tabloda açıklandığı gibi, kayıt kümesinin bir değişken kümesi mi yoksa anlık görüntü mi olduğunu belirtir.

   |Seçenek|Açıklama|
   |------------|-----------------|
   |**Dynaset**|Kayıt kümesinin bir Dynaset olduğunu belirtir. DYNASET, sorgulanan veritabanının verilerine dizinli bir görünüm sağlayan sorgunun sonucudur. DYNASET, özgün verilerin yalnızca bir integral dizinini önbelleğe alır ve bu nedenle bir anlık görüntü üzerinde performans kazancı sağlar. Dizin, bir sorgunun sonucu olarak bulunan her bir kayda doğrudan işaret eder ve bir kaydın kaldırılıp kaldırılmadığını gösterir. Ayrıca, sorgulanan kayıtlardaki güncelleştirilmiş bilgilere erişebilirsiniz.|
   |**Görüntüye**|Kayıt kümesinin bir anlık görüntü olduğunu belirtir. Anlık görüntü, bir sorgunun sonucudur ve tek seferde bir veritabanında görüntülenir. Sorgunun bir sonucu olarak bulunan tüm kayıtlar önbelleğe alınır, bu nedenle özgün kayıtlarda herhangi bir değişiklik görmezsiniz.|

## <a name="see-also"></a>Ayrıca bkz.

[MFC Uygulama Sihirbazı](../../mfc/reference/mfc-application-wizard.md)
