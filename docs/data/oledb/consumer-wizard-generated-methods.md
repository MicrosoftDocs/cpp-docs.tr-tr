---
title: "Tüketici Sihirbazı tarafından oluşturulan yöntemler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 2578de53cfab40ee779f0d0444b227b214e3caa9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="consumer-wizard-generated-methods"></a>Tüketici Sihirbazı Tarafından Oluşturulan Yöntemler
ATL OLE DB Tüketici Sihirbazı ve MFC Uygulama Sihirbazı'nı hangisinin bilmeniz gereken bazı işlevler üret. Not birkaç uyarılar olduklarından bazı yöntemler farklı öznitelikli projelerinde uygulanır; her durumda, aşağıda ele alınmıştır. Eklenen kodu görüntüleme hakkında daha fazla bilgi için bkz: [eklenen kod hata ayıklama](/visualstudio/debugger/how-to-debug-injected-code).  
  
-   `OpenAll`veri kaynağı, satır kümeleri, açılır ve varsa yer işaretlerini açar.  
  
-   `CloseAll`Tüm açık satır kümeleri kapatır ve tüm komut yürütmeleri serbest bırakır.  
  
-   `OpenRowset`tüketicinin satır kümesi veya satır kümeleri açmak için OpenAll tarafından çağrılır.  
  
-   `GetRowsetProperties`satır kümesinin özellik hangi özelliklerin ayarlanabileceği ayarlamak için bir işaretçi alır.  
  
-   `OpenDataSource`içinde belirtilen başlatma dizesi kullanarak veri kaynağına açılır **veri bağlantısı özelliklerini** iletişim kutusu.  
  
-   `CloseDataSource`veri kaynağı uygun bir şekilde kapatır.  
  
## <a name="openall-and-closeall"></a>OpenAll ve CloseAll  
  
```  
HRESULT OpenAll();   
void CloseAll();  
```  
  
 Aşağıdaki örnek, nasıl çağırabilirsiniz gösterir `OpenAll` ve `CloseAll` çalıştırdığınızda aynı komutu tekrar tekrar. Aşağıdaki kod örneğinde karşılaştırmak [CCommand::Close](../../data/oledb/ccommand-close.md), çağıran bir değişim gösterir **Kapat** ve `ReleaseCommand` yerine `CloseAll`.  
  
```  
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
 Tanımladığınız gerçekleştiriyorsanız bir `HasBookmark` yöntemi, `OpenAll` kod DBPROP_IRowsetLocate özelliğini ayarlar; yalnızca bunu sağlayıcınız bu özelliği destekliyorsa emin olun.  
  
## <a name="openrowset"></a>OpenRowset  
  
```  
// OLE DB Template version:   
HRESULT OpenRowset(DBPROPSET* pPropSet = NULL)  
// Attribute-injected version:  
HRESULT OpenRowset(const CSession& session, LPCWSTR szCommand = NULL);  
```  
  
 **OpenAll** satır kümesi veya satır kümeleri tüketicideki açmak için bu yöntemi çağırır. Genellikle, arama gerekmez `OpenRowset` birden çok veri kaynakları/oturumları/satır kümeleri ile çalışma istemiyorsanız. `OpenRowset`komut veya tablo sınıfı üstbilgi dosyasında bildirilen:  
  
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
  
 Bu yöntem desteklememesinden öznitelikleri. Bu sürüm, bir oturum nesnesi ve farklı bir geçirebilirsiniz ancak db_command içinde belirtilen komut dizesi varsayılan olarak bir komut dizesini alır. Tanımladığınız gerçekleştiriyorsanız bir `HasBookmark` yöntemi, `OpenRowset` kod DBPROP_IRowsetLocate özelliğini ayarlar; yalnızca bunu sağlayıcınız bu özelliği destekliyorsa emin olun.  
  
```  
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
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet);  
```  
  
 Bu yöntem satır kümesinin özellik kümesi için bir işaretçi alır; Bu işaretçinin DBPROP_IRowsetChange gibi özelliklerini ayarlamak için kullanabilirsiniz. `GetRowsetProperties`Kullanıcı kayıt sınıfında aşağıdaki gibi kullanılır. Ek satır kümesi özelliklerini ayarlamak için bu kodu değiştirebilirsiniz:  
  
```  
void GetRowsetProperties(CDBPropSet* pPropSet)  
{  
   pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_IRowsetChange, true, DBPROPOPTIONS_OPTIONAL);  
   pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
}  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir genel tanımlamamalıdır `GetRowsetProperties` yöntemi ile bir çakışma çünkü sihirbaz tarafından tanımlanan. Bu şablonlu ve öznitelikli projelerle Alma Sihirbazı tarafından oluşturulan bir yöntem olduğunu unutmayın; öznitelikleri, bu kod yerleştirir değil.  
  
## <a name="opendatasource-and-closedatasource"></a>OpenDataSource ve CloseDataSource  
  
```  
HRESULT OpenDataSource();   
void CloseDataSource();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Sihirbaz yöntemleri tanımlar `OpenDataSource` ve `CloseDataSource`; `OpenDataSource` çağrıları [CDataSource::OpenFromInitializationString](../../data/oledb/cdatasource-openfrominitializationstring.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sihirbaz Kullanarak bir OLE DB Tüketicisi Oluşturma](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)