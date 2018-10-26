---
title: Bağlantı seçenekleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- nothrownew.obj
- newmode.obj
- noenv.obj
- psetargv.obj
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91b97c653a5f035a767fbedcfcbfdfa7ca178327
ms.sourcegitcommit: 038f1406b1172318f8832371ad14176f788c44fa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50132159"
---
# <a name="link-options"></a>Bağlantı Seçenekleri

CRT kitaplığı dizini herhangi bir kod değişikliği olmadan belirli CRT özellikler sağlayan küçük nesne dosyaları içerir. Yalnızca bunları kullanmak için bağlayıcı komut satırına eklenecek olduğundan bunlar "bağlantı seçenekleri" olarak adlandırılır.

Bu nesnelerin CLR pure modunda sürümleri Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor. Normal sürümleri, yerel ve/CLR kodunu kullanın.

|Yerel ve/CLR|Pure modunda|Açıklama|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Varsayılan dosya çevirisi modu ikili biçimde ayarlar. Bkz: [_fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|yok|Yığın denetimi ve alloca CRT kullanılmadığında desteği sağlar.|
|commode.obj|pcommode.obj|"İşleme için" genel tamamlama bayrağını ayarlar. Bkz: [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) ve [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|exe_initialize_mta.lib|yok|COM nesneleri genel akıllı işaretçilerin kullanılmasına EXE başlatılırken MTA apartman başlatır. Bu seçenek bir MTA Grup başvurusu kapatılırken sızıntıları olduğundan DLL'leri için kullanmayın. Bu bağlama, combase.h dahil olmak üzere ve _EXE_INITIALIZE_MTA tanımlama eşdeğerdir. |
|fp10.obj|yok|Varsayılan duyarlık denetimi 64 bit ile değiştirir. Bkz: [kayan nokta desteği](../c-runtime-library/floating-point-support.md).|
|invalidcontinue.obj|pinvalidcontinue.obj|Geçersiz parametreler CRT işlevleri için geçirilen yani hiçbir şey yapmaz bir varsayılan geçersiz parametre işleyicisi yalnızca olacak kümeleri errno ayarlayın ve bir hata sonucu döndürür.|
|loosefpmath.obj|yok|Kayan nokta kodu göstereceği, sağlar denormal değerleri.|
|newmode.obj|pnewmode.obj|Neden [malloc](../c-runtime-library/reference/malloc.md) hatasında yeni işleyici çağırmak için. Bkz: [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md), ve [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|Argc argv ve tüm işlemleri devre dışı bırakır.|
|nochkclr.obj|yok|Hiçbir şey yapılmaz. Projenizden kaldırın.|
|noenv.obj|pnoenv.obj|Önbelleğe alınan bir ortam oluşturmak için CRT devre dışı bırakır.|
|nothrownew.obj|pnothrownew.obj|Oluşturmayan sürümünde yeni CRT sağlar. Bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).|
|setargv.obj|psetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesi sağlar. Bkz: [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Etkinleştirir tüm yeni iş parçacığı yerel ayarı varsayılan olarak iş parçacığı başına.|
|wsetargv.obj|pwsetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesi sağlar. Bkz: [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>Ayrıca bkz.

- [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
