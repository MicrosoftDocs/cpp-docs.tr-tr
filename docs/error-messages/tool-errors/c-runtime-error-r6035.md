---
title: C çalışma zamanı hatası R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: bb215668fc13ecf84efdbf5f7ec6bb25c922181b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668266"
---
# <a name="c-runtime-error-r6035"></a>C çalışma zamanı hatası R6035

Bu güvenlik tanımlama bilgisinde bağlı olan bir işlev etkin durumdayken Microsoft Visual C++ çalışma zamanı kitaplığı, hatası R6035 - Bu uygulamadaki bir modül modülün genel güvenlik tanımlama bilgisi başlatılıyor.  __Security_init_cookie önceki çağırın.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) genel güvenlik tanımlama bilgisi ilk kullanımından önce çağrılmalıdır.

Genel güvenlik tanımlama bilgisi ile derlenmiş kodda arabellek taşması koruma için kullanılan [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ve yapılandırılmış özel durum işleme kullanan kod. Esas olarak, giriş taşması korumalı bir işleve tanımlama bilgisi yığına yerleştirilir ve Çıkışta, yığında değeri genel tanımlama bilgisinin karşı karşılaştırılır. Aralarındaki fark, bir arabellek taşması oluştu ve programı hemen sonlandırılması sonuçları gösterir.

Hatası R6035 gösteren bir çağrı `__security_init_cookie` korumalı bir işlev girilen sonra yapıldı. Yürütme devam etmek için varsa, yığın tanımlama bilgisinde, artık genel tanımlama bilgisi eşleşir çünkü sahte bir arabellek taşması algılanır.

Aşağıdaki örnek DLL göz önünde bulundurun. DLL giriş noktası için DllEntryPoint bağlayıcı ayarlanır [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) seçeneği. Bu DLL çağırmanız gerekir böylece hangi genel güvenlik tanımlama bilgisi, normalde başlatmak CRT'ın başlatma atlar `__security_init_cookie`.

```
// Wrong way to call __security_init_cookie
DllEntryPoint(...) {
   DllInitialize();
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}

void DllInitialize() {
   __security_init_cookie();
}
```

Bu örnekte DllEntryPoint yapılandırılmış özel durum işleme ve bu yüzden arabellek taşmalarına algılamak için güvenlik tanımlama bilgisi kullanır çünkü hatası R6035 oluşturur. Zaman DllInitialize çağrılır, genel güvenlik tanımlama bilgisi zaten yığında alındığından.

Doğru yolu; Bu örnekte gösterilmiştir:

```
// Correct way to call __security_init_cookie
DllEntryPoint(...) {
   __security_init_cookie();
   DllEntryHelper();
}

void DllEntryHelper() {
   ...
   __try {
      ...
   } __except()... {
      ...
   }
}
```

Bu durumda, DllEntryPoint arabellek taşmalarına karşı korumalı değildir (yerel dize arabellek yok sahiptir ve yapılandırılmış özel durum işleme kullanmaz); Bu nedenle güvenle çağırabilirsiniz `__security_init_cookie`. Ardından, korumalı bir yardımcı işlevini çağırır.

> [!NOTE]
>  Hata iletisi R6035 x86 tarafından oluşturulan yalnızca CRT hata ayıklama ve yapılandırılmış özel durum işleme, ancak bir koşul için bir hata özel durum biçimlerinin yanı sıra, tüm platformlarda, C++ EH gibi işleyen.

## <a name="see-also"></a>Ayrıca Bkz.

[MSVC güvenlik özellikleri](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)