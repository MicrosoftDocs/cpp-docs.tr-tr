---
title: Satır Kümelerini Güncelleştirme
ms.date: 10/19/2018
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
ms.openlocfilehash: 7151d897469993b2f9be3575eb11a08844af3c69
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028366"
---
# <a name="updating-rowsets"></a>Satır Kümelerini Güncelleştirme

Bir temel veritabanı güncelleştirmek veya veri deposuna veri yazmak için bir işlemdir. OLE DB'de güncelleştirme mekanizmasını basittir: tüketici uygulamanızın bağımlı veri üyelerinin değerlerini ayarlar ve sonra bu değerleri satır kümesi için; yazar Tüketici, sağlayıcı veri deposunda güncelleştirme ardından ister.

Tüketiciler, satır kümesi veri güncelleştirmeleri aşağıdaki türde tamamlayabilir: bir satırdaki sütun değerleri ayarlama, satır ekleme ve bir satırın silinmesi. OLE DB Şablon sınıfı bu işlemlerin tamamlanması [CRowset](../../data/oledb/crowset-class.md) uygulayan [IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85)) arabirim ve aşağıdaki arabirim yöntemini geçersiz kılar:

- [SetData](../../data/oledb/crowset-setdata.md) değişiklikleri sütun bir satır kümesi bir satır değerleri; bu SQL güncelleştirme komut için karşılık gelmektedir.

- [INSERT](../../data/oledb/crowset-insert.md) bir satır kümesine; bir satır ekler, SQL ekleme komutuna karşılık gelmektedir.

- [Silme](../../data/oledb/crowset-delete.md) bir satır kümesinden; satırları siler, SQL'i Sil komutu karşılık gelmektedir.

## <a name="supporting-update-operations"></a>Güncelleştirme işlemleri destekleme

Bir tüketici ile oluşturduğunuzda **ATL OLE DB Tüketicisi Sihirbazı**, birini seçerek güncelleştirme işlemleri destekleyebilir veya daha fazla üç onay kutularını işaretleyin **değişiklik**, **Ekle**, ve **Sil**. Bu Seçenekler'i seçerseniz, sihirbaz kodu seçtiğiniz değişikliklerin türünü desteklemek için uygun şekilde değiştirir. Sihirbazı'nı kullanmıyorsanız, ancak aşağıdaki satır kümesi özelliklerini ayarlamak için ihtiyacınız `VARIANT_TRUE` güncelleştirmeleri desteklemek için:

- `DBPROPVAL_UP_CHANGE` bir satır veri değerlerini değiştirmenizi sağlar.

- `DBPROPVAL_UP_INSERT` bir satır eklemenizi sağlar.

- `DBPROPVAL_UP_DELETE` bir satır silmenize olanak sağlar.

Özellikleri şu şekilde ayarlayın:

```cpp
CDBPropSet ps(DBPROPSET_ROWSET);

ps.AddProperty(DBPROP_IRowsetChange, true);
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);
```

Bir veya daha fazla sütun yazılabilir değilse, değiştirme, ekleme veya silme işlemleri başarısız olabilir. Bu sorunu düzeltmek için imleç harita değiştirin.

## <a name="setting-data-in-rows"></a>Satırlardaki verileri ayarlama

[CRowset::SetData](../../data/oledb/crowset-setdata.md) geçerli satırın bir veya daha fazla sütun veri değerlerini ayarlar. Aşağıdaki kod, bağlı veri üyelerinin değerlerini ayarlar `Name` ve `Units in Stock` tablonun `Products` ve `SetData` bu değerleri kümesi % 100'lük bir satır yazmak için:

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

## <a name="inserting-rows-into-rowsets"></a>Satır kümelerine ekleme

[CRowset::INSERT](../../data/oledb/crowset-insert.md) oluşturur ve veri erişimci kullanarak yeni bir satır başlatır. `Insert` Geçerli satırın sonra tamamen yeni bir satır oluşturur. sonraki satırda geçerli satıra artırmak ya da değiştirmeden belirtmek zorunda. Ayarlayarak bunu *bGetRow* parametresi:

```cpp
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)
```

