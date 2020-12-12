---
description: 'Daha fazla bilgi edinin: Sihirbaz kullanmadan tüketici oluşturma'
title: Sihirbaz Kullanmadan bir Tüketici Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: 4c642e0b346bd9825d590f54c3de3f6536722d01
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323267"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Sihirbaz Kullanmadan bir Tüketici Oluşturma

Aşağıdaki örnek, varolan bir ATL projesine OLE DB tüketici desteği eklediğinizi varsayar. Bir MFC uygulamasına OLE DB tüketici desteği eklemek istiyorsanız, gerekli tüm desteği oluşturan ve uygulamayı yürütmek için gerekli MFC yordamlarını çağıran **MFC Uygulama Sihirbazı 'nı** çalıştırmanız gerekir.

**ATL OLE DB Tüketici Sihirbazı 'nı** kullanmadan OLE DB tüketici desteği eklemek için:

- *Pch. h* dosyanızda aşağıdaki `#include` deyimleri ekleyin:

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

Programlı olarak, bir tüketici genellikle aşağıdaki işlem dizisini gerçekleştirir:

1. Sütunları yerel değişkenlere bağlayan bir kullanıcı kayıt sınıfı oluşturun. Bu örnekte, `CMyTableNameAccessor` Kullanıcı kayıt sınıfıdır (bkz. [Kullanıcı kayıtları](../../data/oledb/user-records.md)). Bu sınıf, sütun eşlemesi ve parametre eşlemesi içerir. Sütun haritanızda belirttiğiniz her alan için Kullanıcı kayıt sınıfında bir veri üyesi bildirin; Bu veri üyelerinin her biri için, bir durum veri üyesi ve bir uzunluk veri üyesi da bildirir. Daha fazla bilgi için [Wizard-Generated Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)bölümüne bakın.

    > [!NOTE]
    > Kendi tüketicinizi yazarsanız, veri değişkenlerinin durum ve uzunluk değişkenlerinden önce gelmesi gerekir.

- Bir veri kaynağı ve oturum oluşturun. Ne tür erişimci ve satır kümesi kullanacağınızı belirleyin ve ardından [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md)kullanarak bir satır kümesi oluşturun:

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- `CoInitialize`Com başlatma çağrısı. Bu, ana kodda çağırılır. Örneğin:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- [CDataSource:: Open](./cdatasource-class.md#open) veya çeşitlerinden birini çağırın.

- Veri kaynağına bir bağlantı açın, oturumu açın ve satır kümesini açın ve başlatın (Ayrıca bir komut varsa, yürütün):

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- İsteğe bağlı olarak, kullanarak satır kümesi özelliklerini ayarlayın `CDBPropSet::AddProperty` ve bunları parametresi olarak geçirin `rs.Open` . Bunun nasıl yapıldığını gösteren bir örnek için, bkz `GetRowsetProperties` . [Tüketici Wizard-Generated yöntemleri](../../data/oledb/consumer-wizard-generated-methods.md).

- Artık verileri almak/işlemek için satır kümesini kullanabilirsiniz.

- Uygulamanız tamamlandığında, bağlantıyı, oturumu ve satır kümesini kapatın:

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   Bir komut kullanıyorsanız, daha sonra çağırmak isteyebilirsiniz `ReleaseCommand` `Close` . [CCommand:: Close](./ccommand-class.md#close) içindeki kod örneği, ve ' nin nasıl çağrılacağını gösterir `Close` `ReleaseCommand` .

- `CoUnInitialize`UNINITIALIZE com öğesine çağrı. Bu, ana kodda çağırılır.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)
