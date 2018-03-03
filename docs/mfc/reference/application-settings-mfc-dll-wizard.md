---
title: "Uygulama ayarları, MFC DLL Sihirbazı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1851460d5cf9deb8a803b13ec75d92c45c03e607
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="application-settings-mfc-dll-wizard"></a>Uygulama Ayarları, MFC DLL Sihirbazı
Tasarım ve yeni bir MFC DLL projesi temel özellikleri eklemek için MFC DLL Sihirbazı'nın bu sayfayı kullanın.  
  
## <a name="dll-type"></a>DLL türü  
 Oluşturmak istediğiniz DLL türünü seçin.  
  
 **MFC DLL kullanarak Normal MFC DLL paylaşılan**  
 MFC kitaplığını programınız paylaşılan DLL olarak bağlamak için bu seçeneği belirleyin. Bu seçeneği kullanarak, DLL ve çağıran uygulamada arasında MFC nesneleri paylaşamaz. Programınızın çalışma zamanında MFC kitaplığını çağrılar. MFC kitaplığını kullanan birden çok yürütme dosyaları oluşuyorsa bu seçenek programınızı disk ve bellek gereksinimlerini azaltır. Win32 ve MFC programları, DLL işlevleri çağırabilir. MFC DLL projesi bu tür ile yeniden dağıtmanız gerekir.  
  
 **MFC ile Normal MFC DLL statik olarak bağlı**  
 Programınızı derleme zamanında statik olarak MFC Kitaplığı'na bağlamak için bu seçeneği belirleyin. Win32 ve MFC programları, DLL işlevleri çağırabilir. Bu seçenek programınızı boyutunu artırır, ancak bu proje türü ile MFC DLL yeniden dağıtmanız gerekmez. MFC nesneleri DLL ve çağıran uygulamada arasında paylaşamaz.  
  
 **MFC uzantı DLL'si**  
 Çalışma zamanında MFC kitaplığını çağrı yapmak için program istiyorsanız ve MFC nesneleri DLL ve çağıran uygulamada arasında paylaşmak istiyorsanız bu seçeneği belirleyin. MFC Kitaplığı kullanan birden fazla yürütülebilir dosyaların oluşuyorsa bu seçenek programınızı, disk ve bellek gereksinimlerini azaltır. Yalnızca MFC programlar, DLL işlevleri çağırabilir. MFC DLL projesi bu tür ile yeniden dağıtmanız gerekir.  
  
## <a name="additional-features"></a>Ek Özellikler  
 MFC DLL Otomasyon destekleyip desteklemeyeceğini ve Windows sockets desteği gerekmediğini seçin.  
  
 **Otomatikleştirme**  
 Seçin **Otomasyon** programınızı başka bir programda uygulanan nesneleri işlemek izin vermek için. Seçme **Otomasyon** programınızı diğer Otomasyon istemcileri için de sunar. Bkz: [Otomasyon](../../mfc/automation.md) daha fazla bilgi için.  
  
 **Windows Yuvaları**  
 Programınızın Windows Yuvaları desteklediğini belirtmek için bu seçeneği belirleyin. Windows yuvaları, TCP/IP ağları üzerinden iletişim kuran programlar yazmasına izin verir.  
  
 Desteği, MFC DLL Windows ile yuva oluşturulduğunda, [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) başlatır desteklemek için yuva ve MFC üstbilgi dosyası StdAfx.h AfxSock.h içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC DLL Sihirbazı](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL Projesi Oluşturma](../../mfc/reference/creating-an-mfc-dll-project.md)

