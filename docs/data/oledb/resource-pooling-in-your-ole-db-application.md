---
title: OLE DB Uygulamanızda Kaynak Havuzu
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 3604f6eaaf0f34a0ff7e54826923c2aa92eef4a2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209806"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB Uygulamanızda Kaynak Havuzu

Uygulamanızda havuzlamayı kullanabilmek için, `IDataInitialize` veya `IDBPromptInitialize`aracılığıyla veri kaynağınızı alarak OLE DB hizmetlerinin çağrıldığından emin olmanız gerekir. Sağlayıcıyı sağlayıcının CLSID 'SINE göre çağırmak için doğrudan `CoCreateInstance` kullanıyorsanız, hiçbir OLE DB hizmeti çağrılmaz.

OLE DB Hizmetleri, `IDataInitialize` veya `IDBPromptInitialize` bir başvuru olduğu ve kullanımda olan bir bağlantı olduğu sürece bağlı veri kaynakları havuzlarını korur. Havuzlar Ayrıca bir COM+ 1,0 hizmetleri veya Internet Information Services (IIS) ortamı içinde otomatik olarak korunur. Uygulamanız bir COM+ 1,0 hizmetleri veya IIS ortamına ait havuzdan yararlanıyorsa, `IDataInitialize` veya `IDBPromptInitialize` bir başvuru tutmanız ya da en az bir bağlantıyı tutmanız gerekir. Son bağlantı uygulama tarafından serbest bırakıldığında havuzun yok edilmediğinden emin olmak için, uygulamanızın kullanım ömrü boyunca başvuruyu saklayın veya bağlantı üzerinde tutun.

OLE DB Hizmetleri, `Initialize` çağrıldığı sırada bağlantının çizildiği havuzu belirler. Bağlantı havuzdan çizildikten sonra, farklı bir havuza taşınamaz. Bu nedenle, uygulamanızda `Initialize`çağrılmadan önce `QueryInterface` `UnInitialize` çağırma veya sağlayıcıya özgü bir arabirim için çağrı yapma gibi başlatma bilgilerini değiştiren bir şeyler yapmaktan kaçının. Ayrıca, DBPROMPT_NOPROMPT dışında bir istem değeriyle kurulan bağlantılar havuza alınmamış. Ancak, istem aracılığıyla kurulan bir bağlantıdan alınan başlatma dizesi, aynı veri kaynağına havuza alınmış ek bağlantılar oluşturmak için kullanılabilir.

Bazı sağlayıcıların her oturum için ayrı bir bağlantı yapması gerekir. Bu ek bağlantılar, varsa, dağıtılmış işlemde ayrı olarak listeye alınmalıdır. OLE DB Hizmetleri, veri kaynağı başına tek bir oturumu önbelleğe alır ve yeniden kullanır, ancak uygulama tek bir veri kaynağından aynı anda birden fazla oturum istiyorsa, sağlayıcı ek bağlantılar yapıyor ve bu, ek işlem kayıtlar yapıyor havuza alınmamış. Tek bir veri kaynağından birden çok oturum oluşturmak yerine, havuza alınmış bir ortamdaki her oturum için ayrı bir veri kaynağı oluşturmak daha etkilidir.

Son olarak, ADO OLE DB hizmetlerini otomatik olarak kullandığından, bağlantı kurmak için ADO 'YU kullanabilirsiniz ve havuz oluşturma ve kayıt otomatik olarak gerçekleşir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)
