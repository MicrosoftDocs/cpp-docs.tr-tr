---
description: 'Hakkında daha fazla bilgi edinin: Delay-Loaded DLL için tüm Içeri aktarmaları yükleme'
title: Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: 0f1334f30568e4722bd97579145ddcae9851b901
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190932"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme

Delayhlp. cpp içinde tanımlanan **__HrLoadAllImportsForDll** işlevi, bağlayıcının tüm içeri aktarmaları [/delayload](delayload-delay-load-import.md) BAĞLAYıCı seçeneğiyle belirtilen bir dll 'den yüklemesini söyler.

Tüm içeri aktarmaları yüklemek kodunuzda bir yerde hata işleme yerleştirmenizi sağlar ve içeri aktarmalar için yapılan gerçek çağrılar etrafında özel durum işlemeyi kullanmak zorunda değildir. Ayrıca, bir içeri aktarma işleminin yüklenemediği yardımcı kodun bir sonucu olarak, uygulamanızın bir işlemde kısmen başarısız olmasına neden olan bir durumu önler.

**__HrLoadAllImportsForDll** çağırmak kancalar ve hata işleme davranışını değiştirmez; daha fazla bilgi için bkz. [hata işleme ve bildirim](error-handling-and-notification.md) .

**__HrLoadAllImportsForDll** geçirilen dll adı, dll 'nin içinde depolanan adla karşılaştırılır ve büyük/küçük harfe duyarlıdır.

Aşağıdaki örnek, **__HrLoadAllImportsForDll** nasıl çağrılacağını göstermektedir:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Delay-Loaded dll 'Ler için bağlayıcı desteği](linker-support-for-delay-loaded-dlls.md)
