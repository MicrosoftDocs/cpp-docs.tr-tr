---
title: .SAFESEH
ms.date: 11/05/2019
f1_keywords:
- .SAFESEH
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
ms.openlocfilehash: 4577bd5d76949dfb777a359c80d91814f1c45fe2
ms.sourcegitcommit: 45f1d889df633f0f7e4a8e813b46fa73c9858b81
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/06/2019
ms.locfileid: "73703954"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-bit masa)

Bir işlevi yapılandırılmış özel durum işleyicisi olarak kaydeder. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> . SAFESEH tanımlayıcısı

## <a name="remarks"></a>Açıklamalar

*tanımlayıcı* yerel olarak tanımlanan bir [proc](../../assembler/masm/proc.md) veya [EXTRN](../../assembler/masm/extrn.md) proc için kimlik olmalıdır. [Etikete](../../assembler/masm/label-masm.md) izin verilmiyor. İçin. SAFESEH yönergesi [/SafeSEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml. exe komut satırı seçeneğini gerektirir.

Yapılandırılmış özel durum işleyicileri hakkında daha fazla bilgi için bkz. [/SafeSEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).

Örneğin, güvenli bir özel durum işleyicisini kaydetmek için yeni bir MASı dosyası oluşturun (aşağıdaki gibi),/SafeSEH ile birleştirin ve bağlı nesnelere ekleyin.

```asm
.386
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>