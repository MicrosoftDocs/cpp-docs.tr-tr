---
title: __security_init_cookie | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- __security_init_cookie
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
- security_init_cookie
- __security_init_cookie
dev_langs:
- C++
helpviewer_keywords:
- security cookie [C++]
- __security_init_cookie function
- security_init_cookie function
- global security cookie
ms.assetid: 32119905-0897-4a1c-84ca-bffd16c9b2af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 699a75da7829feb39142a777a34a14fcd85be653
ms.sourcegitcommit: a738519aa491a493a8f213971354356c0e6a5f3a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/05/2018
ms.locfileid: "48821153"
---
# <a name="securityinitcookie"></a>__security_init_cookie

Genel güvenlik tanımlama bilgisi başlatır.

## <a name="syntax"></a>Sözdizimi

```C
void __security_init_cookie(void);
```

## <a name="remarks"></a>Açıklamalar

Genel güvenlik tanımlama bilgisi ile derlenmiş kodda arabellek taşması koruma için kullanılan [/GS (arabellek güvenlik denetimi)](../../build/reference/gs-buffer-security-check.md) ve özel durum işleme kullanan kod. Girişi taşması korumalı bir işleve, tanımlama bilgisi yığına yerleştirilir ve Çıkışta, yığında değeri genel tanımlama bilgisi ile karşılaştırılır. Aralarındaki fark, bir arabellek taşması oluştu ve programı hemen sonlandırılmasına neden gösterir.

Normalde, **__security_init_cookie** tarafından CRT başlatıldığında çağrılır. CRT başlatma atlarsanız — Örneğin, kullanırsanız [/Entry](../../build/reference/entry-entry-point-symbol.md) giriş noktasını belirtmek için — çağırmalısınız sonra **__security_init_cookie** kendiniz. Varsa **__security_init_cookie** çağrılmaz; genel güvenlik tanımlama bilgisi, varsayılan değerine ayarlanır ve arabellek taşması koruma biri riske. Bir saldırganın bu varsayılan tanımlama bilgisi değeri'arabellek taşma denetimleri yemektir yararlanabilir olduğundan her zaman çağırmanızı öneririz **__security_init_cookie** kendi giriş noktası tanımladığınızda.

Çağrı **__security_init_cookie** herhangi önce taşması korumalı hale getirilmesi gereken işlevi girilir; sahte bir arabellek taşması algıladı Aksi takdirde. Daha fazla bilgi için [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="example"></a>Örnek

Örneklere bakın [C çalışma zamanı hatası R6035](../../error-messages/tool-errors/c-runtime-error-r6035.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**__security_init_cookie**|\<Process.h >|

**__security_init_cookie** standart C çalışma zamanı kitaplığı Microsoft uzantısıdır. Uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft Güvenlik Yanıt Merkezi](https://www.microsoft.com/msrc?rtc=1)
