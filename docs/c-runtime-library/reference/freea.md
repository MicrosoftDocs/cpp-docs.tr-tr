---
title: _freea
ms.date: 11/04/2016
apiname:
- _freea
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
apitype: DLLExport
f1_keywords:
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: ac9c5528755898b0de131bccf94185b501b0e720
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605900"
---
# <a name="freea"></a>_freea

Kaldırır veya bir bellek bloğunu serbest bırakır.

## <a name="syntax"></a>Sözdizimi

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Daha önce ayrılmış bellek bloğu serbest bırakılacak.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Freea** işlevi bir bellek bloğunu kaldırır (*memblock*) önceden ayrılmış bir çağrı tarafından [_malloca](malloca.md). **_freea** bellek yığın veya yığın üzerinde ayrılan durumunda olup olmadığını kontrol eder. Stack ayırdığınızda **_freea** hiçbir şey yapmaz. Yığında ayrılmış olan, serbest bırakılan bayt sayısı bloğu ayrıldı, istenen bayt sayısını eşdeğerdir. Varsa *memblock* olduğu **NULL**, işaretçi yok sayılır ve **_freea** hemen döndürür. Geçersiz işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğuna işaretçi **_malloca**) sonraki ayırma isteklerini etkiler ve hatalara neden olabilir.

**_freea** çağrıları **ücretsiz** dahili olarak bellek yığında ayrılır bulursa. Yığında bellek olduğu ya da yığının bir işaretçi tarafından belirlenir bellek tahsis edilen bellek hemen önceki adresindeki yerleştirilir.

Bellek serbest bırakma hata oluşması durumunda **errno** bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bir bellek bloğunu serbest sonra [_heapmin](heapmin.md) kullanılmayan bölgeleri birleşim ve işletim sistemine bırakmadan yığın boş bellek miktarı en aza indirir. İşletim sistemi tarafından serbest bırakılmış bellek serbest havuza geri ve yeniden ayırma için kullanılabilir.

Bir çağrı **_freea** tüm çağrıları eşlik gerekir **_malloca**. Ayrıca çağırmak için bir hata olduğunu **_freea** iki kez aynı bellek üzerinde. Ne zaman uygulama bağlı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile özellikle [_malloc_dbg](malloc-dbg.md) tanımlayarak özellikleriyle **_CRTDBG_MAP_ALLOC**, daha kolay eksik veya Çağrı yinelenen **_freea**. Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

**_freea** işaretlenmiş `__declspec(noalias)`, işlevin genel değişkenleri garanti anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_freea**|\<stdlib.h > ve \<malloc.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_malloca](malloca.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
