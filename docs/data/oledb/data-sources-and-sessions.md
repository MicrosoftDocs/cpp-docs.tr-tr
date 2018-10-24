---
title: Veri kaynakları ve oturumlar | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- data sources [C++], OLE DB
- connections [C++], data source
- OLE DB consumer templates [C++], data sources
ms.assetid: 6ee52216-e082-4869-a1d6-ce561cfb76e5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 0a1904c0b0c416c216a28ddcaf7bb20ce408ba0a
ms.sourcegitcommit: c045c3a7e9f2c7e3e0de5b7f9513e41d8b6d19b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2018
ms.locfileid: "49989950"
---
# <a name="data-sources-and-sessions"></a>Veri Kaynakları ve Oturumlar

Aşağıdaki şekil, bağlanma ve bir veri kaynağına erişimi destekleyen sınıfları gösterir. Her sınıf, standart bir OLE DB bileşeni uygulama üzerinde temel alır.  
  
![Veri kaynağı ve oturumu sınıfları](../../data/oledb/media/vcdatasourcesessionclasses.gif "vcdatasourcesessionclasses")  
Veri kaynağı ve oturum sınıfı  
  
Sınıfları şunlardır:  
  
- [CDataSource](../../data/oledb/cdatasource-class.md) oluşturur ve bir veri kaynağına OLE DB sağlayıcısı üzerinden bir bağlantı yöneten veri kaynağı nesnesi bu sınıfın örneğini oluşturur. Veri kaynağı bağlantı dizesi şeklinde veri kaynağı adresini ve kimlik doğrulama bilgileri gibi bilgileri alır.  
  
     Ayrıca, hatalarının ayıklanabileceğini belirtmekte yarar yardımcı sınıf [CEnumerator](../../data/oledb/cenumerator-class.md) bir sistemde kayıtlı yok sağlayıcıları listesini almak için herhangi bir bağlantı kurulmadan önce sık sık kullanılır. Bu veri kaynağı olarak bir sağlayıcı seçmenize olanak sağlar. Örneğin, **veri bağlantı özellikleri** iletişim kutusu sağlayıcılarının listesini doldurmak için bu sınıfı kullanan **sağlayıcıları** sekmesi. Bu karşılık gelir `SQLBrowseConnect` veya `SQLDriverConnect` işlevi.  
  
- [CSession](../../data/oledb/csession-class.md) veri kaynağına tek erişim oturumu temsil eden bir oturum nesnesi bu sınıfın örneğini oluşturur. Ancak, bir veri kaynağında birden çok oturumu oluşturabilirsiniz. Her oturum için satır kümeleri, komutların ve diğer nesneleri veri kaynağından verilere erişmek için oluşturabilirsiniz. Oturum hareketlerini işler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Tüketici Şablonları](../../data/oledb/ole-db-consumer-templates-cpp.md)