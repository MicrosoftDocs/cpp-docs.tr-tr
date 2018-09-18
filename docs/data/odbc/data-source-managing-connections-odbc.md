---
title: 'Veri kaynağı: Bağlantıları yönetme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: a8f5a57b1ef97b38b6756931038ec18045aea746
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053732"
---
# <a name="data-source-managing-connections-odbc"></a>Veri Kaynağı: Bağlantıları Yönetme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.  
  
Bu konu şunları açıklar:  
  
- [Bir veri kaynağı yapılandırma](#_core_configuring_a_data_source).  
  
- [Çok kullanıcılı bir ortamda, bir veri kaynağı ve onun kayıt kümelerini nasıl etkilediğini](#_core_working_in_a_multiuser_environment).  
  
- [Bir veri kaynağı bağlantı dizesi generalize neden](#_core_generalizing_the_connection_string).  
  
- [Bir veri kaynağına bağlanma](#_core_connecting_to_a_specific_data_source).  
  
- [Bir veri kaynağından bağlantısını kesmek nasıl](#_core_disconnecting_from_a_data_source).  
  
- [CDatabase nesnesi nasıl yeniden](#_core_reusing_a_cdatabase_object).  
  
Bir veri kaynağına bağlanmak, verilere erişmek için DBMS ile iletişim kurulması anlamına gelir. ODBC sürücüsü aracılığıyla bir uygulamadan bir veri kaynağına bağlandığınızda, sürücü yerel olarak ya da bir ağ üzerinden bağlantı sizin için yapar.  
  
ODBC sürücüsü olan herhangi bir veri kaynağına bağlanabilirsiniz. Uygulamanızın kullanıcılarının ayrıca veri kaynakları için aynı ODBC sürücüsüne sahip olmalıdır. ODBC sürücülerini yeniden dağıtma hakkında daha fazla bilgi için bkz. [ODBC bileşenlerini müşterilerinize yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md).  
  
##  <a name="_core_configuring_a_data_source"></a> Bir veri kaynağını yapılandırma  

ODBC Yöneticisi veri kaynaklarınızı yapılandırmak için kullanılır. Veri kaynakları ekleyip için yüklemeden sonra ODBC Yöneticisi de kullanabilirsiniz. Uygulamalar oluşturduğunuzda, kullanıcılarınızın ODBC veri kaynakları eklemeleri izin vermek için yöneticinin ya da yönlendirebilir veya doğrudan ODBC yükleme çağrıları yaparak bu işlevselliği uygulamanıza oluşturabilirsiniz. Daha fazla bilgi için [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).  
  
Bir Excel dosyasını veri kaynağı olarak kullanabilirsiniz ve kayıtlı ve görünür olacak şekilde yapılandırmanız gerekir **veri kaynağı Seç** iletişim kutusu.  
  
#### <a name="to-use-an-excel-file-as-a-data-source"></a>Bir Excel dosyası veri kaynağı olarak kullanmak için  
  
1. Dosya, ODBC Veri Kaynağı Yöneticisi ile yapılandırın.  
  
1. Üzerinde **DSN dosyası** sekmesinde **Ekle**.  
  
1. İçinde **yeni veri kaynağı oluştur** iletişim kutusu, bir Excel sürücüsünü seçin ve ardından **sonraki**.  
  
1. Tıklayın **Gözat**ve veri kaynağı olarak kullanılacak dosya adını seçin.  
  
> [!NOTE]
>  Seçmeniz gerekebilir **tüm dosyaları** .xls dosyalarını görüntülemek için açılan menüsünde.  
  
1. **İleri**'ye ve ardından **Son**'a tıklayın.  
  
1. İçinde **ODBC Microsoft Excel Kurulumu** iletişim kutusunda, veritabanı sürümünü ve çalışma kitabını seçin.  
  
##  <a name="_core_working_in_a_multiuser_environment"></a> Çok kullanıcılı bir ortamda çalışma  

Birden çok kullanıcı bir veri kaynağına bağlanırsa, kayıt kümeleri içinde düzenleme ancak bunlar veri değiştirebilirsiniz. Benzer şekilde, değişiklikleriniz diğer kullanıcıların kayıt kümeleri etkileyebilir. Daha fazla bilgi için [kayıt kümesi: nasıl kayıt kümelerini güncelleştirme kayıtları (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [işlem (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_generalizing_the_connection_string"></a> Bağlantı dizelerini genelleme  

Sihirbazlar bir veri kaynağına bağlantı kurmak için varsayılan bağlantı dizesi kullanır. Uygulamanızı geliştirdiğiniz sırada tabloları ve sütunları görüntülemek için bu bağlantıyı kullanın. Ancak, bu varsayılan bağlantı dizesi kullanıcılarınızın uygulamanız aracılığıyla veri kaynağı bağlantıları için uygun olmayabilir. Örneğin, veri kaynağı ve konumuna yol uygulamanızı geliştirmede kullanılandan farklı olabilir. Bu durumda, yeniden uygulayın [CRecordset::GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevini daha genel bir şekilde ve sihirbaz uygulamasını atmalısınız. Örneğin, aşağıdaki yaklaşımlardan birini kullanın:  
  
- Kaydolun ve bağlantı dizelerini ODBC Yöneticisi'ni kullanarak yönetin.  
  
- Bağlantı düzesini düzenleyin ve veri kaynağı adını kaldırın. Framework ODBC veri kaynağı olarak sağlar; Çalışma zamanında, ODBC veri kaynağı adını ve diğer gerekli bağlantı bilgilerini soran bir iletişim kutusu görüntüler.  
  
- Yalnızca veri kaynağı adını sağlayın. ODBC gerekirse kullanıcı Kimliğini ve parolasını ister. Örneğin, Genelleştirme önce bağlantı dizesi şuna benzer:  
  
    ```cpp  
    CString CApp1Set::GetDefaultConnect()  
    {  
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";  
    }  
    ```  
  
     Bu bağlantı dizesi, Windows NT tümleşik güvenliğini kullanan güvenilir bir bağlantı belirtir. Bir parola sabit kodlama kaçınmanız gerekir ya da boş parola belirlemekten belirten bir önemli güvenlik açığına oluşturur. Bunun yerine, verebilirsiniz `GetDefaultConnect` yeni bir bağlantı dizesi bir kullanıcı kimliği ve parolası sorgular.  
  
    ```cpp  
    // User must select data source and supply user ID and password:  
        return "ODBC;";  
    // User ID and password required:  
        return "ODBC;DSN=mydb;";  
    // Password required (myuserid must be replaced with a valid user ID):  
        return "ODBC;DSN=mydb;UID=myuserid;";  
    // Hard-coded user ID and password (SECURITY WEAKNESS--AVOID):  
        return "ODBC;DSN=mydb;UID=sa;PWD=777;";  
    ```  
  
##  <a name="_core_connecting_to_a_specific_data_source"></a> Belirli bir veri kaynağına bağlanma  

Belirli bir veri kaynağına bağlanmak için veri kaynağınızın zaten ile yapılandırılmış olması gerekir [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).  
  
#### <a name="to-connect-to-a-specific-data-source"></a>Belirli bir veri kaynağına bağlanmak için  
  
1. Oluşturmak bir `CDatabase` nesne.  
  
1. Çağrı, `OpenEx` veya `Open` üye işlevi.  
  
Veri kaynağını sihirbaz ile belirtilen dışında bir şey ise belirtme hakkında daha fazla bilgi için bkz. [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) içinde *MFC Başvuru*.  
  
##  <a name="_core_disconnecting_from_a_data_source"></a> Bir veri kaynağı bağlantısını kesme  

Çağırmadan önce açık tüm kayıt kümelerini kapatmalısınız `Close` üye işlevini `CDatabase`. İle ilişkili kayıt kümelerinde `CDatabase` kapatmak istediğinizden, bekleyen herhangi bir nesne `AddNew` veya `Edit` deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır.  
  
#### <a name="to-disconnect-from-a-data-source"></a>Bir veri kaynağından bağlantısını kesmek için  
  
1. Çağrı `CDatabase` nesnenin [Kapat](../../mfc/reference/cdatabase-class.md#close) üye işlevi.  
  
1. Yeniden kullanmak istemiyorsanız nesneyi yok edin.  
  
##  <a name="_core_reusing_a_cdatabase_object"></a> CDatabase nesnesini yeniden kullanma  

Yeniden kullanabileceğiniz bir `CDatabase` aynı veri kaynağına yeniden bağlanmak veya farklı veri kaynağına bağlanmak için kullanıp kestikten sonra nesne.  
  
#### <a name="to-reuse-a-cdatabase-object"></a>CDatabase nesnesini yeniden kullanmak için  
  
1. Nesnenin orijinal bağlantısını kapatın.  
  
1. Çağrı nesneyi yok etmek yerine kendi `OpenEx` veya `Open` yeniden üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Veri Kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Veri Kaynağı: Veri Kaynağının Şemasını Belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)