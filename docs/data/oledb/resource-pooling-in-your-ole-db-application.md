---
title: OLE DB uygulamanızda kaynak havuzu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 483523db7452c9c1adda38114e69f246e18856ea
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093031"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB Uygulamanızda Kaynak Havuzu

Uygulamanızda havuzu yararlanmak için OLE DB hizmetleri, veri kaynağınızın elde ederek çağrılır emin olmalısınız `IDataInitialize` veya `IDBPromptInitialize`. Doğrudan kullanırsanız `CoCreateInstance` OLE DB hizmet sağlayıcısının CLSID tabanlı sağlayıcı çağırmak için çağrılır.  
  
OLE DB hizmetleri bağlı veri kaynakları için bir başvuru olarak uzun havuzlarını sürdürür `IDataInitialize` veya `IDBPromptInitialize` tutulan ya da bağlantı kullanımda olduğundan uzun. Havuzları bir COM + 1.0 Hizmetleri veya Internet Information Services (IIS) ortamında otomatik olarak korunur. Uygulamanızın bir COM + 1.0 Services veya IIS ortamının dışında havuz yararlanır, başvuru tutmalısınız `IDataInitialize` veya `IDBPromptInitialize` veya en az bir bağlantı tutun. Son bağlantı uygulama tarafından serbest bırakıldığında havuzu yok edilmediğinden emin emin olmak için başvurusunu korumanız veya bağlantı için uygulamanızın yaşam ömrü tutun.  
  
OLE DB hizmetleri içinden bağlantı zamanında çizilmez havuzunu tanımlamak, `Initialize` çağrılır. Bağlantı havuzundan çekildikten sonra başka bir havuza taşınamaz. Bu nedenle, arama gibi başlatma bilgileri değiştirmek şeyler uygulamanızdaki önlemek `UnInitialize` veya çağırma `QueryInterface` çağırmadan önce bir sağlayıcıya özgü arabirimi `Initialize`. Ayrıca, DBPROMPT_NOPROMPT bir istem değeri ile kurulan bağlantılar havuza değil. Ancak, isteyen aracılığıyla kurulan bir bağlantı alınan başlatma dizesi aynı veri kaynağına ek havuza alınmış bağlantıları kurmak için kullanılabilir.  
  
Bazı sağlayıcıların her oturum için ayrı bir bağlantı yapmanız gerekir. Varsa, bu ek bağlantılar dağıtılmış işlemde ayrı olarak listelenmesi gerekir. OLE DB hizmetleri önbelleğe alır ve veri kaynağı başına tek bir oturumda kullanır, ancak uygulama, tek bir veri kaynağından aynı anda birden fazla oturum isterse, sağlayıcı ek bağlantılar ve olan ek işlem kayıtlar yapılması yukarı sonunda Havuzda değil. Havuza alınmış bir ortamda tek bir veri kaynağından birden çok oturumu oluşturmak için daha her oturum için ayrı bir veri kaynağı oluşturmak için gerçekten daha verimlidir.  
  
Son olarak, ADO otomatik olarak OLE DB kullandığından Hizmetleri ADO bağlantılar kurmak için kullanabileceğiniz ve havuzu ve kaydı otomatik olarak gerçekleşir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)