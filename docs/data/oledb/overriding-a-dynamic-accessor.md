---
title: "Dinamik erişimciyi geçersiz kılma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
- overriding, dynamic accessors
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e06e1d5b0a5aa34116456c342f9cec233edcb6a1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-a-dynamic-accessor"></a>Dinamik Erişimciyi Geçersiz Kılma
Kullandığınızda, dinamik erişimciyi gibi `CDynamicAccessor`, komut **açık** yöntemi, otomatik olarak açılan satır kümesinin sütun bilgileri temel alarak için bir erişimci oluşturur. Tam olarak nasıl sütunları bağlı denetlemek için dinamik erişimciyi geçersiz kılabilirsiniz.  
  
 Dinamik erişimciyi geçersiz kılmak için geçirmek **false** son parametre olarak `CCommand::Open` yöntemi. Bu engeller **açık** erişimci otomatik olarak oluşturmasına. Ardından çağırabilirsiniz `GetColumnInfo` ve arama `AddBindEntry` bağlamak istediğiniz her bir sütun için. Aşağıdaki kod nasıl yapılacağını gösterir:  
  
```  
USES_CONVERSION;  
double   dblProductID;  
  
CCommand<CDynamicAccessor> product;  
// Open the table, passing false to prevent automatic binding   
product.Open(session, _T("Select * FROM Products"), NULL, NULL, DBGUID_DEFAULT, false);  
  
ULONG         nColumns;  
DBCOLUMNINFO*   pColumnInfo;  
// Get the column information from the opened rowset.  
product.GetColumnInfo(&nColumns, &pColumnInfo);  
  
// Bind the product ID as a double.  
pColumnInfo[0].wType          = DBTYPE_R8;  
pColumnInfo[0].ulColumnSize = 8;  
product.AddBindEntry(pColumnInfo[0]);  
  
// Bind the product name as it is.  
product.AddBindEntry(pColumnInfo[1]);  
  
// Bind the reorder level as a string.  
pColumnInfo[8].wType          = DBTYPE_STR;  
pColumnInfo[8].ulColumnSize = 10;  
product.AddBindEntry(pColumnInfo[8]);  
  
// You have finished specifying the bindings. Go ahead and bind.  
product.Bind();  
// Free the memory for the column information that was retrieved in   
// previous call to GetColumnInfo.  
CoTaskMemFree(pColumnInfo);  
  
char*   pszProductName;  
char*   pszReorderLevel;  
bool   bRC;  
  
// Loop through the records tracing out the information.  
while (product.MoveNext() == S_OK)  
{  
   bRC = product.GetValue(1, &dblProductID);  
   pszProductName   = (char*)product.GetValue(2);  
   pszReorderLevel  = (char*)product.GetValue(9);  
  
   ATLTRACE(_T("Override = %lf \"%s\" \"%s\"\n"), dblProductID,  
      A2T(pszProductName), A2T(pszReorderLevel));  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)