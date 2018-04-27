---
title: memcpy, wmemcpy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- memcpy
- wmemcpy
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
- wmemcpy
- memcpy
dev_langs:
- C++
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a31ada40bfab599b6da41da268bf79792f8ebf20
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

Arabellekler arasında kopyaları bayt sayısı. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md).

## <a name="syntax"></a>Sözdizimi

```C
void *memcpy(
   void *dest,
   const void *src,
   size_t count
);
wchar_t *wmemcpy(
   wchar_t *dest,
   const wchar_t *src,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Yeni bir arabellek.

*src*<br/>
Kopyalanacak arabelleği.

*Sayısı*<br/>
Kopyalamak için karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Değeri *taşınmaya*.

## <a name="remarks"></a>Açıklamalar

**memcpy** kopya *sayısı* baytlar *src* için *taşınmaya*; **wmemcpy** kopya *sayısı* geniş karakterler (iki bayt cinsinden). Kaynak ve hedef çakışma varsa, davranışını **memcpy** tanımlanmadı. Kullanım **memmove** çakışan bölgeler işlemek için.

> [!IMPORTANT]
> Kaynak arabelleği daha büyük veya boyut hedef arabelleği aynı olduğundan emin olun. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

> [!IMPORTANT]
> Çok fazla sayıda arabellek taşmaları ve böylece olası güvenlik açıkları, yanlış kullanımı için izlenen olduğundan **memcpy**, bu işlev "Engellenenler" işlevleri arasında güvenlik geliştirme yaşam döngüsü (SDL) tarafından listelenir.  Bazı VC ++ kitaplığı sınıfları kullanmaya devam gözlemleyebilirsiniz **memcpy**.  Ayrıca, VC ++ derleyici iyileştirici bazen için çağrı yayar gözlemleyebilirsiniz **memcpy**.  Visual C++ ürün SDL işlem uygun olarak geliştirilen ve böylece bu Engellenenler işlevi kullanımını yakından değerlendirildikten.  Kitaplık durumunda çağrıları dikkatle arabellek taşmaları bu çağrılar izin verilmiyor emin olmak için scrutinized, bunu kullanın.  Derleyicinin söz konusu olduğunda, bazen belirli kod düzenleri desenini için aynı tanınır **memcpy**ve bu nedenle işlevi çağrısı ile değiştirilir.  Böyle durumlarda, kullanımını **memcpy** özgün daha fazla güvenli değildir yönergeleri olabilirdi; bunlar yalnızca performans olarak ayarlanmış bir çağrı için iyileştirilmiş **memcpy** işlevi.  "Safe" CRT işlevleri kullanımını (bunlar yalnızca yapın, güvenilmez olarak daha zor) güvenliği garanti etmez gibi "Engellenenler" işlevleri kullanımını (yalnızca ihtiyaç güvenliği sağlamak için büyük scrutiny) tehlike garanti etmez.
>
> Çünkü **memcpy** VC ++ derleyici ve kitaplıkları kullanımı bu nedenle dikkatli bir şekilde scrutinized, aksi takdirde SDL ile uyumlu olan kod içinde bu Çağrılara izin verilir.  **memcpy** uygulamanın kaynak kodunda sunulan çağrıları yalnızca SDL ile uyumlu kullanan güvenlik uzmanları tarafından gözden olduğunda.

**Memcpy** ve **wmemcpy** işlevleri yalnızca kullanım dışı varsa sabiti **_CRT_SECURE_DEPRECATE_MEMORY** sırada ekleme deyimi önce tanımlanan kullanım dışı, aşağıdaki örnekteki gibi olacak şekilde işlevleri:

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <memory.h>
```

veya

```C
#define _CRT_SECURE_DEPRECATE_MEMORY
#include <wchar.h>
```

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**memcpy**|\<Memory.h > veya \<string.h >|
|**wmemcpy**|\<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: [memmove](memmove-wmemmove.md) nasıl kullanılacağına ilişkin bir örnek için **memcpy**.

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
