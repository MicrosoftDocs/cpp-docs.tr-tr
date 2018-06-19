---
title: _cexit, _c_exit | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _c_exit
- _cexit
apilocation:
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
apitype: DLLExport
f1_keywords:
- _cexit
- c_exit
- _c_exit
- cexit
dev_langs:
- C++
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b0840ccec85d46a13984b65ebe99e53b968bedeb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395828"
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

Temizleme işlemleri gerçekleştirir ve işlem sonlandırılıyor olmadan döndürür.

## <a name="syntax"></a>Sözdizimi

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Açıklamalar

**_Cexit** işlev çağrısı, son giren ilk çıkar (LIFO) sırası, tarafından kaydedilen işlevleri **atexit** ve **_onexit**. Ardından **_cexit** tüm g/ç arabelleklerini alır ve döndürmeden önce tüm açık akışları kapatır. **_c_exit** aynı **_exit** ancak arama işlemi işleme olmadan döndürür **atexit** veya **_onexit** veya akış arabellekleri temizleme. Davranışını **çıkmak**, **_exit**, **_cexit**, ve **_c_exit** aşağıdaki tabloda gösterilmiştir.

|İşlev|Davranış|
|--------------|--------------|
|**Çıkış**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_cexit**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döndürür, ancak işlemi sonlandırmamız değil.|
|**_c_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana verir, ancak işlemi sonlandırmamız değil.|

Çağırdığınızda **_cexit** veya **_c_exit** İşlevler, çağrı sırada mevcut geçici veya otomatik nesneleri için Yıkıcılar çağrılmaz. Bir otomatik bir işlevin tanımlı olduğu bir nesne nereye nesne statik olarak bildirilmedi nesnesidir. Geçici bir nesne derleyici tarafından oluşturulan nesnedir. Otomatik nesneyi çağırmadan önce yok etmek için **_cexit** veya **_c_exit**, açıkça yıkıcı nesne için şu şekilde çağırın:

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cexit**|\<Process.h >|
|**_c_exit**|\<Process.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
