---
title: MFC ODBC Tüketici Sihirbazı
ms.date: 08/29/2019
helpviewer_keywords:
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
ms.openlocfilehash: c915408eede80c1564dacc88ab7b9354bd72fc11
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92918845"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC Tüketici Sihirbazı

::: moniker range="msvc-160"

Bu sihirbaz, Visual Studio 2019 ve sonrasında kullanılamaz.

::: moniker-end

::: moniker range="<=msvc-150"

Bu sihirbaz, belirtilen veri kaynağına erişmek için gereken bir ODBC kayıt kümesi sınıfını ve veri bağlamalarını ayarlar.

## <a name="uielement-list"></a>UIElement Listesi

- **Veri Kaynağı**

  **Veri kaynağı** düğmesi, belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını ayarlamanıza olanak sağlar. Veri kaynağı dosyaları (DSN) hakkında daha fazla bilgi için bkz. ODBC SDK 'daki [dosya veri kaynakları](/sql/odbc/reference/file-data-sources) .

  **Veri kaynağı seç** iletişim kutusu iki sekmeye sahiptir:

  - **Dosya veri kaynağı** sekmesi:

     **Içindeki ara** kutusu, veri kaynağı olarak kullanılacak dosyaların seçilecek dizini belirtir. Varsayılan değer \Program Files\Common Files\ODBC\Data kaynaklarıdır. Mevcut dosya veri kaynakları (. DSN dosyaları) ana liste kutusunda görünür. [ODBC veri kaynağı Yöneticisi](/sql/odbc/admin/odbc-data-source-administrator)'NDEKI **dosya DSN** sekmesini kullanarak veri kaynaklarını zaman içinde ayarlayabilir veya bu iletişim kutusunu kullanarak yeni bir tane oluşturabilirsiniz.

     Bu iletişim kutusundan yeni bir dosya veri kaynağı oluşturmak için, `New` BIR DSN adı belirtmek için öğesine tıklayın; **Yeni veri kaynağı oluştur** iletişim kutusu görüntülenir. **Yeni veri kaynağı oluştur** iletişim kutusunda, uygun bir sürücü seçin ve ' a tıklayın `Next` ve veri **Browse** kaynağı olarak kullanılacak dosyanın adını seçin (. xls dosyaları gibi DSN olmayan dosyaları görüntülemek için "tüm dosyalar" ı seçmeniz gerekir) `Next` , ve ardından **son** ' a tıklayın. (DSN olmayan bir dosya seçtiyseniz, dosyayı bir DSN 'e dönüştürecek "ODBC Microsoft Excel kurulumu" gibi sürücüye özgü bir iletişim kutusu alacaksınız.)

     > [!NOTE]
     > ODBC veri kaynağı Yöneticisi 'ni kullanarak önceden yeni bir dosya veri kaynağı da oluşturabilirsiniz. **Başlat** menüsünde **Ayarlar** , **Denetim Masası** , **Yönetim Araçları** , **veri kaynakları (ODBC)** ve ardından **ODBC veri kaynağı Yöneticisi** ' ni seçin.

     **DSN adı** kutusu, dosya veri kaynağı için bir ad belirtmenizi sağlar. DSN adının, Excel dosyaları için. xls veya erişim dosyaları için. mdb gibi uygun dosya uzantısıyla bitdiğinden emin olmanız gerekir.

     DSN hakkında daha fazla bilgi için bkz. ODBC SDK 'sında [dosya veri kaynakları](/sql/odbc/reference/file-data-sources) .

  - **Makine veri kaynağı** sekmesi:

     Bu sekme, sistem ve Kullanıcı VERI kaynaklarını listeler. Kullanıcı veri kaynakları, bu makinedeki bir kullanıcıya özeldir. Sistem veri kaynakları, bu makinedeki veya bir sistem genelinde bir hizmette bulunan tüm kullanıcılar tarafından kullanılabilir. Bkz. ODBC SDK 'sindeki [makine veri kaynakları](/sql/odbc/reference/machine-data-sources)

     ODBC veri kaynakları hakkında daha fazla bilgi için bkz. ODBC SDK 'daki [veri kaynakları](/sql/odbc/reference/data-sources) .

  Ayarlamayı bitirmek için **Tamam** 'a tıklayın. **Veritabanı nesnesi Seç** iletişim kutusu görünür. Bu iletişim kutusunda, tüketicinin kullanacağı tabloyu veya görünümü seçin. Öğeler ' i tıklatırken denetim tuşunu basılı tutarak birden çok görünüm ve tablo seçebilirsiniz. Ayarlamayı bitirmek için **Tamam** 'a tıklayın.

- **Sınıf**

   Seçtiğiniz dosya veya makine veri kaynağı adı üzerinde varsayılan olarak temel alan tüketici sınıfının adı.

- **. h dosyası**

   Seçtiğiniz dosya veya makine veri kaynağı adı üzerinde varsayılan olarak temel alan tüketici sınıfı üstbilgi dosyasının adı.

- **. cpp dosyası**

   Seçtiğiniz dosya veya makine veri kaynağı adı üzerinde varsayılan olarak temel alan tüketici sınıfı uygulama dosyasının adı.

- **Tür**

   Kayıt kümesinin Dynaset (varsayılan) veya anlık görüntü olduğunu belirtir.

  - **Dynaset** : kayıt kümesinin bir Dynaset olduğunu belirtir. DYNASET, sorgulanan veritabanının verilerine dizinli bir görünüm sağlayan sorgunun sonucudur. DYNASET, özgün verilerin yalnızca bir integral dizinini önbelleğe alır ve bu nedenle bir anlık görüntü üzerinde performans kazancı sağlar. Dizin, bir sorgunun sonucu olarak bulunan her bir kayda doğrudan işaret eder ve bir kaydın kaldırılıp kaldırılmadığını gösterir. Ayrıca, sorgulanan kayıtlardaki güncelleştirilmiş bilgilere erişebilirsiniz. Bu varsayılan seçenektir.

  - **Anlık görüntü** : kayıt kümesinin bir anlık görüntü olduğunu belirtir. Anlık görüntü, bir sorgunun sonucudur ve tek seferde bir veritabanında görüntülenir. Sorgunun bir sonucu olarak bulunan tüm kayıtlar önbelleğe alınır, bu nedenle özgün kayıtlarda herhangi bir değişiklik görmezsiniz.

- **Tüm sütunları bağla**

   Seçili tablodaki tüm sütunların bağlanıp bağlanmadığını belirtir. Bu kutuyu (varsayılan) seçerseniz, tüm sütunlar bağlanır; Bu kutuyu seçmezseniz, hiçbir sütun bağlı değildir ve bunları kayıt kümesi sınıfında el ile bağlamanız gerekir.

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[MFC ODBC tüketme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Kod Sihirbazlarıyla İşlevsellik Ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)
