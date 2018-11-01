---
title: Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: a9e9df6b0bae49eaf599e56e5d96040afae315e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536571"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme

**__Hrloadallımportsfordll** delayhlp.cpp içinde tanımlanan işlevi bağlayıcıya DLL'den ile belirtilen tüm içe aktarmaları yükleme [/delayload](../../build/reference/delayload-delay-load-import.md) bağlayıcı seçeneği.

Tüm içe aktarmaları yükleme, tek bir yerde kodunuzda hata yerleştirin ve özel durum işleme Imports gerçek çağrıları etrafında kullanmak zorunda kalmazsınız olanak tanır. Ayrıca, burada, uygulamanızın kısmen alma yüklenmezse yardımcı kod sonucu olarak bir işlemle başarısız bir durumda önler.

Çağırma **__hrloadallımportsfordll** kancaları ve hata davranışına değiştirmez; bkz [hata işleme ve bildirme](../../build/reference/error-handling-and-notification.md) daha fazla bilgi için.

DLL adı için geçirilen **__hrloadallımportsfordll** DLL içinde depolanan adı karşılaştırılır ve büyük/küçük harfe duyarlıdır.

Aşağıdaki örnek nasıl çağrılacağını gösterir **__hrloadallımportsfordll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Ayrıca Bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)