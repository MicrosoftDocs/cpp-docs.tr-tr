---
title: ATL OLE DB Tüketici Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
- connection strings [C++], OLE DB consumers
- ATL OLE DB Consumer Wizard
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0d51569eaece5e3fac59c7cc2ff82a8454a5f959
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32364956"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketici Sihirbazı
Bu sihirbaz bir OLE DB Tüketici sınıfı veri bağlamalarla belirtilen OLE DB sağlayıcısı ile belirtilen veri kaynağına erişmek için gerekli ayarlar.  
  
> [!NOTE]
>  Bu Sihirbazı'nı tıklatın gerektirir **veri kaynağı** adlarında girmeden önce bir veri kaynağı seçmek için düğmesini `Class` ve **.h dosyası** alanları.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Veri kaynağı**  
 **Veri kaynağı** düğmesi belirtilen OLE DB Sağlayıcısı'nı kullanarak belirtilen veri kaynağını ayarlamanıza imkan sağlar. Bu düğmeye tıkladığınızda **veri bağlantısı özelliklerini** iletişim kutusu görüntülenir. Bağlantı dizeleri oluşturma hakkında daha fazla bilgi ve **veri bağlantısı özelliklerini** iletişim kutusu, bkz: [veri bağlantısı API genel bakış](https://msdn.microsoft.com/library/ms718102.aspx) Windows SDK belgelerinde.  
  
> [!NOTE]
>  Önceki sürümlerde, SHIFT tuşunu **veri kaynağı** düğmesi, bir veri bağlantısı (UDL) dosyasını seçmek izin vermek için bir dosya Aç iletişim kutusu açılır. Bu işlev artık desteklenmemektedir.  
  
 İletişim kutusu dört sekme bulunur:  
  
- **Sağlayıcı** sekmesi  
  
- **Bağlantı** sekmesi  
  
- **Gelişmiş** sekmesi  
  
