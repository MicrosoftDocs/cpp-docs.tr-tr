---
title: "Sağlayıcınızdaki bir özelliğe başvurma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 625dbceb65a7f387e8ce83b70de2cccc7f6774f9
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="referencing-a-property-in-your-provider"></a>Sağlayıcınızdaki Bir Özelliğe Başvurma
Özellik grubu ve özellik kimliği özelliği için bulun. Daha fazla bilgi için bkz: [OLE DB özellikleri](https://msdn.microsoft.com/en-us/library/ms722734.aspx) içinde *OLE DB Programcının Başvurusu*.  
  
 Aşağıdaki örnek, satır kümesinden bir özellik get yapılmaya çalışılırken olduğunu varsayar. Oturum ya da komutu kullanmak için kodu benzer ancak farklı bir arabirim kullanır.  
  
 Oluşturma bir [CDBPropSet](../../data/oledb/cdbpropset-class.md) Oluşturucusu parametre olarak özellik grubunu kullanarak nesne. Örneğin:  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 Çağrı [AddProperty](../../data/oledb/cdbpropset-addproperty.md), özellik kimliği ve bir değer özelliğine atanacak geçirme. Değerin türü kullandığınız özelliğe bağlıdır.  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 Kullanım `IRowset` çağırmak için arabirimi **GetProperties**. Bir parametre özellik geçirin. Son kod aşağıdaki gibidir:  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  

DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  

HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  

if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Sağlayıcı Şablonlarıyla Çalışma](../../data/oledb/working-with-ole-db-provider-templates.md)