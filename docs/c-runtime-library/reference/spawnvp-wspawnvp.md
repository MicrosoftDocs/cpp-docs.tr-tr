---
description: 'Hakkında daha fazla bilgi edinin: _spawnvp _wspawnvp'
title: _spawnvp, _wspawnvp
ms.date: 4/2/2020
api_name:
- _wspawnvp
- _spawnvp
- _o__spawnvp
- _o__wspawnvp
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wspawnvp
- _spawnvp
- wspawnvp
helpviewer_keywords:
- wspawnvp function
- processes, creating
- _wspawnvp function
- processes, executing new
- spawnvp function
- process creation
- _spawnvp function
ms.assetid: 8d8774ec-6ad4-4680-a5aa-440cde1e0249
ms.openlocfilehash: c0cb9ea9808266772528751e6c10dfa22aee77c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282932"
---
# <a name="_spawnvp-_wspawnvp"></a>_spawnvp, _wspawnvp

Bir işlem oluşturur ve yürütür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
intptr_t _spawnvp(
   int mode,
   const char *cmdname,
   const char *const *argv
);
intptr_t _wspawnvp(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>Parametreler

*modundaysa*<br/>
İşlemi çağırmak için yürütme modu.

*cmdname*<br/>
Yürütülecek dosyanın yolu.

*argv*<br/>
Bağımsız değişkenlere işaretçiler dizisi. *Argv*[0] bağımsız değişkeni, genellikle gerçek moddaki bir yolun veya korunan moddaki program adının bir işaretçisidir *ve argv*[**n**] arasındaki *argv*[1], yeni bağımsız değişken listesini oluşturan karakter dizelerine yönelik işaretçilerdir. *Argv*[**n** + 1] bağımsız değişkeni, bağımsız değişken listesinin sonunu işaretlemek için bir **null** işaretçi olmalıdır.

## <a name="return-value"></a>Dönüş Değeri

Zaman uyumlu bir **_spawnvp** veya **_wspawnvp** ( *mod* için belirtilen **_P_WAIT** ) dönüş değeri, yeni işlemin çıkış durumudur. Zaman uyumsuz bir **_spawnvp** veya **_wspawnvp** (**_P_NOWAIT** veya *mod* için belirtilen **_P_NOWAITO** ) dönüş değeri işlem tanıtıcıdır. İşlem normal şekilde sonlandırılırsa çıkış durumu 0 ' dır. Oluşturulan işlem özellikle **Çıkış** yordamını çağırmak için sıfır dışında bir bağımsız değişken kullanıyorsa çıkış durumunu sıfır dışında bir değere ayarlayabilirsiniz. Yeni işlem açıkça pozitif bir çıkış durumu ayarlanmamışsa, bir pozitif çıkış durumu, bir iptal veya kesme ile olağan dışı bir çıkış olduğunu gösterir. -1 ' in dönüş değeri bir hatayı gösterir (yeni işlem başlatılmaz). Bu durumda, **errno** aşağıdaki değerlerden birine ayarlanır:

| Değer | Açıklama |
|-|-|
| **E2BIG** | Bağımsız değişken listesi 1024 baytı aşıyor. |
| **EıNVAL** | *Mode* bağımsız değişkeni geçersiz. |
| **ENOENT** | Dosya veya yol bulunamadı. |
| **ENOEXEC** | Belirtilen dosya yürütülebilir değil veya geçersiz yürütülebilir dosya biçimine sahip. |
| **ENOMEM** | Yeni işlemi yürütmek için yeterli kullanılabilir bellek yok. |

Bunlar ve diğer geri dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri yeni bir işlem oluşturur ve bunu yürütür ve komut satırı bağımsız değişkenlerine bir işaretçiler dizisi geçirir ve yürütülecek dosyayı bulmak için **Path** ortam değişkenini kullanır.

Bu işlevler, parametrelerini doğrular. *Cmdname* veya *argv* bir null işaretçisiyse ya da *argv* null işaretçisine işaret ediyorsa ya da *argv*[0] boş bir dize ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür. Yeni işlem oluşturulmadı.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_spawnvp**|\<stdio.h> veya \<process.h>|
|**_wspawnvp**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Spawn, _Wspawn işlevlerde](../../c-runtime-library/spawn-wspawn-functions.md)örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İşlem ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn, _wspawn Işlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[durdur](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec, _wexec Işlevleri](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
