---
title: .SAFESEH
ms.date: 08/30/2018
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: adfb9106095de3d15bafb67172b001d0f4597418
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649858"
---
# <a name="safeseh"></a>.SAFESEH

Bir işlev bir yapılandırılmış özel durum işleyici kaydeder.

## <a name="syntax"></a>Sözdizimi

> . SAFESEH tanımlayıcısı

## <a name="remarks"></a>Açıklamalar

*tanımlayıcı* yerel olarak tanımlanan bir kimliği olmalı [PROC](../../assembler/masm/proc.md) veya [EXTRN](../../assembler/masm/extrn.md) yordam A [etiket](../../assembler/masm/label-masm.md) izin verilmiyor. . SAFESEH yönergesi gerektirir [SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe komut satırı seçeneği.

Yapılandırılmış özel durum işleyicileri hakkında daha fazla bilgi için bkz. [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Örneğin, bir güvenli özel durum işleyicisini kaydetmek için yeni MASM dosyası (gibi) oluşturmak, SAFESEH ile birleştirin ve bağlı nesnelere ekleyin.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>