---
title: CAtlServiceModuleT::Run işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CServiceModule::Run
- CServiceModule.Run
- CSecurityDescriptor
dev_langs:
- C++
helpviewer_keywords:
- ATL services, security
ms.assetid: 42c010f0-e60e-459c-a63b-a53a24cda93b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e509ad88a744f6ebaaca41ecd0d6455d68c2585c
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37850660"
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT::Run işlevi
`Run` yönelik çağrılar bulunur `PreMessageLoop`, `RunMessageLoop`, ve `PostMessageLoop`. Çağrılan sonra `PreMessageLoop` ilk hizmetin iş parçacığı kimliğini depolar. Hizmetinin kendisi Win32 API işlevini kullanarak bir WM_QUIT iletisi göndererek kapatmak için bu kimliği kullanacağı [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` Daha sonra çağırır `InitializeSecurity`. Varsayılan olarak, `InitializeSecurity` çağrıları [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) güvenlik tanımlayıcısı NULL olarak ayarlamak, yani herhangi bir kullanıcı, nesneyi erişimi olduğunu.  
  
 Kendi güvenlik belirtmek için hizmet istemiyorsanız, geçersiz kılma `PreMessageLoop` ve Remove() çağırmayın `InitializeSecurity`, ve COM ardından kayıt defteri güvenlik ayarlarını belirleyin. Kayıt defteri ayarlarını yapılandırmak için kullanışlı bir yöntem, [DCOMCNFG](../atl/dcomcnfg.md) daha sonra bu bölümde açıklanan yardımcı programı.  
  
 Güvenlik belirlendikten sonra yeni istemcilerin programa bağlanabilmesi nesne COM ile kaydedilir. Son olarak, program çalıştığı ve programın bir ileti döngüsü girer Hizmet Denetimi Yöneticisi (SCM) bildirir. Bir hizmet kapanması bağlı çıkış iletisi gönderir kadar program çalışan kalır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CSecurityDesc sınıfı](../atl/reference/csecuritydesc-class.md)   
 [CSid sınıfı](../atl/reference/csid-class.md)   
 [CDacl sınıfı](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

