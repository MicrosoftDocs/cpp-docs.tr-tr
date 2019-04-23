---
title: Tüketici Sihirbazı Tarafından Oluşturulan Sınıflar
ms.date: 10/17/2018
helpviewer_keywords:
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- command classes in OLE DB consumer
- classes [C++], OLE DB Consumer Wizard-generated
- consumer wizard-generated classes and methods
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
ms.openlocfilehash: 7cd1fbe69186a2fcdbf25f1b2aa12727c98065da
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59036425"
---
# <a name="consumer-wizard-generated-classes"></a>Tüketici Sihirbazı Tarafından Oluşturulan Sınıflar

Kullanırken **ATL OLE DB Tüketicisi Sihirbazı** tüketici oluşturmak için OLE DB Şablonları ya da OLE DB öznitelikleri kullanma seçeneğiniz vardır. Her iki durumda da sihirbaz bir komutu ve bir kullanıcı kaydı sınıfı oluşturur. Komut sınıfı Sihirbazı'nda belirtilen satır kümesi ve veri kaynağını açmak için kodu içerir. Sütun eşlemesi, seçtiğiniz veritabanı tablosu için kullanıcı kayıt sınıfı içerir. Ancak, oluşturulan kod her durumda farklıdır:

- Şablonlu bir tüketici seçerseniz, sihirbazın bir komutu ve bir kullanıcı kaydı sınıfı oluşturur. Komut sınıfının girdiğiniz ada sahip olacaktır **sınıfı** sihirbazda kutusunda (örneğin, `CProducts`), ve kullanıcı kayıt sınıfı bir adı olacaktır "*ClassName*erişimci" (örneğin, `CProductsAccessor`). Her iki sınıfları, tüketicinin üstbilgi dosyasında yerleştirilir.

- Öznitelikli bir tüketici seçerseniz, kullanıcı kayıt sınıfı bir adı olacaktır "_*ClassName*erişimci" ve eklenecek. Diğer bir deyişle, yalnızca komut sınıfı Metin Düzenleyicisi'nde görüntülemek mümkün olacaktır; Kullanıcı kayıt sınıfı eklenen kodu yalnızca görüntüleyebilir. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

Aşağıdaki örneklerde oluşturulan komut sınıfı `Products` tablosu `Northwind` komut ve kullanıcı kayıt sınıfı Tüketici Sihirbazı tarafından oluşturulan kodu göstermek için veritabanı.

## <a name="templated-user-record-classes"></a>Şablonlu kullanıcı kayıt sınıfları

OLE DB Şablonları (OLE DB öznitelikleri yerine) kullanarak bir OLE DB Tüketicisi Oluşturma, sihirbaz bu bölümde açıklanan şekilde kod oluşturur.

### <a name="column-data-members"></a>Sütun veri üyeleri

