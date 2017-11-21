---
title: "Veri kaynağı: Bağlantıları yönetme (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC data sources [C++], multiuser environments
- generalizing connection strings
- ODBC [C++], disconnecting from data sources
- connection strings [C++], generalizing
- database connections [C++], creating
- GetDefaultConnect method
- connections [C++], data source
- ODBC connections [C++], configuring
- disconnecting from data sources
- databases [C++], connecting to
- ODBC connections [C++], disconnecting
- data sources [C++], connecting to
- ODBC connections [C++], connecting to data source
- ODBC data sources [C++], connections
- database connections [C++], MFC ODBC classes
ms.assetid: c0adbcdd-c000-40c6-b199-09ffdc7b6ef2
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6a88aab7023791de7f01ea9c3b189528e845bd02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="data-source-managing-connections-odbc"></a>Veri Kaynağı: Bağlantıları Yönetme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda açıklanmaktadır:  
  
-   [Bir veri kaynağını yapılandırmak nasıl](#_core_configuring_a_data_source).  
  
-   [Çok kullanıcılı bir ortamda bir veri kaynağı ve onun kayıt kümelerini etkilemesi](#_core_working_in_a_multiuser_environment).  
  
-   [Bir veri kaynağı için bir bağlantı dizesi generalize neden](#_core_generalizing_the_connection_string).  
  
-   [Bir veri kaynağına bağlanma](#_core_connecting_to_a_specific_data_source).  
  
-   [Bir veri kaynağından bağlantıyı kesmek nasıl](#_core_disconnecting_from_a_data_source).  
  
-   [CDatabase nesnesini yeniden kullanmak nasıl](#_core_reusing_a_cdatabase_object).  
  
 Bir veri kaynağına bağlanma verilere erişmek için bir DBMS ile iletişim kurulması anlamına gelir. ODBC sürücüsü aracılığıyla bir uygulamadan bir veri kaynağına bağlandığınızda, sürücü yerel olarak ya da bir ağ üzerinden bağlantı sizin için yapar.  
  
 ODBC sürücüsü olan herhangi bir veri kaynağına bağlanabilir. Uygulamanızın kullanıcılarının, kendi veri kaynağı için aynı ODBC sürücüsü de olmalıdır. ODBC sürücüleri hakkında daha fazla bilgi için bkz: [bilgisayarınızı müşterilere ODBC bileşenleri yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a>Bir veri kaynağını yapılandırma  
 ODBC Yöneticisi, veri kaynaklarınızı yapılandırmak için kullanılır. Ayrıca yüklendikten sonra ODBC Yöneticisi eklemek veya veri kaynaklarını kaldırmak için kullanabilirsiniz. Uygulamaları oluştururken ya da kullanıcılarınızın ODBC veri kaynakları ekleyin bildirmek için yöneticinin yönlendirebilirsiniz veya doğrudan ODBC yükleme çağrıları yaparak bu işlevselliği uygulamanıza oluşturabilirsiniz. Daha fazla bilgi için bkz: [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).  
  
 Bir Excel dosyası veri kaynağı olarak kullanabilirsiniz ve böylece kaydedilir ve görünür dosya yapılandırmanıza gerek **veri kaynağı Seç** iletişim kutusu.  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>Bir Excel dosyası veri kaynağı olarak kullanmak için  
  
1.  Dosya ODBC Veri Kaynağı Yöneticisi ile yapılandırın.  
  
2.  Üzerinde **dosya DSN** sekmesini tıklatın, **Ekle**.  
  
3.  İçinde **yeni veri kaynağı oluştur** iletişim kutusu, bir Excel sürücüsünü seçin ve ardından **sonraki**.  
  
4.  Tıklatın **Gözat**ve veri kaynağı olarak kullanılacak dosya adını seçin.  
  
> [!NOTE]
>  Seçmeniz gerekebilir **tüm dosyaları** .xls dosyalarını görüntülemek için açılan menüsünde.  
  
1.  **İleri**'ye ve ardından **Son**'a tıklayın.  
  
2.  İçinde **ODBC Microsoft Excel Kurulumu** iletişim kutusunda, veritabanı sürümü ve çalışma kitabını seçin.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a>Çok kullanıcılı bir ortamda çalışma  
 Birden çok kullanıcı bir veri kaynağına bağlıysanız, kayıt kümeleri içinde düzenleme sırada bunlar verileri değiştirebilir. Benzer şekilde, değişikliklerinizi diğer kullanıcıların kayıt kümelerini etkileyebilir. Daha fazla bilgi için bkz: [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a>Bağlantı dizelerini genelleme  
 Sihirbazlar, bir veri kaynağı bağlantı kurmak için varsayılan bir bağlantı dizesi kullanır. Uygulamanızı geliştirirken tabloları ve sütunları görüntülemek için bu bağlantıyı kullanın. Ancak, bu varsayılan bağlantı dizesi, kullanıcılarınızın bağlantılar uygulamanız aracılığıyla veri kaynağı için uygun olmayabilir. Örneğin, kendi veri kaynağı ve yolun konumuna uygulamanızı geliştirmede kullanılır farklı olabilir. Bu durumda, yeniden uygulamalı [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlev daha genel bir şekilde ve sihirbaz uygulamasını atmalısınız. Örneğin, aşağıdaki yaklaşımlardan birini kullanın:  
  
-   Kaydolun ve ODBC Yöneticisi'ni kullanarak bağlantı dizelerini Yönet.  
  
-   Bağlantı dizesi düzenleyin ve veri kaynağı adı kaldırın. Framework ODBC veri kaynağı olarak sağlar; Çalışma zamanında ODBC veri kaynağı adı ve diğer gerekli bağlantı bilgilerini soran bir iletişim kutusu görüntüler.  
  
-   Yalnızca veri kaynağı adını sağlayın. ODBC kullanıcı kimliği ve parola, gerekirse sorar. Örneğin, genelleme öncesinde bağlantı dizesi şu şekildedir:  
  
    ```  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     Bu bağlantı dizesi Windows NT tümleşik güvenlik kullanan güvenilir bir bağlantı belirtir. Bir parola kodlamak kaçınmalısınız veya Bunun yapılması için boş bir parola belirterek bir önemli güvenlik zayıflık oluşturur. Bunun yerine, verebilirsiniz `GetDefaultConnect` yeni bir bağlantı dizesi böylece bir kullanıcı kimliği ve parolası sorgular.  
  
    ```  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a>Belirli bir veri kaynağına bağlanma  
 Belirli bir veri kaynağına bağlanmak için veri kaynağı zaten ile yapılandırılmış olması gerekir [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).  
  
#### <a name="to-connect-to-a-specific-data-source"></a>Belirli bir veri kaynağına bağlanmak için  
  
1.  Oluşturmak bir `CDatabase` nesnesi.  
  
2.  Çağrı kendi `OpenEx` veya **açık** üye işlevi.  
  
 Veri kaynağı Sihirbazı ile belirtilen bir dışında bir şey olması durumunda belirtme hakkında daha fazla bilgi için bkz: [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) içinde *MFC Başvuru*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a>Bir veri kaynağından bağlantıyı kesme  
 Çağırmadan önce açık tüm kayıt kümelerini kapatmalısınız **kapatmak** üye işlevini `CDatabase`. İle ilişkili kümelerinde `CDatabase` istediğiniz kapatmak, bekleyen herhangi bir nesne `AddNew` veya **Düzenle** deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır.  
  
#### <a name="to-disconnect-from-a-data-source"></a>Bir veri kaynağından bağlantıyı kesmek için  
  
1.  Çağrı `CDatabase` nesnenin [Kapat](../../mfc/reference/cdatabase-class.md#close) üye işlevi.  
  
2.  Yeniden istemediğiniz sürece nesne yok.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a>CDatabase nesnesini yeniden kullanma  
 Yeniden kullanabileceğiniz bir `CDatabase` aynı veri kaynağına bağlanmayı veya farklı bir veri kaynağına bağlanmak için kullanıp bağlantıyı kestikten sonra nesnesi.  
  
#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase nesnesini yeniden kullanmak için  
  
1.  Nesnenin orijinal bağlantısını kapatın.  
  
2.  Nesne yok etme yerine çağrı kendi `OpenEx` veya **açık** yeniden üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)   
 [Veri kaynağı: (ODBC) veri kaynağının şemasını belirleme](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)