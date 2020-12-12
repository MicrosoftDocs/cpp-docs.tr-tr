---
description: 'Daha fazla bilgi edinin: OLE DB uygulamanızda kaynak havuzu oluşturma'
title: OLE DB Uygulamanızda Kaynak Havuzu
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 504217092f4e4a19a3db2898b97e6a35269db7ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316875"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB Uygulamanızda Kaynak Havuzu

Uygulamanızda havuzlamayı kullanabilmek için, veya aracılığıyla veri kaynağınızı alarak OLE DB hizmetlerin çağrıldığından emin olmanız gerekir `IDataInitialize` `IDBPromptInitialize` . Sağlayıcıyı `CoCreateInstance` sağlayıcının CLSID 'sine göre çağırmak için doğrudan kullanıyorsanız, OLE DB hizmetleri çağrılmaz.

OLE DB Hizmetleri, bağlı veri kaynakları havuzlarını, `IDataInitialize` veya `IDBPromptInitialize` kullanımda olan bir bağlantı olduğu sürece veya tutulduğu sürece korur. Havuzlar Ayrıca bir COM+ 1,0 hizmetleri veya Internet Information Services (IIS) ortamı içinde otomatik olarak korunur. Uygulamanız bir COM+ 1,0 hizmetlerine veya IIS ortamına dış havuzdan yararlanıyorsa, `IDataInitialize` `IDBPromptInitialize` en az bir bağlantıya sahip veya en az bir bağlantı tutmanız gerekir. Son bağlantı uygulama tarafından serbest bırakıldığında havuzun yok edilmediğinden emin olmak için, uygulamanızın kullanım ömrü boyunca başvuruyu saklayın veya bağlantı üzerinde tutun.

OLE DB Hizmetleri, bağlantı verilen sürede çizildiği havuzu belirler `Initialize` . Bağlantı havuzdan çizildikten sonra, farklı bir havuza taşınamaz. Bu nedenle, uygulamanızda, `UnInitialize` `QueryInterface` çağrılmadan önce sağlayıcıya özel arabirim çağırma veya çağırma gibi başlatma bilgilerini değiştiren bir şeyler yapmaktan kaçının `Initialize` . Ayrıca, DBPROMPT_NOPROMPT dışında bir istem değeriyle kurulan bağlantılar havuza alınmamış. Ancak, istem aracılığıyla kurulan bir bağlantıdan alınan başlatma dizesi, aynı veri kaynağına havuza alınmış ek bağlantılar oluşturmak için kullanılabilir.

Bazı sağlayıcıların her oturum için ayrı bir bağlantı yapması gerekir. Bu ek bağlantılar, varsa, dağıtılmış işlemde ayrı olarak listeye alınmalıdır. OLE DB Hizmetleri, veri kaynağı başına tek bir oturumu önbelleğe alır ve yeniden kullanır, ancak uygulama tek bir veri kaynağından aynı anda birden fazla oturum istiyorsa, sağlayıcı ek bağlantılar yapıyor ve havuza alınmamış ek işlem listelerinizi gerektirebilir. Tek bir veri kaynağından birden çok oturum oluşturmak yerine, havuza alınmış bir ortamdaki her oturum için ayrı bir veri kaynağı oluşturmak daha etkilidir.

Son olarak, ADO OLE DB hizmetlerini otomatik olarak kullandığından, bağlantı kurmak için ADO 'YU kullanabilirsiniz ve havuz oluşturma ve kayıt otomatik olarak gerçekleşir.

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak havuzu ve Hizmetleri OLE DB](../../data/oledb/ole-db-resource-pooling-and-services.md)
