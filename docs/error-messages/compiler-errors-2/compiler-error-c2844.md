---
title: "Derleyici Hatası C2844 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2844
dev_langs: C++
helpviewer_keywords: C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 45e0a7eb7a8846d90cc8e0743f5484ba1b58208a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2844"></a>Derleyici Hatası C2844
'member': arabirimi 'arabirim' üyesi olamaz  
  
 Bir [arabirimi sınıfı](../../windows/interface-class-cpp-component-extensions.md) ayrıca bir özelliği olmadığı sürece veri üye içeremez.  
  
 Bir özellik veya üye işlevi dışındaki herhangi bir arabirim izin verilmiyor. Ayrıca, Oluşturucular, yok ediciler ve işleçler izin verilmez.  
  
 Aşağıdaki örnek C2844 oluşturur:  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
