---
title: Derleyici Hatası C3139 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3139
dev_langs:
- C++
helpviewer_keywords:
- C3139
ms.assetid: 95c92263-10ac-4ff3-b385-6312dd92adbc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06d63ef93c4924e0ee5e8808c5783ee5a0fb7f79
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247996"
---
# <a name="compiler-error-c3139"></a>Derleyici Hatası C3139
'struct': UDT üyeleri olmadan dışarı aktarılamaz  
  
 Uygulamayı denedi [verme](../../windows/export.md) özniteliği boş bir UDT (kullanıcı tanımlı tür). Örneğin:  
  
```  
// C3139.cpp  
#include "unknwn.h"  
[emitidl];  
[module(name=xx)];  
  
[export] struct MyStruct {   // C3139 empty type  
};  
int main(){}  
```