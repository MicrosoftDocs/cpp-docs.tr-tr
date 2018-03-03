---
title: "CAtlServiceModuleT::Start işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5d4ee7899cda213bf8d8cfd529fd7609976e20d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlservicemoduletstart-function"></a>CAtlServiceModuleT::Start işlevi
Hizmet çalıştırdığınızda **_tWinMain** çağrıları **CAtlServiceModuleT::WinMain**, sırayla çağıran `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start`bir dizi ayarlar **SERVICE_TABLE_ENTRY** her hizmetin kendi başlangıç işlevini eşleme yapıları. Bu dizi sonra Win32 API işlevine geçirilen [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324). Teorik olarak bir EXE birden fazla hizmet ele ve dizi birden çok olabilir **SERVICE_TABLE_ENTRY** yapıları. Şu anda, ancak bir ATL oluşturulan hizmet EXE başına yalnızca bir hizmet destekler. Bu nedenle, hizmet adını içeren tek bir giriş dizisi olduğundan ve **_ServiceMain** olarak başlangıç işlevi. **_ServiceMain** bir statik üye işlevidir `CAtlServiceModuleT` statik olmayan üye işlevi çağırır `ServiceMain`.  
  
> [!NOTE]
>  Hata **StartServiceCtrlDispatcher** bağlanmak için Hizmet Denetimi Yöneticisi (SCM) büyük olasılıkla program hizmet olarak çalışmıyor anlamına gelir. Bu durumda, programı çağırır `CAtlServiceModuleT::Run` doğrudan programı yerel bir sunucu olarak çalıştırabilirsiniz. Yerel bir sunucu olarak programı çalıştırma hakkında daha fazla bilgi için bkz: [hata ayıklama ipuçları](../atl/debugging-tips.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hizmetleri](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)

