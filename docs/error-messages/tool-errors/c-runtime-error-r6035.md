---
title: C Çalışma Zamanı Hatası R6035
ms.date: 11/04/2016
f1_keywords:
- R6035
helpviewer_keywords:
- R6035
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
ms.openlocfilehash: ff3cd0259df92aa5cdade3f78a240e69f8f6f7de
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377475"
---
# <a name="c-runtime-error-r6035"></a>C Çalışma Zamanı Hatası R6035

Microsoft Visual C++ Runtime Library, Error R6035 - Bu uygulamadaki bir modül, modülün genel güvenlik çerezini başlatırken, güvenlik çerezine dayanan bir işlev etkindir.  __security_init_cookie erken ara.

[__security_init_cookie,](../../c-runtime-library/reference/security-init-cookie.md) genel güvenlik çerezinin ilk kullanımından önce çağrılmalıdır.

Genel güvenlik çerezi, [/GS (Arabellek Güvenlik Denetimi)](../../build/reference/gs-buffer-security-check.md) ile derlenen kodda ve yapılandırılmış özel durum işleme kullanan kodda arabellek taşma koruması için kullanılır. Esasen, taşma korumalı bir işleve girişte, çerez yığına konur ve çıkışta, yığındaki değer genel çerezle karşılaştırılır. Aralarındaki herhangi bir fark, arabellek taşma nın oluştuğunu ve programın hemen sonlandırılmasıyla sonuçlandığını gösterir.

Hata R6035, korumalı `__security_init_cookie` bir işlev girildikten sonra bir arama yapıldığını gösterir. Yürütme devam ederse, yığındaki çerez artık genel çerezle eşleşmeyeceği için sahte bir arabellek taşma algılanır.

Aşağıdaki DLL örneğini göz önünde bulundurun. DLL giriş noktası, bağlayıcı [/ENTRY (Entry-Point Symbol)](../../build/reference/entry-entry-point-symbol.md) seçeneği ile DllEntryPoint olarak ayarlanır. Bu, CRT'nin genel güvenlik çerezini normalde ilke olarak ilke landıracak `__security_init_cookie`olan başlatılmasını atlar, bu nedenle DLL'nin kendisi aramalıdır.

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

DllEntryPoint yapılandırılmış özel durum işleme kullanır ve bu nedenle arabellek taşmaları algılamak için güvenlik çerez kullanır, çünkü bu örnek hata R6035 oluşturur. DllInitialize çağrıldığında, genel güvenlik çerezi yığına zaten konulmuştur.

Doğru yol bu örnekte gösterilmiştir:

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

Bu durumda, DllEntryPoint arabellek taşmaları karşı korumalı değildir (hiçbir yerel dize arabellekleri vardır ve yapılandırılmış özel durum işleme kullanmaz); bu nedenle güvenle `__security_init_cookie`arayabilirsiniz . Daha sonra korunan bir yardımcı işlevi çağırır.

> [!NOTE]
> Hata iletisi R6035 yalnızca x86 hata ayıklama CRT tarafından oluşturulur ve yalnızca yapılandırılmış özel durum işleme için, ancak koşul tüm platformlarda bir hatadır ve C++ EH gibi tüm özel durum işleme biçimleri için.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC'de Güvenlik Özellikleri](https://blogs.msdn.microsoft.com/vcblog/2017/06/28/security-features-in-microsoft-visual-c/)
