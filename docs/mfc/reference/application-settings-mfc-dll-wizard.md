---
title: Uygulama ayarları, MFC DLL Sihirbazı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- vc.appwiz.mfc.dll.appset
dev_langs:
- C++
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 04fcf796c7d08cc2733edbf23b66c591e07ec71a
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704983"
---
# <a name="application-settings-mfc-dll-wizard"></a>Uygulama Ayarları, MFC DLL Sihirbazı
MFC DLL Sihirbazı bu sayfa, tasarım ve yeni bir MFC DLL projesi için temel özellikleri eklemek için kullanın.  
  
## <a name="dll-type"></a>DLL türü  
 DLL oluşturmak istediğiniz türü seçin.  
  
- **Paylaşılan MFC DLL kullanan Normal MFC DLL'SİNİN**

   MFC Kitaplığı programınız paylaşılan DLL olarak bağlamak için bu seçeneği belirleyin. Bu seçeneği kullanarak DLL'nizi çağıran uygulama arasındaki MFC nesneleri paylaşamazsınız. Programınızın çalışma zamanında MFC Kitaplığı çağrılar. Bu seçenek, MFC Kitaplığı kullanan birden çok yürütme dosyaları oluşturuluyorsa programınızı disk ve bellek gereksinimlerini azaltır. Win32 ve MFC programları, DLL'deki işlevleri çağırabilir. Bu tür bir proje ile MFC DLL'yi yeniden dağıtmanız gerekir.  
  
- **MFC ile Normal MFC DLL'SİNİN statik olarak bağlı**

   Programınızı oluşturma zamanında statik olarak MFC Kitaplığı'na bağlamak için bu seçeneği belirleyin. Win32 ve MFC programları, DLL'deki işlevleri çağırabilir. Bu seçenek, programınızın boyutu artar, ancak bu tür bir proje ile MFC DLL'yi yeniden dağıtmanız gerekmez. MFC nesneleri DLL'nizi çağıran uygulama arasındaki paylaşamazsınız.  
  
- **MFC uzantısı DLL**

   MFC Kitaplığı çağrı çalışma zamanında yapmak için program istiyorsanız ve MFC nesneleri DLL'nizi çağıran uygulama arasındaki paylaşmak istiyorsanız bu seçeneği belirleyin. MFC Kitaplığı kullanan birden fazla yürütülebilir dosya oluşuyorsa, bu seçenek programınızda, disk ve bellek gereksinimlerini azaltır. Yalnızca MFC programları, DLL'deki işlevleri çağırabilir. Bu tür bir proje ile MFC DLL'yi yeniden dağıtmanız gerekir.  
  
## <a name="additional-features"></a>Ek Özellikler  

MFC DLL dosyanızı Otomasyon destekleyip desteklemeyeceğini ve onu Windows sockets destekleyip desteklemeyeceğini seçin.  
  
- **Otomatikleştirme**

   Seçin **Otomasyon** başka bir programda uygulanan nesneleri değiştirmek, programınızın izin vermek için. Seçme **Otomasyon** ayrıca programınızı diğer Otomasyon istemcilerine kullanıma sunar. Bkz: [Otomasyon](../../mfc/automation.md) daha fazla bilgi için.  
  
- **Windows Yuvaları**

   Programınızı Windows sockets desteklediğini belirtmek için bu seçeneği belirleyin. Windows Yuvaları TCP/IP ağları üzerinden iletişim kuran yazma olanak sağlar.  
  
   MFC DLL ile Windows yuva desteği oluşturulduğunda, [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) başlatır için yuva desteği ve MFC üst bilgi dosyası StdAfx.h AfxSock.h içerir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC DLL Sihirbazı](../../mfc/reference/mfc-dll-wizard.md)   
 [MFC DLL Projesi Oluşturma](../../mfc/reference/creating-an-mfc-dll-project.md)

