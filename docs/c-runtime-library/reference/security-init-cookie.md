---
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
ms.openlocfilehash: 9f7e9924f4a96803749418d777e5ee2020f9df78
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70948714"
---
# <a name="__security_init_cookie"></a>__security_init_cookie

Genel güvenlik tanımlama bilgisini başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Açıklamalar

Genel güvenlik tanımlama bilgisi, [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ile derlenen kodda ve özel durum işleme kullanan kodda arabellek taşma koruması için kullanılır. Taşma korumalı bir işleve girişte, tanımlama bilgisi yığına konur ve çıkışta, yığındaki değer genel tanımlama bilgisiyle karşılaştırılır. Aralarında herhangi bir farklılık, bir arabellek taşmasının gerçekleştiğini ve programın anında sonlandırılmasını gösterir.

Normalde, **__security_ınit_cookie** başlatıldığında CRT tarafından çağırılır. CRT başlatmayı atlayabilirsiniz — Örneğin, bir giriş noktası belirtmek için [/Entry](../../build/reference/entry-entry-point-symbol.md) kullanırsanız — daha sonra **__security_ınit_cookie** öğesini kendiniz çağırmanız gerekir. **__Security_ınit_cookie** çağrılmadığı takdirde, genel güvenlik tanımlama bilgisi varsayılan bir değere ayarlanır ve arabellek taşması koruması tehlikeye girebilir. Bir saldırgan, arabellek taşma denetimlerini ertelemeyi sağlamak için bu varsayılan tanımlama bilgisi değerinden yararlanabileceğinden, kendi giriş noktanızı tanımladığınızda her zaman **__security_ınit_cookie** öğesini çağırmanız önerilir.

**__Security_ınit_cookie** çağrısı, herhangi bir taşma korumalı işlev girilmadan önce yapılmalıdır; Aksi takdirde, bir spurde bellek taşması algılanır. Daha fazla bilgi için bkz. [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Örnek

[C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md)içindeki örneklere bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__security_init_cookie**|\<Process. h >|

**__security_ınit_cookie** , standart C çalışma zamanı kitaplığı 'Nın bir Microsoft uzantısıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Güvenlik Yanıt Merkezi](https://www.microsoft.com/msrc?rtc=1)
