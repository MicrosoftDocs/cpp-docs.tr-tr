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
ms.openlocfilehash: f65bd0f90832039d453d84ab9765781c30750318
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91507374"
---
# <a name="commands-and-tables"></a>Komutlar ve Tablolar

Komutlar ve tablolar, satır kümelerine erişmenize izin verir; diğer bir deyişle, satır kümelerini açın, komutları yürütün ve sütunları bağlayın. [CCommand](../../data/oledb/ccommand-class.md) ve [CTable](../../data/oledb/ctable-class.md) sınıfları, sırasıyla komut ve tablo nesnelerini oluşturur. Bu sınıflar, aşağıdaki şekilde gösterildiği gibi [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) 'den türetilir.

![CCommand ve CTable](../../data/oledb/media/vccommandstables.gif "CCommand ve CTable")<br/>
Komut ve tablo sınıfları

Önceki tabloda, `TAccessor` [erişimci türlerinde](../../data/oledb/accessors-and-rowsets.md)listelenen herhangi bir erişimci türü olabilir. `TRowset`[satır kümesi türlerinde](../../data/oledb/accessors-and-rowsets.md)listelenen herhangi bir satır kümesi türü olabilir. `TMultiple` sonuç türünü belirtir (tek veya birden çok sonuç kümesi).

[ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md) , bir komut veya tablo nesnesi isteyip istemediğinizi belirtmenizi sağlar.

- Komutları olmayan veri kaynakları için `CTable` sınıfını kullanabilirsiniz. Genellikle parametre belirtmeyen ve birden çok sonuç gerektirmeyen basit satır kümelerinde kullanılır. Bu basit sınıf, belirttiğiniz tablo adı kullanılarak bir veri kaynağındaki bir tabloyu açar.

- Komutları destekleyen veri kaynakları için, `CCommand` bunun yerine sınıfını kullanabilirsiniz. Bir komutu yürütmek için bu sınıfta [Açık](./ccommand-class.md#open) ' ı çağırın. Alternatif olarak, birden `Prepare` çok kez yürütmek istediğiniz bir komutu hazırlamak için öğesini çağırabilirsiniz.

   `CCommand` üç şablon bağımsız değişkeni vardır: erişimci türü, satır kümesi türü ve sonuç türü ( `CNoMultipleResults` , varsayılan olarak veya `CMultipleResults` ). Belirtirseniz `CMultipleResults` , `CCommand` sınıfı `IMultipleResults` arabirimini destekler ve birden çok satır kümesi işler. [DBViewer](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Consumer) örneği, birden çok sonucun nasıl işleneceğini gösterir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)
