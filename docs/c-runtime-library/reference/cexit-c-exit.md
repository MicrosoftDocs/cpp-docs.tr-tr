---
description: 'Hakkında daha fazla bilgi edinin: _cexit _c_exit'
title: _cexit, _c_exit
ms.date: 4/2/2020
api_name:
- _c_exit
- _cexit
- _o__cexit
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: e901e7d7e37c8702efaae8b3b70e98a400f48ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275106"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Temizleme işlemlerini gerçekleştirir ve işlemi sonlandırmadan döndürür.

## <a name="syntax"></a>Syntax

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Açıklamalar

**_Cexit** işlevi, en son, ilk çıkar (LIFO) sırasına, **atexit** ve **_onexit** tarafından kaydedilen işlevleri çağırır. Sonra tüm g/ç arabelleklerini **_cexit** boşaltır ve döndürmeden önce tüm açık akışları kapatır. **_c_exit** **_exit** aynıdır, ancak **atexit** veya **_onexit** işlemeden ya da akış arabelleğini temizlemeden çağıran işleme geri döner. **Çıkış**, **_exit**, **_cexit** ve **_c_exit** davranışı aşağıdaki tabloda gösterilmiştir.

|İşlev|Davranış|
|--------------|--------------|
|**çıkıp**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_exit**|Hızlı C Kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_cexit**|Tüm C Kitaplığı sonlandırma yordamlarını gerçekleştirir ve çağırana döner, ancak işlemi sonlandırmaz.|
|**_c_exit**|Hızlı C Kitaplığı sonlandırma yordamlarını gerçekleştirir ve çağırana döner, ancak işlemi sonlandırmaz.|

**_Cexit** veya **_c_exit** işlevlerini çağırdığınızda, çağrı sırasında mevcut olan geçici veya otomatik nesnelerin yıkıcıları çağrılmaz. Otomatik nesne, nesnenin statik olduğu bildirilmemiş bir işlevde tanımlanmış bir nesnedir. Geçici bir nesne, derleyici tarafından oluşturulan bir nesnedir. **_Cexit** veya **_c_exit** çağrılmadan önce otomatik bir nesneyi yok etmek için, açıkça nesne için yıkıcıyı aşağıdaki gibi çağırın:

```cpp
myObject.myClass::~myClass( );
```

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[durdur](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
