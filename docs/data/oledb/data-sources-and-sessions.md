---
title: Veri Kaynakları ve Oturumlar
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: 0514f6a9285936c85608f08774c1d377fd72d6ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80211061"
---
# <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar

Aşağıdaki şekilde, bir veri kaynağına bağlanmayı ve bu kaynağa erişmeyi destekleyen sınıflar gösterilmektedir. Her sınıf bir standart OLE DB bileşen uygulamasını temel alır.

![Veri kaynağı ve oturum sınıfları](../../data/oledb/media/vcdatasourcesessionclasses.gif "Veri kaynağı ve oturum sınıfları") <br/>
Veri kaynağı ve oturum sınıfları

Sınıflar şunlardır:

- [CDataSource](../../data/oledb/cdatasource-class.md) Bu sınıf, bir OLE DB sağlayıcı aracılığıyla bir veri kaynağına bağlantı oluşturan ve yöneten veri kaynağı nesnesini başlatır. Veri kaynağı, veri kaynağı adresi ve kimlik doğrulama bilgileri gibi bilgileri bir bağlantı dizesi biçiminde alır.

   Ayrıca, bir sistemde kayıtlı olan kullanılabilir sağlayıcıların bir listesini almak için herhangi bir bağlantı oluşturulmadan önce, [CEnumerator](../../data/oledb/cenumerator-class.md) yardımcı sınıfının genellikle kullanıldığını belirten bir değer de vardır. Bu, bir sağlayıcıyı veri kaynağı olarak seçmenizi sağlar. Örneğin, **veri bağlantısı özellikleri** iletişim **kutusu, sağlayıcılar sekmesindeki sağlayıcı** listesini doldurmak için bu sınıfı kullanır. `SQLBrowseConnect` veya `SQLDriverConnect` işlevine karşılık gelir.

- [CSession](../../data/oledb/csession-class.md) Bu sınıf, veri kaynağına yönelik tek bir erişim oturumunu temsil eden oturum nesnesini başlatır. Ancak, bir veri kaynağı üzerinde birden çok oturum oluşturabilirsiniz. Her oturum için veri kaynağındaki verilere erişmek üzere satır kümeleri, komutlar ve diğer nesneler oluşturabilirsiniz. Oturum işlemleri işler.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB tüketici şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)
