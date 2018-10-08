---
title: ATL OLE DB Tüketicisi Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 08/31/2018
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
ms.openlocfilehash: 163949c4421cca8e4d5e414a18bda4ed98f32d3d
ms.sourcegitcommit: 997e6b7d336cddb388bb6e9e56527725fcaa0624
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/08/2018
ms.locfileid: "48861648"
---
# <a name="atl-ole-db-consumer-wizard"></a>ATL OLE DB Tüketicisi Sihirbazı

Bu sihirbaz bir OLE DB Tüketici sınıfı veri bağlamaları ile belirtilen OLE DB sağlayıcısı belirtilen veri kaynağına erişmek için gereken ayarlar.

> [!NOTE]
> Bu sihirbaz tıklayın gerektiren **veri kaynağı** adlarında girmeden önce bir veri kaynağı seçmek için düğmesini `Class` ve **.h dosyası** alanları.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri kaynağı**

   **Veri kaynağı** düğmesi belirtilen OLE DB sağlayıcısı kullanılarak belirtilen veri kaynağını ayarlamanıza imkan sağlar. Bu düğmeye tıkladığınızda **veri bağlantı özellikleri** iletişim kutusu görüntülenir. Bağlantı dizeleri derleme hakkında daha fazla bilgi ve **veri bağlantı özellikleri** iletişim kutusu, bkz: [veri bağlantısı API'sine genel bakış](/previous-versions/windows/desktop/ms718102\(v=vs.85\)) Windows SDK belgelerinde.

   Aşağıdaki ek bilgileri sekmeleri açıklar **veri bağlantı özellikleri** iletişim kutusu.

   - **Sağlayıcı** sekmesi

      Veri kaynağı bağlantısı yönetmek için uygun bir sağlayıcı seçin. Sağlayıcı türü, genellikle bağlanmakta olduğunuz veritabanı türüne göre belirlenir. Tıklayın **sonraki** düğmesine veya tıklayın **bağlantı** sekmesi.

   - **Bağlantı** sekmesi

      Bu sekme içeriğini seçtiğiniz sağlayıcısına bağlıdır. Sağlayıcıları türlerde olsa da, bu bölüm iki bağlantılarında kapsar en yaygın: SQL ve ODBC veri. Diğerleri, burada açıklanan alanlara benzer çeşidi alanlarıdır.

      SQL verileri için:

      1. **Sunucu adını seçin veya girin:** tüm kayıtlı veri sunucuları ağ üzerinde görüntülemek için aşağı açılır menüsünü tıklatın ve seçin.

      1. **Sunucuda oturum açmak için bilgileri girin:** bir kullanıcı adı ve veri sunucuya oturum açmak için parola girin.

         > [!NOTE]
         > Veri Bağlantı Özellikleri iletişim kutusunun "Parola kaydetmeye izin ver" özelliği ile bir güvenlik sorunu var. "Sunucuya oturum açmak için Enter bilgileri," iki radyo düğmeleri vardır:
         >
         > - **Windows NT tümleşik güvenliğini kullan**
         > - **Belirli bir kullanıcı adı ve parolayı kullanın**
         >
         > Seçerseniz **belirli bir kullanıcı adı ve parolayı kullanın**, ("Parola kaydetmeye izin ver" için onay kutusunu kullanarak) parolayı kaydetme seçeneğiniz vardır; ancak, bu seçeneği güvenli değildir. Seçtiğiniz önerilir **kullanım Windows NT tümleşik güvenliği**; bu seçenek, parolayı şifreler için güvenlidir.
         > "Parola kaydetmeye izin ver"'i seçmek istediğiniz durumlar olabilir Örneğin, özel veritabanı çözümü bir kitaplıkla yayınlıyorsanız, veritabanına doğrudan erişim değil ancak orta katmanlı bir uygulama kullanıcının (seçtiğiniz hangi kimlik doğrulama düzeni) üzerinden doğrulayın ve ardından veri sıralama sınırlamak için kullanın kullanıcı için kullanılabilir.

      1. **Sunucu üzerindeki veritabanı seçin:** veri sunucusunda kayıtlı tüm veritabanlarını görüntülemek için aşağı açılır menüsünü tıklatın ve seçin.

         \- veya -

         **Bir veritabanı adı olarak veritabanı dosya Ekle:** veritabanı olarak kullanılacak bir dosya belirtin; açık yol adını girin.

      ODBC veri için:

      1. **Veri kaynağını belirtin:** , bir veri kaynağı adı veya bağlantı dizesini kullanabilirsiniz.

         **Veri kaynağı adı kullan:** makinenizde kayıtlı veri kaynaklarına bu açılan liste görüntüler. Veri kaynakları önceden ODBC Veri Kaynağı Yöneticisi'ni kullanarak ayarlayabilirsiniz.

         \- veya -

         **Bağlantı dizesini kullan:** önce almış olan veya tıklayın bir bağlantı dizesi girin **derleme** düğmesini; **veri kaynağı Seç** iletişim kutusu görüntülenir. Bir dosya veya makine veri kaynağını seçin ve tıklayın **Tamam**.

         > [!NOTE]
         > Var olan bir bağlantı özelliklerini görüntüleyerek bir bağlantı dizesi edinebilirsiniz **Sunucu Gezgini**, ya da çift tıklayarak bir bağlantı oluşturabilirsiniz **Bağlantı Ekle** içinde **sunucusu Explorer**.

      1. **Sunucuda oturum açmak için bilgileri girin:** bir kullanıcı adı ve veri sunucuya oturum açmak için parola girin.

      1. Kullanılacak Initial catalog girin.

      1. Tıklayın **Bağlantıyı Sına**; sınama başarılı olursa, tıklayın **Tamam**. Aksi halde oturum açma bilgilerinizi kontrol edin, başka bir veritabanı deneyin veya başka bir veri sunucusu deneyin.

   - **Gelişmiş** sekmesi

      **Ağ ayarları:** belirtin **kimliğe bürünme düzeyi** (sunucu, istemci kimliğine bürünme kullanmasına izin verilir; karşılık gelen RPC kimliğe bürünme düzeyi doğrudan kimliğe bürünme düzeyi) ve  **Koruma düzeyi** (veri koruma düzeyini istemci ve sunucu; arasında gönderilen doğrudan RPC koruma düzeyleri karşılık gelir).

      **Diğer:** içinde **bağlantı zaman aşımı**, boşta kalma süresi bir zaman aşımı oluşmadan önce izin verilen saniye sayısını belirtin. İçinde **erişim izinlerini**, veri bağlantısına erişim izinlerini belirtin.

       Gelişmiş başlatma özellikleri hakkında daha fazla bilgi için her özel OLE DB sağlayıcısı ile sağlanan belgelere bakın.

   - **Tüm** sekmesi

      Bu sekme, belirttiğiniz bağlantı ve veri kaynağı için başlatma özellikleri özetini görüntüler. Bu değerleri düzenleyebilirsiniz.

   Tıklayın **Tamam** tamamlanması. **Veritabanı nesnesini Seç** iletişim kutusu görüntülenir. Bu iletişim kutusunda, tablo, görünüm veya tüketici kullanacağı bir saklı yordam seçin.

- **Sınıfı**

   Bir veri kaynağını seçtikten sonra bu kutu tablo veya seçtiğiniz saklı yordam dayalı bir varsayılan sınıf adını doldurulur (bkz **bir veri kaynağı** aşağıda). Sınıf adını düzenleyebilirsiniz.

- **.h dosyası**

   Bir veri kaynağını seçtikten sonra bu kutu, tablo veya seçtiğiniz saklı yordam dayalı varsayılan üstbilgi sınıf adıyla doldurulur (bkz **bir veri kaynağı** aşağıda). Üst bilgi dosyanın adını düzenleyebilir veya var olan bir üst bilgi dosyasını seçebilirsiniz.

- **Öznitelikli**

   Bu seçenek, sihirbaz öznitelikler veya şablon bildirimleri kullanarak tüketici sınıflar oluşturacak olup olmadığını belirtir. Bu seçeneği belirlediğinizde sihirbaz (varsayılan seçenek budur) şablon bildirimleri yerine öznitelikleri kullanır. Bu seçeneği belirlediğinizde sihirbaz şablon bildirimleri yerine öznitelikleri kullanır.

   - Bir tüketici seçerseniz **türü** , **tablo**, Sihirbazı'nı kullanan `db_source` ve `db_table` tablosu ve tablo erişimci sınıf bildirimleri oluşturmak için öznitelikleri ve kullandığı `db_column` için Sütun eşlemesi oluşturun. Örneğin, bu eşlemeyi oluşturur:

        ```cpp
        // Inject table class and table accessor class declarations
        [db_source("<initialization_string>"), db_table("dbo.Orders")]
        ...
        // Column map
        [ db_column(1, status=m_dwOrderIDStatus, length=m_dwOrderIDLength) ] LONG m_OrderID;
        [ db_column(2, status=m_dwCustomerIDStatus, length=m_dwCustomerIDLength) ] TCHAR m_CustomerID[6];
        ...
        ```

      yerine `CTable` tablosu ve tablo erişimci sınıfı ve bu örnekte olduğu gibi sütun eşlemesi oluşturmak için BEGIN_COLUMN_MAP ve END_COLUMN_MAP makroları bildirmek için bir şablon sınıfı:

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

   - Bir tüketici seçerseniz **türü** , **komut**, Sihirbazı kullanır `db_source` ve `db_command` öznitelikleri ve kullandığı `db_column` sütun eşlemesi oluşturmak için. Örneğin, bu eşlemeyi oluşturur:

        ```cpp
        [db_source("<initialization_string>"), db_command("SQL_command")]
        ...
        // Column map using db_column is the same as for consumer type of 'table'
        ```

      komut ve komut erişimci kullanmak yerine komut sınıfı .h dosyası bildirimlerinde örneğin sınıfı:

        ```cpp
        // Command accessor class:
            class CListOrdersAccessor;
        // Command class:
            class CListOrders : public CCommand<CAccessor<CListOrdersAccessor>>;
        // ...
        // Column map using BEGIN_COLUMN_MAP ... END_COLUMN_MAP is the same as
        // for consumer type of 'table'
        ```

      Bkz: [öznitelikleri temel mekanizması](../../windows/basic-mechanics-of-attributes.md) daha fazla bilgi için.

- **Türü**

   Tüketici sınıfı öğesinden türetilmiş olup olmadığını belirtmek için bu radyo düğmeleri birini `CTable` veya `CCommand` (varsayılan).

   - **Tablo**

      Kullanmak istiyorsanız bu seçeneği `CTable` veya `db_table` tablosu ve tablo erişimci sınıf bildirimleri oluşturmak için.

   - **Komutu**

      Kullanmak istiyorsanız bu seçeneği `CCommand` veya `db_command` komut ve komut erişimci sınıf bildirimleri oluşturmak için. Varsayılan seçenek budur.

- **Destek**

   (Varsayılan, Yok'tur) tüketicide desteklenmesi için güncelleştirmeleri türlerini belirtmek için onay kutularını seçin. Aşağıdakilerin her biri ayarlayacak [DBPROP_IRowsetChange](/previous-versions/windows/desktop/ms715892\(v=vs.85\)) ve uygun girişleri [DBPROP_UPDATABILITY](/previous-versions/windows/desktop/ms722676\(v=vs.85\)) eşleme özelliğini ayarlayın.

   - **Değişiklik**

      Tüketici satır kümesinde satır veri güncelleştirmelerini desteklediğini belirtir.

   - **Ekle**

      Tüketici satır içine satır ekleme desteği belirtir.

   - **Delete**

      Tüketici satır satır silme desteklediğini belirtir.

## <a name="see-also"></a>Ayrıca bkz.

[ATL OLE DB Tüketicisi](../../atl/reference/adding-an-atl-ole-db-consumer.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[Bağlantı dizelerini ve veri bağlantıları (OLE DB)](/previous-versions/windows/desktop/ms718376\(v=vs.85\))
