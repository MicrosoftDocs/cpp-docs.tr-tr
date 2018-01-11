---
title: "MFC ODBC Tüketici Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.class.mfc.consumer.overview
dev_langs: C++
helpviewer_keywords:
- MFC ODBC Consumer Wizard
- wizards [MFC]
ms.assetid: f64a890b-a252-4887-88a1-782a7cd4ff3d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ad9e4aeb15d2af04987883b6554d569e3cc16b8d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-odbc-consumer-wizard"></a>MFC ODBC Tüketici Sihirbazı
"Arama sonuçları" Özet buraya ekleyin.  
  
 Bu sihirbaz, bir ODBC kayıt kümesi sınıfı ve veri bağlamaları belirtilen veri kaynağına erişmek için gerekli ayarlar.  
  
## <a name="uielement-list"></a>UIElement Listesi  
 **Veri kaynağı**  
 **Veri kaynağı** düğmesi belirtilen ODBC sürücüsünü kullanarak belirtilen veri kaynağını ayarlamanıza imkan sağlar. Veri kaynağı dosyaları (DSN) hakkında daha fazla bilgi için bkz: [dosya veri kaynaklarını](https://msdn.microsoft.com/library/ms715401.aspx) ODBC SDK. **Veri kaynağı Seç** iletişim kutusu iki sekme içerir:  
  
-   **Veri kaynağı dosyası** sekmesi: **konum** kutusunda veri kaynağı olarak kullanılacak dosyaları seçmek üzere dizinini belirtir. \Program Files\ODBC\Data kaynakları varsayılandır. Var olan dosya veri kaynaklarını (.dsn dosyaları) ana liste kutusunda görüntülenir. Saat kullanarak öncesinde veri kaynaklarını ya da ayarlayabilirsiniz **dosya DSN** sekmesi [ODBC Veri Kaynağı Yöneticisi](https://msdn.microsoft.com/library/ms714024.aspx), veya bu iletişim kutusunu kullanarak yeni bir tane oluşturun.  
  
     Bu iletişim kutusunu kullanarak yeni bir dosya veri kaynağı oluşturmak için tıklatın `New` DSN adı; belirtmek için **yeni veri kaynağı oluştur** iletişim kutusu görüntülenir. İçinde **yeni veri kaynağı oluştur** iletişim kutusunda, uygun bir sürücü seçin ve tıklatın `Next`; tıklatın **Gözat**ve (olması için "Tüm dosyaları" seçmek için veri kaynağı olarak kullanılacak dosya adını seçin Görünüm DSN olmayan dosyalar .xls dosyaları gibi); tıklatın `Next`ve ardından **son**. (Bir DSN olmayan dosya seçerseniz, "ODBC Microsoft Excel, dosyayı bir DSN'ye dönüştürecek Kur," gibi bir sürücüye özgü iletişim kutusu alırsınız.)  
  
    > [!NOTE]
    >  Ayrıca, önceden ODBC Veri Kaynağı Yöneticisi'ni kullanarak yeni bir dosya veri kaynağı oluşturabilirsiniz. Gelen **Başlat** menüsünde, select **ayarları**, **Denetim Masası**, **Yönetimsel Araçlar**, **veri kaynakları (ODBC)**ve ardından **ODBC Veri Kaynağı Yöneticisi**.  
  
     **DSN adı** kutusunu dosyası veri kaynağı için bir ad belirtmenize olanak verir. DSN adı .xls Excel dosyaları ya da dosyalara erişmek için .mdb gibi uygun dosya uzantısıyla biten emin olmalısınız.  
  
     DSN hakkında daha fazla bilgi için bkz: [dosya veri kaynaklarını](https://msdn.microsoft.com/library/ms715401.aspx) ODBC SDK.  
  
-   **Makine veri kaynağı** sekmesi: Bu sekmede sistemi ve kullanıcı veri kaynakları listelenir. Kullanıcı veri kaynakları, bu makinede bir kullanıcı için özeldir. Sistem veri kaynakları, bu makinede veya yükleyebilecek hizmetine tüm kullanıcılar tarafından kullanılabilir. Bkz: [makine veri kaynakları](https://msdn.microsoft.com/library/ms710952.aspx) ODBC SDK  
  
 ODBC veri kaynakları hakkında daha fazla bilgi için bkz: [veri kaynakları](https://msdn.microsoft.com/library/ms711688.aspx) ODBC SDK.  
  
 Tıklatın **Tamam** tamamlamak için. **Veritabanı nesnesi Seç** iletişim kutusu görüntülenir. Bu iletişim kutusundan tabloyu seçin veya tüketici kullanacağını görüntüleyin. Birden çok görünüm ve tablolar öğeler üzerinde denetim anahtarı tutarak seçebileceğiniz olduğunu unutmayın.  
  
 **Sınıfı**  
 Varsayılan olarak, seçilen dosya veya makine veri kaynağı adını temel alarak tüketici sınıfın adı.  
  
 **.h dosyası**  
 Varsayılan olarak, seçilen dosya veya makine veri kaynağı adını temel alarak tüketici sınıfı üstbilgi dosyası adı.  
  
 **.cpp dosyası**  
 Varsayılan olarak, seçilen dosya veya makine veri kaynağı adını temel alarak tüketici sınıfı uygulama dosyasının adıdır.  
  
 **Türü**  
 Kayıt kümesi dynaset (varsayılan) veya bir anlık görüntü olup olmadığını belirtir.  
  
-   **Dynaset**: kayıt bir dynaset olduğunu belirtir. Bir dinamik bir dizini oluşturulmuş görünüm sorgulanan veritabanının veri sağlayan bir sorgu sonucudur. Dinamik küme özgün veriler yalnızca bir tam sayı dizine önbelleğe alır ve bu nedenle bir anlık görüntü üzerinde bir performans sunar elde. Dizin noktalarına doğrudan her kayıt bir sorgu sonucunda bulunan ve bir kaydı kaldırılırsa, gösterir. Ayrıca güncelleştirilmiş bilgilere sorgulanan kayıtları erişebilirsiniz. Bu varsayılandır.  
  
-   **Anlık Görüntü**: kayıt bir anlık görüntü olduğunu belirtir. Bir anlık görüntü sorgu sonucu ve bir noktada bir veritabanı içine bir görünüm saattir. Sorgu sonucu olarak bulunan tüm kayıtları önbelleğe alınmış özgün kayıtlarının değişiklikleri görmezsiniz.  
  
 **Tüm sütunları bağlayın**  
 Seçili tablodaki tüm sütunları bağlı olup olmadığını belirtir. Bu kutu (varsayılan) seçeneğini belirlerseniz, tüm sütunlar bağlıdır; Bu kutuyu işaretlemeyin, hiçbir sütun bağlı olan ve, bunları el ile kayıt kümesi sınıfında bağlamanız gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Kod sihirbazlarıyla işlevsellik ekleme](../../ide/adding-functionality-with-code-wizards-cpp.md)

