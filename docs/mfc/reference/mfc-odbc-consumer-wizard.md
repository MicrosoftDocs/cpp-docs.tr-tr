---
title: MFC ODBC Tüketici Sihirbazı
ms.date: 10/03/2018
f1_keywords:
- vc.codewiz.class.mfc.consumer.overview
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: 75d62eb5ce3d24322d7af5030fb8d723ffa8fedb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57259938"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC Tüketici Sihirbazı

> [!WARNING]
> Visual Studio 2017 sürüm 15.9 bu kod Sihirbazı kullanım dışıdır ve Visual Studio'nun gelecekteki bir sürümde kaldırılacak. Bu sihirbaz nadiren kullanılır. ATL ve MFC genel desteği, bu sihirbazın kaldırma işlemi etkilenmez. Bu kullanımdan kaldırma hakkındaki görüşlerinizi paylaşmak istiyorsanız, Lütfen tamamlayın [bu anketi](https://www.surveymonkey.com/r/QDWKKCN). Geri bildiriminiz bizim için önemlidir.

Bu sihirbaz bir ODBC kayıt kümesi sınıfı ve veri bağlamaları belirtilen veri kaynağına erişmek için gereken ayarlar.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri kaynağı**

  **Veri kaynağı** düğmesi belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını ayarlamanıza imkan sağlar. Veri kaynağı dosyaları (DSN) hakkında daha fazla bilgi için bkz: [dosya veri kaynaklarını](/previous-versions/windows/desktop/ms715401) ODBC SDK.

  **Veri kaynağı Seç** iletişim kutusu iki sekme içerir:

  - **Veri kaynağı dosyası** sekmesinde:

     **Konum** kutusunda veri kaynağı olarak kullanılacak dosyalarını seçmek dizin belirtir. \Program Files\ODBC\Data kaynakları varsayılandır. Mevcut dosya veri kaynakları (.dsn dosyaları), ana liste kutusunda görünür. Veri kaynaklarını kullanarak zaman önüne ya da ayarlayabilirsiniz **DSN dosyası** sekmesinde [ODBC Veri Kaynağı Yöneticisi](/previous-versions/windows/desktop/ms714024), bu iletişim kutusunu kullanarak yenilerini mi oluşturacaksınız.

     Bu iletişim kutusundan yeni bir dosya veri kaynağı oluşturmak için tıklayın `New` DSN ad; belirtmek üzere **yeni veri kaynağı oluştur** iletişim kutusu görüntülenir. İçinde **yeni veri kaynağı oluştur** iletişim kutusunda, uygun bir sürücü seçip tıklayın `Next`; tıklayın **Gözat**ve (olması için "Tüm dosyaları" seçmek için bir veri kaynağı olarak kullanılacak dosya adını seçin Görünüm DSN olmayan dosyalar .xls dosyaları gibi); tıklayın `Next`ve ardından **son**. (Bir olmayan DSN dosyası seçtiyseniz, "ODBC Microsoft Excel dosyası bir DSN'ye dönüştürecek Kurulumu" gibi bir sürücüye özel iletişim kutusu açılır.)

     > [!NOTE]
     > Ayrıca, önceden ODBC Veri Kaynağı Yöneticisi'ni kullanarak yeni bir dosya veri kaynağı oluşturabilirsiniz. Gelen **Başlat** menüsünde **ayarları**, **Denetim Masası**, **Yönetimsel Araçlar**, **veri kaynakları (ODBC)**, ardından **ODBC Veri Kaynağı Yöneticisi**.

     **DSN adı** kutusu dosyası veri kaynağı için bir ad belirtmenize olanak verir. DSN adı gibi .xls Excel dosyaları ya da .mdb dosyaları erişim için uygun dosya uzantısıyla biten emin olmanız gerekir.

     DSN hakkında daha fazla bilgi için bkz. [dosya veri kaynaklarını](/previous-versions/windows/desktop/ms715401) ODBC SDK.

  - **Veri kaynağı makine** sekmesinde:

     Bu sekme, sistem ve kullanıcı veri kaynaklarını listeler. Kullanıcı veri kaynakları, bir kullanıcı bu makinedeki özgüdür. Sistem veri kaynakları, bu makinede veya bir sistem çapında hizmetinde tüm kullanıcılar tarafından kullanılabilir. Bkz: [makine veri kaynaklarını](/previous-versions/windows/desktop/ms710952) ODBC SDK

     ODBC veri kaynakları hakkında daha fazla bilgi için bkz. [veri kaynakları](/previous-versions/windows/desktop/ms711688) ODBC SDK.

  Ayarlamayı bitirmek için **Tamam**'a tıklayın. **Veritabanı nesnesini Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan tabloyu seçin veya tüketici kullanacağını görüntüleyin. Birden çok görünüm ve tablo öğelerde tıklatırken CTRL tuşunu basılı tutarak seçebileceğinizi unutmayın. Ayarlamayı bitirmek için **Tamam**'a tıklayın.

- **Sınıfı**

      The name of the consumer class, based by default on the name of the file or machine data source that you selected.

- **.h dosyası**

   Varsayılan olarak, seçtiğiniz dosya veya makine veri kaynağı adını temel alarak tüketici sınıfı üst bilgi dosyasının adı.

- **.cpp dosyası**

   Varsayılan olarak, seçtiğiniz dosya veya makine veri kaynağı adını temel alarak tüketici sınıf uygulaması dosya adı.

- **Tür**

   Kayıt kümesi bir dynaset (varsayılan) veya bir anlık görüntü olup olmadığını belirtir.

   - **Dynaset**: Kayıt kümesi bir dinamik olduğunu belirtir. Bir dinamik sorgulanan veritabanının verilerini dizinli bir görünüm sağlar bir sorgu sonucudur. Bir dinamik özgün verilere yalnızca integral dizin önbelleğe alır ve böylece bir anlık görüntü üzerinde bir performans sunar elde edin. Dizin noktaları doğrudan her kayıt için bir sorgu sonucunda bulunan ve bir kaydı kaldırılırsa, gösterir. Ayrıca güncel bilgilere sorgulanan kayıtlara erişebilirsiniz. Bu varsayılandır.

   - **Anlık Görüntü**: Kayıt kümesi bir anlık görüntü olduğunu belirtir. Bir anlık görüntü sorgu sonucu ve zaman içinde bir noktadaki bir veritabanına görünümüdür. Özgün kayıtlarının değişiklikleri görmek için bir sorgu sonucunda bulunan tüm kayıtları önbelleğe alınır.

- **Tüm sütunları bağlayın**

   Seçili tablodaki tüm sütunları bağlanıp bağlanmadığını belirtir. Bu kutuyu (varsayılan) seçeneğini belirlerseniz, tüm sütunları bağlıdır; Bu kutuyu işaretlemeyin, hiçbir sütun bağlı ve el ile kayıt kümesi sınıfında bağlanmalıdır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
