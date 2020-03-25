---
title: Sihirbaz Kullanmadan bir Tüketici Oluşturma
ms.date: 05/09/2019
helpviewer_keywords:
- OLE DB consumers, creating
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
ms.openlocfilehash: fff4146681e31f0f1fea9fbaa559de7c722740d2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211464"
---
# <a name="creating-a-consumer-without-using-a-wizard"></a>Sihirbaz Kullanmadan bir Tüketici Oluşturma

Aşağıdaki örnek, varolan bir ATL projesine OLE DB tüketici desteği eklediğinizi varsayar. Bir MFC uygulamasına OLE DB tüketici desteği eklemek istiyorsanız, gerekli tüm desteği oluşturan ve uygulamayı yürütmek için gerekli MFC yordamlarını çağıran **MFC Uygulama Sihirbazı 'nı**çalıştırmanız gerekir.

**ATL OLE DB Tüketici Sihirbazı 'nı**kullanmadan OLE DB tüketici desteği eklemek için:

- *Pch. h* dosyanızda aşağıdaki `#include` deyimlerini ekleyin:

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

- COM başlatmak için `CoInitialize` çağırın. Bu, ana kodda çağırılır. Örneğin:

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

- İsteğe bağlı olarak, `CDBPropSet::AddProperty` kullanarak satır kümesi özelliklerini ayarlayın ve `rs.Open`bir parametre olarak geçirin. Bunun nasıl yapıldığını gösteren bir örnek için bkz. [Tüketici Sihirbazı tarafından oluşturulan yöntemler](../../data/oledb/consumer-wizard-generated-methods.md)`GetRowsetProperties`.

- Artık verileri almak/işlemek için satır kümesini kullanabilirsiniz.

- Uygulamanız tamamlandığında, bağlantıyı, oturumu ve satır kümesini kapatın:

    ```cpp
    rs.Close();
    ss.Close();
    ds.Close();
    ```

   Bir komut kullanıyorsanız, `Close`sonra `ReleaseCommand` çağırmak isteyebilirsiniz. [CCommand:: Close](../../data/oledb/ccommand-close.md) içindeki kod örneği, `Close` ve `ReleaseCommand`nasıl çağrılacağını gösterir.

- Uninitialize COM 'a `CoUnInitialize` çağırın. Bu, ana kodda çağırılır.

    ```cpp
    CoUninitialize();
    ```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer.md)
