---
title: CRT'de küresel durum
ms.date: 04/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 1b32e8d4f23d2361a52a9b81150ef7c5c7422761
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745350"
---
# <a name="global-state-in-the-crt"></a>CRT'de küresel durum

Evrensel C Runtime (UCRT) bazı işlevleri genel durumu kullanır. Örneğin, `setlocale()` basamak ayırıcılarını, metin kodu sayfasını ve benzeri sayıları etkileyen tüm programın yerel ayarını ayarlar.

UCRT'nin küresel durumu uygulamalar ve işletim sistemi arasında paylaşılmaz. Örneğin, uygulamanız ararsa, `setlocale()`C çalışma süresini kullanan işletim sistemi bileşenlerinin yerel ayarı etkilemez veya bunun tersi de olmaz.

## <a name="os-specific-versions-of-crt-functions"></a>CRT fonksiyonlarının işletim sistemi için özel sürümleri

UCRT'de, küresel durumla etkileşimedebilen işlevler, önceden belirlenmiş `_o_`bir "ikiz" işlevine sahiptir. Örneğin:

- `setlocale()`uygulamaya özgü genel durumu etkiler.
- `_o_setlocale()`tüm işletim sistemi bileşenleri tarafından paylaşılan genel durumu etkiler, ancak uygulamaları etkilemez.

Bu "ikiz" işlevler arasındaki tek fark, genel CRT durumunu okuduklarında/yazdıklarında, işletim egörere `_o_`özgü sürümlerin (diğer bir şekilde başlayan sürümler) uygulamanın küresel durum kopyası yerine küresel devletin işletim sistemi kopyasını kullanmasıdır.

Bu işlevlerin işletim sistemi özgü `ucrt.osmode.lib`sürümleri. Örneğin, işletim sistemi özel `setlocale()` sürümü`_o_setlocale()`

Bileşeninizin CRT durumunu bir uygulamanın CRT durumundan yalıtmanın iki yolu vardır:

- Derleyici seçenekleri /MT (sürüm) veya MTd (hata ayıklama) kullanarak bileşeninizi statik olarak bağla. Ayrıntılar için bkz: [/MD, /MT, /LD](https://docs.microsoft.com/cpp/build/reference/md-mt-ld-use-run-time-library?view=vs-2019). Statik bağlantının ikili boyutu büyük ölçüde artırabileceğini unutmayın.
- Windows 10 20H2 ile başlayarak, CRT'ye dinamik olarak bağlanarak CRT durum yalıtımı alın, ancak IŞLETIM sistemi moddışlamalarını _(o_ile başlayan işlevler) arayın. OS modu dışa aktarımlarını aramak için, daha önce olduğu gibi statik `/NODEFAULTLIB:libucrt.lib` bağlantı, `/NODEFAULTLIB:libucrtd.lib` ancak ayrıntılar için bağlantı seçeneği (sürüm) veya (hata ayıklama) Bkz. [/NODEFAULTLIB (Kitaplıkları Yoksay)](https://docs.microsoft.com/cpp/build/reference/nodefaultlib-ignore-libraries?view=vs-2019) kullanarak statik UCRT'yi yoksay. Ve `ucrt.osmode.lib` bağlayıcı girişi ekleyin.

> [!Note]
> Kaynak kodunda, `setlocale()`yazmak `_o_setlocale()`, değil . Bağlantı `ucrt.osmode.lib`yaptığınızda, bağlayıcı otomatik olarak işlevin işletim sistemi özel sürümünü yerine geçer. Yani, `setlocale()` ile değiştirilecektir `_o_setlocale()`.

Yalnızca `ucrt.osmode.lib` uygulama modunda kullanılabilen bazı UCRT çağrıları devre dışı kalır. Bunları çağırmaya çalışmak bir bağlantı hatasına neden olur.

## <a name="global-state-affected-by-appos-separation"></a>Uygulama/işletim sistemi ayrımından etkilenen küresel durum

Uygulama ve işletim sistemi durumunun ayrılmasından etkilenen küresel durum şunları içerir:

- [Yerel veri](locale.md)
- Sinyal tarafından ayarlanan [sinyal](reference/signal.md) işleyicileri
- Sonlandırma yordamları [sonlandırma](reference/set-terminate-crt.md) tarafından ayarlanmış
- [errno ve _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [Rand](reference/rand.md) and [srand](reference/srand.md) tarafından kullanılan rasgele sayı oluşturma durumu
- [Strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [Tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmtime, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- _putch tarafından kullanılan [arabellek, _putwch](reference/putch-putwch.md)
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) ve [_set_new_mode](reference/set-new-mode.md)
- [fmode] (text-and-binary-mode-file-i-o.md)
- [Saat dilimi bilgileri](time-management.md)

## <a name="see-also"></a>Ayrıca bkz.

[C Run-Time kitaplığı başvurusu](c-run-time-library-reference.md)
