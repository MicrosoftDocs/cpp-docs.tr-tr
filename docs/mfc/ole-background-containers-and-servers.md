---
description: 'Daha fazla bilgi edinin: OLE arka planı: kapsayıcılar ve sunucular'
title: 'OLE Arka Planı: Kapsayıcılar ve Sunucular'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE full-server applications [MFC]
- server applications [MFC], communication with containers
- full-server [MFC]
- server applications [MFC], requirements
- server applications [MFC], defined
- OLE server applications [MFC], about server applications
- server applications [MFC], full-server vs. mini-server
- OLE server applications [MFC], mini-server applications
- OLE containers [MFC], container applications
- containers [MFC], OLE container applications
- server applications [MFC]
ms.assetid: dafbb31d-096c-4654-b774-12900d832919
ms.openlocfilehash: 3ea578ce14165b16e84520b22bc545fc5d2a8882
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254787"
---
# <a name="ole-background-containers-and-servers"></a>OLE Arka Planı: Kapsayıcılar ve Sunucular

Kapsayıcı uygulama, katıştırılmış veya bağlantılı öğeleri kendi belgelerine birleştiresağlayan bir uygulamadır. Bir kapsayıcı uygulaması tarafından yönetilen belgeler, OLE belge bileşenlerinin yanı sıra uygulamanın kendisi tarafından oluşturulan verileri de depolayıp görüntüleyebilmelidir. Bir kapsayıcı uygulama, kullanıcıların gerektiğinde sunucu uygulamalarını etkinleştirerek yeni öğe eklemesine veya varolan öğeleri düzenlemesine izin vermelidir. Bir kapsayıcı uygulamasının Kullanıcı arabirimi gereksinimleri, makale [kapsayıcıları: User-Interface sorunları](containers-user-interface-issues.md)bölümünde listelenmiştir.

Sunucu uygulaması veya bileşen uygulaması, kapsayıcı uygulamaları tarafından kullanılmak üzere OLE belge bileşenleri oluşturabileceğiniz bir uygulamadır. Sunucu uygulamaları genellikle, bir kapsayıcı uygulamanın verileri katıştırılmış veya bağlantılı bir öğe olarak ekleyebilmesi için verileri sürükleyip Pano 'ya kopyalamayı destekler. Bir uygulama hem kapsayıcı hem de sunucu olabilir.

Çoğu sunucu tek başına uygulamalardır veya tam sunuculardır; Bunlar, tek başına uygulamalar olarak çalıştırılabilir veya bir kapsayıcı uygulaması tarafından başlatılabilir. Minıver, yalnızca bir kapsayıcı tarafından başlatılabilen özel bir tür sunucu uygulamasıdır. Tek başına bir uygulama olarak çalıştırılamaz. Microsoft Draw ve Microsoft Graph sunucular, minıse örnekleri örneğidir.

Kapsayıcılar ve sunucular doğrudan iletişim kurmaz. Bunun yerine, OLE sistemi dinamik bağlantı kitaplıkları (DLL) üzerinden iletişim kurar. Bu dll 'Ler kapsayıcıları ve sunucuları çağıran işlevleri sağlar ve kapsayıcılar ve sunucular dll 'Lerin çağırdığını geri çağırma işlevlerini sağlar.

Bu iletişim bu şekilde kullanıldığında, bir kapsayıcının sunucu uygulamasının uygulama ayrıntılarını bilmeleri gerekmez. Bir kapsayıcının, üzerinde çalıştığı sunucu türlerini tanımlamak zorunda kalmadan herhangi bir sunucu tarafından oluşturulan öğeleri kabul etmesine izin verir. Sonuç olarak, bir kapsayıcı uygulamasının kullanıcısı gelecekteki uygulamalardan ve veri biçimlerinden faydalanabilir. Bu yeni uygulamalar OLE bileşenleriniz ise, bileşik bir belge bu uygulamalar tarafından oluşturulan öğeleri birleştirebilecektir.

## <a name="see-also"></a>Ayrıca bkz.

[OLE arka planı](ole-background.md)<br/>
[OLE arka planı: MFC Uygulama](ole-background-mfc-implementation.md)<br/>
[Kapsayıcılar](containers.md)<br/>
[Sunucular](servers.md)<br/>
[Kapsayıcılar: Istemci öğeleri](containers-client-items.md)<br/>
[Sunucular: sunucu öğeleri](servers-server-items.md)
