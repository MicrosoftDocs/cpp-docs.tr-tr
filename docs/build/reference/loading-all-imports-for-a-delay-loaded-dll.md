---
description: Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükleme hakkında daha fazla bilgi edinin
title: Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükle
ms.date: 01/19/2021
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.openlocfilehash: b197c50d3b6b68d77dbfccda99e3c2986c515204
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667211"
---
# <a name="load-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli yüklenen DLL için tüm içeri aktarmaları yükle

`__HrLoadAllImportsForDll`İçinde tanımlanan işlevi, *`delayhlp.cpp`* bağlayıcının bağlayıcı seçeneğiyle BELIRTILEN bir dll 'den tüm içeri aktarmaları yüklemesini söyler [`/delayload`](delayload-delay-load-import.md) .

Tüm içeri aktarmaları yüklemek kodunuzda bir yerde hata işleme yerleştirmenizi sağlar ve içeri aktarmalar için yapılan gerçek çağrılar etrafında özel durum işlemeyi kullanmak zorunda değildir. Ayrıca, bir içeri aktarma işleminin yüklenemediği yardımcı kodun bir sonucu olarak uygulamanızın bir işlem aracılığıyla başarısız olduğu bir durumu önler.

Çağırma `__HrLoadAllImportsForDll` , kancalar ve hata işleme davranışlarını değiştirmez. Daha fazla bilgi için bkz. [hata işleme ve bildirim](error-handling-and-notification.md).

Geçirilen DLL adı, `__HrLoadAllImportsForDll` DLL 'nin içinde depolanan adla karşılaştırılır ve büyük/küçük harfe duyarlıdır.

Aşağıdaki örnek nasıl çağrılacağını göstermektedir `__HrLoadAllImportsForDll` :

```C
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
