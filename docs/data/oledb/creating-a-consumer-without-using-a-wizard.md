---
title: Sihirbaz kullanmadan bir tüketici oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c9f6bbc1ba45ec0b510dac015688fd29801c8449
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Sihirbaz Kullanmadan bir Tüketici Oluşturma
Aşağıdaki örnek, varolan bir ATL projesine OLE DB tüketici desteği ekleme varsayar. OLE DB tüketici desteği, MFC Uygulama eklemek istiyorsanız, tüm destek gerekli oluşturan ve MFC yordamları uygulamasını çalıştırmak gerekli çağırır MFC Uygulama Sihirbazı çalıştırmanız gerekir.  
  
 ATL OLE DB Tüketici Sihirbazı'nı kullanmadan OLE DB tüketici desteği eklemek için:  
  
-   Aşağıdaki Stdafx.h dosyanıza ekleme `#include` deyimleri:  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 Program aracılığıyla, bir tüketici genellikle sırayla aşağıdaki işlemleri gerçekleştirir:  
  
-   Sütunları yerel değişkenlere bağlayan bir kullanıcı kaydı sınıfı oluşturun. Bu örnekte, `CMyTableNameAccessor` kullanıcı kayıt sınıfı (bkz [kullanıcı kayıtlarını](../../data/oledb/user-records.md)). Bu sınıf, sütun ve parametre eşlemesi içerir. Sütun eşlemesinde belirttiğiniz her bir alan için kullanıcı kayıt sınıfı veri üyesi bildirin; Her bu veri üyeleri için de bir durum veri üyesi ve uzunluk veri üyesi bildirin. Daha fazla bilgi için bkz: [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
    > [!NOTE]
    >  Kendi tüketici yazarsanız, veri değişkenleri durum ve uzunluk değişkenlerinden önce gelmelidir.  
  
-   Bir veri kaynağı ve oturum başlatır. Ne tür erişimci ve satır kümesi kullanın ve sonra bir satır kullanma örneği karar [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md):  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>  
    ```  
  
-   Çağrı **CoInitialize** COM başlatılamadı Bu, genellikle ana kodda çağrılır. Örneğin:  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   Çağrı [CDataSource::Open](../../data/oledb/cdatasource-open.md) veya kendi Çeşitlemeler biri.  
  
-   Veri kaynağı bir bağlantı açmak, oturumu açın ve açın ve satır başlatmak (ve ayrıca bir komutu Yürüt):  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   İsteğe bağlı olarak, kullanarak kümesi satır kümesi özelliklerini `CDBPropSet::AddProperty` ve bunları bir parametre olarak geçirmek `rs.Open`. GetRowsetProperties bunun nasıl yapılacağı ilişkin bir örnek için bkz: [Tüketici Sihirbazı tarafından oluşturulan yöntemler](../../data/oledb/consumer-wizard-generated-methods.md).  
  
-   Satır kümesi artık verileri almak/işlemek için de kullanabilirsiniz.  
  
-   Uygulamanızı işiniz bittiğinde, bağlantı, oturum ve satır kümesi kapatın:  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     Bir komut kullanıyorsanız, aramak istediğiniz `ReleaseCommand` sonra **Kapat**. Aşağıdaki kod örneğinde [CCommand::Close](../../data/oledb/ccommand-close.md) nasıl çağrılacağını gösterir **Kapat** ve `ReleaseCommand`.  
  
-   Çağrı **CoUnInitialize** COM'u kapatmak için Bu, genellikle ana kodda çağrılır.  
  
    ```  
    CoUninitialize();  
    ```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)