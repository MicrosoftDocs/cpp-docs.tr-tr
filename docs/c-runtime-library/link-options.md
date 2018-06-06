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
ms.openlocfilehash: 98965b94c83b69e15c38319d7bc5a6e4151b323e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704892"
---
# <a name="link-options"></a>Bağlantı Seçenekleri

CRT lib dizin, herhangi bir kod değişikliği olmadan belirli CRT özellikleri etkinleştirmek küçük nesne dosyaları sayısını içerir. Bunları kullanmak için bağlayıcı komut satırı eklemek zorunda olduğundan bunlara "bağlantı seçenekleri" denir.

CLR saf mod sürümleri bu nesneler, Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor. Normal sürümleri yerel ve/CLR kodunu kullanın.

|Yerel ve/CLR|Saf modu|Açıklama|
|----------------------|---------------|-----------------|
|binmode.obj|pbinmode.obj|Varsayılan dosya çevirisi modu ikili biçimde ayarlar. Bkz: [_fmode](../c-runtime-library/fmode.md).|
|chkstk.obj|yok|Yığını denetleme ve alloca CRT kullanmadığınızda desteği sağlar.|
|commode.obj|pcommode.obj|Commit"için" genel tamamlama bayrağını ayarlar. Bkz: [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) ve [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md).|
|fp10.obj|yok|Varsayılan duyarlık denetimi 64 bit ile değiştirir. Bkz: [kayan nokta desteği](../c-runtime-library/floating-point-support.md).|
|invalidcontinue.obj|pinvalidcontinue.obj|Geçersiz parametreler CRT, işlevlere geçirilen anlamı hiçbir işlem yapmayan bir varsayılan geçersiz parametre işleyicisi yalnızca olacak kümeleri errno ayarlamak ve bir hata sonucu döndürür.|
|loosefpmath.obj|yok|Kayan nokta kodu göstereceği olduğunu sağlar değerleri normal dışı.|
|newmode.obj|pnewmode.obj|Neden [malloc](../c-runtime-library/reference/malloc.md) hatada yeni işleyicisi çağırmak için. Bkz: [_set_new_mode](../c-runtime-library/reference/set-new-mode.md), [_set_new_handler](../c-runtime-library/reference/set-new-handler.md), [calloc](../c-runtime-library/reference/calloc.md), ve [realloc](../c-runtime-library/reference/realloc.md).|
|noarg.obj|pnoarg.obj|Argc ve argv tüm işlemeyi devre dışı bırakır.|
|nochkclr.obj|yok|Hiçbir şey yapılmaz. Projenizden kaldırın.|
|noenv.obj|pnoenv.obj|CRT için önbelleğe alınmış bir ortam oluşturmayı devre dışı bırakır.|
|nothrownew.obj|pnothrownew.obj|Atma olmayan sürümünde yeni CRT sağlar. Bkz: [yeni ve delete işleçleri](../cpp/new-and-delete-operators.md).|
|setargv.obj|psetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesi sağlar. Bkz: [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|
|threadlocale.obj|pthreadlocale.obj|Etkinleştirir tüm yeni iş parçacığı yerel ayarı varsayılan olarak iş parçacığı başına.|
|wsetargv.obj|pwsetargv.obj|Komut satırı bağımsız değişkeni joker karakter genişletmesi sağlar. Bkz: [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md).|

## <a name="see-also"></a>Ayrıca bkz.

- [CRT Kitaplık Özellikleri](../c-runtime-library/crt-library-features.md)
