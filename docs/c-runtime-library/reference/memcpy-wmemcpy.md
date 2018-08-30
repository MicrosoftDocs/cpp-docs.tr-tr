---
title: memcpy, wmemcpy | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f75aa6a32277fda0796fe2433062f5062fdd47eb
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43196085"
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

Arabellekler arasında bayt kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md).

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
Arabellek kopyalayın.

*Sayısı*<br/>
Kopyalanacak karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Değerini *dest*.

## <a name="remarks"></a>Açıklamalar

**memcpy** kopyaları *sayısı* bayt *src* için *dest*; **wmemcpy** kopyaları *sayısı* geniş karakterler (iki bayt). Kaynak ve hedef örtüştürürse davranışını **memcpy** tanımsızdır. Kullanım **memmove** çakışan bölgeleri işlemek için.

> [!IMPORTANT]
> Boyutta veya daha büyük kaynak arabelleği hedef arabellek aynı olduğundan emin olun. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Çok fazla arabellek taşmalarını ve böylece olası güvenlik açıklarını yanlış kullanımı için izlenen olduğundan **memcpy**, bu işlev "yasaklı" işlevleri arasında Security Development Lifecycle (SDL) olarak listelenir.  Bazı VC ++ kitaplığı sınıflarını kullanmak devam ettiğini gözlemleyin **memcpy**.  Ayrıca, VC ++ derleyici iyileştiricisi bazen çağrıları yayan gözlemleyin **memcpy**.  Visual C++ ürün SDL işlemine uygun olarak geliştirilir ve bu nedenle bu yasaklı işlevi kullanımını yakından değerlendirildi.  Kitaplık söz konusu olduğunda çağrıları dikkatle arabellek taşmalarına bu çağrılar izin verilmiyor emin olmak için scrutinized, bunu kullanın.  Derleyicinin söz konusu olduğunda, bazen belirli kod desenleri desenini aynı tanınır **memcpy**ve bu nedenle işlevine bir çağrı ile değiştirilir.  Böyle durumlarda, kullanımını **memcpy** özgün değerinden daha fazla güvenli değil yönergeleri olabilirdi; bunlar yalnızca performans olarak ayarlanmış bir çağrı için iyileştirilmiş **memcpy** işlevi.  "Güvenli" CRT işlevlerinin kullanımını (bunlar olmanız yeterlidir, daha güvenli olmasını), güvenlik garanti etmez gibi "yasaklı" işlevlerin kullanımını (yalnızca duydukları güvenliği sağlamak için büyük scrutiny) tehlike garanti etmez.
>
> Çünkü **memcpy** VC ++ derleyicisini ve kütüphanelerini kullanımını bu nedenle dikkatli bir şekilde scrutinized, aksi takdirde SDL ile uyumlu kod içinde bu çağrıları izin verilir.  **memcpy** çağrıları uygulamanın kaynak kodunda sunulan bazı yalnızca SDL ile uyumlu kullanan güvenlik uzmanları tarafından gözden geçirilir.

**Memcpy** ve **wmemcpy** işlevleri yalnızca kullanımdan kaldırılacaktır varsa sabiti **_CRT_SECURE_DEPRECATE_MEMORY** ekleme deyimi için sırayla önce tanımlanır kullanım dışı, aşağıdaki örnekte olduğu gibi olmasını İşlevler:

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

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bkz: [memmove](memmove-wmemmove.md) nasıl kullanılacağını gösteren bir örnek **memcpy**.

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
