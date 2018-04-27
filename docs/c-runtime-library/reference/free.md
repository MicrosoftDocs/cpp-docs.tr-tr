---
title: Ücretsiz | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecb214f5b7f53682fe1f1327089836a172319015
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="free"></a>serbest

Kaldırır veya bir bellek bloğu boşaltır.

## <a name="syntax"></a>Sözdizimi

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>Parametreler

*memblock* boşaltılacak bellek bloğu önceden ayrılmış.

## <a name="remarks"></a>Açıklamalar

**Ücretsiz** işlevi bir bellek bloğu kaldırır (*memblock*) önceden ayrılmış bir çağrı tarafından **calloc**, **malloc**, veya **realloc**. Boşaltılmış bayt sayısı bloğu ayrıldı, istenen bayt sayısı eşdeğerdir (veya yeniden tahsis edilmesini durumunda **realloc**). Varsa *memblock* olan **NULL**, işaretçi yok sayılır ve **ücretsiz** hemen döndürür. Geçersiz bir işaretçi serbest bırakma girişimi (tarafından ayrılmamış bir bellek bloğu için bir işaretçi **calloc**, **malloc**, veya **realloc**) sonraki ayırma isteklerini etkileyebilir ve hatalara neden olabilir.

Bellek boşaltma içinde bir hata oluşursa, **errno** bilgilerle hata işletim sisteminden yapısı üzerinde ayarlanır. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Bir bellek bloğu serbest sonra [_heapmin](heapmin.md) kullanılmayan bölgeler birleştirmesi ve işletim sistemine geri serbest öbek boş bellek miktarı en aza indirir. İşletim sistemine serbest bırakılmış belleği serbest havuza geri ve yeniden ayırma için kullanılamıyor.

Uygulama hata ayıklama sürümü C çalışma zamanı kitaplıkları ile bağlandığında **ücretsiz** çözümler [_free_dbg](free-dbg.md). Öbek hata ayıklama işlemi sırasında nasıl yönetilir hakkında daha fazla bilgi için bkz: [CRT hata ayıklama yığını](/visualstudio/debugger/crt-debug-heap-details).

**Ücretsiz** işaretlenmiş `__declspec(noalias)`, işlev genel değişkenler değiştirmemeniz garanti anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md).

İle ayrılan belleği boşaltmak için [_malloca](malloca.md), kullanın [_freea](freea.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**free**|\<stdlib.h > ve \<malloc.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [malloc](malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
