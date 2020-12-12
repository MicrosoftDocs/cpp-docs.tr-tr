---
description: 'Daha fazla bilgi edinin: uygulama ayarları, MFC DLL Sihirbazı'
title: Uygulama Ayarları, MFC DLL Sihirbazı
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.mfc.dll.appset
helpviewer_keywords:
- MFC DLL Wizard, application settings
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
ms.openlocfilehash: da9579ef9a834fa0c2362b1569c2efa808132faa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322804"
---
# <a name="application-settings-mfc-dll-wizard"></a>Uygulama Ayarları, MFC DLL Sihirbazı

Yeni bir MFC DLL projesine temel özellikler tasarlamak ve eklemek için MFC DLL Sihirbazı 'nın bu sayfasını kullanın.

## <a name="dll-type"></a>DLL türü

Oluşturmak istediğiniz DLL türünü seçin.

- **Paylaşılan MFC DLL kullanan normal MFC DLL**

   MFC kitaplığını programınıza paylaşılan bir DLL olarak bağlamak için bu seçeneği belirleyin. Bu seçeneği kullanarak, DLL 'niz ile çağıran uygulama arasında MFC nesnelerini paylaşamazsınız. Programınız, çalışma zamanında MFC kitaplığına çağrılar yapar. Bu seçenek, MFC kitaplığı kullanan birden çok yürütme dosyasından oluşuyorsa programınızın disk ve bellek gereksinimlerini azaltır. Hem Win32 hem de MFC programları, DLL 'inizdeki işlevleri çağırabilir. MFC DLL 'sini bu proje türüyle yeniden dağıtmanız gerekir.

- **MFC statik olarak bağlantılı normal MFC DLL**

   Programınızı derleme zamanında statik olarak MFC kitaplığına bağlamak için bu seçeneği belirleyin. Hem Win32 hem de MFC programları, DLL 'inizdeki işlevleri çağırabilir. Bu seçenek programınızın boyutunu artırsa da, MFC DLL 'sini bu proje türüyle yeniden dağıtmanız gerekmez. MFC nesnelerini DLL 'niz ile çağıran uygulama arasında paylaşamazsınız.

- **MFC uzantı DLL 'SI**

   Programınızın, çalışma zamanında MFC kitaplığına çağrı yapmasını istiyorsanız ve DLL 'niz ile çağıran uygulama arasında MFC nesneleri paylaşmak istiyorsanız bu seçeneği belirleyin. Bu seçenek, programın MFC kitaplığı kullanan birden fazla yürütülebilir dosyadan oluşuyorsa, programınızın disk ve bellek gereksinimlerini azaltır. Yalnızca MFC programları DLL 'inizdeki işlevleri çağırabilir. MFC DLL 'sini bu proje türüyle yeniden dağıtmanız gerekir.

## <a name="additional-features"></a>Ek özellikler

MFC DLL 'nizin Otomasyonu destekleyip desteklemediğini ve Windows Sockets 'i destekleyip desteklemediğini seçin.

- **Otomasyon**

   Programınızın başka bir programda uygulanan nesneleri işlemesini sağlamak için **Otomasyon** ' u seçin. **Otomasyon** seçimi, programınızı diğer otomasyon istemcilerine da sunar. Daha fazla bilgi için bkz. [Otomasyon](../../mfc/automation.md) .

- **Windows Yuvaları**

   Programınızın Windows Yuvaları desteklediğini belirtmek için bu seçeneği belirleyin. Windows yuvaları, TCP/IP ağları üzerinden iletişim kuran programlar yazmanıza izin verir.

   MFC DLL 'niz Windows Sockets desteği ile oluşturulduysa, [CWinApp:: InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) yuvalar için desteği başlatır ve Stbafx. h MFC üstbilgi dosyası afxsock. h içerir.

## <a name="see-also"></a>Ayrıca bkz.

[MFC DLL Sihirbazı](../../mfc/reference/mfc-dll-wizard.md)<br/>
[MFC DLL projesi oluşturma](../../mfc/reference/creating-an-mfc-dll-project.md)
