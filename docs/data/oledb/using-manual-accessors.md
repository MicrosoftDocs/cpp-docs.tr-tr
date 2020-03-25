---
title: El ile Çalışan Erişimcileri Kullanma
ms.date: 10/24/2018
helpviewer_keywords:
- command handling, OLE DB Templates
- manual accessors
- accessors [C++], manual
ms.assetid: 29f00a89-0240-482b-8413-4120b9644672
ms.openlocfilehash: a6c0e5236702229a61a828344ba5d0d288898aee
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209332"
---
# <a name="using-manual-accessors"></a>El ile Çalışan Erişimcileri Kullanma

Bilinmeyen bir komutu işlerken yapmanız gereken dört şey vardır:

- Parametreleri belirleme

- Komutu yürütün

- Çıkış sütunlarını belirleme

- Birden çok dönüş satır kümesi olup olmadığını görün

OLE DB tüketici şablonlarıyla bu işlemleri yapmak için `CManualAccessor` sınıfını kullanın ve şu adımları izleyin:

1. Şablon parametresi olarak `CManualAccessor` bir `CCommand` nesnesi açın.

    ```cpp
    CCommand<CManualAccessor, CRowset, CMultipleResults> rs;
    ```

1. `IDBSchemaRowset` arabirimi için oturumu sorgulayın ve yordam parametreleri satır kümesini kullanın. `IDBSchemaRowset` arabirimi kullanılamıyorsa, `ICommandWithParameters` arabirimini sorgulayın. Bilgi için `GetParameterInfo` çağırın. Arabirim yoksa, hiçbir parametre olmadığını varsayabilirsiniz.

1. Her parametre için, parametreleri eklemek ve bunları ayarlamak için `AddParameterEntry` çağırın.

1. Satır kümesini açın, ancak bind parametresini **false**olarak ayarlayın.

1. Çıkış sütunlarını almak için `GetColumnInfo` çağırın. Bağlama çıkış sütununu eklemek için `AddBindEntry` kullanın.

1. Daha fazla satır kümelerinin kullanılabilir olup olmadığını anlamak için `GetNextResult` çağırın. 2 ila 5 arasındaki adımları yineleyin.

El ile erişimciye bir örnek için bkz. [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneğindeki `CDBListView::CallProcedure`.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
