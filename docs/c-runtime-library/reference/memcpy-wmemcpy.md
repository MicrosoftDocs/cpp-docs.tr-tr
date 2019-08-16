---
title: memcpy, wmemcpy
ms.date: 11/04/2016
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wmemcpy
- memcpy
helpviewer_keywords:
- wmemcpy function
- memcpy function
ms.assetid: 34abb90b-bffb-46dc-a2f3-a5e9940839d6
ms.openlocfilehash: f687e231060c287e206017dc61fe1d5193d8f0de
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69499633"
---
# <a name="memcpy-wmemcpy"></a>memcpy, wmemcpy

Baytları, arabellekler arasında kopyalar. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [memcpy_s, wmemcpy_s](memcpy-s-wmemcpy-s.md).

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

*HD*<br/>
Yeni arabellek.

*YN*<br/>
Kopyalanacak arabellek.

*biriktirme*<br/>
Kopyalanacak karakter sayısı.

## <a name="return-value"></a>Dönüş Değeri

*Hedef*değeri.

## <a name="remarks"></a>Açıklamalar

**memckay** , *src* 'den *hedefe*kadar olan *sayıları* bayt olarak kopyalar; **wmemcpy** kopya *sayısı* geniş karakter (iki bayt). Kaynak ve hedef çakışırsa, **memcservicebehavior** davranışı tanımsızdır. Çakışan bölgeleri işlemek için **memmove** kullanın.

> [!IMPORTANT]
> Hedef arabelleğinin boyut veya Kaynak arabelleğinden daha büyük olduğundan emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!IMPORTANT]
> Bu nedenle çok sayıda arabellek taşması ve bu nedenle olası güvenlik açıkları, **memcler**'in hatalı kullanımıyla izlenmediğinden, bu Işlev güvenlik geliştirme yaşam döngüsü (SDL) tarafından "yasaklanmış" işlevler arasında listelenir.  Bazı VC + + kitaplık sınıflarının memcleyde kullanmaya devam edipedebiliriz.  Ayrıca, VC + + derleyici iyileştiricinin bazen memcleya çağrıları yaydığıgözlemleyebilirsiniz.  Görsel C++ ürün, SDL işlemine uygun olarak geliştirilmiştir ve bu nedenle bu yasaklanmış işlevin kullanımı yakından değerlendirilir.  Kitaplık kullanımı durumunda, bu çağrılar aracılığıyla arabellek taşmalarına izin verilmeyeceğini sağlamak için çağrılar dikkatle scrutinized.  Derleyici söz konusu olduğunda bazen bazı kod desenleri **memctable**deseniyle aynı şekilde tanınır ve bu nedenle, işlev çağrısıyla değiştirilmiştir.  Bu gibi durumlarda, **memckopyala** kullanımı özgün yönergelerden daha güvenli değildir; Bunlar, performansı ayarlanmış **memcler** işlevine yapılan bir çağrıya en iyi duruma getirilmiştir.  "Güvenli" CRT işlevlerinin kullanılması güvenliği garanti etmez (yalnızca güvenli olmaması önerilir), "yasaklanmış" işlevlerinin kullanılması olma tehlikesi 'yi garanti etmez (yalnızca güvenliği sağlamak için daha fazla scrlanlı olması gerekir).
>
> VC + + derleyicisi ve kitaplıklar tarafından daha dikkatli scrutinized olduğundan, bu çağrılara, başka BIR şekilde SDL ile uyumlu olan kod içinde izin verilir.  uygulama kaynak kodunda tanıtılan **memcler** çağrıları yalnızca, bu kullanım güvenlik uzmanları tarafından incelenmek için SDL ile uyumludur.

**Memcler** ve **wmemcpy** işlevleri, işlevlerin kullanım dışı olması için, aşağıdaki örnekte olduğu gibi, yalnızca sabit **_CRT_SECURE_DEPRECATE_MEMORY** , ekleme ifadesiyle önce tanımlanırsa kullanım dışı bırakılır:

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
|**memcpy**|\<Memory. h > veya \<String. h >|
|**wmemcpy**|\<wchar. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

**Memckopyala**'nın nasıl kullanılacağına ilişkin bir örnek için bkz. [memmove](memmove-wmemmove.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Ara Bellek Düzenlemesi](../../c-runtime-library/buffer-manipulation.md)<br/>
[_memccpy](memccpy.md)<br/>
[memchr, wmemchr](memchr-wmemchr.md)<br/>
[memcmp, wmemcmp](memcmp-wmemcmp.md)<br/>
[memmove, wmemmove](memmove-wmemmove.md)<br/>
[memset, wmemset](memset-wmemset.md)<br/>
[strcpy_s, wcscpy_s, _mbscpy_s](strcpy-s-wcscpy-s-mbscpy-s.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
