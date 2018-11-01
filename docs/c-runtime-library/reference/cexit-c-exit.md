---
title: _cexit, _c_exit
ms.date: 11/04/2016
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
helpviewer_keywords:
- cleanup operations during processes
- cexit function
- _c_exit function
- _cexit function
- c_exit function
ms.assetid: f3072045-9924-4b1a-9fef-b0dcd6d12663
ms.openlocfilehash: a075e8a8e965a195765b86ffa21fed0915dbf5ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50495140"
---
# <a name="cexit-cexit"></a>_cexit, _c_exit

Temizleme işlemlerini gerçekleştiren ve işlemi sonlandırmaz döndürür.

## <a name="syntax"></a>Sözdizimi

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Açıklamalar

**_Cexit** işlev çağrısı, son giren ilk çıkar (LIFO) sırası, kaydeden işlevleri **atexit** ve **_onexit**. Ardından **_cexit** tüm g/ç arabelleklerini boşaltır ve döndürmeden önce tüm açık akışları kapatır. **_c_exit** aynı **_exit** ancak işlem çağırma işlemine geri gönderir **atexit** veya **_onexit** veya akış arabellekleri boşaltma. Davranışını **çıkmak**, **_exit**, **_cexit**, ve **_c_exit** aşağıdaki tabloda gösterilmiştir.

|İşlev|Davranış|
|--------------|--------------|
|**Çıkış**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve belirtilen durum koduyla çıkar.|
|**_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve belirtilen durum koduyla çıkar.|
|**_cexit**|Tam C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner, ancak işlemi sonlandırmak değil.|
|**_c_exit**|Hızlı C Kitaplığı sonlandırma yordamları gerçekleştirir ve çağırana döner, ancak işlemi sonlandırmak değil.|

Çağırdığınızda **_cexit** veya **_c_exit** İşlevler, çağrı sırada mevcut geçici veya otomatik nesneler için yok ediciler değil çağrılır. Otomatik bir nesne bir işlev içinde tanımlanan bir yere nesne statik olarak bildirilmedi nesnedir. Geçici bir nesne, derleyici tarafından oluşturulan bir nesnedir. Çağırmadan önce otomatik bir nesneyi yok etmek için **_cexit** veya **_c_exit**, açıkça call yok Edicisi nesne için şu şekilde:

```cpp
myObject.myClass::~myClass( );
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cexit**|\<Process.h >|
|**_c_exit**|\<Process.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec İşlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
