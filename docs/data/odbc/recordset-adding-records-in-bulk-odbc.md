---
title: "Kayıt kümesi: Kayıtları toplu (ODBC) ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ODBC recordsets, adding records
- recordsets, adding records
- bulk record additions to recordsets
ms.assetid: 4685f656-14b9-4f10-a1c5-147b2b89a0b4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 251d2fa4b7c28c1458fdc5643c9b17c53ba1b0ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-adding-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Ekleme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 MFC [CRecordset](../../mfc/reference/crecordset-class.md) sınıfı, yeni kayıtları bir tabloya toplu ekleme yükleyen verimliliğini artırır yeni bir iyileştirme sahiptir.  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız bkz [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Yeni bir seçenek **dwOptions** parametresi [CRecordset::Open](../../mfc/reference/crecordset-class.md#open) üye işlevi **optimizeBulkAdd**, birden çok kayıt eklerken performansı artırır Art arda çağırmadan **Requery** veya **Kapat**. Yalnızca ilk önce kirli alanları **güncelleştirme** çağrısı işaretlenir için kirli olarak sonraki `AddNew` / **güncelleştirme** çağrıları.  
  
 Veritabanı sınıfları yararlanmak için kullanıyorsanız **:: SQLSetPos** ODBC API işlev eklemek için düzenleme ve kayıt silme, bu en iyi duruma getirme gerekli değildir.  
  
 ODBC imleç kitaplığı yüklenir veya ODBC sürücüsü eklenmeyi desteklemiyor, düzenleme ve silme ile **:: SQLSetPos**, bu en iyi duruma getirme toplu artırmak performans ekleyin. Bu iyileştirmeyi etkinleştirmek için ayarlanmış **dwOptions** parametresinde **açık** çağrısı şu kümeniz için:  
  
```  
appendOnly | optimizeBulkAdd  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: Ekleme, güncelleştirme ve silme kayıtlarını (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)   
 [Kayıt Kümesi: Kayıtları Kilitleme (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)