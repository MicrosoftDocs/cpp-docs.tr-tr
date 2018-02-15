---
title: . SAFESEH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 69212e7a3542a6b6ac88ccbe2ecbbf8894862e65
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
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