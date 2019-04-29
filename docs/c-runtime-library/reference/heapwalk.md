---
title: _heapwalk
ms.date: 11/04/2016
apiname:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
ms.openlocfilehash: cc2a49d9032746cc6c82c9dc401fc96baabbe2e1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331694"
---
# <a name="heapwalk"></a>_heapwalk

Yığında gezer ve sonraki giriş hakkında bilgi döndürür.

> [!IMPORTANT]
> Bu API, dışında Windows çalışma zamanı hata ayıklama yapılarında içinde yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Parametreler

*entryinfo*<br/>
Yığın bilgilerini içeren arabellek.

## <a name="return-value"></a>Dönüş Değeri

**_heapwalk** Malloc.h içinde tanımlı aşağıdaki tam sayı bildirim sabitlerinden birini döndürür.

|Dönüş değeri|Açıklama|
|-|-|
|**_HEAPBADBEGIN**| İlk üstbilgi bilgileri geçersiz veya bulunamadı.|
|**_HEAPBADNODE**| Yığın zarar görmüş veya bozuk düğümü bulunamadı.|
|**_HEAPBADPTR**| **_Pentry** alanını **_heapınfo** yapısı geçerli bir işaretçiyi yığına içermiyor veya *entryinfo* bir null işaretçidir.|
|**_HEAPEND**| Yığının sonuna başarıyla ulaşıldı.|
|**_HEAPEMPTY**| Yığın başlatılmadı.|
|**_HEAPOK**| Kadar hiç hata; *entryinfo* sonraki yığın giriş hakkındaki bilgilerle güncelleştirilir.|

Ayrıca, bir hata oluşursa **_heapwalk** ayarlar **errno** için **ENOSYS**.

## <a name="remarks"></a>Açıklamalar

**_Heapwalk** işlevi, programlardaki yığınla ilişkili sorunlarda hata ayıklama yardımcı olur. İşlev çağrı başına bir girişe geçiş yığın kılavuzluk ve bir türü yapısına bir işaretçi döndürür **_heapınfo** , sonraki yığın girişi hakkında bilgi içerir. **_Heapınfo** Malloc.h içinde tanımlı türü, aşağıdaki öğeleri içerir.

|Alan|Açıklama|
|-|-|
|`int *_pentry`|Yığın Giriş işaretçisi.|
|`size_t _size`|Yığın girişinin boyutu.|
|`int _useflag`|Yığın girdinin kullanımda olup olmadığını gösteren bayrak.|

Bir çağrı **_heapwalk** döndüren **_HEAPOK** girişin boyutunu depolayan **_boyut** alan ve kümelerini **_useflag** ya da alanı **_FREEENTRY** veya **_USEDENTRY** (her ikisi de Malloc.h içinde tanımlanan sabit değerlerdir). Yığındaki ilk girişle ilgili bu bilgileri almak için geçirin **_heapwalk** bir işaretçi bir **_heapınfo** yapısına **_pentry** üyesidir **NULL** . İşletim sistemi desteklemiyorsa **_heapwalk**(örneğin, Windows 98), işlev döndürür **_HEAPEND** ve ayarlar **errno** için **ENOSYS**.

Bu işlev, parametresini doğrular. Varsa *entryinfo* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev döndürür **_HEAPBADPTR**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_heapwalk.c

// This program "walks" the heap, starting
// at the beginning (_pentry = NULL). It prints out each
// heap entry's use, location, and size. It also prints
// out information about the overall state of the heap as
// soon as _heapwalk returns a value other than _HEAPOK
// or if the loop has iterated 100 times.

#include <stdio.h>
#include <malloc.h>

void heapdump(void);

int main(void)
{
    char *buffer;

    heapdump();
    if((buffer = (char *)malloc(59)) != NULL)
    {
        heapdump();
        free(buffer);
    }
    heapdump();
}

void heapdump(void)
{
    _HEAPINFO hinfo;
    int heapstatus;
    int numLoops;
    hinfo._pentry = NULL;
    numLoops = 0;
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&
          numLoops < 100)
    {
        printf("%8s block at %Fp of size %4.4X\n",
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),
               hinfo._pentry, hinfo._size);
        numLoops++;
    }

    switch(heapstatus)
    {
    case _HEAPEMPTY:
        printf("OK - empty heap\n");
        break;
    case _HEAPEND:
        printf("OK - end of heap\n");
        break;
    case _HEAPBADPTR:
        printf("ERROR - bad pointer to heap\n");
        break;
    case _HEAPBADBEGIN:
        printf("ERROR - bad start of heap\n");
        break;
    case _HEAPBADNODE:
        printf("ERROR - bad node in heap\n");
        break;
    }
}
```

```Output
    USED block at 00310650 of size 0100
    USED block at 00310758 of size 0800
    USED block at 00310F60 of size 0080
    FREE block at 00310FF0 of size 0398
    USED block at 00311390 of size 000D
    USED block at 003113A8 of size 00B4
    USED block at 00311468 of size 0034
    USED block at 003114A8 of size 0039
...
    USED block at 00312228 of size 0010
    USED block at 00312240 of size 1000
    FREE block at 00313250 of size 1DB0
OK - end of heap
```

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_heapadd](../../c-runtime-library/heapadd.md)<br/>
[_heapchk](heapchk.md)<br/>
[_heapmin](heapmin.md)<br/>
[_heapset](../../c-runtime-library/heapset.md)<br/>
