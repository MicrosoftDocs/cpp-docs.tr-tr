---
title: El ile Çalışan Erişimcileri Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: 8b969b7bb939d8e7d2217234795b564e8d137208
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651769"
---
# <a name="using-manual-accessors"></a>El ile Çalışan Erişimcileri Kullanma

Bilinmeyen bir komutu işlerken dört şeyler vardır:

- Parametreleri belirleme

- Komutu yürütün

- Çıktı sütunları belirleyin

- Birden fazla dönüş satır kümeleri olup olmadığını

OLE DB Tüketici Şablonları ile bunları yapmak için `CManualAccessor` sınıfı ve aşağıdaki adımları izleyin:

1. Açık bir `CCommand` nesnesi ile `CManualAccessor` şablon parametresi olarak.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Oturum için sorgu `IDBSchemaRowset` arabirim ve yordam parametreleri satır kümesi kullanın. Varsa `IDBSchemaRowset` arabirimi kullanılamıyor, sorgu `ICommandWithParameters` arabirimi. Çağrı `GetParameterInfo` bilgi. Hiçbiri arabirimi varsa, hiçbir parametre yok varsayabilirsiniz.

1. Her parametre için çağrı `AddParameterEntry` parametreleri ekleyin ve bunları ayarlamak için.

1. Açık satır kümesi, ancak bağlama parametresini **false**.

1. Çağrı `GetColumnInfo` çıkış sütunları alınamıyor. Kullanım `AddBindEntry` çıkış sütunu bağlama eklemek için.

1. Çağrı `GetNextResult` daha fazla satır kümeleri kullanılabilir olup olmadığını belirlemek için. 2-5 arası adımları tekrarlayın.

El ile erişimci örneği için bkz: `CDBListView::CallProcedure` içinde [DBVIEWER](https://github.com/Microsoft/VCSamples) örnek.

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)