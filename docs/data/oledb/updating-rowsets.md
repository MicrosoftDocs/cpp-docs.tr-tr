---
title: Satır kümelerini güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, updating data
- updating data, rowsets
- updating rowsets
- rowsets
ms.assetid: 39588758-5c72-4254-a10d-cc2b1f473357
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8ca0ef94ba6c60bd43e24672fe7db669a3930fd7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="updating-rowsets"></a>Satır Kümelerini Güncelleştirme
Bir çok basit bir veritabanı güncelleştirmek veya veri deposuna veri yazmak için bir işlemdir. OLE DB'de güncelleme mekanizması basittir: tüketici uygulamanız bağlı veri üyelerinin değerlerini ayarlar ve ardından bu değerleri satır kümesine yazar; Tüketici sonra sağlayıcının veri deposunu güncelleştirmek ister.  
  
 Tüketiciler, satır kümesi veri üzerinde güncelleştirmeleri şu tür gerçekleştirebilir: satır içindeki sütun değerlerini ayarlama, satır ekleme ve bir satırın silinmesi. OLE DB Şablon sınıfı bu işlemleri gerçekleştirmek için [CRowset](../../data/oledb/crowset-class.md) uygulayan [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) arabirim ve aşağıdaki arabirim yöntemini geçersiz kılar:  
  
-   [SetData](../../data/oledb/crowset-setdata.md) değişiklikleri sütun değerleri satır satırda; SQL güncelleştirme komut eşdeğerdir.  
  
-   [INSERT](../../data/oledb/crowset-insert.md) satır kümesine; bir satır ekler SQL INSERT komutu ile eşdeğerdir.  
  
-   [Silme](../../data/oledb/crowset-delete.md) bir satır kümesinden; satırları siler SQL DELETE komutu ile eşdeğerdir.  
  
## <a name="supporting-update-operations"></a>Güncelleştirme işlemleri destekleme  
 ATL OLE DB Tüketici Sihirbazı'yla bir tüketici oluşturduğunuzda, birini seçerek güncelleştirme işlemlerini destekleyebilir veya daha fazla üç onay kutularını **değişiklik**, **Ekle**, ve **Sil**. Bunlar seçerseniz sihirbaz kodu seçtiğiniz değişikliklerin türünü desteklemek için uygun şekilde değiştirir. Sihirbaz kullanmazsanız, ancak aşağıdaki satır kümesi özelliklerini ayarlamak için ihtiyacınız `VARIANT_TRUE` güncelleştirmelerini desteklemek için:  
  
-   **DBPROPVAL_UP_CHANGE** bir satır veri değerlerini değiştirmenizi sağlar.  
  
-   **DBPROPVAL_UP_INSERT** satır ekleme olanak tanır.  
  
-   **DBPROPVAL_UP_DELETE** bir satır silmenize olanak sağlar.  
  
 Özellikleri aşağıdaki gibi ayarlayın:  
  
```  
CDBPropSet ps(DBPROPSET_ROWSET);  

ps.AddProperty(DBPROP_IRowsetChange, true)  
ps.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE)  
```  
  
 Bir veya daha fazla sütun yoksa yazılabilir değişiklik, ekleme veya silme işlemleri başarısız olabilir. Bu sorunu gidermek için imleç haritanızı değiştirin.  
  
## <a name="setting-data-in-rows"></a>Satırlardaki verileri ayarlama  
 [CRowset::SetData](../../data/oledb/crowset-setdata.md) geçerli satırda bir veya daha fazla sütunlarında veri değerlerini ayarlar. Aşağıdaki kod sütunlara "Name" ve "Stoktaki" Ürünler tablosunun bağlı veri üyelerinin değerlerini ayarlar ve ardından çağırır `SetData` 100. satırın satır kümesi için bu değerleri yazmak için:  
  
```  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the current row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

product.m_UnitsInStock = 10000;  
  
// Set the data  
HRESULT hr = product.SetData();  
```  
  
## <a name="inserting-rows-into-rowsets"></a>Satır kümelerine ekleme  
 [CRowset::INSERT](../../data/oledb/crowset-insert.md) oluşturur ve erişimci verilerini kullanarak yeni bir satır başlatır. **INSERT** sonra geçerli satır; tamamen yeni bir satır oluşturur sonraki satıra geçerli satır Artır ya da değiştirmeden bırakın belirtmeniz gerekir. Ayarlayarak bunu *bGetRow* parametre:  
  
```  
HRESULT Insert(int nAccessor = 0, bool bGetRow = false)  
```  
  
