---
title: _aligned_offset_realloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 892fa0a3de0294437f74c6dc20c0910aa5e3fe60
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393582"
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc

İle ayrılmış bir bellek bloğu boyutu değişir [_aligned_malloc](aligned-malloc.md) veya [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*memblock*<br/>
Geçerli bellek bloğu işaretçisi.

*Boyutu*<br/>
Bellek ayırma boyutu.

*Hizalama*<br/>
Hizalama değeri bir tamsayı güç 2 olmalıdır.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma içine uzaklığı.

## <a name="return-value"></a>Dönüş Değeri

**_aligned_offset_realloc** bırakılan (ve muhtemelen taşınan) bellek bloğuna void işaretçi döndürür. Dönüş değeri **NULL** boyutu sıfır ise ve arabellek bağımsız değişken değil **NULL**, veya blok verilen boyuta genişletmek için yeterli kullanılabilir bellek değilse. İlk durumda, özgün blok serbest bırakılır. İkinci durumda, özgün blok değiştirilmez. Dönüş değeri, nesnenin herhangi bir türde bir depolama için uygun hizalanacak garanti bir depolama alanı işaret eder. Dönüş değerini cast türü void, kullanım dışında bir tür için bir işaretçi almak için.

**_aligned_offset_realloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevi genel değişkenler değiştirmemeniz sağlanır ve işaretçiyi değil diğer döndürülen anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).

## <a name="remarks"></a>Açıklamalar

Gibi [_aligned_offset_malloc](aligned-offset-malloc.md), **_aligned_offset_realloc** yapısı içinde bir uzaklığındaki hizalanacak yapısı sağlar.

**_aligned_offset_realloc** dayanır **malloc**. Kullanma hakkında daha fazla bilgi için **_aligned_offset_malloc**, bkz: [malloc](malloc.md). Varsa *memblock* olan **NULL**, işlev çağrıları **_aligned_offset_malloc** dahili olarak.

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyük olursa **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_realloc** parametrelerini doğrular. Varsa *hizalama* 2'in üssü değil veya *uzaklık* büyük veya eşit *boyutu* ve sıfır dışında bu işlev geçersiz parametre işleyicisi anlatıldığıgibiçağırır.[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz: [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
