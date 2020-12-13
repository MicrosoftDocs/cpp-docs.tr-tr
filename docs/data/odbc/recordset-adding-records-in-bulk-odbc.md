---
description: 'Şu konuda daha fazla bilgi edinin: kayıt kümesi: kayıtları toplu ekleme (ODBC)'
title: 'Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: 5cb47fc8e96a38b2e5cc6c83cf464f28f2a85aaf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340404"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfının, bir tabloya toplu olarak yeni kayıtlar eklerken verimliliği artıran yeni bir iyileştirmesi vardır.

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme kullanıyorsanız, bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

[CRecordset:: Open](../../mfc/reference/crecordset-class.md#open) üye Işlevine *dwOptions* parametresine yönelik yeni bir seçenek, `optimizeBulkAdd` veya çağrılmadan birden çok kayıt art arda eklenirken performansı geliştirir `Requery` `Close` . Yalnızca ilk çağrıdan önce kirli olan alanlar `Update` sonraki çağrılar için kirli olarak işaretlenir `AddNew` / `Update` .

`::SQLSetPos`Kayıt ekleme, düzenlemesi ve silme için ODBC API işlevinden yararlanmak üzere veritabanı sınıflarını kullanıyorsanız, bu iyileştirme gereksizdir.

ODBC Imleç kitaplığı yüklenirse veya ODBC sürücüsü ekleme, düzenlemenin ve silmeyi desteklemez `::SQLSetPos` , bu iyileştirme toplu ekleme performansını artırmalıdır. Bu iyileştirmeyi açmak için, kayıt kümenizin çağrısındaki *dwOptions* parametresini `Open` Şu şekilde ayarlayın:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: kayıtları ekleme, güncelleştirme ve silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt kümesi: kayıtları kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)
