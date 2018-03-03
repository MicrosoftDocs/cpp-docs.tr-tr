---
title: "OLE arka planı: Kapsayıcılar ve sunucular | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b3c6f3c15b0ea398ec621ba5f6e34a9fb6e0aae8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-containers-and-servers"></a>OLE Arka Planı: Kapsayıcılar ve Sunucular
Bir kapsayıcı uygulama kendi belgelerine katıştırılmış veya bağlı öğeleri içeren bir uygulamadır. Bir kapsayıcı uygulama tarafından yönetilen belgeleri depolamak ve OLE belge bileşenlerini ve bunun yanı sıra uygulama tarafından oluşturulan veri görüntüler kurabilmesi gerekir. Bir kapsayıcı uygulama aynı zamanda yeni öğeler eklemek veya var olan öğeleri sunucu uygulamaları gerektiğinde etkinleştirerek düzenlemek kullanıcılara izin vermesi gerekir. Bir kapsayıcı uygulama kullanıcı arabirimi gereksinimlerini makalesinde listelenen [kapsayıcılar: kullanıcı arabirimi sorunları](../mfc/containers-user-interface-issues.md).  
  
 Sunucu uygulaması veya bileşen uygulama kapsayıcı uygulamaları tarafından kullanılmak OLE belge bileşenlerini oluşturan bir uygulamadır. Sunucu uygulamaları genellikle sürükle ve bırak veya bir kapsayıcı uygulama verileri katıştırılmış veya bağlantılı bir öğe olarak ekleyebilirsiniz böylece verilerini Panoya kopyalama destekler. Bir uygulama, bir kapsayıcı ve bir sunucu olabilir.  
  
 Bağımsız uygulamalar veya tam sunucuları birçok sunucusu olan; Bunlar, tek başına uygulamaları olarak da çalıştırılabilir veya bir kapsayıcı uygulama tarafından başlatılabilir. Bir miniserver yalnızca kapsayıcı tarafından başlatılan sunucu uygulaması özel bir türde değil. Bağımsız bir uygulama olarak çalıştırılamaz. Microsoft Draw ve Microsoft Graph sunucuları miniservers bir örnektir.  
  
 Kapsayıcılar ve sunucular doğrudan iletişim kurmazlar. Bunun yerine, OLE Sistem dinamik bağlantı kitaplığı (DLL) iletişim kurarlar. Bu DLL'ler kapsayıcılar ve sunucular arama işlevleri sağlar ve kapsayıcılar ve sunucular dll çağrı geri arama işlevleri sağlar.  
  
 Bunun anlamı iletişimin kullanarak, bir kapsayıcı sunucu uygulamasının uygulama ayrıntılarını bilmeniz gerekmez. Sunucu ile çalışabilirsiniz türlerini tanımlamak zorunda kalmadan herhangi bir sunucusu tarafından oluşturulan öğeleri kabul etmek bir kapsayıcı sağlar. Sonuç olarak, bir kapsayıcı uygulama kullanıcı gelecekteki uygulamaların ve veri biçimleri yararlanabilir. Bu yeni uygulamalar OLE bileşenleri varsa, bir bileşik belge bu uygulamaları tarafından oluşturulan öğeleri dahil mümkün olacaktır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE arka planı](../mfc/ole-background.md)   
 [OLE arka planı: MFC uygulaması](../mfc/ole-background-mfc-implementation.md)   
 [Kapsayıcıları](../mfc/containers.md)   
 [Sunucuları](../mfc/servers.md)   
 [Kapsayıcılar: İstemci öğeleri](../mfc/containers-client-items.md)   
 [Sunucular: Sunucu Öğeleri](../mfc/servers-server-items.md)

