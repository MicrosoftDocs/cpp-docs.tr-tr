---
title: Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme
ms.date: 11/04/2016
helpviewer_keywords:
- __HrLoadAllImportsForDll linker option
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
ms.openlocfilehash: e855b648dc7a9ee0670c3704a11aa1897a238403
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301675"
---
# <a name="loading-all-imports-for-a-delay-loaded-dll"></a>Gecikmeli Yüklenen DLL için Tüm İçe Aktarmaları Yükleme

**__Hrloadallımportsfordll** delayhlp.cpp içinde tanımlanan işlevi bağlayıcıya DLL'den ile belirtilen tüm içe aktarmaları yükleme [/delayload](delayload-delay-load-import.md) bağlayıcı seçeneği.

Tüm içe aktarmaları yükleme, tek bir yerde kodunuzda hata yerleştirin ve özel durum işleme Imports gerçek çağrıları etrafında kullanmak zorunda kalmazsınız olanak tanır. Ayrıca, burada, uygulamanızın kısmen alma yüklenmezse yardımcı kod sonucu olarak bir işlemle başarısız bir durumda önler.

Çağırma **__hrloadallımportsfordll** kancaları ve hata davranışına değiştirmez; bkz [hata işleme ve bildirme](error-handling-and-notification.md) daha fazla bilgi için.

DLL adı için geçirilen **__hrloadallımportsfordll** DLL içinde depolanan adı karşılaştırılır ve büyük/küçük harfe duyarlıdır.

Aşağıdaki örnek nasıl çağrılacağını gösterir **__hrloadallımportsfordll**:

```
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {
   printf ( "failed on snap load, exiting\n" );
   exit(2);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](linker-support-for-delay-loaded-dlls.md)
