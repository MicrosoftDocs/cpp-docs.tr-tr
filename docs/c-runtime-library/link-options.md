---
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
ms.openlocfilehash: ea71faab639a8c0a09d6e332618dd7e09159a4e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351107"
---
# <a name="link-options"></a>Bağlantı Seçenekleri

CRT lib dizini, herhangi bir kod değişikliği olmadan belirli CRT özelliklerini etkinleştiren bir dizi küçük nesne dosyası içerir. Bunları kullanmak için bağlayıcı komut satırına eklemeniz olduğundan bunlara "bağlantı seçenekleri" denir.

Bu nesnelerin CLR saf mod sürümleri Visual Studio 2015'te ve Visual Studio 2017'de desteklenmeden küçümsenen. Yerel ve /clr kodu için normal sürümleri kullanın.

|Yerli ve /clr|Saf mod|Açıklama|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Varsayılan dosya çeviri modunu ikili olarak ayarlar. [Bkz. _fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|yok|CRT'yi kullanmadığında yığın denetimi ve alloca desteği sağlar.|
|commode.obj|pcommode.obj|Küresel taahhüt bayrağını "işlemek" için ayarlar. Bkz. [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) ve [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|exe_initialize_mta.lib|yok|GLOBAL akıllı işaretçilerde COM nesnelerinin kullanılmasına olanak tanıyan EXE başlatma sırasında MTA dairesini başlatir. Bu seçenek kapatma sırasında bir MTA daire başvurusu sızdırdığından, DL'ler için kullanmayın. Buna bağlanmak combase.h ve _EXE_INITIALIZE_MTA tanımlamaya eşdeğerdir. |
|fp10.obj|yok|Varsayılan kesinlik denetimini 64 bit olarak değiştirir. Bkz. [Kayan Nokta Desteği.](../c-runtime-library/floating-point-support.md)|
|invalidcontinue.obj|pinvalidcontinue.obj|Hiçbir şey yapmayan varsayılan geçersiz parametre işleyicisi ayarlar, crt işlevlerine geçirilen geçersiz parametreler yalnızca errno ayarlar ve bir hata sonucu döndürür.|
|legacy_stdio_float_rounding.obj|yok|Windows 10 19041 Evrensel C Çalışma Süresi ile kayan nokta değerlerini yazdırma (örneğin, [printf](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)kullanırken) düzeltildi. Şimdi düzgün tam olarak temsil edilebilir kayan nokta numaraları yuvarlar ve [fesetenv](../c-runtime-library/reference/fesetenv1.md)tarafından istenen kayan nokta yuvarlama saygı duyar. Bu davranış güncelleştirmesi Visual Studio 2019 sürüm 16.2 ve sonraki sürümlerde kullanılabilir. Eski davranış Visual Studio önceki sürümlerinde veya bu bağlantı seçeneği sağlayarak kullanılır.|
|loosefpmath.obj|yok|Kayan nokta kodunun normal olmayan değerleri tolere eder.|
|newmode.obj|pnewmode.obj|[Malloc'un](../c-runtime-library/reference/malloc.md) yeni işleyiciyi arıza konusunda çağırmasına neden olur. [Bkz. _set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md), ve [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|argc ve argv'ın tüm işlemlerini devre dışı kılabilir.|
|nochkclr.obj|yok|Hiçbir şey yapılmaz. Projenizden kaldırın.|
|noenv.obj|pnoenv.obj|CRT için önbelleğe alınmış bir ortam oluşturulmasını devre dışı kılabilir.|
|nothrownew.obj|pnothrownew.obj|CRT'de yeninin fırlatılmayan sürümünü etkinleştirir. Yeni görün [ve Operatörler'i silin.](../cpp/new-and-delete-operators.md)|
|setargv.obj|psetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesağlar. Bkz. [Joker Karakter Bağımsız Değişkenlerini Genişletme](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Varsayılan olarak tüm yeni iş parçacıkları için iş parçacığı başına yerel izini sağlar.|
|wsetargv.obj|pwsetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesağlar. Bkz. [Joker Karakter Bağımsız Değişkenlerini Genişletme](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>Ayrıca bkz.

- [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
