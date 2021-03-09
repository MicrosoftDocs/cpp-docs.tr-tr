---
description: 'Daha fazla bilgi edinin: bağlantı seçenekleri'
title: Bağlantı Seçenekleri
ms.date: 11/04/2016
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
- legacy_stdio_float_rounding.obj
- loosefpmath.obj
- smallheap.obj
- fp10.obj
- nochkclr.obj
- chkstk.obj
- pcommode.obj
- pnoenv.obj
- link options [C++]
- invalidcontinue.obj
- pnothrownew.obj
- pwsetargv.obj
- pinvalidcontinue.obj
- wsetargv.obj
- binmode.obj
- setargv.obj
- noarg.obj
- pnewmode.obj
- commode.obj
- pthreadlocale.obj
- pbinmode.obj
- threadlocale.obj
- pnoarg.obj
ms.assetid: 05b5a77b-9dd1-494b-ae46-314598c770bb
ms.openlocfilehash: 3fce62718518138303900be379458dce950acfbe
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514401"
---
# <a name="link-options"></a>Bağlantı Seçenekleri

CRT lib dizini, herhangi bir kod değişikliği yapmadan belirli CRT özelliklerini etkinleştiren bir dizi küçük nesne dosyasını içerir. Bunlar, bunları kullanmak için bağlayıcı komut satırına eklemeniz gereken için "bağlantı seçenekleri" olarak adlandırılır.

Bu nesnelerin CLR saf mod sürümleri Visual Studio 2015 ' de kullanımdan kaldırılmıştır ve Visual Studio 2017 ' de desteklenmez. Yerel ve/clr kodu için normal sürümleri kullanın.

|Yerel ve/clr|Saf mod|Description|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Varsayılan dosya çevirisi modunu binary olarak ayarlar. Bkz. [_fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|yok|CRT kullanılırken yığın denetimi ve alloca desteği sağlar.|
|commode.obj|pcommode.obj|Global COMMIT bayrağını "COMMIT" olarak ayarlar. Bkz. [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) ve [fopen_s _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|exe_initialize_mta. lib|yok|EXE başlatması sırasında, genel akıllı işaretçilerde COM nesnelerinin kullanılmasına izin veren MTA grubu başlatır. Bu seçenek, kapatılırken bir MTA grubu başvurusunu sızıntısına neden olduğundan, dll 'Ler için kullanmayın. Bu öğesine bağlama, ComBase. h dahil ve _EXE_INITIALIZE_MTA tanımlama ile eşdeğerdir. |
|fp10.obj|yok|Varsayılan duyarlık denetimini 64 bit olarak değiştirir. Bkz. [kayan nokta desteği](../c-runtime-library/floating-point-support.md).|
|invalidcontinue.obj|pinvalidcontinue.obj|Hiçbir şey yapan varsayılan geçersiz parametre işleyicisini ayarlar, yani CRT işlevlerine geçirilen geçersiz parametrelerin errno ayarlaması ve bir hata sonucu döndürmeyeceği anlamına gelir.|
|legacy_stdio_float_rounding. obj|yok|Windows 10 19041 Universal C çalışma zamanı ile kayan nokta değerlerini (örneğin, [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)kullanırken) yazdırma düzeltildi. Artık tam olarak gösterilemeyen kayan noktalı sayıları doğru bir şekilde yuvarlar ve [fesetround](../c-runtime-library/reference/fegetround-fesetround2.md)tarafından istenen kayan nokta yuvarlamaya uyar. Bu davranış güncelleştirmesi, Visual Studio 2019 sürüm 16,2 ve sonraki sürümlerinde kullanılabilir. Eski davranış, Visual Studio 'nun önceki sürümlerinde veya bu bağlantı seçeneği sağlanarak kullanılır.|
|loosefpmath.obj|yok|Kayan nokta kodunun denormal değerlerini toleransı sağlar.|
|newmode.obj|pnewmode.obj|Hata durumunda [malloc](../c-runtime-library/reference/malloc.md) 'in yeni işleyiciyi çağırmasını sağlar. Bkz. [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md)ve [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|Argc ve argv 'nin tüm işlemesini devre dışı bırakır.|
|nochkclr.obj|yok|Hiçbir şey yapılmaz. Projenizden kaldırın.|
|noenv.obj|pnoenv.obj|CRT için önbelleğe alınmış bir ortamın oluşturulmasını devre dışı bırakır.|
|nothrownew.obj|pnothrownew.obj|CRT içinde yeni bir atma sürümü sunar. Bkz. [New ve delete işleçleri](../cpp/new-and-delete-operators.md).|
|setargv.obj|psetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesine izin vermez. Bkz. [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Varsayılan olarak tüm yeni iş parçacıkları için iş parçacığı başına yerel ayarları sunar.|
|wsetargv.obj|pwsetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesine izin vermez. Bkz. [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>Ayrıca bkz.

- [C çalışma zamanı (CRT) ve C++ standart kitaplığı (STL) `.lib` dosyaları](../c-runtime-library/crt-library-features.md)
