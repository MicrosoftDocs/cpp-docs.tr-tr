---
title: CAtlServiceModuleT::Run işlevi
ms.date: 11/04/2016
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 448a955f2e72e8c523bbf74d6ee7e122828915ad
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57264423"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT::Run işlevi

`Run` yönelik çağrılar bulunur `PreMessageLoop`, `RunMessageLoop`, ve `PostMessageLoop`. Çağrılan sonra `PreMessageLoop` ilk hizmetin iş parçacığı kimliğini depolar. Hizmetinin kendisi Win32 API işlevini kullanarak bir WM_QUIT iletisi göndererek kapatmak için bu kimliği kullanacağı [PostThreadMessage](/windows/desktop/api/winuser/nf-winuser-postthreadmessagea).

`PreMessageLoop` Daha sonra çağırır `InitializeSecurity`. Varsayılan olarak, `InitializeSecurity` çağrıları [CoInitializeSecurity](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializesecurity) güvenlik tanımlayıcısı NULL olarak ayarlamak, yani herhangi bir kullanıcı, nesneyi erişimi olduğunu.

Kendi güvenlik belirtmek için hizmet istemiyorsanız, geçersiz kılma `PreMessageLoop` ve Remove() çağırmayın `InitializeSecurity`, ve COM ardından kayıt defteri güvenlik ayarlarını belirleyin. Kayıt defteri ayarlarını yapılandırmak için kullanışlı bir yöntem, [DCOMCNFG](../atl/dcomcnfg.md) daha sonra bu bölümde açıklanan yardımcı programı.

Güvenlik belirlendikten sonra yeni istemcilerin programa bağlanabilmesi nesne COM ile kaydedilir. Son olarak, program çalıştığı ve programın bir ileti döngüsü girer Hizmet Denetimi Yöneticisi (SCM) bildirir. Bir hizmet kapanması bağlı çıkış iletisi gönderir kadar program çalışan kalır.

## <a name="see-also"></a>Ayrıca bkz.

[Hizmetler](../atl/atl-services.md)<br/>
[CSecurityDesc Sınıfı](../atl/reference/csecuritydesc-class.md)<br/>
[CSid Sınıfı](../atl/reference/csid-class.md)<br/>
[CDacl Sınıfı](../atl/reference/cdacl-class.md)<br/>
[CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)
