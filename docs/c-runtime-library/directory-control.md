---
title: Dizin denetimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.programs
dev_langs:
- C++
helpviewer_keywords:
- controls [C++], directory
- directory control routines
ms.assetid: a72dcf6f-f366-4d20-8850-0e19cc53ca18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c0ab24a55cddc13b743a28a022475b0c0b84e77
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389734"
---
# <a name="directory-control"></a>Dizin Denetimi

Bu yordamlar erişim, değiştirmek ve dizin yapısı hakkında bilgi edinin.

## <a name="directory-control-routines"></a>Dizin denetim yordamları

|Yordam|Bir yönetim grubuna bağlanmak veya bağlı bir yönetim grubunun özelliklerini düzenlemek için Yönetim çalışma alanında|
|-------------|---------|
|[_chdir, _wchdir](../c-runtime-library/reference/chdir-wchdir.md)|Değişiklik geçerli çalışma dizini|
|[_chdrive](../c-runtime-library/reference/chdrive.md)|Geçerli sürücüyü değiştirin|
|[_getcwd, _wgetcwd](../c-runtime-library/reference/getcwd-wgetcwd.md)|Geçerli çalışma dizini için varsayılan sürücü Al|
|[_getdcwd, _wgetdcwd](../c-runtime-library/reference/getdcwd-wgetdcwd.md)|Geçerli çalışma dizini için belirtilen sürücüyü alın|
|[_getdiskfree](../c-runtime-library/reference/getdiskfree.md)|Dolduran bir **_diskfree_t** yapısı bir disk sürücüsü hakkında bilgi.|
|[_getdrive](../c-runtime-library/reference/getdrive.md)|Geçerli (varsayılan) sürücüyü alın|
|[_getdrives](../c-runtime-library/reference/getdrives.md)|Şu anda kullanılabilir disk sürücüleri temsil eden bir bit maskesi döndürür.|
|[_mkdir, _wmkdir](../c-runtime-library/reference/mkdir-wmkdir.md)|Yeni dizin oluşturun|
|[_rmdir, _wrmdir](../c-runtime-library/reference/rmdir-wrmdir.md)|Dizini kaldırın|
|[_searchenv, _wsearchenv](../c-runtime-library/reference/searchenv-wsearchenv.md), [_searchenv_s, _wsearchenv_s](../c-runtime-library/reference/searchenv-s-wsearchenv-s.md)|Belirtilen yollar dosyada verilen arayın|

## <a name="see-also"></a>Ayrıca Bkz.

[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [Dosya İşleme](../c-runtime-library/file-handling.md)<br/>
 [Sistem Çağrıları](../c-runtime-library/system-calls.md)<br/>
