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
ms.openlocfilehash: c732bcf45f2dfbd4927366670aed6bfbdcfb4721
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679993"
---
# <a name="using-manual-accessors"></a>El ile Çalışan Erişimcileri Kullanma
Bilinmeyen bir komutu işlerken dört şeyler vardır:  
  
-   Parametreleri belirleme  
  
-   Komutu yürütün  
  
-   Çıktı sütunları belirleyin  
  
-   Birden fazla dönüş satır kümeleri olup olmadığını  
  
 OLE DB tüketici şablonlarıyla Bunu yapmak için `CManualAccessor` sınıfı ve aşağıdaki adımları izleyin:  
  
1.  Açık bir `CCommand` nesnesi ile `CManualAccessor` şablon parametresi olarak.  
  
    ```cpp  
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;  
    ```  
  
2.  Oturum için sorgu `IDBSchemaRowset` arabirim ve yordam parametreleri satır kümesi kullanın. Varsa `IDBSchemaRowset` arabirimi kullanılabilir değil, sorgu `ICommandWithParameters` arabirimi. Çağrı `GetParameterInfo` bilgi. Hiçbiri arabirimi varsa, hiçbir parametre yok varsayabilirsiniz.  
  
3.  Her parametre için çağrı `AddParameterEntry` parametreleri ekleyin ve bunları ayarlamak için.  
  
4.  Açık satır kümesi, ancak bağlama parametresini **false**.  
  
5.  Çağrı `GetColumnInfo` çıkış sütunları alınamıyor. Kullanım `AddBindEntry` çıkış sütunu bağlama eklemek için.  
  
6.  Çağrı `GetNextResult` daha fazla satır kümeleri kullanılabilir olup olmadığını belirlemek için. 2-5 arası adımları tekrarlayın.  
  
 El ile erişimci örneği için bkz: `CDBListView::CallProcedure` içinde [DBVIEWER](https://github.com/Microsoft/VCSamples) örnek.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)