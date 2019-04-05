---
title: OLE DB Uygulamanızda Kaynak Havuzu
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], resource pooling
- resource pooling [OLE DB], services
- OLE DB, resource pooling
- OLE DB providers, resource pooling
ms.assetid: 2ead1bcf-bbd4-43ea-a307-bb694b992fc1
ms.openlocfilehash: 786c2b31bb93b0691d80885c86377e2afba8c1dc
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029310"
---
# <a name="resource-pooling-in-your-ole-db-application"></a>OLE DB Uygulamanızda Kaynak Havuzu

Uygulamanızda havuzu yararlanmak için OLE DB hizmetleri, veri kaynağınızın alarak çağrılır emin olmalısınız `IDataInitialize` veya `IDBPromptInitialize`. Doğrudan kullanırsanız `CoCreateInstance` OLE DB hizmet sağlayıcısının CLSID tabanlı sağlayıcı çağırmak için çağrılır.

OLE DB hizmetleri bağlı veri kaynakları için bir başvuru olarak uzun havuzlarını sürdürür `IDataInitialize` veya `IDBPromptInitialize` tutulan ya da bağlantı kullanımda olduğundan uzun. Havuzları bir COM + 1.0 Hizmetleri veya Internet Information Services (IIS) ortamında otomatik olarak korunur. Uygulamanızın bir COM + 1.0 Hizmetleri veya IIS ortamına havuz dış avantajlarından yararlanır, başvuru tutmalısınız `IDataInitialize` veya `IDBPromptInitialize` veya en az bir bağlantı tutun. Son bağlantı uygulama tarafından serbest bırakıldığında havuzu yok değil emin emin olmak için başvurusunu korumanız veya bağlantı için uygulamanızın yaşam ömrü tutun.

OLE DB hizmetleri içinden bağlantı zamanında çizilmez havuzunu tanımlamak, `Initialize` çağrılır. Bağlantı havuzundan çekildikten sonra başka bir havuza taşınamaz. Bu nedenle, arama gibi başlatma bilgileri değiştirmek şeyler uygulamanızdaki önlemek `UnInitialize` veya çağırma `QueryInterface` çağırmadan önce bir sağlayıcıya özgü arabirimi `Initialize`. Ayrıca bir istem değeri DBPROMPT_NOPROMPT ile kurulan bağlantıları havuza değildir. Ancak, isteyen aracılığıyla kurulan bir bağlantı alınan başlatma dizesi aynı veri kaynağına ek havuza alınmış bağlantıları kurmak için kullanılabilir.

Bazı sağlayıcıların her oturum için ayrı bir bağlantı yapmanız gerekir. Varsa, bu ek bağlantılar dağıtılmış işlemde ayrı olarak listelenmesi gerekir. OLE DB hizmetleri önbellekler ve veri kaynağı başına tek bir oturumda kullanır, ancak uygulama, tek bir veri kaynağından aynı anda birden fazla oturum isterse, sağlayıcı ek bağlantılar ve ek işlem kayıtlar yapılması yukarı sonunda, Havuzda değil. Havuza alınmış bir ortamda tek bir veri kaynağından birden çok oturumu oluşturmak için daha her oturum için ayrı bir veri kaynağı oluşturmak için daha verimlidir.

Son olarak, ADO otomatik olarak OLE DB kullandığından Hizmetleri ADO bağlantılar kurmak için kullanabileceğiniz ve havuzu ve kaydı otomatik olarak gerçekleşir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE DB Kaynak Havuzu ve Hizmetleri](../../data/oledb/ole-db-resource-pooling-and-services.md)