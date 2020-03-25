---
title: C Çalışma Zamanı Hatası R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: 7c497347689bcfc5528280bd22aa5183d5fafd61
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80197010"
---
# <a name="c-runtime-error-r6035"></a>C Çalışma Zamanı Hatası R6035

Microsoft Visual C++ çalışma zamanı kitaplığı, Error R6035-bu uygulamadaki bir modül, bu güvenlik tanımlama bilgisine bağlı bir işlev etkinken modülün genel güvenlik tanımlama bilgisini başlatıyor.  Daha önce __security_init_cookie çağırın.

[__security_init_cookie](../../c-runtime-library/reference/security-init-cookie.md) , genel güvenlik tanımlama bilgisinin ilk kullanılmadan önce çağrılmalıdır.

Genel güvenlik tanımlama bilgisi, [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ile derlenen kodda ve yapılandırılmış özel durum işleme kullanan kodda arabellek taşma koruması için kullanılır. Temelde, taşma korumalı bir işleve girişte, tanımlama bilgisi yığına konur ve çıkışta, yığındaki değer genel tanımlama bilgisine göre karşılaştırılır. Aralarında herhangi bir farklılık, bir arabellek taşmasının gerçekleştiğini ve programın anında sonlandırmasına neden olduğunu gösterir.

Hata R6035, korunan bir işlev girildikten sonra `__security_init_cookie` çağrısının yapıldığını gösterir. Yürütmenin devam etmesi gerekiyorsa, yığındaki tanımlama bilgisi artık genel tanımlama bilgisiyle eşleşmediğinden, bir Spur, arabellek taşması algılanır.

Aşağıdaki DLL örneğini göz önünde bulundurun. DLL giriş noktası, bağlayıcı [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md) seçeneği aracılığıyla DllEntryPoint olarak ayarlanır. Bu, genellikle genel güvenlik tanımlama bilgisini başlatacak olan CRT başlatmasını atlar, bu yüzden DLL 'in kendisi `__security_init_cookie`çağırmalıdır.

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

Bu durumda, DllEntryPoint arabellek taşmalarına karşı korunmaz (yerel dize arabellekleri yoktur ve yapılandırılmış özel durum işleme kullanmaz); Bu nedenle, `__security_init_cookie`güvenle çağırabilir. Ardından, korunan bir yardımcı işlevi çağırır.

> [!NOTE]
>  Hata iletisi R6035 yalnızca x86 hata ayıklama CRT ve yalnızca yapılandırılmış özel durum işleme tarafından oluşturulur, ancak koşul tüm platformlarda bir hata ve C++ Eh gibi özel durum işleme biçimleri için bir hatadır.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC 'deki güvenlik özellikleri](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)
