---
title: . SAFESEH | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 8ea34448b4dae0525e7feb2fd7cca310a95a6e3c
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="safeseh"></a>.SAFESEH
Bir işlev yapılandırılmış özel durum işleyici olarak kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
.SAFESEH identifier  
```  
  
## <a name="remarks"></a>Açıklamalar  
 *tanımlayıcı* yerel olarak tanımlanmış bir kimliği olmalıdır [PROC](../../assembler/masm/proc.md) veya [EXTRN](../../assembler/masm/extrn.md) yordam A [etiket](../../assembler/masm/label-masm.md) verilmez. . SAFESEH yönergesi gerektirir [SAFESEH](../../assembler/masm/ml-and-ml64-command-line-reference.md) ml.exe komut satırı seçeneği.  
  
 Yapılandırılmış özel durum işleyicileri hakkında daha fazla bilgi için bkz: [SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md).  
  
 Örneğin, güvenli özel durum işleyici kaydetmek için yeni bir MASM dosyası (gibi) oluşturmak, SAFESEH ile birleştirin ve bağlı nesnelere ekleyin.  
  
```  
.386  
.model  flat  
MyHandler   proto  
.safeseh    MyHandler  
end  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönergeler Başvurusu](../../assembler/masm/directives-reference.md)