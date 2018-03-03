---
title: "Derleyici Hatası C3222 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3222
dev_langs:
- C++
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0028b9540127433bdbd17b01f1a5a3dfd9361558
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
