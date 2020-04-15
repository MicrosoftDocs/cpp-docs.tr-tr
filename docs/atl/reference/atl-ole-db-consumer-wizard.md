---
title: ATL OLE DB Tüketicisi Sihirbazı
ms.date: 07/02/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
ms.openlocfilehash: 16b2863bc3919edadeef29691c4588838010d9dc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81319265"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketicisi Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz Visual Studio 2019 ve sonraki yıllarda kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Bu sihirbaz, belirtilen OLE DB sağlayıcısı aracılığıyla belirtilen veri kaynağına erişmek için gereken veri bağlamaları ile bir OLE DB tüketici sınıfı ayarlar.

> [!NOTE]
> Bu sihirbaz, `Class` ve **.h dosya** alanlarına adlar girmeden önce bir veri kaynağı seçmek için Veri **Kaynağı** düğmesini tıklatmanızı gerektirir.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri Kaynağı**

   **Veri Kaynağı** düğmesi, belirtilen OLE DB sağlayıcısını kullanarak belirtilen veri kaynağını ayarlamanızı sağlar. Bu düğmeyi tıklattığınızda, **Veri Bağlantısı Özellikleri** iletişim kutusu görüntülenir. Bağlantı dizeleri oluşturma ve **Veri Bağlantısı Özellikleri** iletişim kutusu hakkında daha fazla bilgi için Windows SDK belgelerinde Veri Bağlantısı [API Genel Bakışı'na](/previous-versions/windows/desktop/ms718102(v=vs.85)) bakın.

   Aşağıdaki ek bilgiler, **Veri Bağlantısı Özellikleri** iletişim kutusundaki sekmeleri açıklar.

  - **Sağlayıcı** sekmesi

      Veri kaynağına bağlantıyı yönetmek için uygun bir sağlayıcı seçin. Sağlayıcı türü genellikle bağlandığınız veritabanı türüne göre belirlenir. **İleri** düğmesini tıklatın veya **Bağlantı** sekmesini tıklatın.

  - **Bağlantı** sekmesi

      Bu sekmenin içeriği seçtiğiniz sağlayıcıya bağlıdır. Birçok sağlayıcı türü olmasına rağmen, bu bölüm en yaygın iki bağlantıyı kapsar: SQL ve ODBC verileri. Diğerleri burada açıklanan alanlarda benzer varyasyonlar vardır.

      SQL verileri için:

      1. **Bir sunucu adı seçin veya girin:** Ağdaki tüm kayıtlı veri sunucularını görüntülemek için açılır liste menüsünü tıklatın ve birini seçin.

      1. **Sunucuda oturum açmak için bilgileri girin:** Veri sunucusunda oturum açmak için bir kullanıcı adı ve parola girin.

         > [!NOTE]
         > Veri Bağlantısı Özellikleri iletişim kutusunun "Parola kaydetmeye izin ver" özelliğiyle ilgili bir güvenlik sorunu vardır. "Sunucuda oturum açmak için bilgileri girin" adlı iki radyo düğmesi vardır:
         >
         > - **Windows NT tümleşik güvenliğini kullanma**
         > - **Belirli bir kullanıcı adı ve parola kullanma**
         >
         > **Belirli bir kullanıcı adı ve parola kullan'ı**seçerseniz, parolayı kaydetme seçeneğiniz vardır ("Parola kaydetmeye izin verin" onay kutusunu kullanarak); ancak, bu seçenek güvenli değildir. **Windows NT tümleşik güvenlik kullan'ı**seçmeniz önerilir; parolayı şifrelediği için bu seçenek güvenlidir.
         > "Kayda ayırma parolasına izin ver"i seçmek istediğiniz durumlar olabilir. Örneğin, özel bir veritabanı çözümü içeren bir kitaplık yayımlıyorsanız, veritabanına doğrudan erişmemelisiniz, bunun yerine kullanıcıyı doğrulamak için bir orta katman uygulaması kullanmalı (seçtiğiniz kimlik doğrulama düzeni aracılığıyla) ve ardından kullanıcının kullanabileceği veri türlerini sınırlamanız gerekir.

      1. **Sunucudaki veritabanını seçin:** Veri sunucusundaki tüm kayıtlı veritabanlarını görüntülemek için açılır liste menüsünü tıklatın ve birini seçin.

         \-veya -

         **Veritabanı dosyalarını veritabanı adı olarak ekleme:** Veritabanı olarak kullanılacak bir dosya belirtin; açık yol adını girin.

      ODBC verileri için:

      1. **Veri kaynağını belirtin:** Bir veri kaynağı adı veya bağlantı dizesi kullanabilirsiniz.

         **Veri kaynağı adını kullanın:** Bu açılır liste, makinenizde kayıtlı veri kaynaklarını görüntüler. ODBC Veri Kaynağı Yöneticisi'ni kullanarak veri kaynaklarını önceden ayarlayabilirsiniz

         \-veya -

         **Bağlantı dizelerini kullanın:** Daha önce almış olduğunuz bir bağlantı dizesini girin veya **Oluştur** düğmesini tıklatın; **Veri Kaynağı Seç** iletişim kutusu görüntülenir. Bir dosya veya makine veri kaynağı seçin ve **Tamam'ı**tıklatın.

         > [!NOTE]
         > **Sunucu Gezgini'nde**varolan bir bağlantının özelliklerini görüntüleyerek bir bağlantı dizesi edinebilir veya Server **Explorer'da** **Bağlantı Ekle'yi** çift tıklatarak bağlantı oluşturabilirsiniz.

      1. **Sunucuda oturum açmak için bilgileri girin:** Veri sunucusunda oturum açmak için bir kullanıcı adı ve parola girin.

      1. Kullanmak için ilk kataloğu girin.

      1. **Test Bağlantısı'nı**tıklatın ; test başarılı olursa, **Tamam'ı**tıklatın. Değilse, oturum açma bilgilerinizi kontrol edin, başka bir veritabanı deneyin veya başka bir veri sunucusu deneyin.

  - **Gelişmiş** sekme

      **Ağ ayarları:** **Kimliğe bürünme düzeyini** (istemciyi taklit ederken sunucunun kullanmasına izin verilen kimliğe bürünme düzeyi; doğrudan RPC kimliğe bürünme düzeylerine karşılık gelir) ve **Koruma düzeyini** (istemci ve sunucu arasında gönderilen verilerin koruma düzeyi; doğrudan RPC koruma düzeylerine karşılık gelir) belirtin.

      **Diğer:** **Bağlama zaman diliminde,** zaman aramadan önce izin verilen saniye saniye sayısını belirtin. **Access izinlerinde,** veri bağlantısındaki erişim izinlerini belirtin.

      Gelişmiş başlatma özellikleri hakkında daha fazla bilgi için, her belirli OLE DB sağlayıcısıyla sağlanan belgelere bakın.

  - **Tüm** sekme

      Bu sekme, belirttiğiniz veri kaynağı ve bağlantı için başlatma özelliklerinin bir özetini görüntüler. Bu değerleri atayabilirsiniz.

      Ayarlamayı bitirmek için **Tamam**'a tıklayın. **Veritabanı Nesnesini Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan, tüketicinin kullanacağı tabloyu, görünümü veya depolanmış yordamı seçin.

- **Sınıfı**

   Bir veri kaynağı seçtikten sonra, bu kutu, seçtiğiniz tabloya veya depolanan yordamı temel alan varsayılan sınıf adıyla doldurulur (bkz. aşağıdaki **veri kaynağını seç).** Sınıf adını da atabilirsiniz.

- **.h dosyası**

   Bir veri kaynağı seçtikten sonra, bu kutu, seçtiğiniz tabloya veya depolanan yordamı temel alan varsayılan üstbilgi sınıf adıyla doldurulur (bkz. aşağıdaki **veri kaynağını seçin).** Üstbilgi dosyasının adını veya varolan bir üstbilgi dosyasını seçebilirsiniz.

- **Yazarından**

   Bu seçenek, sihirbazın öznitelikleri veya şablon bildirimleri kullanarak tüketici sınıfları oluşturup oluşturmayacağını belirtir. Bu seçeneği seçtiğinizde, sihirbaz şablon bildirimleri yerine öznitelikleri kullanır (bu varsayılan seçenektir). Bu seçeneği seçtiğinizde, sihirbaz öznitelikler yerine şablon bildirimleri kullanır.

  - Bir tüketici **Tablo**Türü seçerseniz, sihirbaz `db_source` `db_table` tablo ve tablo erişimci sınıf bildirimleri oluşturmak `db_column` için öznitelikleri kullanır ve sütun eşlemi oluşturmak için kullanır. **Type** Örneğin, bu haritayı oluşturur:

    ```cpp
    // Inject table class and table accessor class declarations
    [db_source("<initialization_string>"), db_table("dbo.Orders")]
    ...
    // Column map
    [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;
    [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];
    ...
    ```

     tablo ve `CTable` tablo aksesuar ı bildirmek için şablon sınıfını kullanmak yerine, sütun eşlemi oluşturmak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP makroları, bu örnekte olduğu gibi:

    ```cpp
    // Table accessor class
        class COrdersAccessor; // Table class
        class COrders : public CTable<CAccessor<COrdersAccessor>>;
    // ...
    // Column map
        BEGIN_COLUMN_MAP(COrderDetailsAccessor)
            COLUMN_ENTRY_LENGTH_STATUS(1, m_OrderID, m_dwOrderIDLength, m_dwOrderIDStatus)
            COLUMN_ENTRY_LENGTH_STATUS(2, m_CustomerID, m_dwCustomerIDLength, m_dwCustomerIDStatus)
            // ...
        END_COLUMN_MAP()
    ```

  - Bir tüketici **Komut** **Türü** seçerseniz, sihirbaz `db_source` `db_command` kullanır ve `db_column` öznitelikleri ve sütun eşlemi oluşturmak için kullanır. Örneğin, bu haritayı oluşturur:

    ```cpp
    [db_source("<initialization_string>"), db_command("SQL_command")]
    ...
    // Column map using db_column is the same as for consumer type of 'table'
    ```

     komut sınıfındaki komut ve komut erişimci sınıf bildirimlerini kullanmak yerine,örneğin:

    ```cpp
    // Command accessor class:
        class CListOrdersAccessor;
    // Command class:
        class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;
    // ...
    // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
    // for consumer type of 'table'
    ```

     Daha fazla bilgi için [Özniteliklerin Temel Mekaniği](../../windows/basic-mechanics-of-attributes.md) bölümüne bakın.

- **Tür**

   Tüketici sınıfının türetilip türetilmeyeceğini `CTable` veya `CCommand` (varsayılan) alınıp alınmayacağını belirtmek için bu radyo düğmelerinden birini seçin.

  - **Tablo**

      Tablo ve tablo erişimci `CTable` `db_table` sınıf bildirimlerini kullanmak veya oluşturmak istiyorsanız bu seçeneği belirleyin.

  - **Komut**

      Komut ve komut erişimci `CCommand` `db_command` sınıf bildirimlerini kullanmak veya oluşturmak istiyorsanız bu seçeneği belirleyin. Bu varsayılan seçimdir.

- **Destek**

   Tüketicide desteklenecek güncelleştirme türlerini belirtmek için onay kutularını seçin (varsayılan değer yok). Aşağıdakilerin her biri [DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892(v=vs.85)) ve özellik kümesi haritasında [DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676(v=vs.85)) için uygun girişleri ayarlar.

  - **Değiştir**

      Satır kümesindeki satır verilerinin tüketici desteğinin güncelleştirmelerini belirtir.

  - **Ekle**

      Satır kümesine satır ekleme tüketici desteği belirtir.

  - **Sil**

      Tüketici desteğinin satır kümesinden satırların silinmesini belirtir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL OLE DB Tüketici](../../atl/reference/adding-an-atl-ole-db-consumer.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Bağlantı Dizeleri ve Veri Bağlantıları (OLE DB)](/previous-versions/windows/desktop/ms718376(v=vs.85))
