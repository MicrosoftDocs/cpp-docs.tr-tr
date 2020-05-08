---
title: serbest
ms.date: 4/2/2020
api_name:
- free
- _o_free
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: 0e0a53dd9d24634442c8dd456e4f9d38f742e292
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920419"
---
# <a name="free"></a>serbest

Bellek bloğunu ayırır veya serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Serbest bırakmak için önceden ayrılmış bellek bloğu.

## <a name="remarks"></a>Açıklamalar

**Free** işlevi, daha önce **calloc**, **malloc**veya **realloc**çağrısıyla ayrılmış bir bellek bloğunu (*memblock*) ayırır. Serbest bırakılan bayt sayısı, blok ayrıldığında (veya yeniden atandığında, **realloc**durumunda) istenen bayt sayısına eşittir. *Memblock* **null**ise, işaretçi yok sayılır ve **serbest** hemen döndürülür. Geçersiz bir işaretçi serbest bırakma girişimi ( **calloc**, **malloc**veya **realloc**tarafından ayrılmamış bir bellek bloğunun işaretçisi) sonraki ayırma isteklerini etkileyebilir ve hatalara neden olabilir.

Belleği boşaltmaya yönelik bir hata oluşursa, **errno** , işletim sisteminden hata doğasından bilgi olarak ayarlanır. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bellek bloğu serbest bırakıldıktan sonra, [_heapmin](heapmin.md) kullanılmayan bölgeleri birleştirerek ve bunları işletim sistemine yeniden bırakarak yığındaki boş bellek miktarını en aza indirir. İşletim sisteminde yayımlanmayan serbest bırakılan bellek, ücretsiz havuza geri yüklenir ve yeniden tahsis için kullanılabilir.

Uygulama, C çalışma zamanı kitaplıklarının bir hata ayıklama sürümü ile bağlantılı olduğunda, **ücretsiz** olarak [_free_dbg](free-dbg.md)çözümlenmektedir. Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**Free** işaretlenir `__declspec(noalias)`, yani işlevin genel değişkenleri değiştirmeyeceği garanti edilir. Daha fazla bilgi için bkz. [noalias](../../cpp/noalias.md).

[_Malloca](malloca.md)ile ayrılmış belleği boşaltmak için [_freea](freea.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Süz**|\<Stdlib. h> ve \<malloc. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Malloc](malloc.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
