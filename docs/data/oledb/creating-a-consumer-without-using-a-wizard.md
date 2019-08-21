---
title: Sihirbaz Kullanmadan bir Tüketici Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: 85e95afa92c8a968865d9a3031e1a309e68ae7d3
ms.sourcegitcommit: 9d4ffb8e6e0d70520a1e1a77805785878d445b8a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/20/2019
ms.locfileid: "69630756"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Sihirbaz Kullanmadan bir Tüketici Oluşturma

Aşağıdaki örnek, varolan bir ATL projesine OLE DB tüketici desteği eklediğinizi varsayar. Bir MFC uygulamasına OLE DB tüketici desteği eklemek istiyorsanız, gerekli tüm desteği oluşturan ve uygulamayı yürütmek için gerekli MFC yordamlarını çağıran **MFC Uygulama Sihirbazı 'nı**çalıştırmanız gerekir.

**ATL OLE DB Tüketici Sihirbazı 'nı**kullanmadan OLE DB tüketici desteği eklemek için:

- *Pch. h* dosyanızda aşağıdaki `#include` deyimleri ekleyin:

    ```cpp
    #include <atlbase.h>
    #include <atldbcli.h>
    #include <atldbsch.h> // if you are using schema templates
    ```

Programlı olarak, bir tüketici genellikle aşağıdaki işlem dizisini gerçekleştirir:

1. Sütunları yerel değişkenlere bağlayan bir kullanıcı kayıt sınıfı oluşturun. Bu örnekte, `CMyTableNameAccessor` Kullanıcı kayıt sınıfıdır (bkz. [Kullanıcı kayıtları](../../data/oledb/user-records.md)). Bu sınıf, sütun eşlemesi ve parametre eşlemesi içerir. Sütun haritanızda belirttiğiniz her alan için Kullanıcı kayıt sınıfında bir veri üyesi bildirin; Bu veri üyelerinin her biri için, bir durum veri üyesi ve bir uzunluk veri üyesi da bildirir. Daha fazla bilgi için, bkz. [sihirbaz tarafından oluşturulan Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

    > [!NOTE]
    > Kendi tüketicinizi yazarsanız, veri değişkenlerinin durum ve uzunluk değişkenlerinden önce gelmesi gerekir.

- Bir veri kaynağı ve oturum oluşturun. Ne tür erişimci ve satır kümesi kullanacağınızı belirleyin ve ardından [CCommand](../../data/oledb/ccommand-class.md) veya [CTable](../../data/oledb/ctable-class.md)kullanarak bir satır kümesi oluşturun:

    ```cpp
    CDataSource ds;
    CSession ss;
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor>>
    ```

- COM `CoInitialize` başlatma çağrısı. Bu, ana kodda çağırılır. Örneğin:

    ```cpp
    HRESULT hr = CoInitialize(NULL);
    ```

- [CDataSource:: Open](../../data/oledb/cdatasource-open.md) veya çeşitlerinden birini çağırın.

- Veri kaynağına bir bağlantı açın, oturumu açın ve satır kümesini açın ve başlatın (Ayrıca bir komut varsa, yürütün):

    ```cpp
    hr = ds.Open();
    hr = ss.Open(ds);
    hr = rs.Open();            // (Open also executes the command)
    ```

- İsteğe bağlı olarak, kullanarak `CDBPropSet::AddProperty` satır kümesi özelliklerini ayarlayın ve bunları `rs.Open`parametresi olarak geçirin. Bunun nasıl yapıldığını gösteren bir örnek için, bkz `GetRowsetProperties` . [Tüketici Sihirbazı tarafından oluşturulan Yöntemler](../../data/oledb/consumer-wizard-generated-methods.md).

- Artık verileri almak/işlemek için satır kümesini kullanabilirsiniz.

- Uygulamanız tamamlandığında, bağlantıyı, oturumu ve satır kümesini kapatın:

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   Bir komut kullanıyorsanız, daha sonra `ReleaseCommand` `Close`çağırmak isteyebilirsiniz. [CCommand:: Close](../../data/oledb/ccommand-close.md) içindeki kod örneği, ve ' `Close` `ReleaseCommand`nin nasıl çağrılacağını gösterir.

- Uninitialize `CoUnInitialize` com öğesine çağrı. Bu, ana kodda çağırılır.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)