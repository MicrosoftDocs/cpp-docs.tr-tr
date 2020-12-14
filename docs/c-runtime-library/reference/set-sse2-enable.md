---
description: 'Hakkında daha fazla bilgi edinin: _set_SSE2_enable'
title: _set_SSE2_enable
ms.date: 04/05/2018
api_name:
- _set_SSE2_enable
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
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _set_SSE2_enable
- set_SSE2_enable
helpviewer_keywords:
- _set_SSE2_enable function
- Streaming SIMD Extensions 2 instructions
- set_SSE2_enable function
ms.assetid: 55db895d-fc1e-475a-9110-b781a9bb51c5
ms.openlocfilehash: a9c82b2f17d90bc158ac77b8d7ad9625491856aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97211212"
---
# <a name="_set_sse2_enable"></a>_set_SSE2_enable

CRT matematik yordamlarında Streaming SIMD Extensions 2 (SSE2) yönergelerinin kullanımını etkinleştirilir veya devre dışı bırakır. (SSE2 varsayılan olarak etkinleştirildiğinden, bu işlev x64 mimarilerinde kullanılamaz.)

## <a name="syntax"></a>Sözdizimi

```C
int _set_SSE2_enable(
   int flag
);
```

### <a name="parameters"></a>Parametreler

*bayrağıyla*<br/>
1 SSE2 uygulamasını etkinleştirmek için; SSE2 uygulamasını devre dışı bırakmak için 0. Varsayılan olarak, SSE2 uygulamasını destekleyen işlemcilerde etkin hale gelir.

## <a name="return-value"></a>Dönüş Değeri

SSE2 uygulamasının etkinleştirilmiş olması halinde sıfır dışı; SSE2 uygulamasının devre dışı olması durumunda sıfır.

## <a name="remarks"></a>Açıklamalar

Aşağıdaki işlevlerde **_set_SSE2_enable** kullanılarak ETKINLEŞTIRILENEBILIR SSE2 uygulamaları vardır:

- [atan](atan-atanf-atanl-atan2-atan2f-atan2l.md)

- [Ceil](ceil-ceilf-ceill.md)

- [exp](exp-expf.md)

- [sını](floor-floorf-floorl.md)

- [açmasını](log-logf-log10-log10f.md)

- [log10](log-logf-log10-log10f.md)

- [modf](modf-modff-modfl.md)

- [POW](pow-powf-powl.md)

Bu işlevlerin SSE2 uygulamaları varsayılan uygulamalardan biraz farklı yanıtlar verebilir, çünkü SSE2 ara değerleri 64 bitlik kayan nokta miktarları, ancak varsayılan uygulama ara değerleri 80 bit kayan nokta miktarları.

> [!NOTE]
> Projeyi derlemek için [/Oi (Iç Işlevler üret)](../../build/reference/oi-generate-intrinsic-functions.md) derleyici seçeneğini kullanırsanız, **_set_SSE2_enable** hiçbir etkisi olmaz. **/Oi** derleyici SEÇENEĞI derleyiciye CRT çağrılarını değiştirmek için iç bilgileri kullanma yetkisi verir; Bu davranış **_set_SSE2_enable** etkisini geçersiz kılar. **/Oi** 'ın **_set_SSE2_enable** geçersiz kılmadığından emin olmak istiyorsanız, projenizi derlemek için **/Oi-** kullanın. Bu, **/Oi** belirten diğer derleyici anahtarlarını kullandığınızda da iyi bir uygulama olabilir.

SSE2 uygulama yalnızca tüm özel durumlar maskelenise kullanılır. Özel durumları maskelemek için [_control87 _controlfp](control87-controlfp-control87-2.md) kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_set_SSE2_enable**|\<math.h>|

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

[CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md)<br/>
