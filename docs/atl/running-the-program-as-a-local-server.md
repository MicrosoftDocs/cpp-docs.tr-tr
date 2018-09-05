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
ms.openlocfilehash: e7ff7c2f7564a5da2c7a1db3913526a95660fe1d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43754689"
---
# <a name="running-the-program-as-a-local-server"></a>Programı yerel sunucu olarak çalıştırma

Program, hizmet olarak çalışan kullanışsız ise, program normal yerel sunucu olarak çalıştırılır, böylece kayıt geçici olarak değiştirebilirsiniz. Yalnızca yeniden adlandırma `LocalService` değeri için AppID altında `_LocalService` olun `LocalServer32` anahtarı altına, düzgün şekilde ayarlandığını. (Uygulamanızın farklı bir bilgisayarda çalışması gerektiğini belirtmek için DCOMCNFG kullanarak adlandırır olduğunu unutmayın, `LocalServer32` anahtarını `_LocalServer32`.) Yerel bir sunucuya çünkü başlangıçta birkaç saniye daha aldığından programınızı çalıştıran çağrısı `StartServiceCtrlDispatcher` içinde `CAtlServiceModuleT::Start` başarısız önce birkaç saniye sürer.

## <a name="see-also"></a>Ayrıca Bkz.

[Hata Ayıklama İpuçları](../atl/debugging-tips.md)

