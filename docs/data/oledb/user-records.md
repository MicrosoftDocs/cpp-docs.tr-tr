---
title: Kullanıcı Kayıtları
ms.date: 05/09/2019
f1_keywords:
- COLUMN_ENTRY_MAP
helpviewer_keywords:
- rowsets [C++], accessors
- COLUMN_ENTRY macro
- COLUMN_ENTRY_MAP macro
- user records, OLE DB consumer templates
- OLE DB consumer templates, user records
- CAccessor class, example
- BEGIN_ACCESSOR_MAP macro
- accessors [C++], rowsets
- accessors [C++], static
- BEGIN_ACCESSOR macro, example
ms.assetid: 2de9e5eb-53ce-42b1-80fa-57d46600a80c
ms.openlocfilehash: 94a70b48793d44eda4fd76d9b59460418cfbc032
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209449"
---
# <a name="user-records"></a>Kullanıcı Kayıtları

> [!NOTE]
> ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](creating-a-consumer-without-using-a-wizard.md).

Statik bir erişimci (yani `CAccessor`türetilen bir erişimci) kullanmak için tüketicinizin bir kullanıcı kaydına sahip olması gerekir. Kullanıcı kaydı, girişi veya C++ çıktıyı işlemek için veri öğeleri içeren bir sınıftır. **ATL OLE DB Tüketici Sihirbazı** tüketicinizin Kullanıcı kaydını oluşturur. Komutları işlemek gibi isteğe bağlı görevler için kullanıcı kaydına Yöntemler ekleyebilirsiniz.

Aşağıdaki kod, komutları işleyen bir örnek kayıt gösterir. Kullanıcı kaydında BEGIN_COLUMN_MAP, bir sağlayıcıdan tüketiciye geçirilen bir veri satır kümesini temsil eder. BEGIN_PARAM_MAP bir komut parametreleri kümesini temsil eder. Bu örnek, komut parametrelerini işlemek için bir [CCommand](../../data/oledb/ccommand-class.md) sınıfı kullanır. Harita girdilerindeki veri üyeleri, sınıfın her örneği için bir bitişik bellek öbeğiyle uzaklıkları temsil eder. COLUMN_ENTRY makroları sağlayıcı tarafındaki PROVIDER_COLUMN_ENTRY makrolara karşılık gelir.

COLUMN_MAP ve PARAM_MAP makroları hakkında daha fazla bilgi için bkz. [OLE DB tüketici şablonları Için makrolar](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md).

```cpp
class CArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_COLUMN_MAP(CArtists)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
   COLUMN_ENTRY(3, m_nAge)
END_COLUMN_MAP()

// Parameter binding map
BEGIN_PARAM_MAP(CArtists)
   COLUMN_ENTRY(1, m_nAge)
END_PARAM_MAP()
};
```

## <a name="wizard-generated-user-records"></a>Sihirbaz tarafından oluşturulan kullanıcı kayıtları

Bir tüketici oluşturmak için **ATL OLE DB Tüketici Sihirbazı 'nı** kullanıyorsanız, OLE DB şablonlarını veya OLE DB özniteliklerini kullanma seçeneğiniz vardır. Oluşturulan kod her durumda farklı olur. Bu kod hakkında daha fazla bilgi için bkz. [Tüketici Sihirbazı tarafından oluşturulan sınıflar](../../data/oledb/consumer-wizard-generated-classes.md).

## <a name="user-record-support-for-multiple-accessors"></a>Birden çok erişimci için Kullanıcı kaydı desteği

Birden çok erişimci kullanmanız gereken senaryolara ilişkin ayrıntılı bir tartışma için bkz. [bir satır kümesinde birden çok erişimci kullanma](../../data/oledb/using-multiple-accessors-on-a-rowset.md).

Aşağıdaki örnek, satır kümesinde birden çok erişimciyi destekleyecek şekilde değiştirilen Kullanıcı kaydını gösterir. BEGIN_COLUMN_MAP ve END_COLUMN_MAP yerine, her erişimci için [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md) ve [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) kullanır. BEGIN_ACCESSOR makrosu, erişimci numarasını (sıfırdan uzaklığa) ve erişimcinin bir oto erişimcisi olup olmadığını belirtir. Otomatik erişimciler, [MoveNext](../../data/oledb/crowset-movenext.md)çağrısına verileri otomatik olarak almak için `GetData` çağırır. Otomatik olmayan erişimciler, verileri açıkça almanızı gerektirir. Her kayıt için almak istemediğiniz büyük bir veri alanına (bir bit eşlem resmi gibi) bağlıyorsanız, otomatik olmayan bir erişimci kullanın.

```cpp
class CMultiArtists
{
public:
// Data Elements
   CHAR m_szFirstName[20];
   CHAR m_szLastName[30];
   short m_nAge;

// Column binding map
BEGIN_ACCESSOR_MAP(CMultiArtists, 2)
   BEGIN_ACCESSOR(0, true)    // true specifies an auto accessor
    COLUMN_ENTRY(1, m_szFirstName)
    COLUMN_ENTRY(2, m_szLastName)
   END_ACCESSOR()
   BEGIN_ACCESSOR(1, false)   // false specifies a manual accessor
    COLUMN_ENTRY(3, m_nAge)
   END_ACCESSOR()
END_ACCESSOR_MAP()
};
```

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)
