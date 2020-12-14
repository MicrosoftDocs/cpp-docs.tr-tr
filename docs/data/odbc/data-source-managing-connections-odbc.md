---
description: 'Daha fazla bilgi edinin: veri kaynağı: bağlantıları yönetme (ODBC)'
title: 'Veri Kaynağı: Bağlantıları Yönetme (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: 748e81dd82190e8269ef30983a66dc3bb5f75731
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253890"
---
# <a name="data-source-managing-connections-odbc"></a>Veri Kaynağı: Bağlantıları Yönetme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konuda aşağıdakiler açıklanmaktadır:

- [Veri kaynağını yapılandırma](#_core_configuring_a_data_source).

- [Çok kullanıcılı bir ortamın bir veri kaynağını ve kayıt kümelerini nasıl etkilediği](#_core_working_in_a_multiuser_environment).

- [Neden bir veri kaynağına bir bağlantı dizesi genelleştirdiğinizde](#_core_generalizing_the_connection_string).

- [Bir veri kaynağına bağlanma](#_core_connecting_to_a_specific_data_source).

- [Bir veri kaynağıyla bağlantısını kesme](#_core_disconnecting_from_a_data_source).

- [Bir CDatabase nesnesini yeniden kullanma](#_core_reusing_a_cdatabase_object).

Bir veri kaynağına bağlanmak, verilere erişmek için bir DBMS ile iletişim kurulması anlamına gelir. Bir ODBC sürücüsü aracılığıyla bir uygulamadan bir veri kaynağına bağlandığınızda, sürücü yerel olarak veya ağ üzerinden sizin için bağlantıyı yapar.

ODBC sürücünüze sahip olduğunuz herhangi bir veri kaynağına bağlanabilirsiniz. Uygulamanızın kullanıcıları, veri kaynakları için aynı ODBC sürücüsüne de sahip olmalıdır. ODBC sürücülerini yeniden dağıtma hakkında daha fazla bilgi için bkz. [ODBC bileşenlerini müşterilerinize yeniden dağıtma](../../data/odbc/redistributing-odbc-components-to-your-customers.md).

## <a name="configuring-a-data-source"></a><a name="_core_configuring_a_data_source"></a> Veri kaynağını yapılandırma

ODBC Yöneticisi, veri kaynaklarınızı yapılandırmak için kullanılır. Veri kaynaklarını eklemek veya kaldırmak için yüklemeden sonra ODBC Yöneticisi 'ni de kullanabilirsiniz. Uygulama oluştururken, kullanıcılarınızı veri kaynakları eklemesine izin vermek için ODBC yöneticisine yönlendirebilirsiniz veya doğrudan ODBC yükleme çağrıları yaparak uygulamanızda bu işlevselliği oluşturabilirsiniz. Daha fazla bilgi için bkz. [ODBC Yöneticisi](../../data/odbc/odbc-administrator.md).

Bir Excel dosyasını veri kaynağı olarak kullanabilirsiniz ve dosyayı kayıtlı olacak şekilde yapılandırmanız ve **veri kaynağı seç** iletişim kutusunda görünmesi gerekir.

#### <a name="to-use-an-excel-file-as-a-data-source"></a>Bir Excel dosyasını veri kaynağı olarak kullanmak için

1. Dosyayı ODBC veri kaynağı Yöneticisi ile yapılandırın.

1. **Dosya DSN** sekmesinde **Ekle**' ye tıklayın.

1. **Yeni veri kaynağı oluştur** iletişim kutusunda bir Excel sürücüsü seçin ve ardından **İleri**' ye tıklayın.

1. **Araştır**' a tıklayın ve bir tarih kaynağı olarak kullanılacak dosyanın adını seçin.

> [!NOTE]
> . Xls dosyalarını görüntülemek için açılan menüdeki **tüm dosyalar** ' ı seçmeniz gerekebilir.

1. **İleri**’ye ve ardından **Son**’a tıklayın.

1. **ODBC Microsoft Excel kurulumu** iletişim kutusunda veritabanı sürümünü ve çalışma kitabını seçin.

## <a name="working-in-a-multiuser-environment"></a><a name="_core_working_in_a_multiuser_environment"></a> Çok kullanıcılı bir ortamda çalışma

Birden çok kullanıcı bir veri kaynağına bağlıysa, kayıt kümelerinizi değiştirirken verileri değiştirebilirler. Benzer şekilde, değişiklikleriniz diğer kullanıcıların kayıt kümelerini etkileyebilir. Daha fazla bilgi için bkz. [Recordset: kayıt kümeleri kayıtları güncelleştirme (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) ve [işlem (ODBC)](../../data/odbc/transaction-odbc.md).

## <a name="generalizing-the-connection-string"></a><a name="_core_generalizing_the_connection_string"></a> Bağlantı dizesi genelleştiriliyor

Sihirbazlar bir veri kaynağıyla bağlantı kurmak için varsayılan bir bağlantı dizesi kullanır. Uygulamanızı geliştirirken tabloları ve sütunları görüntülemek için bu bağlantıyı kullanın. Ancak, bu varsayılan bağlantı dizesi, kullanıcılarınızın uygulamanız aracılığıyla veri kaynağıyla bağlantıları için uygun olmayabilir. Örneğin, veri kaynakları ve konumunun yolu, uygulamanızı geliştirmede kullanılan verilerden farklı olabilir. Bu durumda, [CRecordset:: GetDefaultConnect](../../mfc/reference/crecordset-class.md#getdefaultconnect) üye işlevini daha genel bir biçimde yeniden uygulamanız ve sihirbaz uygulamasını atmanız gerekir. Örneğin, aşağıdaki yaklaşımlardan birini kullanın:

- ODBC Yöneticisi 'ni kullanarak bağlantı dizelerini kaydedin ve yönetin.

- Bağlantı dizesini düzenleyin ve veri kaynağı adını kaldırın. Framework, veri kaynağı olarak ODBC sağlar; çalışma zamanında ODBC, veri kaynağı adı ve diğer gerekli bağlantı bilgilerini soran bir iletişim kutusu görüntüler.

- Yalnızca veri kaynağı adını sağlayın. ODBC, gerekirse kullanıcı KIMLIĞINI ve parolayı ister. Örneğin, genelleştirmeye başlamadan önce bağlantı dizesi şöyle görünür:

    ```cpp
    CString CApp1Set::GetDefaultConnect()
    {
       return "ODBC;DSN=afx;Trusted_Connection=Yes;";
    }
    ```

   Bu bağlantı dizesi, Windows NT tümleşik güvenliğini kullanan güvenilir bir bağlantı belirtir. Bir parolanın sabit kodlanmasını veya boş bir parola belirtmekten kaçının, çünkü bu durum önemli bir güvenlik zayıflılığını oluşturuyor. Bunun yerine, `GetDefaultConnect` bir kullanıcı kimliği ve parola sorgulaması için yeni bir bağlantı dizesi verebilirsiniz.

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

## <a name="connecting-to-a-specific-data-source"></a><a name="_core_connecting_to_a_specific_data_source"></a> Belirli bir veri kaynağına bağlanma

Belirli bir veri kaynağına bağlanmak için veri kaynağınız [ODBC yöneticisiyle](../../data/odbc/odbc-administrator.md)zaten yapılandırılmış olmalıdır.

#### <a name="to-connect-to-a-specific-data-source"></a>Belirli bir veri kaynağına bağlanmak için

1. Bir `CDatabase` nesne oluşturun.

1. `OpenEx`Veya `Open` üye işlevini çağırın.

Veri kaynağının, sihirbazla belirtenden başka bir şey olması halinde belirtilmesi hakkında daha fazla bilgi için *MFC başvurusunda* bkz. [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) veya [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) .

## <a name="disconnecting-from-a-data-source"></a><a name="_core_disconnecting_from_a_data_source"></a> Veri kaynağı bağlantısı kesiliyor

Üye işlevini çağırmadan önce açık olan tüm kayıt kümelerini kapatmanız gerekir `Close` `CDatabase` . Kapatmak istediğiniz nesneyle ilişkili kayıt kümelerinde `CDatabase` , bekleyen `AddNew` veya `Edit` deyimleri iptal edilir ve tüm bekleyen işlemler geri alınır.

#### <a name="to-disconnect-from-a-data-source"></a>Bir veri kaynağıyla bağlantısını kesmek için

1. `CDatabase`Nesnenin [Close](../../mfc/reference/cdatabase-class.md#close) üye işlevini çağırın.

1. Yeniden kullanmak istemediğiniz müddetçe nesneyi yok edin.

## <a name="reusing-a-cdatabase-object"></a><a name="_core_reusing_a_cdatabase_object"></a> Bir CDatabase nesnesini yeniden kullanma

`CDatabase`Aynı veri kaynağına yeniden bağlanmak veya farklı bir veri kaynağına bağlanmak için kullanıp kullanmayacağınızı, bağlantısını kestikten sonra bir nesneyi yeniden kullanabilirsiniz.

#### <a name="to-reuse-a-cdatabase-object"></a>Bir CDatabase nesnesini yeniden kullanmak için

1. Nesnenin özgün bağlantısını kapatın.

1. Nesneyi yok etmek yerine, `OpenEx` veya `Open` üye işlevini yeniden çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Veri kaynağı (ODBC)](../../data/odbc/data-source-odbc.md)<br/>
[Veri kaynağı: veri kaynağının şemasını belirleme (ODBC)](../../data/odbc/data-source-determining-the-schema-of-the-data-source-odbc.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
