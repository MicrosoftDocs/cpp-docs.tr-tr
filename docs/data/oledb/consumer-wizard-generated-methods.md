---
title: Tüketici Sihirbazı tarafından oluşturulan yöntemler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OpenAll method
- attribute-injected classes and methods
- wizard-generated classes and methods
- OLE DB consumers, wizard-generated classes and methods
- methods [C++], OLE DB Consumer Wizard-generated
- CloseDataSource method
- consumer wizard-generated classes and methods
- OpenDataSource method
- CloseAll method
- OpenRowset method
- GetRowsetProperties method
ms.assetid: d80ee51c-8bb3-4dca-8760-5808e0fb47b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9c8a3605a94e0feffa1072d1c7cd92a8bdfecb66
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340886"
---
# <a name="consumer-wizard-generated-methods"></a>Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler
ATL OLE DB Tüketicisi Sihirbazı ve MFC Uygulama Sihirbazı hangi bilmeniz gereken bazı işlevler oluşturun. Bazı uyarılar olduğundan bazı yöntemler öznitelikli projelerinde, farklı uygulandığını unutmayın. her durumda, aşağıda ele alınmıştır. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kodda hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).  
  
-   `OpenAll` veri kaynağı, satır açılır ve kullanılabilir olmaları durumunda yer işaretlerini açar.  
  
-   `CloseAll` Tüm açık satır kümeleri kapatır ve tüm komut yürütme serbest bırakır.  
  
-   `OpenRowset` tüketicinin satır veya satır kümeleri açma OpenAll tarafından çağrılır.  
  
-   `GetRowsetProperties` Hangi özellikler ile ayarlanabilir satır kümesinin özelliği için bir işaretçi alır.  
  
-   `OpenDataSource` içinde belirtilen başlatma dizesi kullanarak veri kaynağına açılır **veri bağlantı özellikleri** iletişim kutusu.  
  
-   `CloseDataSource` veri kaynağı, uygun bir şekilde kapatılır.  
  
## <a name="openall-and-closeall"></a>OpenAll ve CloseAll  
  
```cpp  
HRESULT OpenAll();   

void CloseAll();  
```  
  
 Aşağıdaki örnek nasıl çağırabilirsiniz gösterir `OpenAll` ve `CloseAll` yürüttüğünüzde aynı komutu tekrar tekrar. Aşağıdaki kod örneğinde karşılaştırma [CCommand::Close](../../data/oledb/ccommand-close.md), çağıran bir değişim gösterir `Close` ve `ReleaseCommand` yerine `CloseAll`.  
  
```cpp  
int main(int argc, char* argv[])  
{  
   HRESULT hr;  
  
   hr = CoInitialize(NULL);  
  
   CCustOrdersDetail rs;      // Your CCommand-derived class  
   rs.m_OrderID = 10248;      // Open order 10248  
   hr = rs.OpenAll();         // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the first command execution  
   rs.Close();  
  
   rs.m_OrderID = 10249;      // Open order 10249 (a new order)  
   hr = rs.Open();            // (Open also executes the command)  
   hr = rs.MoveFirst();         // Move to the first row and print it  
   printf( "Name: %s, Unit Price: %d, Quantity: %d, Discount %d, Extended Price %d\n", rs.m_ProductName, rs.m_UnitPrice.int64, rs.m_Quantity, rs.m_Discount, rs.m_ExtendedPrice.int64 );  
  
   // Close the second command execution;  
   // Instead of rs.CloseAll() you could call  
   // rs.Close() and rs.ReleaseCommand():  
   rs.CloseAll();  
  
   CoUninitialize();  
   return 0;  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Tanımladığınız gerçekleştiriyorsanız bir `HasBookmark` yöntemi `OpenAll` kod DBPROP_IRowsetLocate özelliğini ayarlar; yalnızca bunu sağlayıcınız bu özellik destekliyorsa emin olun.  
  
## <a name="openrowset"></a>OpenRowset  
  
```cpp  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 `OpenAll` satır veya satır kümeleri tüketicideki açmak için bu yöntemi çağırır. Genellikle, arama gerekmez `OpenRowset` birden çok veri kaynakları/oturumları/satır kümesi ile çalışmak istemiyorsanız. `OpenRowset` komut veya tablo sınıf üstbilgi dosyasında bildirilir:  
  
```  
// OLE DB Template version:  
HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
{  
   HRESULT hr = Open(m_session, NULL, pPropSet);  
   #ifdef _DEBUG  
   if(FAILED(hr))  
      AtlTraceErrorRecords(hr);  
   #endif  
   return hr;  
}  
```  
  
 Öznitelikler bu yöntem farklı şekilde uygular. Bu sürüm, bir oturum nesnesi ve farklı bir geçirebilirsiniz ancak db_command içinde belirtilen komut dizesi varsayılan olarak bir komut dizesi alır. Tanımladığınız gerçekleştiriyorsanız bir `HasBookmark` yöntemi `OpenRowset` kod DBPROP_IRowsetLocate özelliğini ayarlar; yalnızca bunu sağlayıcınız bu özellik destekliyorsa emin olun.  
  
```cpp  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand=NULL)  
{  
  
   DBPROPSET *pPropSet = NULL;  
   CDBPropSet propset(DBPROPSET_ROWSET);  
   __if_exists(HasBookmark)  
  
   {  
      propset.AddProperty(DBPROP_IRowsetLocate, true);  
      pPropSet= &propset;  
      }  
...  
}  
```  
  
## <a name="getrowsetproperties"></a>GetRowsetProperties  
  
```cpp 
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 Bu yöntem satır kümesinin özellik kümesi için bir işaretçi alır; Bu işaretçinin DBPROP_IRowsetChange gibi özelliklerini ayarlamak için kullanabilirsiniz. `GetRowsetProperties` Kullanıcı kayıt sınıfı şu şekilde kullanılır. Ek satır kümesi özelliklerini ayarlamak için bu kodu değiştirebilirsiniz:  
  
```cpp  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Genel bir tanımlanmamalıdır `GetRowsetProperties` yöntemi ile bir çakışma çünkü sihirbaz tarafından tanımlanan. Şablonlu ve öznitelikli projeleriyle Alma Sihirbazı tarafından oluşturulan bir yöntem olduğunu unutmayın. öznitelikler, bu kod ekleme değil.  
  
## <a name="opendatasource-and-closedatasource"></a>OpenDataSource ve CloseDataSource  
  
```cpp  
HRESULT OpenDataSource();   

void CloseDataSource();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sihirbaz yöntemlerini `OpenDataSource` ve `CloseDataSource`; `OpenDataSource` çağrıları [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)