---
title: 'Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: f561cb0275933a973e97ef0518148e81e14a0234
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213024"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfının, bir tabloya toplu olarak yeni kayıtlar eklerken verimliliği artıran yeni bir iyileştirmesi vardır.

> [!NOTE]
> Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

[CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) üye Işlevine yönelik *dwOptions* parametresine yönelik yeni bir seçenek, `optimizeBulkAdd`, `Requery` veya `Close`çağrılmadan arka arkaya birden çok kayıt eklerken performansı geliştirir. Yalnızca ilk `Update` çağrısından önce kirli olan alanlar, sonraki `AddNew`/`Update` çağrıları için kirli olarak işaretlenir.

Kayıt ekleme, düzenlemesi ve silme için `::SQLSetPos` ODBC API işlevinden yararlanmak üzere veritabanı sınıflarını kullanıyorsanız, bu iyileştirme gereksizdir.

ODBC Imleç kitaplığı yüklenirse veya ODBC sürücüsü `::SQLSetPos`ekleme, düzenlemenin ve silmeyi desteklemiyorsa, bu iyileştirmenin toplu ekleme performansını artırmalıdır. Bu iyileştirmeyi açmak için, kayıt kümeniz için `Open` çağrısındaki *dwOptions* parametresini aşağıdaki şekilde ayarlayın:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
