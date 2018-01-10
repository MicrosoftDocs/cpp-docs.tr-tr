---
title: "Derleyici Hatası C3237 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3237
dev_langs: C++
helpviewer_keywords: C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ba4c89340c2c00f79b9888028867a34d1b5fbed9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3237"></a>Derleyici Hatası C3237
'generic_class': genel bir sınıf özel özniteliği olamaz.  
  
 Genel sınıflar, kullanıcı tanımlı öznitelikleri olamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3237 oluşturur.  
  
```  
// C3237.cpp  
// compile with: /clr /c  
// C3237 expected  
using namespace System;  
  
generic <class T>  
// Delete the following line to resolve.  
[attribute(AttributeTargets::All, AllowMultiple=true)]  
public ref class GR {};  
```