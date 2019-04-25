---
title: serbest
ms.date: 11/04/2016
apiname:
- free
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
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: f56212874f05ea5d4ab7bd826a7a4c145551dfc0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287765"
---
# <a name="free"></a>serbest

Kaldırır veya bir bellek bloğunu serbest bırakır.

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

**Ücretsiz** işlevi bir bellek bloğunu kaldırır (*memblock*) önceden ayrılmış bir çağrı tarafından **calloc**, **malloc**, veya **realloc**. Serbest bırakılan bayt sayısı bloğu ayrıldı, istenen bayt sayısını eşdeğerdir (veya yeniden tahsis, durumunda **realloc**). Varsa *memblock* olduğu **NULL**, işaretçi yok sayılır ve **ücretsiz** hemen döndürür. Geçersiz işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğuna işaretçi **calloc**, **malloc**, veya **realloc**) sonraki ayırma isteklerini etkileyebilir ve hataya neden olur.

Bellek serbest bırakma hata oluşması durumunda **errno** bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bir bellek bloğunu serbest sonra [_heapmin](heapmin.md) kullanılmayan bölgeleri birleşim ve işletim sistemine bırakmadan yığın boş bellek miktarı en aza indirir. İşletim sistemi tarafından serbest bırakılmış bellek serbest havuza geri ve yeniden ayırma için kullanılabilir.

Uygulamayı hata ayıklama sürümü C çalışma zamanı kitaplıkları ile ilişkilendirildiğinde **ücretsiz** çözümler [_free_dbg](free-dbg.md). Yığının hata ayıklama işlemi sırasında nasıl yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığın](/visualstudio/debugger/crt-debug-heap-details).

**Ücretsiz** işaretlenmiş `__declspec(noalias)`, işlevin genel değişkenleri garanti anlamına gelir. Daha fazla bilgi için [noalias](../../cpp/noalias.md).

İle ayrılan belleği boşaltmak için [_malloca](malloca.md), kullanın [_freea](freea.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**free**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [malloc](malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
