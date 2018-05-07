---
title: Tüketici Sihirbazı tarafından oluşturulan sınıflar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- command classes in OLE DB consumer
- classes [C++], OLE DB Consumer Wizard-generated
- consumer wizard-generated classes and methods
- user record classes in OLE DB consumer
ms.assetid: dba0538f-2afe-4354-8cbb-f202ea8ade5a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 030445a8e6b46afb9f893e21bceb221f7f9e89a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="consumer-wizard-generated-classes"></a>Tüketici Sihirbazı Tarafından Oluşturulan Sınıflar
Tüketici oluşturmak için ATL OLE DB Tüketici Sihirbazı'nı kullandığınızda, OLE DB Şablonları veya OLE DB öznitelikleri kullanma seçeneğiniz vardır. Her iki durumda da sihirbaz komut sınıfı ve kullanıcı kayıt sınıfı oluşturur. Komut sınıfı Sihirbazı'nda belirtilen satır kümesi ve veri kaynağı açmak için kullanılan kodu içerir. Kullanıcı kayıt sınıfı seçtiğiniz veritabanı tablosu için sütun eşlemesi içerir. Bununla birlikte, her durumda oluşturulan kod farklıdır:  
  
-   Şablonu bir tüketici seçerseniz, sihirbaz komut sınıfı ve kullanıcı kayıt sınıfı oluşturur. Komut sınıfı sihirbazın sınıfı kutusuna girdiğiniz ada sahip olacaktır (örneğin, `CProducts`), ve kullanıcı kayıt sınıfı biçiminde bir ada sahip olacaktır "*ClassName*erişimci" (örneğin, `CProductsAccessor`). Her iki sınıfları tüketicinin üstbilgi dosyasında yerleştirilir.  
  
-   Öznitelikli bir tüketici seçerseniz, kullanıcı kayıt sınıfı biçiminde bir ada sahip olacaktır "_*ClassName*erişimci" ve eklenecek. Diğer bir deyişle, yalnızca komut sınıfı Metin Düzenleyicisi'nde görüntüleyemez olacaktır; Bu gibi durumlarda, kullanıcı kayıt sınıfı yalnızca eklenen kodu görüntüleyebilirsiniz. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kod hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).  
  
 Aşağıdaki örnekler komut sınıfı için Tüketici Sihirbazı tarafından oluşturulan kodu göstermek için Northwind veritabanı Ürünler tablosunun oluşturulan komut sınıfı ve kullanıcı kayıt sınıfı kullanın.  
  
## <a name="templated-user-record-classes"></a>Şablonlu kullanıcı kayıt sınıfları  
 OLE DB Şablonları (OLE DB öznitelikleri yerine) kullanarak bir OLE DB Tüketici oluşturursanız, sihirbazın bu bölümde açıklandığı gibi kod oluşturur.  
  
### <a name="column-data-members"></a>Sütun veri üyeleri  
 Kullanıcı kayıt sınıfı ilk bölümü veri üye bildirimleri ve her bir veri ilişkili sütun için durum ve uzunluk veri üyelerini içerir. Bu veri üyeleri hakkında daha fazla bilgi için bkz: [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
> [!NOTE]
>  Kullanıcı kayıt sınıfı değiştirmek veya kendi tüketici yazma, veri değişkenleri durum ve uzunluk değişkenlerinden önce gelmelidir.  
  
> [!NOTE]
>  ATL OLE DB Tüketici Sihirbazı'nı kullanan **DB_NUMERIC** sayısal veri türlerini bağlamak için türü. Bu önceden kullanılan **DBTYPE_VARNUMERIC** (biçimi tarafından açıklanan **DB_VARNUMERIC** yazın; biçim bakın). Tüketici oluşturmak için Sihirbazı kullanmazsanız kullanmanız önerilir **DB_NUMERIC**.  
  
```  
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
 Ardından, sihirbaz satır kümesi özelliklerini ayarlar. Seçtiyseniz **değişiklik**, **Ekle**, veya **silmek** ATL OLE DB Tüketici Sihirbazı'nda uygun özellikler burada ayarlanır (DBPROP_IRowsetChange her zaman ayarlanır, ardından bir veya daha fazla DBPROPVAL_UP_CHANGE, DBPROPVAL_UP_INSERT ve/veya DBPROPVAL_UP_DELETE sırasıyla).  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
### <a name="command-or-table-class"></a>Komut veya tablo sınıfı  
 Komut sınıfı belirtirseniz, sihirbaz komut sınıfını bildirir; şablonlu kod için komut şöyle görünür:  
  
```  
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
 Sihirbaz, ardından sütun bağlamaları veya sütun eşlemesi oluşturur. Bazı sağlayıcılar olan çeşitli sorunları gidermek için aşağıdaki kodu sütunları sağlayıcı tarafından bildirilen daha farklı bir düzende bağlayabilir.  
  
```  
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
  
```  
class CProducts : public CCommand<CAccessor<CProductsAccessor>>  
```  
  
## <a name="attribute-injected-user-record-classes"></a>Öznitelik eklenmiş kullanıcı kayıt sınıfları  
 Veritabanı öznitelikleri kullanarak bir OLE DB Tüketici oluşturursanız ([db_command](../../windows/db-command.md) veya [db_table](../../windows/db-table.md)), formun adı ile bir kullanıcı kayıt sınıfı öznitelikleri Ekle "_*ClassName*Erişimcisi. " Örneğin, komut sınıfınızı adlı `COrders`, kullanıcı kayıt sınıfı olacaktır `_COrdersAccessor`. Kullanıcı kayıt sınıfı Sınıf Görünümü'nde görüntülenir, ancak çift üstbilgi dosyası komut veya tablo sınıfına götürür. Bu durumlarda, öznitelik eklenmiş kod görüntüleyerek yalnızca kullanıcı kayıt sınıfı gerçek bildirimi görüntüleyebilirsiniz.  
  
 Ekler ya da öznitelikli tüketicileri yöntemleri geçersiz kılmak olası karışıklıklardan olabilir. Örneğin, ekleyebilirsiniz bir `_COrdersAccessor` oluşturucuya `COrders` bildirimi, ancak aslında bu bir oluşturucu eklediğini unutmayın `COrdersAccessor` sınıfı. Bu tür bir oluşturucu sütunları/parametreleri başlatabilir, ancak doğrudan başlatılamıyor çünkü bu şekilde kopya Oluşturucu oluşturamazsınız `COrdersAccessor` nesnesi. Doğrudan bir oluşturucu (veya başka bir yöntem) gerekiyorsa `COrders` sınıfı türetme yeni bir sınıf tanımlama önerilir `COrders` ve gerekli yöntemleri ekleyin.  
  
 Aşağıdaki örnekte, sihirbaz sınıfı için bir bildirim oluşturur `COrders`, ancak kullanıcı kayıt sınıfı `COrdersAccessor` öznitelikleri, ekleme için görüntülenmez.  
  
```  
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
  
 Eklenen komut sınıf bildirimi şöyle görünür:  
  
```  
class CProducts : public CCommand<CAccessor<_CProductsAccessor>>  
```  
  
 Eklenen kod çoğunu aynı veya benzer şablonlu sürüme olur. Açıklanan eklenen yöntemler temel farklılıklar şunlardır [Tüketici Sihirbazı tarafından oluşturulan yöntemler](../../data/oledb/consumer-wizard-generated-methods.md).  
  
 Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kod hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)