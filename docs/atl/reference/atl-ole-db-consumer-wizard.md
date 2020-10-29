---
title: ATL OLE DB Tüketicisi Sihirbazı
ms.date: 07/02/2019
helpviewer_keywords:
- ATL projects, adding ATL OLE DB consumers
ms.assetid: dcb68ed1-2224-422f-9f7b-108a74864204
ms.openlocfilehash: 490335f1f61987fc6e5b0b3806ee8e39c82f336f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923748"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketicisi Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bu sihirbaz, belirtilen OLE DB sağlayıcısı aracılığıyla belirtilen veri kaynağına erişmek için gereken veri bağlamalarını içeren bir OLE DB tüketici sınıfı ayarlar.

> [!NOTE]
> Bu sihirbaz, **Data Source** `Class` ve **. h dosya** alanlarına ad girmeden önce bir veri kaynağı seçmek için veri kaynağı düğmesine tıklamaya gerek duyar.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri Kaynağı**

   **Veri kaynağı** düğmesi belirtilen OLE DB sağlayıcıyı kullanarak belirtilen veri kaynağını ayarlamanıza olanak sağlar. Bu düğmeye tıkladığınızda, **veri bağlantısı özellikleri** iletişim kutusu görüntülenir. Bağlantı dizeleri oluşturma ve **veri bağlantısı özellikleri** iletişim kutusu hakkında daha fazla bilgi için, Windows SDK belgelerinde [veri bağlantısı API 'sine genel bakış](/previous-versions/windows/desktop/ms718102(v=vs.85)) bölümüne bakın.

   Aşağıdaki ek bilgiler, **veri bağlantısı özellikleri** iletişim kutusundaki sekmeleri açıklar.

  - **Sağlayıcı** sekmesi

      Veri kaynağıyla bağlantıyı yönetmek için uygun bir sağlayıcı seçin. Sağlayıcının türü genellikle bağlanmakta olduğunuz veritabanı türüne göre belirlenir. **İleri** düğmesine tıklayın veya **bağlantı** sekmesine tıklayın.

  - **Bağlantı** sekmesi

      Bu sekmenin içeriği, seçtiğiniz sağlayıcıya bağlıdır. Birçok sağlayıcı türü olsa da, bu bölümde en yaygın iki SQL ve ODBC verileri için bağlantılar ele alınmaktadır. Diğerleri, burada açıklanan alanlarda benzer çeşitlemelerdir.

      SQL verileri için:

      1. **Sunucu adını seçin veya girin:** Ağ üzerindeki tüm kayıtlı veri sunucularını göstermek için açılan liste menüsüne tıklayın ve bir tane seçin.

      1. **Sunucuda oturum açmak için bilgileri girin:** Veri sunucusunda oturum açmak için bir Kullanıcı adı ve parola girin.

         > [!NOTE]
         > Veri bağlantısı özellikleri iletişim kutusunun "Parola kaydetmeye Izin ver" özelliği ile bir güvenlik sorunu var. "Sunucuda oturum açmak için bilgileri girin," iki radyo düğmesi vardır:
         >
         > - **Windows NT tümleşik güvenliğini kullan**
         > - **Belirli bir Kullanıcı adı ve parola kullan**
         >
         > **Belirli bir Kullanıcı adı ve parola kullan** ' ı seçerseniz, parolayı kaydetme seçeneğiniz vardır ("Parola kaydetmeye izin ver" onay kutusunu kullanarak); Ancak, bu seçenek güvenli değildir. **WINDOWS NT tümleşik güvenliği kullan** ' ı seçmeniz önerilir. parolayı şifreleyen için bu seçenek güvenlidir.
         > "Parola kaydetmeye Izin ver" i seçmek istediğiniz durumlar olabilir. Örneğin, özel bir veritabanı çözümüne sahip bir kitaplık yayınlarsanız, veritabanına doğrudan erişmemelisiniz, bunun yerine kullanıcının doğrulanması için bir orta katmanlı uygulama kullanın (seçtiğiniz kimlik doğrulama şeması aracılığıyla) ve ardından Kullanıcı tarafından kullanılabilen veri sıralamasını sınırlayabilirsiniz.

      1. **Sunucudaki veritabanını seçin:** Tüm kayıtlı veritabanlarını veri sunucusunda göstermek için aşağı açılan liste menüsüne tıklayıp bir tane seçin.

         \- veya

         Veritabanı **adı olarak bir veritabanı dosyası ekleyin:** Veritabanı olarak kullanılacak bir dosya belirtin; açık yol adını girin.

      ODBC verileri için:

      1. **Veri kaynağını belirtin:** Bir veri kaynağı adı veya bağlantı dizesi kullanabilirsiniz.

         **Veri kaynağı adını kullan:** Bu açılan liste, makinenizde kayıtlı veri kaynaklarını görüntüler. ODBC veri kaynağı Yöneticisi 'ni kullanarak veri kaynaklarını zamandan önce ayarlayabilirsiniz

         \- veya

         **Bağlantı dizesi kullan:** Zaten edindiğiniz bir bağlantı dizesi girin veya **Oluştur** düğmesine tıklayın; **veri kaynağı seç** iletişim kutusu görüntülenir. Bir dosya veya makine veri kaynağı seçin ve **Tamam** ' a tıklayın.

         > [!NOTE]
         > **Sunucu Gezgini** var olan bir bağlantının özelliklerini görüntüleyerek bir bağlantı dizesi elde edebilir veya **Sunucu Gezgini** **bağlantı ekle** ' ye çift tıklayarak bir bağlantı oluşturabilirsiniz.

      1. **Sunucuda oturum açmak için bilgileri girin:** Veri sunucusunda oturum açmak için bir Kullanıcı adı ve parola girin.

      1. Kullanılacak başlangıç kataloğunu girin.

      1. **Bağlantıyı Sına** ' ya tıklayın. sınama başarılı olursa **Tamam** ' a tıklayın. Aksi takdirde, oturum açma bilgilerinizi denetleyin, başka bir veritabanı deneyin veya başka bir veri sunucusu deneyin.

  - **Gelişmiş** sekmesi

      **Ağ ayarları:** **Kimliğe bürünme düzeyini** (istemcinin kimliğe bürünme sırasında sunucunun kullanmasına izin verilen kimliğe bürünme düzeyi; doğrudan RPC kimliğe bürünme düzeylerine karşılık gelir) ve **koruma düzeyini** (istemci ve sunucu arasında gönderilen verilerin koruma DÜZEYI), doğrudan RPC koruma düzeylerine karşılık gelir.

      **Diğer:** **Bağlantı zaman aşımı** ' de, bir zaman aşımı gerçekleşmeden önce izin verilen sürenin saniye sayısını belirtin. **Erişim izinleri** ' nde, veri bağlantısında erişim izinlerini belirtin.

      Gelişmiş başlatma özellikleri hakkında daha fazla bilgi için, her belirli OLE DB sağlayıcısıyla birlikte sunulan belgelere bakın.

  - **Tümü** sekmesi

      Bu sekme, belirttiğiniz veri kaynağı ve bağlantı için başlatma özelliklerinin bir özetini görüntüler. Bu değerleri düzenleyebilirsiniz.

      Ayarlamayı bitirmek için **Tamam** 'a tıklayın. **Veritabanı nesnesi Seç** iletişim kutusu görünür. Bu iletişim kutusunda, tüketicinin kullanacağı tablo, görünüm veya saklı yordamı seçin.

- **Sınıf**

   Bir veri kaynağı seçtikten sonra, bu kutu seçtiğiniz tabloya veya saklı yordama göre varsayılan bir sınıf adı ile doldurulur (bkz. aşağıdan **bir veri kaynağı seçme** ). Sınıf adını düzenleyebilirsiniz.

- **. h dosyası**

   Bir veri kaynağı seçtikten sonra, bu kutu seçtiğiniz tabloya veya saklı yordama göre varsayılan bir başlık sınıfı adı ile doldurulur (bkz. aşağıdan **bir veri kaynağı seçme** ). Üst bilgi dosyasının adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **İlişkilendirilmesi**

   Bu seçenek, sihirbazın öznitelikler veya şablon bildirimleri kullanarak tüketici sınıfları oluşturup oluşturmayacağını belirtir. Bu seçeneği belirlediğinizde, sihirbaz şablon bildirimleri yerine öznitelikleri kullanır (Bu varsayılan seçenektir). Bu seçeneğin işaretini kaldırdığınızda, sihirbaz öznitelikler yerine şablon bildirimleri kullanır.

  - Bir tüketici **türü** **seçerseniz, sihirbaz** `db_source` `db_table` tablo ve tablo erişimcisi sınıf bildirimlerini oluşturmak için ve özniteliklerini kullanır ve `db_column` sütun eşlemesini oluşturmak için kullanır. Örneğin, bu eşlemeyi oluşturur:

    ```cpp
    // Inject table class and table accessor class declarations
    [db_source("<initialization_string>"), db_table("dbo.Orders")]
    ...
    // Column map
    [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;
    [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];
    ...
    ```

     `CTable`tablo ve tablo erişimci sınıfını bildirmek için şablon sınıfını kullanmak yerine, bu örnekte olduğu gibi BEGIN_COLUMN_MAP ve end_column_map makroları, sütun haritasını oluşturmak için kullanın:

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

  - Bir tüketici **komut** **türü** seçerseniz, sihirbaz `db_source` ve özniteliklerini kullanır `db_command` ve `db_column` sütun eşlemesini oluşturmak için kullanır. Örneğin, bu eşlemeyi oluşturur:

    ```cpp
    [db_source("<initialization_string>"), db_command("SQL_command")]
    ...
    // Column map using db_column is the same as for consumer type of 'table'
    ```

     komut ve komut erişimci sınıfı bildirimlerini komut sınıfı '. h dosyasında kullanmak yerine, örneğin:

    ```cpp
    // Command accessor class:
        class CListOrdersAccessor;
    // Command class:
        class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;
    // ...
    // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
    // for consumer type of 'table'
    ```

     Daha fazla bilgi için bkz. [temel öznitelik özniteliklerini](../../windows/attributes/cpp-attributes-com-net.md#basic-mechanics-of-attributes) inceleyin.

- **Tür**

   Tüketici sınıfının `CTable` veya (varsayılan) öğesinden türetilip türetilmeyeceğini belirtmek için bu radyo düğmelerinden birini seçin `CCommand` .

  - **Tablo**

      `CTable` `db_table` Tablo ve tablo erişimcisi sınıf bildirimlerini oluşturmak için veya kullanmak istiyorsanız bu seçeneği belirleyin.

  - **Komut**

      `CCommand` `db_command` Komut ve komut erişimcisi sınıf bildirimlerini oluşturmak için veya kullanmak istiyorsanız bu seçeneği belirleyin. Bu, varsayılan seçimdir.

- **Destek**

   Tüketicide desteklenecek güncelleştirme türlerini belirtmek için onay kutularını seçin (varsayılan değer None ' dır). Aşağıdakilerden her biri [DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892(v=vs.85)) ve özellik kümesi eşlemesinde [DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676(v=vs.85)) için uygun girdileri ayarlayacaktır.

  - **Değiştir**

      Tüketicinin satır kümesindeki satır verilerinin güncelleştirmelerini desteklediğini belirtir.

  - **Ekle**

      Tüketicinin satır kümesine ekleme işlemini desteklediğini belirtir.

  - **Silme**

      Tüketicinin satır kümesinden satır silmeyi desteklediğini belirtir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[ATL OLE DB tüketicisi](../../atl/reference/adding-an-atl-ole-db-consumer.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Bağlantı dizeleri ve veri bağlantıları (OLE DB)](/previous-versions/windows/desktop/ms718376(v=vs.85))
