---
title: MFC ODBC Tüketici Sihirbazı
ms.date: 08/29/2019
helpviewer_keywords:
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: 45087434c0093f99383096761d58a8029c9d5009
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373016"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC Tüketici Sihirbazı

::: moniker range="vs-2019"

Bu sihirbaz Visual Studio 2019 ve sonraki yıllarda kullanılamaz.

::: moniker-end

::: moniker range="<=vs-2017"

Bu sihirbaz, bir ODBC kayıt kümesi sınıfı ve belirtilen veri kaynağına erişmek için gerekli veri bağlamaları ayarlar.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri Kaynağı**

  **Veri Kaynağı** düğmesi, belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını ayarlamanızı sağlar. Veri kaynağı dosyaları (DSN) hakkında daha fazla bilgi için, ODBC SDK'daki [Dosya Veri Kaynakları'na](/sql/odbc/reference/file-data-sources) bakın.

  **Veri Kaynağı Seç** iletişim kutusunda iki sekme vardır:

  - **Dosya Veri Kaynağı** sekmesi:

     **Görünüm kutusunda,** veri kaynağı olarak kullanılacak dosyaları seçilecek dizini belirtir. Varsayılan \Program Dosyaları\Ortak Dosyalar\ODBC\Veri Kaynakları. Varolan dosya veri kaynakları (.dsn dosyaları) ana liste kutusunda görünür. Veri kaynaklarını [ODBC Veri Kaynağı Yöneticisi'ndeki](/sql/odbc/admin/odbc-data-source-administrator) **Dosya DSN** sekmesini kullanarak önceden ayarlayabilir veya bu iletişim kutusunu kullanarak yenilerini oluşturabilirsiniz.

     Bu iletişim kutusundan yeni bir dosya veri `New` kaynağı oluşturmak için bir DSN adı belirtmek için tıklatın; **Yeni Veri Kaynağı Oluştur** iletişim kutusu görüntülenir. Yeni **Veri Kaynağı Oluştur** iletişim kutusunda, uygun bir `Next`sürücü seçin ve ; **Gözat'ı**tıklatın ve veri kaynağı olarak kullanılacak dosyanın adını seçin (.xls dosyaları gibi DSN olmayan dosyaları görüntülemek için "Tüm Dosyalar"ı seçmeniz gerekir); tıklatın `Next`ve sonra **Bitir'i**tıklatın. (DSN olmayan bir dosya seçtiyseniz, dosyayı DSN'ye dönüştürecek "ODBC Microsoft Excel Kurulumu" gibi sürücüye özgü bir iletişim kutusu alırsınız.)

     > [!NOTE]
     > ODBC Veri Kaynağı Yöneticisi'ni kullanarak önceden yeni bir dosya veri kaynağı oluşturabilirsiniz. **Başlat** menüsünden **Ayarlar,** **Denetim Masası,** **Yönetim Araçları,** **Veri Kaynakları (ODBC)** ve ardından **ODBC Veri Kaynak Yöneticisi'ni**seçin.

     **DSN Adı** kutusu, dosya veri kaynağı için bir ad belirtmenize olanak tanır. DSN adının Excel dosyaları için .xls veya Access dosyaları için .mdb gibi uygun dosya uzantısı ile sona erdiğinden emin olmalısınız.

     DSN'ler hakkında daha fazla bilgi için ODBC SDK'daki [Dosya Veri Kaynakları'na](/sql/odbc/reference/file-data-sources) bakın.

  - **Makine Veri Kaynağı** sekmesi:

     Bu sekme, sistem ve Kullanıcı VERİlerİ kaynaklarını listeler. Kullanıcı veri kaynakları bu makinedeki bir kullanıcıya özgür. Sistem veri kaynakları bu makinedeki tüm kullanıcılar tarafından veya sistem çapında bir hizmette kullanılabilir. ODBC SDK'daki [Makine Veri Kaynaklarına](/sql/odbc/reference/machine-data-sources) Bakın

     ODBC veri kaynakları hakkında daha fazla bilgi için, ODBC SDK'daki [Veri Kaynakları'na](/sql/odbc/reference/data-sources) bakın.

  Ayarlamayı bitirmek için **Tamam**'a tıklayın. **Veritabanı Nesnesini Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan, tüketicinin kullanacağı tabloyu veya görünümü seçin. Öğelere tıklarken denetim tuşunu basılı tutarak birden çok görünüm ve tablo seçebileceğinizi unutmayın. Ayarlamayı bitirmek için **Tamam**'a tıklayın.

- **Sınıfı**

   Seçtiğiniz dosyanın veya makine veri kaynağının adına varsayılan olarak dayalı tüketici sınıfının adı.

- **.h dosyası**

   Seçtiğiniz dosyanın veya makine veri kaynağının adına varsayılan olarak dayalı tüketici sınıfı üstbilgi dosyasının adı.

- **.cpp dosyası**

   Seçtiğiniz dosyanın veya makine veri kaynağının adına varsayılan olarak dayalı tüketici sınıfı uygulama dosyasının adı.

- **Tür**

   Kayıt kümesinin bir dinamit (varsayılan) veya anlık görüntü olup olmadığını belirtir.

  - **Dynaset**: Kayıt setinin bir dinamit olduğunu belirtir. Dynaset, sorgulanan veritabanıverilerine dizinlenmiş görünüm sağlayan bir sorgunun sonucudur. Bir dinamit, özgün verilere yalnızca ayrılmaz bir dizin önbelleğe gelir ve böylece anlık görüntü üzerinden performans artışı sağlar. Dizin, sorgu nun sonucu olarak bulunan her kayda doğrudan işaret ediyor ve bir kaydın kaldırılıp kaldırılmadı olduğunu gösterir. Ayrıca sorgulanmış kayıtlarda güncelleştirilmiş bilgilere erişebilirsiniz. Bu varsayılandır.

  - **Anlık Görüntü**: Kayıt kümesinin anlık görüntü olduğunu belirtir. Anlık görüntü bir sorgunun sonucudur ve bir zaman içinde bir veritabanına bir görünümdür. Sorgu nun sonucu olarak bulunan tüm kayıtlar önbelleğe alınır, bu nedenle özgün kayıtlarda herhangi bir değişiklik görmezsiniz.

- **Tüm sütunları bağlama**

   Seçili tablodaki tüm sütunların bağlı olup olmadığını belirtir. Bu kutuyu (varsayılan) seçerseniz, tüm sütunlar bağlanır; Bu kutuyu seçmezseniz, sütun bağlı değildir ve bunları kayıt kümesi sınıfında el ile bağlamanız gerekir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[MFC ODBC Tüketimi](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
