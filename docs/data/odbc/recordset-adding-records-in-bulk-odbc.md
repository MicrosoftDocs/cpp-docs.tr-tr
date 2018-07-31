---
title: 'Kayıt kümesi: Kayıtları toplu yakalama (ODBC) içinde ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 167cf817074a992fae5492ba387ea8a3589a10ec
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337235"
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)
Bu konu MFC ODBC sınıflarına uygulanır.  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfında, yeni kayıtları bir tabloya toplu ekleme yükleyen verimliliğini artıran yeni bir iyileştirme.  
  
> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Yeni bir seçenek *dwOptions* parametresi [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevini `optimizeBulkAdd`, çağırmayagerekkalmadanbirdençokkayıtartardaekliyoruzperformansınızıartırır`Requery` veya `Close`. İlk önce kirli olan alanlar `Update` çağrı işaretlenir için kirli olarak sonraki `AddNew` / `Update` çağırır.  
  
 Veritabanı sınıfları yararlanmak için kullanıyorsanız `::SQLSetPos` ODBC API işlevini eklemek için düzenleme ve kayıt silme, bu en iyi duruma getirme gerekli değildir.  
  
 ODBC imleç kitaplığı yüklenir veya ODBC sürücüsü eklemeyi desteklemez, düzenleme ve silme yoluyla `::SQLSetPos`, bu en iyi duruma getirme toplu geliştirmek performansı ekleyin. Bu iyileştirmesini açmak için ayarlanmış *dwOptions* parametresinde `Open` çağrı kümenizin aşağıdaki için:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)