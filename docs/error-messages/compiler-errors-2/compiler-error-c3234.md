---
title: "Derleyici Hatası C3234 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3234
dev_langs: C++
helpviewer_keywords: C3234
ms.assetid: ebefc15a-e40d-424b-a3dd-d7e185d0ed7b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 96291111e8814eb1500ab0dab42c0c6ab90ccda1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3234"></a>Derleyici Hatası C3234
Genel bir sınıf bir genel tür parametresi türetilemez  
  
 Genel bir sınıf bir genel tür parametresi devralır olamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3234 oluşturur.  
  
```  
// C3234.cpp  
// compile with: /clr /c  
generic <class T>  
public ref class C : T {};   // C3234  
// try the following line instead  
// public ref class C {};  
```