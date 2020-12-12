---
description: 'Hakkında daha fazla bilgi edinin: __security_init_cookie'
title: __security_init_cookie
ms.date: 11/04/2016
api_name:
- __security_init_cookie
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- security_init_cookie
- __security_init_cookie
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
ms.openlocfilehash: 48051eb34e7fe9fe1e32e41849072f71d6665d94
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288951"
---
# <a name="__security_init_cookie"></a>__security_init_cookie

Genel güvenlik tanımlama bilgisini başlatır.

## <a name="syntax"></a>Syntax

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Açıklamalar

Genel güvenlik tanımlama bilgisi, [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ile derlenen kodda ve özel durum işleme kullanan kodda arabellek taşma koruması için kullanılır. Taşma korumalı bir işleve girişte, tanımlama bilgisi yığına konur ve çıkışta, yığındaki değer genel tanımlama bilgisiyle karşılaştırılır. Aralarında herhangi bir farklılık, bir arabellek taşmasının gerçekleştiğini ve programın anında sonlandırılmasını gösterir.

Normal olarak, **__security_init_cookie** başlatıldığında CRT tarafından çağırılır. CRT başlatmayı atlayabilirsiniz — Örneğin, bir giriş noktası belirtmek için [/Entry](../../build/reference/entry-entry-point-symbol.md) kullanırsanız, **__security_init_cookie** kendiniz çağırmanız gerekir. **__Security_init_cookie** çağrılmadığı takdirde, genel güvenlik tanımlama bilgisi varsayılan bir değere ayarlanır ve arabellek taşması koruması tehlikeye girebilir. Bir saldırgan, arabellek taşma denetimlerini ertelemeyi sağlamak için bu varsayılan tanımlama bilgisi değerinden yararlanabileceğinden, kendi giriş noktanızı tanımladığınızda **__security_init_cookie** her zaman çağırmanız önerilir.

**__Security_init_cookie** çağrısı, taşma korumalı herhangi bir işlev girilmadan önce yapılmalıdır; Aksi takdirde, bir spurde bellek taşması algılanır. Daha fazla bilgi için bkz. [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Örnek

[C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)içindeki örneklere bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__security_init_cookie**|\<process.h>|

**__security_init_cookie** , standart C çalışma zamanı kitaplığı 'Nın bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Güvenlik Yanıt Merkezi](https://www.microsoft.com/msrc?rtc=1)
