---
description: 'Daha fazla bilgi edinin: CAtlServiceModuleT:: Run Işlevi'
title: 'CAtlServiceModuleT:: Run Işlevi'
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: f8bba170236138f6491c49506bccd29bc23d9dec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97148349"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT:: Run Işlevi

`Run``PreMessageLoop`, ve çağrıları içerir `RunMessageLoop` `PostMessageLoop` . Çağrıldıktan sonra, `PreMessageLoop` önce hizmetin iş parçacığı kimliğini depolar. Hizmet, [PostThreadMessage](/windows/win32/api/winuser/nf-winuser-postthreadmessagew)Win32 API işlevini kullanarak bir WM_QUIT iletisi göndererek kendisini kapatmak IÇIN bu kimliği kullanır.

`PreMessageLoop` ardından çağırır `InitializeSecurity` . Varsayılan olarak, `InitializeSecurity` güvenlik tanımlayıcısı olan [COıNITIALIZESECURITY](/windows/win32/api/combaseapi/nf-combaseapi-coinitializesecurity) 'yi null olarak çağırır, bu da herhangi bir kullanıcının nesneniz erişimi olduğu anlamına gelir.

Hizmetin kendi güvenliğini belirtmesini istemiyorsanız, öğesini geçersiz kılın `PreMessageLoop` ve çağırmayın `InitializeSecurity` ve com, kayıt defterinden güvenlik ayarlarını belirler. Kayıt defteri ayarlarını yapılandırmanın kolay bir yolu, bu bölümün ilerleyen kısımlarında ele alınan [DCOMCNFG](../atl/dcomcnfg.md) yardımcı programıdır.

Güvenlik belirtildiğinde, nesne COM 'a kaydedilir, böylece yeni istemciler programa bağlanabilir. Son olarak program, Service Control Manager 'a (SCM) çalıştığını ve programın bir ileti döngüsü girdiğini söyler. Program, hizmet kapatıldıktan sonra bir çıkış iletisi gönderene kadar çalışmaya devam eder.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CSecurityDesc sınıfı](../atl/reference/csecuritydesc-class.md)<br/>
[CSID sınıfı](../atl/reference/csid-class.md)<br/>
[CDacl sınıfı](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT:: Run](../atl/reference/catlservicemodulet-class.md#run)
