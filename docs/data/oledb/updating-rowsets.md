---
description: 'Daha fazla bilgi için: satır kümelerini güncelleştirme'
title: Satır Kümelerini Güncelleştirme
ms.date: 05/09/2019
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
ms.openlocfilehash: 3e5fcd374e446670df586c27e6b6e89d5da30da6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272532"
---
# <a name="updating-rowsets"></a>Satır Kümelerini Güncelleştirme

Temel bir veritabanı işlemi, veri deposuna verileri güncelleştirmek veya veritabanına yazmak. OLE DB, güncelleştirme mekanizması basittir: tüketici uygulamanız, bağlantılı veri üyelerinin değerlerini ayarlar ve sonra bu değerleri satır kümesine yazar; ardından tüketici, sağlayıcının veri deposunu güncelleştirmesini ister.

Müşteriler satır kümesi verilerinde aşağıdaki tür güncelleştirmeleri tamamlayabilir: satır içindeki sütun değerlerini ayarlama, satır ekleme ve bir satırı silme. Bu işlemleri gerçekleştirmek için, OLE DB Şablon sınıfı [CRowset](../../data/oledb/crowset-class.md) , [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) arabirimini uygular ve aşağıdaki arabirim yöntemlerini geçersiz kılar:

- [SetData](./crowset-class.md#setdata) bir satır kümesinin satırındaki sütun değerlerini değiştirir; SQL UPDATE komutuna karşılık gelir.

- [Ekle](./crowset-class.md#insert) satır kümesine bir satır ekler; SQL INSERT komutuna karşılık gelir.

- [Sil](./crowset-class.md#delete) satır kümesinden satır siler; SQL DELETE komutuna karşılık gelir.

## <a name="supporting-update-operations"></a>Güncelleştirme Işlemlerini destekleme

> [!NOTE]
> ATL OLE DB Tüketici Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. İşlevselliği el ile de ekleyebilirsiniz. Daha fazla bilgi için bkz. [Sihirbaz kullanmadan tüketici oluşturma](creating-a-consumer-without-using-a-wizard.md).

**ATL OLE DB tüketici sihirbazıyla** bir tüketici oluşturduğunuzda, üç onay kutusundan bir veya daha fazlasını **değiştirme**, **ekleme** ve **silme** işlemlerini seçerek güncelleştirme işlemlerini destekleyebilirsiniz. Bu seçenekleri belirlerseniz, sihirbaz seçtiğiniz değişikliklerin türünü desteklemek için kodu uygun şekilde değiştirir. Ancak Sihirbazı kullanmıyorsanız, güncelleştirmeleri desteklemek için aşağıdaki satır kümesi özelliklerini ayarlamanız gerekir `VARIANT_TRUE` :

- `DBPROPVAL_UP_CHANGE` bir satırdaki veri değerlerini değiştirmenize izin verir.

- `DBPROPVAL_UP_INSERT` bir satır eklemenizi sağlar.

- `DBPROPVAL_UP_DELETE` bir satırı silmenizi sağlar.

Özellikleri aşağıdaki şekilde ayarlarsınız:

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

Bir veya daha fazla sütun yazılabilir değilse, değişiklik, ekleme veya silme işlemleri başarısız olabilir. Bu sorunu düzeltmek için imleç eşlemenizi değiştirin.

## <a name="setting-data-in-rows"></a>Satırlardaki verileri ayarlama

[CRowset:: SetData](./crowset-class.md#setdata) , geçerli satırın bir veya daha fazla sütununda veri değerlerini ayarlar. Aşağıdaki kod, sütunlara ve tabloya göre veri üyelerinin değerlerini ayarlar `Name` `Units in Stock` `Products` ve ardından `SetData` Bu değerleri satır kümesinin lük satırına yazmak için çağırır:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_UnitsInStock = 10000;

// Set the data
HRESULT hr = product.SetData();
```

## <a name="inserting-rows-into-rowsets"></a>Satır kümelerine satır ekleme

[CRowset:: INSERT](./crowset-class.md#insert) erişimcisindeki verileri kullanarak yeni bir satır oluşturur ve başlatır. `Insert` geçerli satırdan sonra tamamen yeni bir satır oluşturur; geçerli satırın bir sonraki satıra arttırılıp artırılmayacağını veya değişmeden ayrılmayacağını belirtmeniz gerekir. Bunu, *bGetRow* parametresini ayarlayarak yapabilirsiniz:

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **`false`** (varsayılan değer) geçerli satırın bir sonraki satıra (Bu durumda eklenen satıra işaret ettiğini) artırılacağını belirtir.

- **`true`** geçerli satırın nerede olduğunu belirtir.

Aşağıdaki kod, tablonun sütunlarına göre veri üyelerinin değerlerini ayarlar `Products` ve sonra `Insert` satır kümesinin lük satırından sonra bu değerleri içeren yeni bir satır eklemek için çağırır. Yeni satırda tanımsız verileri önlemek için tüm sütun değerlerini ayarlamanız önerilir:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Set the column values for a row of the Product table, then insert the row
product.m_ProductID = 101;
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Candle" ) );

product.m_SupplierID = 27857;
product.m_CategoryID = 372;
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit, _T( "Pack of 10" ) );

product.m_UnitPrice = 20;
product.m_UnitsInStock = 10000;
product.m_UnitsOnOrder = 5201;
product.m_ReorderLevel = 5000;
product.m_Discontinued = false;

// You must also initialize the status and length fields before setting/inserting data
// Set the column status values
m_dwProductIDStatus = DBSTATUS_S_OK;
m_dwProductNameStatus = DBSTATUS_S_OK;
m_dwSupplierIDStatus = DBSTATUS_S_OK;
m_dwCategoryIDStatus = DBSTATUS_S_OK;
m_dwQuantityPerUnitStatus = DBSTATUS_S_OK;
m_dwUnitPriceStatus = DBSTATUS_S_OK;
m_dwUnitsInStockStatus = DBSTATUS_S_OK;
m_dwUnitsOnOrderStatus = DBSTATUS_S_OK;
m_dwReorderLevelStatus = DBSTATUS_S_OK;
m_dwDiscontinuedStatus = DBSTATUS_S_OK;

// Set the column length value for column data members that are not fixed-length types.
// The value should be the length of the string that you are setting.
m_dwProductNameLength = 6;             // "Candle" has 6 characters
m_dwQuantityPerUnitLength = 10;        // "Pack of 10" has 10 characters

// Insert the data
HRESULT hr = product.Insert();
```

Daha ayrıntılı bir örnek için bkz. [CRowset:: INSERT](./crowset-class.md#insert).

Durum ve uzunluk veri üyelerini ayarlama hakkında daha fazla bilgi için, bkz. [Wizard-Generated erişimcileri Içindeki alan durumu verileri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

## <a name="deleting-rows-from-rowsets"></a>Satır kümelerinde satırları silme

[CRowset::D Sil](./crowset-class.md#delete) , geçerli satırı satır kümesinden siler. Aşağıdaki kod, `Delete` satır kümesinin lük satırını kaldırmak için çağırır:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Delete the row
HRESULT hr = product.Delete();
```

## <a name="immediate-and-deferred-updates"></a>Anında ve ertelenmiş güncelleştirmeler

Aksi belirtilmedikçe,, ve yöntemlerine yapılan çağrılar `SetData` `Insert` `Delete` veri deposunu hemen güncelleştirir. Bununla birlikte, tüm değişiklikleri tüketicinin bir yerel önbellekte sakladığı ve sonra aşağıdaki güncelleştirme yöntemlerinden birini çağırdığınızda bunları veri deposuna aktaran şekilde güncelleştirmeleri erteleyebilirsiniz:

- [CRowset:: Update](./crowset-class.md#update) , en son getirme veya çağrıdan sonra geçerli satırda yapılan bekleyen değişiklikleri aktarır `Update` .

- [CRowset:: UpdateAll](./crowset-class.md#updateall) , en son getirme veya çağırma sonrasında tüm satırlarda yapılan bekleyen değişiklikleri aktarır `Update` .

Güncelleştirme yöntemleri tarafından kullanılan güncelleştirme, komutta değişiklik yapmanın belirli anlamlarına sahiptir ve SQL **Update** komutuyla KARıŞTıRıLMAMALıDıR ( `SetData` SQL **Update** komutuna eşdeğerdir).

Ertelenmiş güncelleştirmeler, örneğin, banka işlemleri dizisi gibi durumlarda faydalıdır; bir işlem iptal edilirse, son bir işlem tamamlanana kadar değişiklik serisini göndermediğinden değişikliği geri alabilirsiniz. Ayrıca sağlayıcı, değişiklikleri daha verimli bir şekilde tek bir ağ çağrısıyla paketleyip.

Ertelenmiş güncelleştirmeleri desteklemek için `DBPROP_IRowsetChange` özelliği, **güncelleştirme işlemlerini destekleme** bölümünde açıklanan özelliklerle birlikte ayarlamanız gerekir:

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

Ya da çağırdığınızda `Update` `UpdateAll` , Yöntemler yerel önbellekten veri deposuna aktarılır ve ardından yerel önbelleği temizler. Güncelleştirme yalnızca geçerli satır için değişiklikleri aktardığından, uygulamanızın hangi satırın güncelleyeceğinizi ve ne zaman güncelleştiğinden emin olmanız önemlidir. Aşağıdaki örnek, art arda iki satırın nasıl güncelleşreceğini göstermektedir:

```cpp
// Instantiate a rowset based on the user record class
CTable<CAccessor<CProductAccessor>> product;
CSession session;

// Open the rowset and move to the 100th row
product.Open(session, "Product", &ps, 1);  // ps is the property set
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row

// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName, _T( "Wick" ) );

product.m_UnitsInStock = 10000;

HRESULT hr = product.SetData();  // No changes made to row 100 yet
product.Update();                 // Update row 100 now

// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table
product.MoveNext();

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName _T( "Wax" ) );

product.m_UnitsInStock = 500;

HRESULT hr = product.SetData();  // No changes made to row 101 yet
product.Update();                 // Update row 101 now
```

Bekleyen değişikliklerin aktarılmasını sağlamak için, `Update` başka bir satıra geçmeden önce öğesini çağırmanız gerekir. Ancak, bu sıkıcı veya verimsiz olduğunda, örneğin, uygulamanızın yüzlerce satırı güncelleştirmesi gerektiğinde, `UpdateAll` tüm satırları tek seferde güncelleştirmek için kullanabilirsiniz.

Örneğin, `Update` Yukarıdaki kodda ilk çağrı eksikse satır 100 değişmeden kalır, ancak satır 101 değişecektir. Bu noktadan sonra uygulamanız, bu satırın güncelleştirilebilmesi için çağrı yapmak `UpdateAll` veya satır 100 ' e geri dönmesi gerekir `Update` .

Son olarak, değişiklikleri ertelenmesi için bir ana neden onları geri alabilir. [CRowset:: Undo](./crowset-class.md#undo) çağrısı, yerel değişiklik önbelleğinin durumunu, bekleyen değişiklikler yapılmadan önce veri deposunun durumuna geri kaydeder. `Undo`Yerel önbelleğin durumunu tek bir adım (yalnızca en son değişiklikten önceki durum) ile geri döndürmediğini unutmayın; bunun yerine, bu satır için yerel önbelleği temizler. Ayrıca, `Undo` yalnızca geçerli satırı etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonlarıyla çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset sınıfı](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))<br/>
