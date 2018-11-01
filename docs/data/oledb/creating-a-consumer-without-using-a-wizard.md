---
title: Sihirbaz Kullanmadan bir Tüketici Oluşturma
ms.date: 10/12/2018
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: a4b95674c2c9c6f0a5dae29e68cff44c759e0fa9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578613"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Sihirbaz Kullanmadan bir Tüketici Oluşturma

Aşağıdaki örnek, varolan bir ATL projesine OLE DB tüketici desteği ekliyoruz varsayar. OLE DB tüketici desteği, MFC Uygulama eklemek istiyorsanız, çalıştırmalısınız **MFC Uygulama Sihirbazı**, gerekli tüm destek oluşturur ve yordamları MFC uygulamasını çalıştırmak gerekli çağırır.

OLE DB tüketici desteği olmadan eklemek için **ATL OLE DB Tüketicisi Sihirbazı**:

- Pch.h dosyanızda aşağıdaki ekleme `#include` ifadeleri:

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

Program aracılığıyla, bir tüketici genellikle sırasıyla aşağıdaki işlemleri gerçekleştirir:

1. Yerel değişkenlere sütunları bağlayan bir kullanıcı kaydı sınıfı oluşturun. Bu örnekte, `CMyTableNameAccessor` kullanıcı kayıt sınıftır (bkz [kullanıcı kayıtlarını](../../data/oledb/user-records.md)). Bu sınıf sütun haritasında ve parametre eşlemesi içerir. Kullanıcı kayıt sınıfı, sütun eşlemesinde belirttiğiniz her bir alan için veri üyesi bildirme; her biri bu veri üyeleri için de bir durum veri üyesi ve uzunluk veri üyesi bildirin. Daha fazla bilgi için [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

    > [!NOTE]
    > Kendi tüketici yazarsanız verisi değişkenleri durum ve uzunluğu değişkenlerinin önce gelmelidir.

- Bir veri kaynağı ile bir oturumu örneği oluşturur. Ardından bir satır kümesi kullanarak örneği oluşturmak ve kullanmak için ne tür erişimci ve satır kümesi karar [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md):

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- Çağrı `CoInitialize` COM başlatılamadı Bu, ana kod adı verilir. Örneğin:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- Çağrı [CDataSource::Open](../../data/oledb/cdatasource-open.md) veya türevlerini biri.

- Veri kaynağı için bir bağlantı açmak, oturumu açın ve açın ve satır başlatmak (ve ayrıca bir komutu yürütme):

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- Kullanarak isteğe bağlı olarak satır kümesi özelliklerini ayarlama `CDBPropSet::AddProperty` ve parametre olarak geçirileceğini `rs.Open`. Bunun nasıl yapıldığına bir örnek için bkz `GetRowsetProperties` içinde [Tüketici Sihirbazı tarafından oluşturulan yöntemler](../../data/oledb/consumer-wizard-generated-methods.md).

- Satır kümesi, verileri almak/işlemek için artık kullanabilirsiniz.

- Uygulamanızı işiniz bittiğinde, bağlantı, oturum ve satır kümesi kapatın:

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   Bir komut kullanıyorsanız çağırmak isteyebilirsiniz `ReleaseCommand` sonra `Close`. Aşağıdaki kod örneğinde [CCommand::Close](../../data/oledb/ccommand-close.md) nasıl çağrılacağını gösterir `Close` ve `ReleaseCommand`.

- Çağrı `CoUnInitialize` COM'u kapatmak için Bu, ana kod adı verilir.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)