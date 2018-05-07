---
title: Derleyici Hatası C3816 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3816
dev_langs:
- C++
helpviewer_keywords:
- C3816
ms.assetid: 2e52cc7f-e31c-41a3-8d6f-9f5fab3648c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be09db4d91b511583b3119f03df8abc61a0153e9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3816"></a>Derleyici Hatası C3816
'bildirimi' daha önce bildirilen veya farklı bir yönetilen veya WinRTmodifier ile tanımlanan  
  
 Bir iletme bildirimine ve gerçek bir bildirimi gerektiren hiçbir çakışması veya özniteliklerin bildiriminde tutarsızlıklar olması.  
  
 Aşağıdaki örnek C3816 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3816a.cpp  
// compile with: /clr /c  
class C1;  
// try the following line instead  
// ref class C1;  
  
ref class C1{  // C3816, forward declaration does not use ref  
};  
```