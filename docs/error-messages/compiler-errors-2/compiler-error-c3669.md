---
title: Derleyici Hatası C3669 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3669
dev_langs:
- C++
helpviewer_keywords:
- C3669
ms.assetid: be9c7ae4-e96f-47ab-922a-39a3537d5ca6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 135ecf7767fddafc3d9e16398edfb4708b7d67cd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266317"
---
# <a name="compiler-error-c3669"></a>Derleyici Hatası C3669
'member': 'override' izin statik üye işlevleri veya oluşturucular tanımlayıcısı geçersiz kıl  
  
 Bir geçersiz kılma hatalı şekilde belirtildi. Daha fazla bilgi için bkz: [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3669 oluşturur.  
  
```  
// C3669.cpp  
// compile with: /clr  
public ref struct R {  
   R() override {}   // C3669  
};  
```