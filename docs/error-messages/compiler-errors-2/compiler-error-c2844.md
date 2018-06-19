---
title: Derleyici Hatası C2844 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2844
dev_langs:
- C++
helpviewer_keywords:
- C2844
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4a45e4a94e3d474be670f822d56a7c080f25693c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247315"
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
