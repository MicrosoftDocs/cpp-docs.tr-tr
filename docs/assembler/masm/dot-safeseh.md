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
ms.openlocfilehash: 5953ad6bdf1d9d1b0070ce83dd1d764799b7440a
ms.sourcegitcommit: 0781c69b22797c41630601a176b9ea541be4f2a3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75317571"
---
# <a name="safeseh-32-bit-masm"></a>. SAFESEH (32-bit masa)

Bir işlevi yapılandırılmış özel durum işleyicisi olarak kaydeder. (yalnızca 32-bit masa.)

## <a name="syntax"></a>Sözdizimi

> **. SAFESEH** *tanımlayıcısı*

## <a name="remarks"></a>Açıklamalar

*tanımlayıcı* yerel olarak tanımlanan bir [proc](proc.md) veya [EXTRN](extrn.md) proc için kimlik olmalıdır. [Etikete](label-masm.md) izin verilmiyor. İçin. SAFESEH yönergesi [/SafeSEH](ml-and-ml64-command-line-reference.md) ml. exe komut satırı seçeneğini gerektirir.

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

[Yönergeler başvurusu](directives-reference.md)\
[MASMG BNF dilbilgisi](masm-bnf-grammar.md)
