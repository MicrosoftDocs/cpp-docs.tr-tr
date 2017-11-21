---
title: "OLE DB uygulamanızda kaynak havuzu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a11fe27fad42e7a27e55a8b4f494980aa9f708a6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB Uygulamanızda Kaynak Havuzu
Uygulamanızda havuzu kullanabilmeniz için OLE DB hizmetleri, veri kaynağınızı elde ederek çağrılır emin olmalısınız **IDataInitialize** veya **IDBPromptInitialize**. Doğrudan kullanırsanız `CoCreateInstance` sağlayıcının CLSID üzerinde dayanarak sağlayıcı çağırmak için OLE DB hizmetleri çağrılır.  
  
 OLE DB hizmetleri bağlı veri kaynağı bir başvuru olarak uzunluğunda havuzlarını sürdürür **IDataInitialize** veya **IDBPromptInitialize** tutulan ya da kullanımda bir bağlantı olarak uzun. Havuzları da otomatik olarak bir COM + 1.0 Hizmetleri veya Internet Information Services (IIS) ortamında korunur. Uygulamanızı bir COM + 1.0 Hizmetleri veya IIS ortamı dışında havuz yararlanır, başvuru tutmalısınız **IDataInitialize** veya **IDBPromptInitialize** veya en az bir tutun bağlantı. Son bağlantı uygulama tarafından serbest bırakıldığında havuzu yok edilmediğinden emin emin olmak için başvuru tutmalısınız ya da bağlantı uygulamanızın ömrü için tutun.  
  
 OLE DB hizmetleri, bağlantı zaman çizilmez havuzu tanımlamak, `Initialize` olarak adlandırılır. Bağlantı bir havuzdan çizilir sonra başka bir havuza taşınamaz. Bu nedenle, uygulamanızda arama gibi başlatma bilgileri değiştiren şeyler yapmaktan kaçınmak `UnInitialize` veya çağırma `QueryInterface` bir sağlayıcıya özgü arabiriminin çağırmadan önce `Initialize`. Ayrıca, bir komut istemi değerle dışında kurulan bağlantılar **DBPROMPT_NOPROMPT** havuza. Ancak, isteyen üzerinden kurulan bir bağlantı alınır başlatma dizesi aynı veri kaynağı için ek havuza alınmış bağlantıları kurmak için kullanılabilir.  
  
 Bazı sağlayıcılar her oturum için ayrı bir bağlantı yapmanız gerekir. Varsa, bu ek bağlantılar dağıtılmış işlemde ayrı olarak listelenmesi gerekir. OLE DB hizmetleri önbelleğe alır ve veri kaynağı başına tek bir oturumla yeniden kullanır, ancak uygulama tek bir veri kaynağından bir seferde birden fazla oturum isterse, sağlayıcı ek bağlantı ve olan ek işlem kayıtlar yapılması yukarı sonunda havuza değil. Bir tek veri kaynağından birden çok oturumu oluşturmak için daha havuza alınmış bir ortamda her oturum için ayrı veri kaynağı oluşturma gerçekten daha etkilidir.  
  
 Son olarak, ADO otomatik olarak OLE DB kullandığından Hizmetleri bağlantıları kurmak için ADO kullanabilirsiniz ve havuzu ve kaydı otomatik olarak gerçekleşir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE DB kaynak havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)