- **false** geçerli satır (Bu durumda da, eklenen satırı'noktaları) sonraki satıra Artır (varsayılan değer) belirtir.

- **doğru** geçerli olduğu halde kalmasını sağlamanız satır belirtir.

Aşağıdaki kod tablonun sütunlarının için bağlı veri üyelerinin değerlerini ayarlar `Products` ve `Insert` satır kümesi % 100'lük satırının sonra bu değerleri içeren yeni bir satır eklemek için. Yeni satırda tanımsız veri önlemek için tüm sütun değerleri ayarlamak önerilir:

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

Daha ayrıntılı bir örnek için bkz. [CRowset::INSERT](../../data/oledb/crowset-insert.md).

Veri üyeleri, durum ve uzunluk ayarlama hakkında daha fazla bilgi için bkz. [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).

## <a name="deleting-rows-from-rowsets"></a>Kümelerinden satırları silme

[CRowset::Delete](../../data/oledb/crowset-delete.md) geçerli satır satır kümesinden siler. Aşağıdaki kod çağrıları `Delete` satır kümesi % 100'lük satırı kaldırmak için:

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

## <a name="immediate-and-deferred-updates"></a>Hemen ve ertelenmiş güncelleştirme

Aksi belirtilmedikçe, çağrılar `SetData`, `Insert`, ve `Delete` veri deposu hemen güncelleştirme yöntemleri. Ancak, tüketici tüm değişiklikleri yerel önbellekte depolar ve ardından bunları veri deposuna aktarır aşağıdaki güncelleştirme yöntemlerini çağırdığınızda güncelleştirmelerini ertele olabilir:

- [CRowset::Update](../../data/oledb/crowset-update.md) bekleyen tüm değişiklikleri geçerli satırın son getirme bu yana yapılan aktarır veya `Update` çağrı.

- [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md) bekleyen tüm değişiklikleri tüm satırları için yapılan son getirme beri aktarır veya `Update` çağrı.

Güncelleştirme, güncelleştirme yöntemleri tarafından kullanılan komutunda değişiklikler yapma belirli bir anlamı vardır ve SQL ile karıştırılır olması değil **güncelleştirme** komut (`SetData` SQL eşdeğerdir **güncelleştirme** komut) .

Ertelenen güncelleştirmeler, örneğin, bir dizi bankacılık işlemleri gibi durumlarda kullanışlıdır; bir işlem iptal edilirse, sonuncu kaydedildikten sonra değişiklikler yapılana kadar bir dizi gönderme olduğundan değişikliği geri alabilirsiniz. Ayrıca, sağlayıcı daha verimli şekilde bir ağ çağrısı değişiklikleri gruplandırabilirsiniz.

Ertelenmiş güncelleştirmeleri destekleyecek şekilde ayarlamalısınız `DBPROP_IRowsetChange` özellik anlatıldığı özellikleri birlikte **güncelleştirme işlemlerini desteklemek**:

```cpp
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);
```

Çağırdığınızda `Update` veya `UpdateAll`, yöntemler aktarımı değişiklikleri yerel önbellekten veri deposuna ve ardından yerel önbelleğini silme. Güncelleştirme yalnızca geçerli satır için değişiklikleri aktardığından uygulamanızın hangi satır güncelleştirme ve ne zaman güncelleştirileceği izler, önemlidir. Aşağıdaki örnek, iki ardışık satırları güncelleştirme gösterilmektedir:

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

Bekleyen değişikliklerin aktarılmasını sağlamak için çağırmalıdır `Update` başka bir satıra geçilmeden önce. Ancak, bu yorucu bir süreç ya da verimsiz olduğunda, örneğin, yüzlerce satırı güncelleştirmek, uygulamanız gerektiğinde kullanabilirsiniz `UpdateAll` tüm satırların aynı anda güncelleştirilecek.

Örneğin, ilk `Update` çağrı yukarıdaki kodda eksik, satır 100 kalın değişmeden satır 101 değişecek ancak. Bu noktadan sonra uygulamanız ya da çağrı gerekirdi `UpdateAll` veya geri taşıyın satır 100 ve çağrı `Update` güncelleştirilecek ilgili satır için.

Son olarak, değişiklikleri ertelemek için bir temel nedeni geri almak mümkün olacak. Çağırma [CRowset::Undo](../../data/oledb/crowset-undo.md) bekleyen değişiklikler yapılmadan önce yerel değişiklik önbelleği durumunu veri deposunun durumuna geri alır. Dikkat etmeniz önemlidir `Undo` geri değil tek bir adımda (durum en son değişikliği) olarak yerel önbellek durumu geri; bunun yerine, ilgili satır için yerel önbellek temizler. Ayrıca, `Undo` yalnızca geçerli satırı etkiler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)<br/>
[CRowset Sınıfı](../../data/oledb/crowset-class.md)<br/>
[IRowsetChange](/previous-versions/windows/desktop/ms715790(v=vs.85))<br/>
