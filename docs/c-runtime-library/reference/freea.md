---
title: _freea | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac01f965e159dae19bbbd748c1692058063a211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="freea"></a>_freea

Kaldırır veya bir bellek bloğu boşaltır.

## <a name="syntax"></a>Sözdizimi

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Boşaltılacak bellek bloğu önceden ayrılmış.

## <a name="return-value"></a>Dönüş Değeri

Yok.

## <a name="remarks"></a>Açıklamalar

**_Freea** işlevi bir bellek bloğu kaldırır (*memblock*) önceden ayrılmış bir çağrı tarafından [_malloca](malloca.md). **_freea** öbek veya yığın belleği ayrıldı durumunda olup olmadığını kontrol eder. Yığında ayırdığınızda **_freea** hiçbir şey yapmaz. Yığında ayrılmış olan, bloğu ayrıldı, istenen bayt sayısı boşaltılmış bayt sayısı eşdeğerdir. Varsa *memblock* olan **NULL**, işaretçi yok sayılır ve **_freea** hemen döndürür. Geçersiz bir işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğu için bir işaretçi **_malloca**) sonraki ayırma isteklerini etkiler ve hatalara neden olabilir.

**_freea** çağrıları **ücretsiz** dahili olarak bellek öbek üzerinde ayrılır bulursa. Bellek öbek üzerinde olduğu ya da yığın işaretleyicisi tarafından belirlenir bellek tahsis edilen bellek hemen önceki adresindeki yerleştirilir.

Bellek boşaltma içinde bir hata oluşursa, **errno** bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bir bellek bloğu serbest sonra [_heapmin](heapmin.md) kullanılmayan bölgeler birleştirmesi ve işletim sistemine geri serbest öbek boş bellek miktarı en aza indirir. İşletim sistemine serbest bırakılmış belleği serbest havuza geri ve yeniden ayırma için kullanılamıyor.

Çağrı **_freea** tüm çağrıları eşlik gerekir **_malloca**. Ayrıca çağırmak için bir hata olduğunu **_freea** aynı bellek üzerindeki iki kez. Ne zaman uygulamanın bağlı olduğu C çalışma zamanı kitaplıkları ile bir hata ayıklama sürümü özellikle [_malloc_dbg](malloc-dbg.md) tanımlayarak etkin Özellikler **_CRTDBG_MAP_ALLOC**, daha kolay eksik veya Çağrı yinelenen **_freea**. Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**_freea** işaretlenmiş `__declspec(noalias)`, işlev genel değişkenler değiştirmemeniz garanti anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**_freea**|\<stdlib.h > ve \<malloc.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_malloca](malloca.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
