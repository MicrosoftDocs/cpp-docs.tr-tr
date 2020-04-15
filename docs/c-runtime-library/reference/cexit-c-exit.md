---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 9eb856efca054423465aa7d30092edaf83a65eeb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333528"
---
# <a name="_cexit-_c_exit"></a>_cexit, _c_exit

Temizleme işlemlerini gerçekleştirir ve işlemi sonlandırmadan döndürür.

## <a name="syntax"></a>Sözdizimi

```C
void _cexit( void );
void _c_exit( void );
```

## <a name="remarks"></a>Açıklamalar

**_cexit** işlevi, son giriş, ilk çıkış (LIFO) sırasına göre, **çıkış** ve **_onexit**tarafından kayıtlı işlevleri çağırır. Daha sonra **_cexit** tüm G/Ç arabelleklerini temizler ve dönmeden önce tüm açık akışları kapatır. **_c_exit** **_exit** ile aynıdır, ancak **çıkışta** veya **_onexit** veya akış arabelleklerini işlemeden arama işlemine geri döner. **Çıkış**davranışı , **_exit**, **_cexit**, ve **_c_exit** aşağıdaki tabloda gösterilir.

|İşlev|Davranış|
|--------------|--------------|
|**Çıkış**|C kitaplığı sonlandırma yordamlarını tamamlar, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_exit**|Hızlı C kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve sağlanan durum koduyla çıkar.|
|**_cexit**|C kitaplığı sonlandırma yordamlarını tamamlar ve arayana geri döner, ancak işlemi sonlandırmaz.|
|**_c_exit**|Hızlı C kitaplığı sonlandırma yordamları gerçekleştirir ve arayana döner, ancak işlemi sona erdirmez.|

**_cexit** veya **_c_exit** işlevlerini çağırdığınızda, çağrı sırasında var olan geçici veya otomatik nesnelerin yıkıcıları çağrılmaz. Otomatik nesne, nesnenin statik olarak bildirilmediğini bir işlevde tanımlanan bir nesnedir. Geçici nesne derleyici tarafından oluşturulan bir nesnedir. **_cexit** veya **_c_exit**çağırmadan önce otomatik bir nesneyi yok etmek için, nesnenin yıkıcısını aşağıdaki gibi açıkça çağırın:

```cpp
myObject.myClass::~myClass( );
```

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_cexit**|\<process.h>|
|**_c_exit**|\<process.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Iptal](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
