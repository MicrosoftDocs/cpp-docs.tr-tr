---
title: El ile çalışan erişimcileri kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ee82a780690c6d5eba7b30debdc592a26ef2cbcc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105910"
---
# <a name="using-manual-accessors"></a>El ile Çalışan Erişimcileri Kullanma
Bilinmeyen komut işlenirken dört şeyler vardır:  
  
-   Parametreleri belirleme  
  
-   Komutu yürütün  
  
-   Çıkış sütunlarında belirleme  
  
-   Birden çok dönüş satır kümeleri olup olmadığını  
  
 OLE DB Tüketici Şablonları ile bunun için kullanın `CManualAccessor` sınıfı ve aşağıdaki adımları izleyin:  
  
1.  Açık bir `CCommand` nesnesi ile `CManualAccessor` şablon parametresi olarak.  
  
    ```  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Oturum için sorgu **IDBSchemaRowset** arabirim ve yordam parametreleri satır kullanın. Varsa **IDBSchemaRowset** arabirimi kullanılabilir değil, sorgu `ICommandWithParameters` arabirimi. Çağrı `GetParameterInfo` bilgi. Hiçbiri arabirimi varsa, parametre yok varsayabilirsiniz.  
  
3.  Her bir parametreyi çağırmak `AddParameterEntry` parametreleri ekleyin ve bunları ayarlayın.  
  
4.  Satır kümesi'ni açın, ancak bağlama parametre kümesine **false**.  
  
5.  Çağrı `GetColumnInfo` çıkış sütunlarında alınamadı. Kullanım `AddBindEntry` çıktı sütun bağlama eklemek için.  
  
6.  Çağrı `GetNextResult` daha fazla satır kümeleri kullanılabilir olup olmadığını belirlemek için. 2 ile 5 arasındaki adımları tekrarlayın.  
  
 El ile erişimci örneği için bkz: **CDBListView::CallProcedure** içinde [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)