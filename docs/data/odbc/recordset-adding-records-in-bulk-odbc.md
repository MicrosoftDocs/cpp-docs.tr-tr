---
title: 'Kayıt kümesi: Ekleme kayıtları toplu yakalama (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
ms.openlocfilehash: a2c3eab8bb4c0e8db76fceb5a2dafd16a4a07079
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038615"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt kümesi: Ekleme kayıtları toplu yakalama (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfında, yeni kayıtları bir tabloya toplu ekleme yükleyen verimliliğini artıran yeni bir iyileştirme.

> [!NOTE]
> Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Yeni bir seçenek *dwOptions* parametresi [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevini `optimizeBulkAdd`, çağırmayagerekkalmadanbirdençokkayıtartardaekliyoruzperformansınızıartırır`Requery` veya `Close`. İlk önce kirli olan alanlar `Update` çağrı işaretlenir için kirli olarak sonraki `AddNew` / `Update` çağırır.

Veritabanı sınıfları yararlanmak için kullanıyorsanız `::SQLSetPos` ODBC API işlevini eklemek için düzenleme ve kayıt silme, bu en iyi duruma getirme gerekli değildir.

ODBC imleç kitaplığı yüklenir veya ODBC sürücüsü eklemeyi desteklemez, düzenleme ve silme yoluyla `::SQLSetPos`, bu en iyi duruma getirme toplu geliştirmek performansı ekleyin. Bu iyileştirmesini açmak için ayarlanmış *dwOptions* parametresinde `Open` çağrı kümenizin aşağıdaki için:

```
appendOnly | optimizeBulkAdd
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)<br/>
[Kayıt kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)