---
title: Tüketici Sihirbazı Tarafından Oluşturulan Sınıflar
ms.date: 05/09/2019
helpviewer_keywords:
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
ms.openlocfilehash: 5c8a975b2f4a8ae3285f035e7b708c5026f5f480
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924592"
---
# <a name="consumer-wizard-generated-classes"></a>Tüketici Sihirbazı Tarafından Oluşturulan Sınıflar

::: moniker range="msvc-160"

ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz.

::: moniker-end

::: moniker range="<=msvc-150"

Bir tüketici oluşturmak için **ATL OLE DB Tüketici Sihirbazı 'nı** kullandığınızda, OLE DB şablonlarını veya OLE DB özniteliklerini kullanma seçeneğiniz vardır. Her iki durumda da, sihirbaz bir komut sınıfı ve bir kullanıcı kayıt sınıfı oluşturur. Komut sınıfı, sihirbazda belirttiğiniz veri kaynağını ve satır kümesini açmak için kod içerir. Kullanıcı kayıt sınıfı, seçtiğiniz veritabanı tablosu için bir sütun eşlemesi içerir. Ancak, oluşturulan kod her durumda farklılık gösterir:

- Şablonlu bir tüketici seçerseniz, sihirbaz bir komut sınıfı ve bir kullanıcı kayıt sınıfı oluşturur. Komut sınıfı, sihirbazdaki **sınıf** kutusuna girdiğiniz ada sahip olur (örneğin, `CProducts` ) ve Kullanıcı kayıt sınıfı " *ClassName* erişimcisi" biçiminde bir ada sahip olur (örneğin, `CProductsAccessor` ). Her iki sınıf de tüketicinin başlık dosyasına yerleştirilir.

- Öznitelikli bir tüketici seçerseniz, Kullanıcı kayıt sınıfı "_ *ClassName* erişimcisi" biçiminde bir ada sahip olur ve eklenir. Diğer bir deyişle, yalnızca komut sınıfını metin düzenleyicisinde görüntüleyebileceksiniz; yalnızca eklenen kod olarak Kullanıcı kayıt sınıfını görüntüleyebilirsiniz. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

Aşağıdaki örnekler, `Products` `Northwind` komut sınıfı ve Kullanıcı kayıt sınıfı için sihirbaz tarafından oluşturulan tüketici kodunu göstermek üzere veritabanının tablosunda oluşturulan bir komut sınıfını kullanır.

## <a name="templated-user-record-classes"></a>Şablonlu kullanıcı kayıt sınıfları

OLE DB şablonlarını kullanarak bir OLE DB tüketicisi oluşturursanız (OLE DB öznitelikleri yerine), sihirbaz bu bölümde açıklanan şekilde kod üretir.

### <a name="column-data-members"></a>Sütun veri üyeleri

Kullanıcı kayıt sınıfının ilk bölümü, veri üyesi bildirimlerini ve her bir veriye dayalı sütun için durum ve uzunluk veri üyelerini içerir. Bu veri üyeleri hakkında daha fazla bilgi için [Wizard-Generated Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md)bölümüne bakın.

> [!NOTE]
> Kullanıcı kayıt sınıfını değiştirir veya kendi tüketicinizi yazarsanız, veri değişkenlerinin durum ve uzunluk değişkenlerinden önce gelmesi gerekir.

> [!NOTE]
> ATL OLE DB Tüketici Sihirbazı `DB_NUMERIC` sayısal veri türlerini bağlamak için türünü kullanır. Daha önce kullanılmış `DBTYPE_VARNUMERIC` olan (türü tarafından açıklanan biçim `DB_VARNUMERIC` ; bkz. OleDb. h). Tüketici oluşturmak için Sihirbazı kullanmıyorsanız kullanmanız önerilir `DB_NUMERIC` .

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

Sonra sihirbaz satır kümesi özelliklerini ayarlar. ATL OLE DB tüketicisi sihirbazında **değişiklik** , **ekleme** veya **silme** seçeneğini belirlediyseniz uygun Özellikler burada ayarlanır (DBPROP_IRowsetChange her zaman ayarlanır, sonra bir veya daha fazla DBPROPVAL_UP_CHANGE, DBPROPVAL_UP_INSERT ve/veya DBPROPVAL_UP_DELETE sırasıyla).

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

Bir komut sınıfı belirtirseniz, sihirbaz komut sınıfını bildirir; şablonlu kod için komut şöyle görünür:

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

### <a name="column-map"></a>Sütun eşleme

Sihirbaz daha sonra sütun bağlamaları veya sütun haritası oluşturur. Bazı sağlayıcılarla ilgili birçok sorunu gidermek için, aşağıdaki kod sütunları sağlayıcı tarafından raporlanan farklı bir sırada bağlayabilir.

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

Son olarak, sihirbaz aşağıdaki gibi bir komut sınıfı bildirimi oluşturur:

```cpp
class CProducts : public CCommand<CAccessor<CProductsAccessor>>
```

## <a name="attribute-injected-user-record-classes"></a>Attribute-Injected Kullanıcı kaydı sınıfları

Veritabanı özniteliklerini ( [db_command](../../windows/attributes/db-command.md) veya [db_table](../../windows/attributes/db-table.md)) kullanarak bir OLE DB tüketicisi oluşturursanız, öznitelikler "_ *ClassName* erişimcisi" biçiminde bir kullanıcı kayıt sınıfı ekler. Örneğin, komut sınıfınızı adlandırdıysanız `COrders` , Kullanıcı kayıt sınıfı olur `_COrdersAccessor` . Kullanıcı kayıt sınıfı **sınıf görünümü** görünmesine karşın, Çift tıklamak bunun yerine üstbilgi dosyasındaki komuta veya tablo sınıfına gider. Bu durumlarda, öznitelik eklenen kodu görüntüleyerek yalnızca Kullanıcı kayıt sınıfının gerçek bildirimini görüntüleyebilirsiniz.

Öznitelikli tüketicilerle Yöntemler ekler veya geçersiz kılındıysanız olası zorluklar olabilir. Örneğin, `_COrdersAccessor` bildirime bir Oluşturucu ekleyebilirsiniz `COrders` , ancak bu, gerçekte eklenen sınıfa bir Oluşturucu ekliyor `COrdersAccessor` . Bu tür bir Oluşturucu sütunları/parametreleri başlatabilir, ancak nesneyi doğrudan örneklemediğinden bu şekilde bir kopya Oluşturucu oluşturamazsınız `COrdersAccessor` . Doğrudan sınıfında bir oluşturucuya (veya başka bir yönteme) ihtiyacınız varsa `COrders` , öğesinden türeten yeni bir sınıf tanımlamanız `COrders` ve gerekli yöntemleri eklemeniz önerilir.

Aşağıdaki örnekte, sihirbaz sınıf için bir bildirim oluşturur `COrders` , ancak öznitelikler onu eklemesine rağmen Kullanıcı kayıt sınıfı `COrdersAccessor` görünmez.

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

Eklenen komut sınıfı bildirimi şöyle görünür:

```cpp
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>
```

Eklenen kodun çoğu, şablonlu sürümle aynı veya benzer. Ana farklılıklar, [tüketici Wizard-Generated yöntemlerinde](../../data/oledb/consumer-wizard-generated-methods.md)açıklanan eklenen metotlardır.

Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz. [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).

::: moniker-end

## <a name="see-also"></a>Ayrıca bkz.

[Sihirbaz kullanarak OLE DB tüketicisi oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)
