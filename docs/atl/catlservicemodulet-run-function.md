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
ms.openlocfilehash: a07ad6b09fa10a81b500625531226dc18fc6281a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="catlservicemoduletrun-function"></a>CAtlServiceModuleT::Run işlevi
**Çalıştırma** çağrıları içeren `PreMessageLoop`, `RunMessageLoop`, ve `PostMessageLoop`. Çağrılan sonra `PreMessageLoop` ilk hizmetin iş parçacığı kimliği depolar Hizmetin kendisi göndererek kapatmak için bu kimliği kullanacağı bir **WM_QUIT** Win32 API işlevini kullanarak ileti [PostThreadMessage](http://msdn.microsoft.com/library/windows/desktop/ms644946).  
  
 `PreMessageLoop` Daha sonra çağırır `InitializeSecurity`. Varsayılan olarak, `InitializeSecurity` çağrıları [CoInitializeSecurity](http://msdn.microsoft.com/library/windows/desktop/ms693736) herhangi bir kullanıcı, nesne erişimi olduğunu gelir güvenlik tanımlayıcısı NULL olarak ayarlayın.  
  
 Kendi güvenlik belirtmek için hizmet istemiyorsanız, geçersiz kılma `PreMessageLoop` ve çağrısı yok `InitializeSecurity`, ve COM ardından kayıt defteri güvenlik ayarlarını belirleyin. Kayıt defteri ayarlarını yapılandırmak için kolay bir yol olduğu [DCOMCNFG](../atl/dcomcnfg.md) daha sonra bu bölümde açıklanan yardımcı programı.  
  
 Güvenlik belirlendikten sonra yeni istemciler için program bağlanabilmesi nesne COM ile kaydedilir. Son olarak, program çalıştığı ve program ileti bir döngüye girer Hizmet Denetim Yöneticisi (SCM) söyler. Hizmet kapatma sırasında çıkma bir ileti gönderir kadar program çalışmaya devam eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CSecurityDesc sınıfı](../atl/reference/csecuritydesc-class.md)   
 [CSID sınıfı](../atl/reference/csid-class.md)   
 [CDacl sınıfı](../atl/reference/cdacl-class.md)   
 [CAtlServiceModuleT::Run](../atl/reference/catlservicemodulet-class.md#run)

