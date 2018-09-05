---
title: . SAFESEH | Microsoft Docs
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- .SAFESEH
dev_langs:
- C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d10f3c751fe05c118203bb5eeff6c5cba6ec1c8b
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43693174"
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
.model  flat
MyHandler   proto
.safeseh    MyHandler
end
```

## <a name="see-also"></a>Ayrıca bkz.

[Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)<br/>