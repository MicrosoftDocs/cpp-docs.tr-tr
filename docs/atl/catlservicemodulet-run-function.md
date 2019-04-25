---
title: CAtlServiceModuleT::Run işlevi
ms.date: 11/04/2016
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
ms.openlocfilehash: 0f50c13912bbfef861e8650ee7589daea1e45725
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62250852"
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
