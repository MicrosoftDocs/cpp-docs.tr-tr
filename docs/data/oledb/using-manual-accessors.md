---
title: El ile Çalışan Erişimcileri Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: b76c6a2d0af404bc526fee8f511320a58ffd86ec
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218292"
---
# <a name="using-manual-accessors"></a>El ile Çalışan Erişimcileri Kullanma

Bilinmeyen bir komutu işlerken yapmanız gereken dört şey vardır:

- Parametreleri belirleme

- Komutu yürütün

- Çıkış sütunlarını belirleme

- Birden çok dönüş satır kümesi olup olmadığını görün

OLE DB tüketici şablonlarıyla bu işlemleri yapmak için, `CManualAccessor` sınıfını kullanın ve şu adımları izleyin:

1. `CCommand` `CManualAccessor` Şablon parametresi olarak bir nesnesi açın.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. Arabirim için oturumu sorgulayın `IDBSchemaRowset` ve yordam parametreleri satır kümesini kullanın. `IDBSchemaRowset`Arabirim kullanılabilir değilse, arabirim için sorgulama yapın `ICommandWithParameters` . `GetParameterInfo`Bilgi için çağrı yapın. Arabirim yoksa, hiçbir parametre olmadığını varsayabilirsiniz.

1. Her parametre için, `AddParameterEntry` parametreleri ekleme ve bunları ayarlama çağrısı yapın.

1. Satır kümesini açın, ancak bind parametresini olarak ayarlayın **`false`** .

1. `GetColumnInfo`Çıkış sütunlarını almak için çağırın. `AddBindEntry`Bağlama çıkış sütununu eklemek için kullanın.

1. `GetNextResult`Daha fazla satır kümesinin kullanılabilir olup olmadığını belirleme çağrısı yapın. 2 ila 5 arasındaki adımları yineleyin.

El ile erişimciye bir örnek için bkz `CDBListView::CallProcedure` . [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneği.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
