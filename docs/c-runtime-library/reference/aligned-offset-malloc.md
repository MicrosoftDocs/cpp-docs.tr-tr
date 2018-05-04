---
title: _aligned_offset_malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bcc5fe0d786c7fdb04455f231cc3c8e60b53a22
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

Belirtilen hizalama sınırında bellek ayırır.

## <a name="syntax"></a>Sözdizimi

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametreler

*Boyutu*<br/>
İstenen bellek ayırma boyutu.

*Hizalama*<br/>
Hizalama değeri bir tamsayı güç 2 olmalıdır.

*uzaklık*<br/>
Hizalama zorlamak için bellek ayırma içine uzaklığı.

## <a name="return-value"></a>Dönüş Değeri

Ayrılmış olan bellek bloğu için bir işaretçi veya **NULL** işlemi başarısız olursa.

## <a name="remarks"></a>Açıklamalar

**_aligned_offset_malloc** hizalama iç içe geçmiş öğe üzerinde; gerek olduğu durumlarda faydalıdır hizalama iç içe bir sınıf üzerinde gerekirse örneğin.

**_aligned_offset_malloc** dayanır **malloc**; daha fazla bilgi için bkz: [malloc](malloc.md).

**_aligned_offset_malloc** işaretlenmiş `__declspec(noalias)` ve `__declspec(restrict)`, işlevi genel değişkenler değiştirmemeniz sağlanır ve işaretçiyi değil diğer döndürülen anlamına gelir. Daha fazla bilgi için bkz: [noalias](../../cpp/noalias.md) ve [kısıtlamak](../../cpp/restrict.md).

Bu işlev ayarlar **errno** için **ENOMEM** bellek ayırma başarısız olursa veya istenen boyutu büyük olursa **_HEAP_MAXREQ**. Hakkında daha fazla bilgi için **errno**, bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ayrıca, **_aligned_offset_malloc** parametrelerini doğrular. Varsa *hizalama* 2'in üssü değil veya *uzaklık* büyük veya eşit *boyutu* ve sıfır dışında bu işlev geçersiz parametre işleyicisi anlatıldığıgibiçağırır.[ Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür **NULL** ve ayarlar **errno** için **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h >|

## <a name="example"></a>Örnek

Daha fazla bilgi için bkz: [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Hizalama](../../c-runtime-library/data-alignment.md)<br/>
