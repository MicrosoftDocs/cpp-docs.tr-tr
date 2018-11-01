---
title: 'Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: 5a6a627054cd2e90420ac66a9e56e570f29d281e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594668"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfında, yeni kayıtları bir tabloya toplu ekleme yükleyen verimliliğini artıran yeni bir iyileştirme.

> [!NOTE]
> Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Yeni bir seçenek *dwOptions* parametresi [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevini `optimizeBulkAdd`, çağırmayagerekkalmadanbirdençokkayıtartardaekliyoruzperformansınızıartırır`Requery` veya `Close`. İlk önce kirli olan alanlar `Update` çağrı işaretlenir için kirli olarak sonraki `AddNew` / `Update` çağırır.

Veritabanı sınıfları yararlanmak için kullanıyorsanız `::SQLSetPos` ODBC API işlevini eklemek için düzenleme ve kayıt silme, bu en iyi duruma getirme gerekli değildir.

ODBC imleç kitaplığı yüklenir veya ODBC sürücüsü eklemeyi desteklemez, düzenleme ve silme yoluyla `::SQLSetPos`, bu en iyi duruma getirme toplu geliştirmek performansı ekleyin. Bu iyileştirmesini açmak için ayarlanmış *dwOptions* parametresinde `Open` çağrı kümenizin aşağıdaki için:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Ekleme, Güncelleştirme ve Silme (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)