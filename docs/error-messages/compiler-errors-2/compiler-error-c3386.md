---
title: "Derleyici Hatası C3386 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3386
dev_langs: C++
helpviewer_keywords: C3386
ms.assetid: 93fa8c33-0f10-402b-8eec-b0a217a1f8dc
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8b912d1d75ae120f993c3641ff2e2b561910b4aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3386"></a>Derleyici Hatası C3386
'type': __declspec(dllexport) /\_yönetilen veya WinRTtype _declspec(dllimport) uygulanamaz  
  
 `dllimport` Ve [dllexport](../../cpp/dllexport-dllimport.md) `__declspec` değiştiricileri yönetilen veya Windows çalışma zamanı geçerli olmayan türü.  
  
 Aşağıdaki örnek C3386 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3386.cpp  
// compile with: /clr /c  
ref class __declspec(dllimport) X1 {   // C3386  
// try the following line instead  
// ref class X1 {  
};  
```