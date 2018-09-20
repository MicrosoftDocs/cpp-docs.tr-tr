---
title: 'OLE arka planı: Kapsayıcılar ve sunucular | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 23aa5e4c13e8049a2240462dab1c5b68bfb514f7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46436942"
---
# <a name="ole-background-containers-and-servers"></a>OLE Arka Planı: Kapsayıcılar ve Sunucular

Bir kapsayıcı uygulaması kendi belgelerine gömülü veya bağlantılı öğeleri içeren bir uygulamadır. Yönetilen bir kapsayıcı uygulama tarafından belgeleri depolamak ve OLE belge bileşenlerinin yanı sıra uygulama tarafından oluşturulan verileri görüntülemek kurabilmesi gerekir. Kapsayıcılı bir uygulama kullanıcıların yeni öğeler eklemek veya mevcut öğeleri sunucu uygulamaları gerektiğinde etkinleştirerek düzenlemek de izin vermeniz gerekir. Bir kapsayıcı uygulaması kullanıcı arabirimi gereksinimlerini makalesinde listelenen [kapsayıcılar: kullanıcı arabirimi sorunları](../mfc/containers-user-interface-issues.md).

Sunucu uygulama veya bileşen uygulama kapsayıcı uygulamalar tarafından kullanılmak OLE belge bileşenleri oluşturan bir uygulamadır. Sunucu uygulamaları, genellikle sürükleyin ve bırakın veya bir kapsayıcı uygulaması verileri gömülü veya bağlantılı bir öğe olarak ekleyebilirsiniz. böylece kendi verilerini panoya kopyalanırken destekler. Bir uygulama bir kapsayıcı hem bir sunucu olabilir.

Çoğu sunucuları, tek başına uygulamalar veya tam sunucuları olan; Bunlar, ya da tek başına uygulamalar olarak çalıştırılabilir veya bir kapsayıcı uygulama tarafından başlatılabilir. Bir miniserver, yalnızca bir kapsayıcı tarafından başlatılabilen sunucu uygulaması özel türüdür. Tek başına bir uygulama olarak çalıştırılamaz. Microsoft Draw ve Microsoft Graph sunucuları miniservers örnekleridir.

Kapsayıcılar ve sunucular doğrudan iletişim kurmaz. Bunun yerine, OLE Sistem dinamik bağlantı kitaplıklarını (DLL) iletişim kurarlar. Bu DLL'leri kapsayıcılar ve sunucular çağıran İşlevler, ve kapsayıcılar ve sunucular DLL'leri Çağırma geri çağırma işlevleri sağlar.

Bunun anlamı iletişimi kullanarak, bir kapsayıcı sunucu uygulamasının uygulama ayrıntıları bilmeniz gerekmez. Sunucu ile çalışabilir türlerini tanımlamak zorunda kalmadan herhangi bir sunucu tarafından oluşturulan öğeler kabul etmek bir kapsayıcı sağlar. Sonuç olarak, bir kapsayıcı uygulamasının kullanıcı gelecekteki uygulamalar ve veri biçimleri yararlanabilirsiniz. Bu yeni uygulamalar OLE bileşenleri, bileşik bir belgeye bu uygulamaları tarafından oluşturulan öğeleri dahil etmek mümkün olacaktır.

## <a name="see-also"></a>Ayrıca Bkz.

[OLE Arka Planı](../mfc/ole-background.md)<br/>
[OLE Arka Planı: MFC Uygulaması](../mfc/ole-background-mfc-implementation.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)<br/>
[Kapsayıcılar: İstemci Öğeleri](../mfc/containers-client-items.md)<br/>
[Sunucular: Sunucu Öğeleri](../mfc/servers-server-items.md)