- **Tüm** sekmesi  
  
     Aşağıdaki ek bilgileri sekmeleri açıklar **veri bağlantısı özelliklerini** iletişim kutusu.  
  
     Tıklatın **Tamam** tamamlamak için. **Veritabanı nesnesi Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan, tablo, görünüm veya tüketici kullanacağı saklı yordam seçin.  
  
 **Sağlayıcı**  
     Veri kaynağı bağlantısı yönetmek için uygun bir sağlayıcı seçin. Sağlayıcı türünü genellikle bağlanmakta olduğunuz veritabanı türüne göre belirlenir. Tıklatın `Next` düğmesini tıklatın veya tıklatın **bağlantı** sekmesi.  
  
 **Bağlantı**  
     Bu sekme içeriğini seçtiğiniz sağlayıcısına bağlıdır. Sağlayıcıları türlerde olsa da, bu bölüm iki bağlantılarında kapsar en yaygın: SQL ve ODBC veri. Burada açıklanan alanları benzer çeşidi diğerleri ise.  
  
     SQL veri için:  
  
    1. **Bir sunucu adı seçin veya girin:** ağ üzerindeki tüm kayıtlı veri sunucuları görüntülemek için aşağı açılır menüsünü tıklatın ve seçin.  
  
    2. **Sunucuya oturum açmak için bilgileri girin:** bir kullanıcı adı ve veri sunucusuna oturum açmak için parola girin.  
  
    3. **Sunucudaki veritabanını seçin:** veri sunucusundaki tüm kayıtlı veritabanlarını görüntülemek için aşağı açılır menüsünü tıklatın ve seçin.  
  
         -veya-  
  
 **Bir veritabanı dosyası bir veritabanı adı olarak ekleme:** açık yol adını girin; veritabanı olarak kullanılacak bir dosya belirtin.  
  
        > [!NOTE]
        >  There is a security problem with the "Allow saving of password" feature of the Data Link Properties dialog box. In "Enter information to log on to the server," there are two radio buttons:  
  
 **Windows NT tümleşik güvenliğini kullan**  
  
 **Belirli bir kullanıcı adı ve parolayı kullanın**  
  
         If you select **Use a specific user name and password**, you have the option of saving the password (using the check box for "Allow saving password"); however, this option is not secure. It is recommended that you select **Use Windows NT integrated security**; this option is secure because it encrypts the password.  
  
         There might be situations in which you want to select "Allow saving password." For example, if you are releasing a library with a private database solution, you should not access the database directly but instead use a middle-tier application to verify the user (through whatever authentication scheme you choose) and then limit the sort of data available to the user.  
  
         For ODBC data:  
  
         1. **Specify the source of data:** You can use a data source name or a connection string.  
  
 **Kullanılacak veri kaynağı adı:** makinenizde kayıtlı veri kaynaklarına Bu aşağı açılan listede görüntülenir. ODBC Veri Kaynağı Yöneticisi'ni kullanarak önceden veri kaynakları ayarlayabilirsiniz- veya -**bağlantı dizesi kullanın:** ya da zaten aldıysanız veya tıklatın bir bağlantı dizesi girin **yapı** düğmesini; **Veri kaynağı Seç** iletişim kutusu görüntülenir. Bir dosya veya makine veri kaynağını seçin ve tıklatın **Tamam**.  
  
        > [!NOTE]
        >  You can obtain a connection string by viewing the properties of an existing connection in Server Explorer, or you can create a connection by double-clicking **Add Connection** in Server Explorer.  
  
         2. **Enter information to log on to the server:** Enter a user name and password to log on to the data server.  
  
         3. Enter the initial catalog to use.  
  
         4. Click **Test Connection**; if the test succeeds, click **OK**. If not, check your logon information, try another database, or try another data server.  
  
 **Gelişmiş**  
 **Ağ ayarları:** belirt **kimliğe bürünme düzeyi** (istemci belirlerken kullanmasına izin verilen; doğrudan RPC kimliğe bürünme düzeyi için karşılık gelen sunucu kimliğe bürünme düzeyi) ve  **Koruma düzeyi** (istemci ve sunucu; arasında veri koruma düzeyiyle gönderilen RPC koruma düzeyleri doğrudan karşılık gelir).  
  
 **Diğer:** içinde **bağlantı zaman aşımı**, boşta kalma süresi bir zaman aşımı oluşmadan önce izin verilen saniye sayısını belirtin. İçinde **erişim izinlerini**, veri bağlantısı erişim izinleri belirtin.  
  
     Gelişmiş başlatma özellikleri hakkında daha fazla bilgi için her belirli OLE DB sağlayıcısı ile sağlanan belgelere bakın.  
  
 **Tüm**  
     Bu sekme, belirttiğiniz bağlantı ve veri kaynağı için başlatma özellikleri özetini görüntüler. Bu değerleri düzenleyebilirsiniz.  
  
     Tıklatın **Tamam** tamamlamak için. **Veritabanı nesnesi Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan, tablo, görünüm veya tüketici kullanacağı saklı yordam seçin.  
  
 `Class`  
 Bir veri kaynağını seçtikten sonra bu kutu tablo veya seçtiğiniz saklı yordam dayalı bir varsayılan sınıf adını doldurulur (bkz **bir veri kaynağı Seç** aşağıda). Sınıf adı düzenleyebilirsiniz.  
  
 **.h dosyası**  
 Bir veri kaynağını seçtikten sonra bu kutu tablo veya seçtiğiniz saklı yordam dayalı bir varsayılan üstbilgisi sınıf adı doldurulur (bkz **bir veri kaynağı Seç** aşağıda). Üstbilgi dosyanın adını düzenleyin veya varolan bir üstbilgi dosyası seçin.  
  
 **Öznitelikli**  
 Bu seçenek, sihirbaz öznitelikleri veya şablon bildirimleri kullanarak tüketici sınıflar oluşturacak olup olmadığını belirtir. Bu seçeneği seçtiğinizde, sihirbaz öznitelikleri şablon bildirimleri yerine (Bu varsayılan seçenektir) kullanır. Bu seçeneğin işaretini kaldırın, sihirbazın şablon bildirimleri yerine özniteliklerini kullanır.  
  