-   **yanlış** geçerli satır (Bu durumda bu, eklenen satırın'noktaları) sonraki satıra Artır (varsayılan değer) belirtir.  
  
-   **doğru** geçerli satır olduğu kalacağını belirtir.  
  
 Aşağıdaki kod, Ürünler tablosunun sütunlara bağlı veri üyelerinin değerlerini ayarlar ve ardından çağırır **Ekle** satır kümesinin 100. satırın sonra bu değerleri içeren yeni bir satır eklemek için. Yeni satırda tanımsız verileri önlemek için tüm sütun değerlerini ayarlamanız önerilir:  
  
```  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Set the column values for a row of the Product table, then insert the row  
product.m_ProductID = 101;  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Candle" ) );  

product.m_SupplierID = 27857;  
product.m_CategoryID = 372;  
_tcscpy_s(product.m_QuantityPerUnit, product.m_sizeOfQuantityPerUnit,  
           _T( "Pack of 10" ) );  

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
  
 Daha ayrıntılı bir örnek için bkz: [CRowset::INSERT](../../data/oledb/crowset-insert.md).  
  
 Durum ve uzunluk veri üyeleri ayarlama hakkında daha fazla bilgi için bkz: [daha fazla Erişimcilerde alan durumu veri üyeleri](../../data/oledb/field-status-data-members-in-wizard-generated-accessors.md).  
  
## <a name="deleting-rows-from-rowsets"></a>Kümelerinden satırları silme  
 [CRowset::Delete](../../data/oledb/crowset-delete.md) geçerli satır satır kümesinden siler. Aşağıdaki kod çağrıları **silmek** satır kümesinin 100. satırın kaldırmak için:  
  
```  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Delete the row  
HRESULT hr = product.Delete();  
```  
  
## <a name="immediate-and-deferred-updates"></a>Anında ve Ertelenmiş Güncelleştirmeler  
 Aksi belirtilmedikçe, çağrılar `SetData`, **Ekle**, ve **silmek** yöntemleri veri deposu hemen güncelleştirin. Böylece tüketici tüm değişiklikleri yerel önbellekte depolar ve ardından bunları veri deposuna aktarır aşağıdaki güncelleştirme yöntemlerini çağırdığınızda ancak, güncelleştirmelerinin erteleneceği olabilir:  
  
-   [CRowset::Update](../../data/oledb/crowset-update.md) bekleyen tüm geçerli satırda son fetch itibaren yaptığınız değişiklikleri aktarır veya **güncelleştirme** üzerinde çağırın.  
  
-   [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md) bekleyen tüm satırları itibaren son fetch yapılan değişiklikler aktarır veya **güncelleştirme** üzerinde çağırın.  
  
 Güncelleştirme yöntemleri tarafından kullanılmak üzere bu güncelleştirmeyi unutmayın, belirli bir anlamı komutunda değişiklikler yapma ve SQL güncelleştirme komut ile karıştırılmamalıdır (`SetData` SQL güncelleştirme komut eşdeğerdir).  
  
 Ertelenen güncelleştirmeleri, örneğin, bir dizi bankacılık işlemleri gibi durumlarda faydalıdır; bir işlem iptal edilirse sonuncu kaydedildikten sonra değişiklikler yapılana kadar bir dizi göndermek için değişikliği geri alabilirsiniz. Ayrıca, sağlayıcı daha verimli şekilde bir ağ çağrısı dönüşene paketleyebilirsiniz.  
  
 Ertelenen güncelleştirmeleri desteklemek için ayarlamalısınız **DBPROP_IRowsetChange** özelliği "Güncelleştirme işlemlerini desteklemek" bahsedilen özelliklere ek olarak:  
  
```  
pPropSet->AddProperty(DBPROP_IRowsetUpdate, true);  
```  
  
 Çağırdığınızda **güncelleştirme** veya `UpdateAll`, yöntemler aktarımı değişiklikleri yerel önbellekten veri deposuna ve yerel önbelleğini silme. Güncelleştirme değişiklikleri yalnızca geçerli satır aktardığından, uygulamanızın izlemeniz güncelleştirileceğini ve ne zaman güncelleştirileceğini hangi satır çok önemlidir. Aşağıdaki örnekte, iki ardışık satırları güncelleştirmek gösterilmektedir:  
  
```  
// Instantiate a rowset based on the user record class  
CTable<CAccessor<CProductAccessor>> product;  
CSession session;  
  
// Open the rowset and move to the 100th row  
product.Open(session, "Product", &ps, 1);  // ps is the property set  
product.MoveToBookmark(&bookmark, 0);      // Assume that bookmark is set to 100th row  
  
// Change the values of columns "Name" and "Units in Stock" in the 100th row of the Product table  
_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName,  
           _T( "Wick" ) );  

product.m_UnitsInStock = 10000;  

HRESULT hr = product.SetData();  // No changes made to row 100 yet  
product.Update();                 // Update row 100 now  
  
// Change the values of columns "Name" and "Units in Stock" in the 101st row of the Product table  
product.MoveNext();  

_tcscpy_s(product.m_ProductName, product.m_sizeOfProductName  
           _T( "Wax" ) );  

product.m_UnitsInStock = 500;  

HRESULT hr = product.SetData();  // No changes made to row 101 yet  
product.Update();                 // Update row 101 now  
```  
  
 Bekleyen değişikliklerin aktarılmasını sağlamak için çağırmalıdır **güncelleştirme** başka bir satıra geçmeden önce. Ancak, bu sıkıcı veya yetersiz olduğunda, örneğin, yüzlerce satırı güncelleştirmek uygulamanız gerektiğinde kullanabilirsiniz `UpdateAll` tüm satırların aynı anda güncelleştirmek için.  
  
 Örneğin, ilk **güncelleştirme** çağrısı yukarıdaki kodda eksik, satır 100 değişmeden kalır, satır 101 değişirken. Bu noktadan sonra uygulamanızın ya da çağrı gerekirdi `UpdateAll` veya geri taşıyın satır 100 ve çağrısı **güncelleştirme** güncelleştirilmesi ilgili satır.  
  
 Son olarak, değişiklikleri ertelemek için bir temel neden onları geri alabilecek olmaktır. Çağırma [CRowset::Undo](../../data/oledb/crowset-undo.md) bekleyen değişiklikler yapılmadan önce yerel değiştirme önbelleğinin durumunu veri deposu durumuna geri alınır. Bu dikkate almak önemlidir **geri** alma değil (yalnızca en son değiştirilmeden önce durumu) tek adım yerel önbellek durumunu geri; bunun yerine, ilgili satır için yerel önbelleği temizler. Ayrıca, **geri** yalnızca geçerli satır etkiler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-consumer-templates.md)   
 [CRowset sınıfı](../../data/oledb/crowset-class.md)   
 [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx)