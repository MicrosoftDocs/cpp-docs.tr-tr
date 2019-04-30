---
title: Komutlar ve Tablolar
ms.date: 11/19/2018
helpviewer_keywords:
- OLE DB consumer templates, table support
- CCommand class, OLE DB consumer templates
- commands [C++], OLE DB Consumer Templates
- CTable class
- CAccessorRowset class, command and table classes
- rowsets, accessing
- tables [C++], OLE DB Consumer Templates
- OLE DB consumer templates, command support
ms.assetid: 4bd3787b-6d26-40a9-be0c-083080537c12
ms.openlocfilehash: b2cdf7a2b439af3a564f5801e015f6064fb141dc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409097"
---
# <a name="commands-and-tables"></a>Komutlar ve Tablolar

Komutlar ve tablolar satır kümeleri erişmenize olanak sağlar. diğer bir deyişle, satır kümeleri'ni açın, komutları yürütmek ve sütunları bağlayın. [CCommand](../../data/oledb/ccommand-class.md) ve [CTable](../../data/oledb/ctable-class.md) sınıflar komut ve tablo nesneleri sırasıyla örneği oluşturun. Bu sınıfların türetilmesi [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) aşağıdaki şekilde gösterildiği gibi.

![CCommand ve CTable](../../data/oledb/media/vccommandstables.gif "CCommand ve CTable")<br/>
Komut ve tablo sınıfları

Önceki tabloda `TAccessor` herhangi bir erişimci türü içinde listelenen [erişimci türleri](../../data/oledb/accessors-and-rowsets.md). `TRowset` satır kümesi her türlü içinde listelenen [satır kümesi türleri](../../data/oledb/accessors-and-rowsets.md). `TMultiple` (tek veya birden çok sonuç kümesi) sonuç türünü belirtir.

[ATL OLE DB Tüketicisi Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md) bir komut veya tablo nesnesi istediğinizi belirtmenize olanak tanır.

- Komutları olmayan veri kaynakları için kullanabileceğiniz `CTable` sınıfı. Genel parametre belirtmezseniz ve birden çok sonuç gerektiren basit satır kümeleri için kullanırsınız. Bu basit sınıf, belirttiğiniz bir tablo adı kullanarak bir veri kaynağında bir tablo açılır.

- Komutları destekleyen veri kaynakları için kullanabileceğiniz `CCommand` bunun yerine sınıf. Bir komut çalıştırmak için çağrı [açık](../../data/oledb/ccommand-open.md) bu sınıfta. Alternatif olarak, çağırabilirsiniz `Prepare` birden çok kez yürütmek istediğiniz komutları hazırlamak için.

   `CCommand` üç şablon bağımsız değişkenlere sahiptir: erişimci türü, bir satır kümesi türü ve bir sonuç türü (`CNoMultipleResults`, varsayılan olarak veya `CMultipleResults`). Belirtirseniz `CMultipleResults`, `CCommand` sınıfı destekler `IMultipleResults` arabirim ve birden çok satır kümeleri işler. [DBVIEWER](https://github.com/Microsoft/VCSamples) örnek, birden çok sonuçların nasıl işleneceğini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)