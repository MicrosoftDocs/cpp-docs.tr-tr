---
title: . SAFESEH | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAFESEH
dev_langs: C++
helpviewer_keywords:
- registering functions as exception handlers
- SAFESEH directive
- .SAFESEH directive
ms.assetid: 6eaac8c4-c46f-47ae-8a66-f5cfeb267e43
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bcbcafef4ad548ab784740a4130fc1679bf43f0a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Yönergeler başvurusu](../../assembler/masm/directives-reference.md)