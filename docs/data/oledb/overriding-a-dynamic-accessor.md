---
title: Dinamik Erişimciyi Geçersiz Kılma
ms.date: 10/19/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
- overriding, dynamic accessors
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
ms.openlocfilehash: 01beab80fb8574e0caa4ad3054d174c60106ce94
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039196"
---
# <a name="overriding-a-dynamic-accessor"></a>Dinamik Erişimciyi Geçersiz Kılma

Kullandığınızda, dinamik erişimciyi gibi `CDynamicAccessor`, komut `Open` açık satır kümesi sütunu bilgilere göre otomatik olarak temel için erişimci yöntemi oluşturur. Sütunları tam olarak nasıl ilişkili denetlemek için dinamik erişimciyi geçersiz kılabilirsiniz.

Dinamik erişimciyi geçersiz kılma için geçirin **false** son parametre olarak `CCommand::Open` yöntemi. Bu engeller `Open` erişimci otomatik olarak oluşturmasını. Ardından çağırabilirsiniz `GetColumnInfo` ve çağrı `AddBindEntry` bağlamak istediğiniz her bir sütun için. Aşağıdaki kod nasıl yapılacağını gösterir:

```cpp
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

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)