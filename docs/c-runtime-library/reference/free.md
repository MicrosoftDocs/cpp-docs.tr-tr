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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: eefbe957ce5057b5038f98bc8da8fb2f0bdd3d1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345987"
---
# <a name="free"></a>serbest

Deallocates veya bir bellek bloğu boşaltıyor.

## <a name="syntax"></a>Sözdizimi

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Daha önce ayrılmış bellek bloğu serbest bırakılacak.

## <a name="remarks"></a>Açıklamalar

**Ücretsiz** fonksiyon deallocates bir bellek bloğu *(memblock*) daha önce **calloc**bir çağrı tarafından tahsis edildi , **malloc**, veya **realloc**. Serbest bırakılan bayt sayısı, blok tahsis edildiğinde istenen bayt sayısına eşittir (veya **realloc**durumunda yeniden tahsis edilir). *Memblock* **NULL**ise, işaretçi yoksayılır ve **ücretsiz** hemen döndürür. Geçersiz bir işaretçiyi **(calloc**, **malloc**veya **realloc**tarafından tahsis edilmemiş bir bellek bloğuna işaretçi) serbest etmeye çalışmak sonraki ayırma isteklerini etkileyebilir ve hatalara neden olabilir.

Belleğin serbest bırakılamasına ilişkin bir hata oluşursa, hatanın doğası hakkında işletim sisteminden gelen bilgilerle **errno** ayarlanır. Daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

Bir bellek bloğu serbest bırakıldıktan sonra, [_heapmin](heapmin.md) kullanılmayan bölgeleri biraraya getirerek ve işletim sistemine geri salarak yığındaki boş bellek miktarını en aza indirir. İşletim sistemine serbest bırakılmayan serbest bellek boşhavuza geri yüklenir ve yeniden tahsis edilebilmektedir.

Uygulama C çalışma zamanı kitaplıklarının hata ayıklama sürümüyle bağlantılı olduğunda, **_free_dbg serbest** çeşnigider. [_free_dbg](free-dbg.md) Hata ayıklama işlemi sırasında yığının nasıl yönetildiği hakkında daha fazla bilgi için [CRT Hata Ayıklama Yığını'na](/visualstudio/debugger/crt-debug-heap-details)bakın.

**serbest** olarak `__declspec(noalias)`işaretlenir, yani işlev in global değişkenleri değiştirmemesi garanti edilir. Daha fazla bilgi için [noalias'a](../../cpp/noalias.md)bakın.

[_malloca](malloca.md)ile ayrılan ücretsiz bellek [için, _freea](freea.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**Ücret -siz**|\<stdlib.h> \<ve malloc.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[Malloc](malloc.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
