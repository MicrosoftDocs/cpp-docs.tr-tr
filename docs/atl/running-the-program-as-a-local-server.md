---
title: Programı yerel sunucu olarak çalışan | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ae2e44ba51a878d293ad5b497a1638cc9d7dc76
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37848489"
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel sunucu olarak çalıştırma
Program, hizmet olarak çalışan kullanışsız ise, program normal yerel sunucu olarak çalıştırılır, böylece kayıt geçici olarak değiştirebilirsiniz. Yalnızca yeniden adlandırma `LocalService` değeri için AppID altında `_LocalService` olun `LocalServer32` anahtarı altına, düzgün şekilde ayarlandığını. (Uygulamanızın farklı bir bilgisayarda çalışması gerektiğini belirtmek için DCOMCNFG kullanarak adlandırır olduğunu unutmayın, `LocalServer32` anahtarını `_LocalServer32`.) Yerel bir sunucuya çünkü başlangıçta birkaç saniye daha aldığından programınızı çalıştıran çağrısı `StartServiceCtrlDispatcher` içinde `CAtlServiceModuleT::Start` başarısız önce birkaç saniye sürer.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata Ayıklama İpuçları](../atl/debugging-tips.md)

