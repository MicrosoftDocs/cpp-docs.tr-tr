---
title: 'CAtlServiceModuleT:: Run Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 0c35020996852731a8f22c15860d4cceb7a8bdb6
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69491526"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT:: Run Işlevi

`Run``PreMessageLoop` ,`RunMessageLoop`ve çağrıları`PostMessageLoop`içerir. Çağrıldıktan sonra, `PreMessageLoop` önce hizmetin iş parçacığı kimliğini depolar. Hizmet, [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)Win32 API işlevini kullanarak bir WM_QUIT iletisi göndererek kendisini kapatmak IÇIN bu kimliği kullanır.

`PreMessageLoop`ardından çağırır `InitializeSecurity`. Varsayılan olarak, `InitializeSecurity` güvenlik tanımlayıcısı olan [CoInitializeSecurity](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) 'yi null olarak çağırır, bu da herhangi bir kullanıcının nesneniz erişimi olduğu anlamına gelir.

Hizmetin kendi güvenliğini belirtmesini istemiyorsanız, öğesini geçersiz kılın `PreMessageLoop` ve çağırmayın `InitializeSecurity`ve com, kayıt defterinden güvenlik ayarlarını belirler. Kayıt defteri ayarlarını yapılandırmanın kolay bir yolu, bu bölümün ilerleyen kısımlarında ele alınan [DCOMCNFG](../atl/dcomcnfg.md) yardımcı programıdır.

Güvenlik belirtildiğinde, nesne COM 'a kaydedilir, böylece yeni istemciler programa bağlanabilir. Son olarak program, Service Control Manager 'a (SCM) çalıştığını ve programın bir ileti döngüsü girdiğini söyler. Program, hizmet kapatıldıktan sonra bir çıkış iletisi gönderene kadar çalışmaya devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CSecurityDesc Sınıfı](../atl/reference/csecuritydesc-class.md)<br/>
[CSid Sınıfı](../atl/reference/csid-class.md)<br/>
[CDacl Sınıfı](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)