-   Bir tüketici seçerseniz **türü** tablonun Sihirbazı'nı kullanan `db_source` ve **db_table** tablosu ve tablo erişimcisi sınıf bildirimleri oluşturmak için öznitelikleri ve kullandığı **db_column**  sütun eşlemesi, örneğin oluşturmak için:  
  
 ``` 
 // Inject table class and table accessor class declarations  
 [db_source("<initialization_string>"), db_table("dbo.Orders")]  
 ... 
 // Column map  
 [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;  
 [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];  
 ...  
 ```  
  
     yerine `CTable` tablosu ve tablo erişimci sınıfı ve örneğin sütun eşlemesi oluşturmak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP makroları bildirmek için Şablon sınıfı:  
  
 ``` 
 // Table accessor class  
    class COrdersAccessor; *// Table class  
    class COrders : public CTable<CAccessor<COrdersAccessor>>;  
 ... 
 // Column map  
    BEGIN_COLUMN_MAP(COrderDetailsAccessor) 
    COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)  
    COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)  
 ...  
    END_COLUMN_MAP() 
 ```  
  
-   Bir tüketici seçerseniz **türü** komutu, Sihirbazı'nı kullanan `db_source` ve **db_command** öznitelikleri ve kullandığı **db_column** sütun eşlemesi, örneğin oluşturmak için :  
  
 ```  
 [db_source("<initialization_string>"), db_command("SQL_command")]  
 ... 
 // Column map using db_column is the same as for consumer type of 'table'  
 ```  
  
     komut ve komut erişimcisi sınıf bildirimleri komutu sınıf .h dosyasında, örneğin kullanmak yerine:  
  
 ```  
    Command accessor class:  
    class CListOrdersAccessor;  
    Command class:  
    class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;  
 ... 
 // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
 // for consumer type of 'table'  
 ```  
  
 Bkz: [temel öznitelikleri mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.  
  
 **Türü**  
 Tüketici sınıfı öğesinden türetilen olup olmadığını belirtmek için bu radyo düğmeleri birini `CTable` veya `CCommand` (varsayılan).  
  
 **Tablo**  
 Kullanmak istiyorsanız bu seçeneği `CTable` veya **db_table** tablosu ve tablo erişimcisi sınıf bildirimleri oluşturmak için.  
  
 **komutu**  
 Kullanmak istiyorsanız bu seçeneği `CCommand` veya **db_command** komut ve komut erişimcisi sınıf bildirimleri oluşturmak için. Bu varsayılan seçimdir.  
  
 **Destek**  
 (Varsayılan, Yok'tur) tüketicideki desteklenmesi için güncelleştirmeleri türlerini belirtmek için onay kutularını seçin. Aşağıdakilerin her biri ayarlayacaktır [DBPROP_IRowsetChange](https://msdn.microsoft.com/library/ms715892.aspx) ve uygun girişleri [DBPROP_UPDATABILITY](https://msdn.microsoft.com/library/ms722676.aspx) eşleme özelliğini ayarlayın.  
  
 **değiştirme**  
 Tüketici satır kümesinde satır veri güncelleştirmelerini destekleyen belirtir.  
  
 **Ekle**  
 Tüketici satır satır ekleme destekleyip desteklemediğini belirtir.  
  
 **Sil**  
 Tüketici satır satırları silinmesini destekleyip desteklemediğini belirtir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL OLE DB Tüketicisi](../../atl/reference/adding-an-atl-ole-db-consumer.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Bağlantı dizeleri ve veri bağlantıları (OLE DB)](https://msdn.microsoft.com/library/ms718376.aspx)
