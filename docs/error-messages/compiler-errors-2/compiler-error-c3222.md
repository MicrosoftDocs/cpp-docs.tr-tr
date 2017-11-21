---
title: "Derleyici Hatası C3222 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3222
dev_langs: C++
helpviewer_keywords: C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: edc882f340e92defeaa2db92d868680f7791e7b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
