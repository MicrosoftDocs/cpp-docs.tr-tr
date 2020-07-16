---
title: C Çalışma Zamanı Hatası R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: 9b92b1e2e123201d4f50422754b77f62b2ec943b
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404404"
---
# <a name="c-runtime-error-r6035"></a>C Çalışma Zamanı Hatası R6035

Microsoft Visual C++ çalışma zamanı kitaplığı, Error R6035-bu uygulamadaki bir modül, bu güvenlik tanımlama bilgisine bağlı bir işlev etkinken modülün genel güvenlik tanımlama bilgisini başlatıyor.  Daha önce __security_init_cookie çağırın.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) , genel güvenlik tanımlama bilgisinin ilk kullanılmadan önce çağrılmalıdır.

Genel güvenlik tanımlama bilgisi, [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ile derlenen kodda ve yapılandırılmış özel durum işleme kullanan kodda arabellek taşma koruması için kullanılır. Temelde, taşma korumalı bir işleve girişte, tanımlama bilgisi yığına konur ve çıkışta, yığındaki değer genel tanımlama bilgisine göre karşılaştırılır. Aralarında herhangi bir farklılık, bir arabellek taşmasının gerçekleştiğini ve programın anında sonlandırmasına neden olduğunu gösterir.

Hata R6035, `__security_init_cookie` korumalı bir işlev girildikten sonra yapılan bir çağrının yapıldığını gösterir. Yürütmenin devam etmesi gerekiyorsa, yığındaki tanımlama bilgisi artık genel tanımlama bilgisiyle eşleşmediğinden, bir Spur, arabellek taşması algılanır.

Aşağıdaki DLL örneğini göz önünde bulundurun. DLL giriş noktası, bağlayıcı [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) seçeneği aracılığıyla DllEntryPoint olarak ayarlanır. Bu, genellikle genel güvenlik tanımlama bilgisini başlatacak olan CRT başlatmasını atlar, bu nedenle DLL 'nin kendisi çağırmalıdır `__security_init_cookie` .

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

Bu örnek, R6035 hatasını üretir çünkü DllEntryPoint yapılandırılmış özel durum işlemeyi kullanır ve bu nedenle arabellek taşmalarını algılamak için güvenlik tanımlama bilgisini kullanır. DLCI 'nin çağrılışında, genel güvenlik tanımlama bilgisi yığına zaten konur.

Bu örnekte doğru şekilde gösterilmiştir:

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

Bu durumda, DllEntryPoint arabellek taşmalarına karşı korunmaz (yerel dize arabellekleri yoktur ve yapılandırılmış özel durum işleme kullanmaz); Bu nedenle, güvenli bir şekilde çağırabilir `__security_init_cookie` . Ardından, korunan bir yardımcı işlevi çağırır.

> [!NOTE]
> Hata iletisi R6035 yalnızca x86 hata ayıklama CRT ve yalnızca yapılandırılmış özel durum işleme tarafından oluşturulur, ancak koşul tüm platformlarda hata ve C++ EH gibi özel durum işleme biçimleri için bir hatadır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC 'deki güvenlik özellikleri](https://devblogs.microsoft.com/cppblog/security-features-in-microsoft-visual-c/)
