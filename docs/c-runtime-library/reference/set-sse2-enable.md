---
title: _set_SSE2_enable
ms.date: 04/05/2018
apiname:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
ms.openlocfilehash: c340423e93b6487a4a951e4b96055cba6e474269
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539340"
---
# <a name="setsse2enable"></a>_set_SSE2_enable

Etkinleştirir ya da CRT matematik yordamlarını Streaming SIMD Extensions 2 (SSE2) yönergeleri kullanımını devre dışı bırakır. (Bu işlev üzerinde x64 kullanılamıyor mimarileri SSE2 varsayılan olarak etkin olduğundan.)

## <a name="syntax"></a>Sözdizimi

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Parametreler

*Bayrağı*<br/>
SSE2 uygulamasını etkinleştirmek için 1; SSE2 uygulama devre dışı bırakmak için 0'ı tıklatın. Varsayılan olarak, bunu destekleyen işlemcilerde SSE2 uygulama etkinleştirilir.

## <a name="return-value"></a>Dönüş Değeri

SSE2 uygulama etkin olursa sıfır dışı; sıfır SSE2 uygulama devre dışı bırakıldı.

## <a name="remarks"></a>Açıklamalar

Şu işlevleri kullanarak etkinleştirilebilir SSE2 uygulamaları sahip **_set_SSE2_enable**:

- [atan](atan-atanf-atanl-atan2-atan2f-atan2l.md)

- [ceil](ceil-ceilf-ceill.md)

- [exp](exp-expf.md)

- [Kat](floor-floorf-floorl.md)

- [log](log-logf-log10-log10f.md)

- [log10](log-logf-log10-log10f.md)

- [modf](modf-modff-modfl.md)

- [POW](pow-powf-powl.md)

Bu işlevlerin SSE2 uygulamaları, SSE2 Ara değerleri 64-bit kayan nokta miktarlar ancak varsayılan uygulama ara değerleri 80 bit olduğundan varsayılan uygulamaları daha biraz farklı yanıtlar vermek kayan nokta miktarlar.

> [!NOTE]
> Kullanırsanız [(iç işlevler Oluştur) /Oi](../../build/reference/oi-generate-intrinsic-functions.md) Projeyi derlemek için derleyici seçeneği, görünebilir **_set_SSE2_enable** hiçbir etkisi olmaz. **/Oi** derleyici seçeneği derleyici CRT çağrıları değiştirilecek yapı içleri kullanma yetkisi verir; bu davranışı geçersiz kılar etkisini **_set_SSE2_enable**. Bunu garanti etmenin istiyorsanız **/Oi** geçersiz **_set_SSE2_enable**, kullanın **/Oi-** projenizi derlemek için. Yaptığından diğer derleyici anahtarları kullandığınızda da yararlı olabilir **/Oi**.

SSE2 uygulama yalnızca tüm özel durumları maskelenmiş kullanılır. Kullanım [_control87, _controlfp](control87-controlfp-control87-2.md) maskesi özel durumlar.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_SSE2_enable**|\<Math.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_set_SSE2_enable.c
// processor: x86
#include <math.h>
#include <stdio.h>

int main()
{
   int i = _set_SSE2_enable(1);

   if (i)
      printf("SSE2 enabled.\n");
   else
      printf("SSE2 not enabled; processor does not support SSE2.\n");
}
```

```Output
SSE2 enabled.
```

## <a name="see-also"></a>Ayrıca bkz.

[CRT Kitaplık Özellikleri](../../c-runtime-library/crt-library-features.md)<br/>
