---
title: Veri Kaynakları ve Oturumlar
ms.date: 11/19/2018
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
ms.openlocfilehash: c43061ccb462fe472821c76251430b5e3b0f0809
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175307"
---
# <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar

Aşağıdaki şekil, bağlanma ve bir veri kaynağına erişimi destekleyen sınıfları gösterir. Her sınıf, standart bir OLE DB bileşeni uygulama üzerinde temel alır.

![Veri kaynağı ve oturumu sınıfları](../../data/oledb/media/vcdatasourcesessionclasses.gif "veri kaynağı ve oturumu sınıfları") <br/>
Veri kaynağı ve oturum sınıfı

Sınıfları şunlardır:

- [CDataSource](../../data/oledb/cdatasource-class.md) oluşturur ve bir veri kaynağına OLE DB sağlayıcısı üzerinden bir bağlantı yöneten veri kaynağı nesnesi bu sınıfın örneğini oluşturur. Veri kaynağı bağlantı dizesi şeklinde veri kaynağı adresini ve kimlik doğrulama bilgileri gibi bilgileri alır.

   Ayrıca, hatalarının ayıklanabileceğini belirtmekte yarar yardımcı sınıf [CEnumerator](../../data/oledb/cenumerator-class.md) bir sistemde kayıtlı yok sağlayıcıları listesini almak için herhangi bir bağlantı kurulmadan önce sık sık kullanılır. Bu veri kaynağı olarak bir sağlayıcı seçmenize olanak sağlar. Örneğin, **veri bağlantı özellikleri** iletişim kutusu sağlayıcılarının listesini doldurmak için bu sınıfı kullanan **sağlayıcıları** sekmesi. Bu karşılık gelir `SQLBrowseConnect` veya `SQLDriverConnect` işlevi.

- [CSession](../../data/oledb/csession-class.md) veri kaynağına tek erişim oturumu temsil eden bir oturum nesnesi bu sınıfın örneğini oluşturur. Ancak, bir veri kaynağında birden çok oturumu oluşturabilirsiniz. Her oturum için satır kümeleri, komutların ve diğer nesneleri veri kaynağından verilere erişmek için oluşturabilirsiniz. Oturum hareketlerini işler.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)