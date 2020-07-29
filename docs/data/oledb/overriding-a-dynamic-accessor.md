---
title: Dinamik Erişimciyi Geçersiz Kılma
ms.date: 10/19/2018
helpviewer_keywords:
- accessors [C++], dynamic
- dynamic accessors
- overriding, dynamic accessors
ms.assetid: cbefd156-6da5-490d-b795-c2d7d874f7ce
ms.openlocfilehash: d616079745c0a5adfa4167e4bdde8e7768f9b9d8
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218318"
---
# <a name="overriding-a-dynamic-accessor"></a>Dinamik Erişimciyi Geçersiz Kılma

Gibi bir dinamik erişimci kullandığınızda `CDynamicAccessor` , komut `Open` yöntemi, açılan satır kümesinin sütun bilgilerine göre sizin için otomatik olarak bir erişimci oluşturur. Sütunların nasıl bağlandığını tam olarak denetlemek için Dinamik erişimciyi geçersiz kılabilirsiniz.

Dinamik erişimciyi geçersiz kılmak için **`false`** yönteme son parametre olarak geçirin `CCommand::Open` . Bu, `Open` erişimcinin otomatik olarak oluşturulmasını engeller. Daha sonra bağlamak istediğiniz `GetColumnInfo` her bir sütun için çağrı ve çağrı yapabilirsiniz `AddBindEntry` . Aşağıdaki kod nasıl yapılacağını göstermektedir:

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

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