Kullanıcı kayıt sınıfı ilk bölümü, veri üye bildirimleri ve verilere bağlı her sütun için durumu ve uzunluğu veri üyeleri içerir. Bu veri üyeleri hakkında daha fazla bilgi için bkz: [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

> [!NOTE]
> Kullanıcı kayıt sınıfı değiştirin ya da kendi tüketici yazma, verileri değişkenleri durum ve uzunluğu değişkenlerinden önce gelmelidir.

> [!NOTE]
> ATL OLE DB Tüketicisi Sihirbazı kullanır `DB_NUMERIC` sayısal veri türleri bağlamak için türü. Eski adıyla kullanılır `DBTYPE_VARNUMERIC` (biçimi tarafından açıklanan `DB_VARNUMERIC` yazın; biçim bakın). Tüketiciler oluşturmak için Sihirbazı kullanmazsanız kullanmanız önerilir `DB_NUMERIC`.

```cpp
// Products.H : Declaration of the CProducts class

class CProductsAccessor
{
public:
   // Column data members:
   LONG m_ProductID;
   TCHAR m_ProductName[41];
   LONG m_SupplierID;
   LONG m_CategoryID;
   TCHAR m_QuantityPerUnit[21];
   CURRENCY m_UnitPrice;
   SHORT m_UnitsInStock;
   SHORT m_UnitsOnOrder;
   SHORT m_ReorderLevel;
   VARIANT_BOOL m_Discontinued;

   // Column status data members:
   DBSTATUS m_dwProductIDStatus;
   DBSTATUS m_dwProductNameStatus;
   DBSTATUS m_dwSupplierIDStatus;
   DBSTATUS m_dwCategoryIDStatus;
   DBSTATUS m_dwQuantityPerUnitStatus;
   DBSTATUS m_dwUnitPriceStatus;
   DBSTATUS m_dwUnitsInStockStatus;
   DBSTATUS m_dwUnitsOnOrderStatus;
   DBSTATUS m_dwReorderLevelStatus;
   DBSTATUS m_dwDiscontinuedStatus;

   // Column length data members:
   DBLENGTH m_dwProductIDLength;
   DBLENGTH m_dwProductNameLength;
   DBLENGTH m_dwSupplierIDLength;
   DBLENGTH m_dwCategoryIDLength;
   DBLENGTH m_dwQuantityPerUnitLength;
   DBLENGTH m_dwUnitPriceLength;
   DBLENGTH m_dwUnitsInStockLength;
   DBLENGTH m_dwUnitsOnOrderLength;
   DBLENGTH m_dwReorderLevelLength;
   DBLENGTH m_dwDiscontinuedLength;
```

### <a name="rowset-properties"></a>Satır kümesi özellikleri

Ardından, sihirbaz satır kümesi özelliklerini ayarlar. Seçtiyseniz **değişiklik**, **Ekle**, veya **Sil** ATL OLE DB Tüketicisi Sihirbazı'nda burada uygun özelliklerini ayarlayın (DBPROP_IRowsetChange her zaman ayarlanır, ardından bir veya daha fazla DBPROPVAL_UP_CHANGE, DBPROPVAL_UP_INSERT ve/veya DBPROPVAL_UP_DELETE sırasıyla).

```cpp
void GetRowsetProperties(CDBPropSet* pPropSet)
{
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
}
```

### <a name="command-or-table-class"></a>Komut veya tablo sınıfı

Komut sınıfı belirtirseniz sihirbaz komut sınıfı bildirir; şablonlu kodu için komut şöyle görünür:

```cpp
DEFINE_COMMAND_EX(CProductsAccessor, L" \
SELECT \
   ProductID, \
   ProductName, \
   SupplierID, \
   CategoryID, \
   QuantityPerUnit, \
   UnitPrice, \
   UnitsInStock, \
   UnitsOnOrder, \
   ReorderLevel, \
   Discontinued \
   FROM dbo.Products")
```

### <a name="column-map"></a>Sütun eşlemesi

Sihirbaz, ardından sütun bağlamaları veya sütun eşlemesi oluşturur. Bazı sağlayıcılarla olan çeşitli sorunları gidermek için aşağıdaki kod sütunları sağlayıcı tarafından bildirilen değerinden farklı bir düzende bağlayabilir.

```cpp
   BEGIN_COLUMN_MAP(CProductsAccessor)
      COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)
      COLUMN_ENTRY_LENGTH_STATUS(3, m_SupplierID, m_dwSupplierIDLength, m_dwSupplierIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(4, m_CategoryID, m_dwCategoryIDLength, m_dwCategoryIDStatus)
      COLUMN_ENTRY_LENGTH_STATUS(5, m_QuantityPerUnit, m_dwQuantityPerUnitLength, m_dwQuantityPerUnitStatus)
      _COLUMN_ENTRY_CODE(6, DBTYPE_CY, _SIZE_TYPE(m_UnitPrice), 0, 0, offsetbuf(m_UnitPrice), offsetbuf(m_dwUnitPriceLength), offsetbuf(m_dwUnitPriceStatus))
      COLUMN_ENTRY_LENGTH_STATUS(7, m_UnitsInStock, m_dwUnitsInStockLength, m_dwUnitsInStockStatus)
      COLUMN_ENTRY_LENGTH_STATUS(8, m_UnitsOnOrder, m_dwUnitsOnOrderLength, m_dwUnitsOnOrderStatus)
      COLUMN_ENTRY_LENGTH_STATUS(9, m_ReorderLevel, m_dwReorderLevelLength, m_dwReorderLevelStatus)
      _COLUMN_ENTRY_CODE(10, DBTYPE_BOOL, _SIZE_TYPE(m_Discontinued), 0, 0, offsetbuf(m_Discontinued), offsetbuf(m_dwDiscontinuedLength), offsetbuf(m_dwDiscontinuedStatus))
   END_COLUMN_MAP()
};
```

### <a name="class-declaration"></a>Sınıf bildirimi

Son olarak, sihirbaz, aşağıdaki gibi bir komut sınıf bildirimi oluşturur:

```cpp
class CProducts : public CCommand<CAccessor<CProductsAccessor>>
```

## <a name="attribute-injected-user-record-classes"></a>Öznitelik eklenmiş kullanıcı kayıt sınıfları

Veritabanı öznitelikleri kullanarak bir OLE DB Tüketicisi Oluşturma, ([db_command](../../windows/db-command.md) veya [db_table](../../windows/db-table.md)), öznitelikleri formun adıyla bir kullanıcı kayıt sınıfı ekleme "_*ClassName*Erişimci. " Örneğin, komut sınıfınıza adlı `COrders`, kullanıcı kayıt sınıfı olacaktır `_COrdersAccessor`. Kullanıcı kayıt sınıfı görünür ancak **sınıf görünümü**, çift gider üstbilgi dosyasında komut veya tablo sınıfı yerine. Bu durumlarda, kullanıcı kayıt sınıfı gerçek bildirimi öznitelik eklenmiş kod görüntüleyerek yalnızca görüntüleyebilir.

Ekler veya geçersiz kılma yöntemleri öznitelikli tüketiciler olası zorluklar olabilir. Örneğin, ekleyebilirsiniz bir `_COrdersAccessor` oluşturucuya `COrders` bildirimi ama aslında bu bir oluşturucu eklediğini unutmayın `COrdersAccessor` sınıfı. Bu tür bir oluşturucuya sütunlar/parametreler başlatabilirsiniz, ancak doğrudan başlatılamıyor çünkü bu şekilde, bir kopya Oluşturucu oluşturamazsınız `COrdersAccessor` nesne. Doğrudan bir oluşturucu (veya başka bir yöntem) gerekiyorsa `COrders` sınıfının yeni bir sınıf türetmek tanımladığınız önerilir `COrders` ve gerekli yöntemleri ekleyin.

Aşağıdaki örnekte, sihirbaz sınıfı için bir bildirim oluşturur `COrders`, ancak kullanıcı kayıt sınıfı `COrdersAccessor` görünmez, çünkü bu öznitelikleri ekleme.

```cpp
#define _ATL_ATTRIBUTES
#include <atlbase.h>
#include <atldbcli.h>
[
   db_source(L"your connection string"),
   db_command(L"Select ShipName from Orders;")
]
class COrders
{
public:

   // COrders()            // incorrect constructor name
   _COrdersAccessor()      // correct constructor name
   {
   }
      [db_column(1) ] TCHAR m_ShipName[41];
   };
```

Eklenen komut sınıf bildiriminin şöyle görünür:

```cpp
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>
```

Eklenen kodu çoğunu aynı veya benzer şablonlu sürüme olur. Açıklanan eklenen yöntemlerini temel farklılıklar şunlardır [Tüketici Sihirbazı tarafından oluşturulan yöntemler](../../data/oledb/consumer-wizard-generated-methods.md).

Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)