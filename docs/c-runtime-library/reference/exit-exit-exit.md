---
title: exit, _Exit, _exit
ms.date: 4/2/2020
api_name:
- _exit
- exit
- _o__exit
- _o_exit
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
- Exit
- _exit
- process/exit
- process/_Exit
- stdlib/exit
- stdlib/_Exit
helpviewer_keywords:
- exit function
- _exit function
- processes, terminating
- function calls, terminating
- process termination, calling
ms.openlocfilehash: 5bdb5ff5c8309e03a49f9518f65a45d5757e9bfa
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347629"
---
# <a name="exit-_exit-_exit"></a>exit, _Exit, _exit

Arama işlemini sonlandırır. **Çıkış** işlevi temizlendikten sonra sonlandırır; **_exit** ve **_Exit** derhal sonlandırır.

> [!NOTE]
> Bu yöntemi, test veya hata ayıklama senaryoları dışında evrensel windows platformu (UWP) uygulamasını kapatmak için kullanmayın. Bir Mağaza uygulamasını kapatmanın programlı veya uI yollarına [Microsoft Mağazası ilkelerine](/legal/windows/agreements/store-policies)göre izin verilmez. Daha fazla bilgi için [UWP App yaşam döngüsüne](/windows/uwp/launch-resume/app-lifecycle)bakın. Windows 10 uygulamaları hakkında daha fazla bilgi için [Windows 10 uygulamaları için Nasıl Yap'ın kılavuzlarına](https://developer.microsoft.com/windows/apps)bakın.

## <a name="syntax"></a>Sözdizimi

```C
void exit(
   int const status
);
void _Exit(
   int const status
);
void _exit(
   int const status
);
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Çıkış durum kodu.

## <a name="remarks"></a>Açıklamalar

**Çıkış**, **_Exit** ve **_exit** işlevleri arama işlemini sonlandırır. **Çıkış** işlevi iş parçacığı yerel nesneler için destructors çağırır, sonra aramaları-son-in-ilk-out (LIFO) sırayla-atexit ve **_onexit**tarafından kayıtlı işlevleri , ve sonra işlem sona erdirilmeden önce tüm dosya arabellekleri temize. **atexit** **_Exit** ve **_exit** işlevleri iş parçacığı yerel nesneleri yok etmeden veya **çıkış** veya **_onexit** işlevlerini işlemeden ve akış arabelleklerini yıkamadan işlemi sonlandırır.

**Çıkış,** **_Exit** ve **_exit** çağrıları bir değer döndürmese de, *durum* daki değer, işlem çıktıktan sonra varsa, ana bilgisayar ortamına veya bekleme arama işlemine kullanılabilir hale getirilir. Genellikle, arayan normal bir çıkış belirtmek için *durum* değerini 0'a veya hata göstermek için başka bir değere ayarlar. *Durum* değeri işletim sistemi toplu **komutu ERRORLEVEL** için kullanılabilir ve iki sabitten biri tarafından temsil edilir: **EXIT_SUCCESS**, 0 veya **EXIT_FAILURE**değerini temsil eden , 1 değerini temsil eden.

**Çıkış**, **_Exit**, **_exit**, **quick_exit**, **_cexit**, ve **_c_exit** fonksiyonları aşağıdaki gibi çalışır.

|İşlev|Açıklama|
|--------------|-----------------|
|**Çıkış**|C kitaplığı sonlandırma yordamlarını tamamlar, işlemi sonlandırır ve sağlanan durum kodunu ana bilgisayar ortamına sağlar.|
|**_Exit**|En az C kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve sağlanan durum kodunu ana bilgisayar ortamına sağlar.|
|**_exit**|En az C kitaplığı sonlandırma yordamlarını gerçekleştirir, işlemi sonlandırır ve sağlanan durum kodunu ana bilgisayar ortamına sağlar.|
|**quick_exit**|Hızlı C kitaplığı sonlandırma yordamları gerçekleştirir, işlemi sonlandırır ve ana bilgisayar ortamına sağlanan durum kodunu sağlar.|
|**_cexit**|C kitaplığı sonlandırma yordamlarını tamamlar ve arayana geri döner. İşlemi sonlandırmaz.|
|**_c_exit**|En az C kitaplığı sonlandırma yordamlarını gerçekleştirir ve arayana geri döner. İşlemi sonlandırmaz.|

**Çıkışı,** **_Exit** veya **_exit** işlevini çağırdığınızda, çağrı sırasında var olan geçici veya otomatik nesnelerin yıkıcıları çağrılmaz. Otomatik nesne, bir işlevde tanımlanan statik olmayan yerel nesnedir. Geçici nesne, işlev çağrısı yla döndürülen bir değer gibi derleyici tarafından oluşturulan bir nesnedir. Otomatik bir nesneyi, _Exit **veya** **_exit** **çağırmadan**önce yok etmek için, burada gösterildiği gibi nesnenin yıkıcısını açıkça arayın:

```cpp
void last_fn() {}
    struct SomeClass {} myInstance{};
    // ...
    myInstance.~SomeClass(); // explicit destructor call
    exit(0);
}
```

**DllMain** **çıkış** aramak için **DLL_PROCESS_ATTACH** kullanmayın. **DLLMain** işlevinden çıkmak için **DLL_PROCESS_ATTACH** **FALSE** döndürün.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**çıkış**, **_Exit**, **_exit**|\<process.h> \<veya stdlib.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_exit.c
// This program returns an exit code of 1. The
// error code could be tested in a batch file.

#include <stdlib.h>

int main( void )
{
   exit( 1 );
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[Iptal](abort.md)<br/>
[atexit](atexit.md)<br/>
[_cexit, _c_exit](cexit-c-exit.md)<br/>
[_exec, _wexec Fonksiyonlar](../../c-runtime-library/exec-wexec-functions.md)<br/>
[_onexit, _onexit_m](onexit-onexit-m.md)<br/>
[quick_exit](quick-exit1.md)<br/>
[_spawn, _wspawn İşlevleri](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
