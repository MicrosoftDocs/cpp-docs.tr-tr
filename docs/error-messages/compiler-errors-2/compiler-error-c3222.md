---
title: Derleyici Hatası C3222 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 424c0f1011d984dff59d3d952347ad4f7b90f515
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3222"></a>Derleyici Hatası C3222
'parametresi': üye için varsayılan bağımsız değişkenler işlevlerini yönetilen veya WinRT türü veya genel işlevler bildiremezsiniz.  
  
Yöntem parametresi varsayılan bağımsız değişkeniyle bildirmek için izin verilmiyor. Bir aşırı yüklenmiş yöntemin bu sorunu çözmek için bir yol biçimidir. Diğer bir deyişle, herhangi bir parametre ile aynı ada sahip bir yöntemi tanımlamak ve yöntem gövdesi değişkeninde başlatma.  
  
Aşağıdaki örnek C3222 oluşturur:  
  
```  
// C3222_2.cpp  
// compile with: /clr  
public ref class G {  
   void f( int n = 0 );   // C3222  
};  
```  
