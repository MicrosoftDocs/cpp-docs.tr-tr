---
description: 'Daha fazla bilgi edinin: memckopyala, wmemcpy'
title: memcpy, wmemcpy
ms.date: 1/14/2021
api_name:
- memcpy
- wmemcpy
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: 49b08877f63bf0d331dcc40e2885b375fe6d1ee7
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/15/2021
ms.locfileid: "98243144"
---
# <a name="memcpy-wmemcpy"></a>`memcpy`, `wmemcpy`

Baytları, arabellekler arasında kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [ `memcpy_s` , `wmemcpy_s` ](memcpy-s-wmemcpy-s.md).

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

*`dest`*\
Yeni arabellek.

*`src`*\
Kopyalanacak arabellek.

*`count`*\
Kopyalanacak karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

Değeri *`dest`* .

## <a name="remarks"></a>Açıklamalar

**`memcpy`** ' *`count`* dan ' a bayt kopyalar *`src`* *`dest`* ; **`wmemcpy`** *`count`* geniş karakterleri kopyalar (iki bayt). Kaynak ve hedef çakışırsa, davranışı **`memcpy`** tanımlı değildir. **`memmove`** Çakışan bölgeleri işlemek için kullanın.

> [!IMPORTANT]
> Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Bu nedenle, çok sayıda arabellek taşması ve bu nedenle olası güvenlik açıklarını kötüye kullanma gibi **`memcpy`** izlendiğinde, bu Işlev güvenlik geliştirme yaşam döngüsü (SDL) tarafından "yasaklanmış" işlevler arasında listelenir.  Bazı VC + + kitaplık sınıflarının kullanmaya devam etmesi gözlemleyebilirsiniz **`memcpy`** .  Ayrıca, VC + + derleyici iyileştiricinin bazen ' ye çağrılar yaydığı gözlemleyebilirsiniz **`memcpy`** .  Visual C++ ürün, SDL işlemine uygun olarak geliştirilmiştir ve bu nedenle bu yasaklanmış işlevin kullanımı yakından değerlendirilir.  Kitaplık kullanımı durumunda, bu çağrılar aracılığıyla arabellek taşmalarına izin verilmeyeceğini sağlamak için çağrılar dikkatle scrutinized.  Derleyici söz konusu olduğunda bazen bazı kod desenleri, deseniyle özdeş olarak tanınır **`memcpy`** ve bu nedenle, işlev çağrısıyla değiştirilmiştir.  Bu gibi durumlarda, öğesinin kullanımı **`memcpy`** özgün yönergelerden daha güvenli değildir; yalnızca performans kümesi işlevine yapılan bir çağrıya en iyi duruma getirilmiştir **`memcpy`** .  "Güvenli" CRT işlevlerinin kullanılması güvenliği garanti etmez (yalnızca güvenli olmaması önerilir), "yasaklanmış" işlevlerinin kullanılması olma tehlikesi 'yi garanti etmez (yalnızca güvenliği sağlamak için daha fazla scrlanlı olması gerekir).
>
> **`memcpy`** VC + + derleyicisinin ve kitaplıklarının kullanımı dikkatle scrutinized olduğundan, bu çağrılara başka bir şekılde SDL ile uyumlu olan kodlar dahilinde izin verilir.  **`memcpy`** uygulama kaynak kodunda tanıtılan çağrılar yalnızca, bu kullanım güvenlik uzmanları tarafından incelenerek SDL ile uyumludur.

**`memcpy`** Ve **`wmemcpy`** işlevleri, **`_CRT_SECURE_DEPRECATE_MEMORY`** Aşağıdaki örnekte olduğu gibi işlevlerin kullanım dışı olması için dahil etme ifadesiyle önce belirtilmemişse kullanım dışı kalır:

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
|**`memcpy`**|`<memory.h>` veya `<string.h>`|
|**`wmemcpy`**|`<wchar.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[`memmove`](memmove-wmemmove.md)Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz **`memcpy`** ..

## <a name="see-also"></a>Ayrıca bkz.

[Arabellek Işleme](../../c-runtime-library/buffer-manipulation.md)\
[`_memccpy`](memccpy.md)\
[`memchr`, `wmemchr`](memchr-wmemchr.md)\
[`memcmp`, `wmemcmp`](memcmp-wmemcmp.md)\
[`memmove`, `wmemmove`](memmove-wmemmove.md)\
[`memset`, `wmemset`](memset-wmemset.md)\
[`strcpy_s`, `wcscpy_s`, `_mbscpy_s`](strcpy-s-wcscpy-s-mbscpy-s.md)\
[`strncpy_s`, `_strncpy_s_l`, `wcsncpy_s`, `_wcsncpy_s_l`, `_mbsncpy_s`, `_mbsncpy_s_l`](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)\
