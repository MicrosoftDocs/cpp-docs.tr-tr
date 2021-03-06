---
title: CRT'deki genel durum
description: Paylaşılan genel durumun Microsoft Universal C çalışma zamanında nasıl işlendiğini açıklar.
ms.topic: conceptual
ms.date: 10/02/2020
helpviewer_keywords:
- CRT global state
ms.openlocfilehash: 6c8b97e2bd6fa71891aedacb1fbfec2bbe382d84
ms.sourcegitcommit: faedcc3be78b29c78e5d51e3c7c7c2f448c745bf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2020
ms.locfileid: "91717521"
---
# <a name="global-state-in-the-crt"></a>CRT'deki genel durum

Evrensel C çalışma zamanı (UCRT) içindeki bazı işlevler genel durumu kullanır. Örneğin, `setlocale()` tüm program için yerel ayarı belirler, bu, rakam ayırıcıları, metin kodu sayfası vb. etkiler.

UıCRT 'ın genel durumu uygulamalar ve işletim sistemi arasında paylaşılmaz. Örneğin, uygulamanız çağırıyorsa `setlocale()` , C çalışma zamanı veya başka bir şekilde veya başka bir şekilde kullanan herhangi bir işletim sistemi bileşeni için yerel ayarı etkilemez.

## <a name="os-specific-versions-of-crt-functions"></a>CRT işlevlerinin işletim sistemine özgü sürümleri

UıCRT 'da, genel durumla etkileşime geçen işlevlerde bir "ikizi" işlevi vardır ve önekli `_o_` . Örnek:

- `setlocale()` uygulamaya özgü genel durumu etkiler.
- `_o_setlocale()` tüm işletim sistemi bileşenleri tarafından paylaşılan genel durumu etkiler, ancak uygulamalar değildir.

Bu "ikizi" işlevleri arasındaki tek fark, genel CRT durumunu okuduklarında/yazarken, işletim sistemine özgü sürümlerin (yani, ile başlayan sürümler `_o_` ), uygulamanın genel durum kopyası yerine genel durum işletim sistemi kopyasını kullanır.

Bu işlevlerin işletim sistemine özgü sürümleri içinde bulunur `ucrt.osmode.lib` . Örneğin, işletim sistemine özgü sürümü `setlocale()``_o_setlocale()`

Bileşenin CRT durumunu uygulamanın CRT durumundan yalıtmak için iki yol vardır:

- Derleyici seçeneklerini `/MT` (sürüm) veya `/MTd` (hata ayıklama) kullanarak bileşeninizi statik olarak bağlayın. Ayrıntılar için bkz. [/MD,/MT,/LD](../build/reference/md-mt-ld-use-run-time-library.md). Statik bağlama, ikili boyutu büyük ölçüde artırabilir.
- Windows 10 sürüm 2004 ' den başlayarak, CRT 'ye dinamik olarak bağlanın ancak işletim sistemi modu dışarı aktarmaları ( _o_ile başlayan işlevler) çağırın. İşletim sistemi modu dışarı aktarmaları çağırmak için, daha önce olarak statik bağlantı yapın, ancak bağlayıcı seçeneğini `/NODEFAULTLIB:libucrt.lib` (sürüm) veya `/NODEFAULTLIB:libucrtd.lib` (hata ayıklama) kullanarak statik UCRT 'yi yoksayın. Ve `ucrt.osmode.lib` bağlayıcı girişine ekleyin. Ayrıntılar için bkz. [/nodefaultlib (kitaplıkları Yoksay)](../build/reference/nodefaultlib-ignore-libraries.md) .

> [!Note]
> Kaynak kodunda, yazma `setlocale()` , değil `_o_setlocale()` . Bağlama yaptığınızda bağlayıcı, `ucrt.osmode.lib` işlevin işletim sistemine özgü sürümünü otomatik olarak yerine geçecek. Diğer bir deyişle, `setlocale()` ile değiştirilecektir `_o_setlocale()` .

İle bağlama `ucrt.osmode.lib` , yalnızca uygulama modunda kullanılabilen bazı UCRT çağrılarını devre dışı bırakır. Bu, çağırma girişimi bir bağlantı hatasına neden olur.

## <a name="global-state-affected-by-appos-separation"></a>Uygulama/işletim sistemi ayrımı tarafından etkilenen küresel durum

Uygulamanın ve işletim sistemi durumunun ayrılarak etkilenen küresel durum şunları içerir:

- [Yerel ayar verileri](locale.md)
- Sinyal işleyicileri [sinyaltarafından](reference/signal.md) ayarlanan
- [Sonlandır](reference/set-terminate-crt.md) tarafından ayarlanan sonlandırma yordamları
- [errno ve _doserrno](errno-doserrno-sys-errlist-and-sys-nerr.md)
- [S_SAYI_ÜRET](reference/rand.md) ve [srand](reference/srand.md) tarafından kullanılan rastgele sayı oluşturma durumu
- Kullanıcının serbest bırakılması gerekmeyen bir arabellek döndüren işlevler:   [strtok, wcstok, _mbstok](reference/strtok-strtok-l-wcstok-wcstok-l-mbstok-mbstok-l.md) [tmpnam, _wtmpnam](reference/tempnam-wtempnam-tmpnam-wtmpnam.md) [asctime, _wasctime](reference/asctime-wasctime.md) [gmsaati, _gmtime32, _gmtime64](reference/gmtime-gmtime32-gmtime64.md) [_fcvt](reference/fcvt.md) [_ecvt](reference/ecvt.md) [strerror, _strerror, _wcserror, __wcserror](reference/strerror-strerror-wcserror-wcserror.md)
- [_Putch, _putwch](reference/putch-putwch.md) tarafından kullanılan arabellek
- [_set_invalid_parameter_handler, _set_thread_local_invalid_parameter_handler](reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md)
- [_set_new_handler](reference/set-new-handler.md) ve [_set_new_mode](reference/set-new-mode.md)
- [fMode](text-and-binary-mode-file-i-o.md)
- [Saat dilimi bilgileri](time-management.md)

## <a name="see-also"></a>Ayrıca bkz.

[C çalışma zamanı kitaplığı başvurusu](c-run-time-library-reference.md)
