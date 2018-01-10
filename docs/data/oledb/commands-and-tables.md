---
title: Komutlar ve tablolar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c42422c156a51cac161f0cc75dfd1947b92eb20e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="commands-and-tables"></a>Komutlar ve Tablolar
Komutlar ve tablolar, satır kümeleri erişmesine izin ver; diğer bir deyişle, satır kümeleri'ni açın, komutları yürütün ve sütunları bağlayın. [CCommand](../../data/oledb/ccommand-class.md) ve [CTable](../../data/oledb/ctable-class.md) sınıfları komut ve tablo nesneleri sırasıyla örneği. Bu sınıf türetin [CAccessorRowset](../../data/oledb/caccessorrowset-class.md) aşağıdaki resimde gösterildiği gibi.  
  
 ![CCommand ve CTable](../../data/oledb/media/vccommandstables.gif "vccommandstables")  
Komut ve tablo sınıfları  
  
 Önceki tabloda `TAccessor` herhangi bir erişimci türü listelenebilir [erişimci türleri](../../data/oledb/accessors-and-rowsets.md). *CRowset* herhangi bir satır kümesi türü listelenebilir [satır kümesi türleri](../../data/oledb/accessors-and-rowsets.md). *TMultiple* (tek veya birden çok sonuç kümesi) sonuç türünü belirtir.  
  
 [ATL OLE DB Tüketici Sihirbazı](../../atl/reference/atl-ole-db-consumer-wizard.md) bir komut veya tablo nesnesi isteyip istemediğinizi belirtmenizi sağlar.  
  
-   Komutları olmayan veri kaynağı için kullandığınız `CTable` sınıfı. Genellikle hiçbir parametrelerini belirtin ve birden çok sonuç gerektiren basit satır kümeleri için kullanırsınız. Bu basit sınıf belirttiğiniz bir tablo adı kullanarak bir veri kaynağında tablo açar.  
  
-   Komutları destekleyen veri kaynakları için kullandığınız `CCommand` yerine sınıfı. Bir komut çalıştırmak için çağrı [açık](../../data/oledb/ccommand-open.md) bu sınıftaki. Alternatif olarak, çağırabilirsiniz `Prepare` birden çok kez çalıştırmak istediğiniz komutları hazırlamak için.  
  
     **CCommand** üç şablon bağımsız değişkenlere sahiptir: erişimci türü, bir satır türü ve bir sonuç türü (`CNoMultipleResults`, varsayılan olarak, veya `CMultipleResults`). Belirtirseniz `CMultipleResults`, `CCommand` sınıf destekler **IMultipleResults** arabirim ve birden çok satır kümeleri işler. [DBVIEWER](http://msdn.microsoft.com/en-us/07620f99-c347-4d09-9ebc-2459e8049832) örnek birden çok sonuçların nasıl işleneceğini gösterir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)