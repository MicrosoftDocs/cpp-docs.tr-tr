---
title: _heapwalk
ms.date: 11/04/2016
api_name:
- _heapwalk
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
- api-ms-win-crt-heap-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- heapwalk
- _heapwalk
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
ms.openlocfilehash: 8dc7ee9335f227bde93a414748ff70b165c44f8d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70954770"
---
# <a name="_heapwalk"></a>_heapwalk

Yığın ile geçer ve sonraki giriş hakkında bilgi döndürür.

> [!IMPORTANT]
> Bu API, hata ayıklama derlemeleri hariç Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _heapwalk( _HEAPINFO *entryinfo );
```

### <a name="parameters"></a>Parametreler

*entryınfo*<br/>
Yığın bilgileri içeren arabellek.

## <a name="return-value"></a>Dönüş Değeri

**_heapizlenecek yol** , malloc. h içinde tanımlanan aşağıdaki tamsayı bildirim sabitlerinden birini döndürür.

|Dönüş değeri|Açıklama|
|-|-|
|**_HEAPBADBEGIN**| İlk üstbilgi bilgisi geçersiz veya bulunamadı.|
|**_HEAPBADNODE**| Yığın hasarlı veya hatalı düğüm bulundu.|
|**_HEAPBADPTR**| **_Heapınfo** yapısının **_pentry** alanı yığında geçerli bir işaretçi içermiyor veya *entryınfo* null bir işaretçisidir.|
|**_HEAPEND**| Yığının sonuna başarıyla erişildi.|
|**_HEAPEMPTY**| Yığın başlatılmadı.|
|**_CENPOK**| Şu ana kadar hata yok; *entryınfo* , sonraki yığın girişi hakkında bilgilerle güncelleştirilir.|

Ayrıca, bir hata oluşursa, **_heapizlenecek yol** , **errsys** olarak ayarlar.

## <a name="remarks"></a>Açıklamalar

**_Heapyürüme** işlevi programlarda yığın ile ilgili sorunların hatalarını ayıklamasına yardımcı olur. İşlevi yığın boyunca ilerler, her çağrı için bir girişe geçiş yapın ve bir sonraki yığın girişi hakkında bilgi içeren **_Heapınfo** türünde bir yapıya bir işaretçi döndürür. Malloc. h içinde tanımlanan **_Heapınfo** türü aşağıdaki öğeleri içerir.

|Alan|Açıklama|
|-|-|
|`int *_pentry`|Yığın giriş işaretçisi.|
|`size_t _size`|Yığın girişinin boyutu.|
|`int _useflag`|Yığın girişinin kullanımda olup olmadığını belirten bayrak.|

**_Cenpok** döndüren **_heapizlenecek** bir çağrı, girişin boyutunu **_Size** alanına depolar ve **_useflag** alanını **_FREEENTRY** ya da **_USEDENTRY** (her ikisi de malloc. h içinde tanımlanan sabitler) olarak ayarlar. Yığındaki ilk giriş hakkında bu bilgileri almak için, **_pentry** üyesi **null**olan **_HEAPINFO** yapısına bir **işaretçi geçirin.** İşletim sistemi **_heapizlenecek yol**(örneğin, Windows 98) desteklemiyorsa, Işlev **_HEAPEND** döndürür ve **errno** , **ENOSYS**olarak ayarlar.

Bu işlev, parametresini doğrular. *Entryınfo* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve Işlev **_HEAPBADPTR**döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_heapwalk**|\<malloc. h >|\<errno. h >|

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
