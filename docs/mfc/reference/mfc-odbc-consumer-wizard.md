---
title: MFC ODBC Tüketicisi Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.codewiz.class.mfc.consumer.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 39a8a2b4c1ef915e98f2f646ad3764a7ab55f7af
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465926"
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC Tüketici Sihirbazı
"Arama sonuçları" Özet buraya ekleyin.  
  
 Bu sihirbaz bir ODBC kayıt kümesi sınıfı ve veri bağlamaları belirtilen veri kaynağına erişmek için gereken ayarlar.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Veri kaynağı**  
 **Veri kaynağı** düğmesi belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını ayarlamanıza imkan sağlar. Veri kaynağı dosyaları (DSN) hakkında daha fazla bilgi için bkz: [dosya veri kaynaklarını](/previous-versions/windows/desktop/ms715401\(v=vs.85\)) ODBC SDK. **Veri kaynağı Seç** iletişim kutusu iki sekme içerir:  
  
-   **Veri kaynağı dosyası** sekmesi: **konum** kutusunda veri kaynağı olarak kullanılacak dosyalarını seçmek dizin belirtir. \Program Files\ODBC\Data kaynakları varsayılandır. Mevcut dosya veri kaynakları (.dsn dosyaları), ana liste kutusunda görünür. Veri kaynaklarını kullanarak zaman önüne ya da ayarlayabilirsiniz **DSN dosyası** sekmesinde [ODBC Veri Kaynağı Yöneticisi](/previous-versions/windows/desktop/ms714024\(v=vs.85\)), bu iletişim kutusunu kullanarak yenilerini mi oluşturacaksınız.  
  
     Bu iletişim kutusundan yeni bir dosya veri kaynağı oluşturmak için tıklayın `New` DSN ad; belirtmek üzere **yeni veri kaynağı oluştur** iletişim kutusu görüntülenir. İçinde **yeni veri kaynağı oluştur** iletişim kutusunda, uygun bir sürücü seçip tıklayın `Next`; tıklayın **Gözat**ve (olması için "Tüm dosyaları" seçmek için bir veri kaynağı olarak kullanılacak dosya adını seçin Görünüm DSN olmayan dosyalar .xls dosyaları gibi); tıklayın `Next`ve ardından **son**. (Bir olmayan DSN dosyası seçtiyseniz, "ODBC Microsoft Excel dosyası bir DSN'ye dönüştürecek Kurulumu" gibi bir sürücüye özel iletişim kutusu açılır.)  
  
    > [!NOTE]
    >  Ayrıca, önceden ODBC Veri Kaynağı Yöneticisi'ni kullanarak yeni bir dosya veri kaynağı oluşturabilirsiniz. Gelen **Başlat** menüsünde **ayarları**, **Denetim Masası**, **Yönetimsel Araçlar**, **veri kaynakları (ODBC)**, ardından **ODBC Veri Kaynağı Yöneticisi**.  
  
     **DSN adı** kutusu dosyası veri kaynağı için bir ad belirtmenize olanak verir. DSN adı gibi .xls Excel dosyaları ya da .mdb dosyaları erişim için uygun dosya uzantısıyla biten emin olmanız gerekir.  
  
     DSN hakkında daha fazla bilgi için bkz. [dosya veri kaynaklarını](/previous-versions/windows/desktop/ms715401\(v=vs.85\)) ODBC SDK.  
  
-   **Veri kaynağı makine** sekmesi: Bu sekmede, sistem ve kullanıcı veri kaynakları listelenir. Kullanıcı veri kaynakları, bir kullanıcı bu makinedeki özgüdür. Sistem veri kaynakları, bu makinede veya bir sistem çapında hizmetinde tüm kullanıcılar tarafından kullanılabilir. Bkz: [makine veri kaynaklarını](/previous-versions/windows/desktop/ms710952\(v=vs.85\)) ODBC SDK  
  
 ODBC veri kaynakları hakkında daha fazla bilgi için bkz. [veri kaynakları](/previous-versions/windows/desktop/ms711688\(v=vs.85\)) ODBC SDK.  
  
 Tıklayın **Tamam** tamamlanması. **Veritabanı nesnesini Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan tabloyu seçin veya tüketici kullanacağını görüntüleyin. Birden çok görünüm ve tablo öğelerde tıklatırken CTRL tuşunu basılı tutarak seçebileceğinizi unutmayın.  
  
 **Sınıfı**  
 Varsayılan olarak, seçtiğiniz dosya veya makine veri kaynağı adını temel alarak tüketici sınıfı adı.  
  
 **.h dosyası**  
 Varsayılan olarak, seçtiğiniz dosya veya makine veri kaynağı adını temel alarak tüketici sınıfı üst bilgi dosyasının adı.  
  
 **.cpp dosyası**  
 Varsayılan olarak, seçtiğiniz dosya veya makine veri kaynağı adını temel alarak tüketici sınıf uygulaması dosya adı.  
  
 **Türü**  
 Kayıt kümesi bir dynaset (varsayılan) veya bir anlık görüntü olup olmadığını belirtir.  
  
-   **Dynaset**: bir dinamik kayıt kümesini belirtir. Bir dinamik sorgulanan veritabanının verilerini dizinli bir görünüm sağlar bir sorgu sonucudur. Bir dinamik özgün verilere yalnızca integral dizin önbelleğe alır ve böylece bir anlık görüntü üzerinde bir performans sunar elde edin. Dizin noktaları doğrudan her kayıt için bir sorgu sonucunda bulunan ve bir kaydı kaldırılırsa, gösterir. Ayrıca güncel bilgilere sorgulanan kayıtlara erişebilirsiniz. Bu varsayılandır.  
  
-   **Anlık Görüntü**: anlık görüntü kayıt kümesini belirtir. Bir anlık görüntü sorgu sonucu ve zaman içinde bir noktadaki bir veritabanına görünümüdür. Özgün kayıtlarının değişiklikleri görmek için bir sorgu sonucunda bulunan tüm kayıtları önbelleğe alınır.  
  
 **Tüm sütunları bağlayın**  
 Seçili tablodaki tüm sütunları bağlanıp bağlanmadığını belirtir. Bu kutuyu (varsayılan) seçeneğini belirlerseniz, tüm sütunları bağlıdır; Bu kutuyu işaretlemeyin, hiçbir sütun bağlı ve el ile kayıt kümesi sınıfında bağlanmalıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)

