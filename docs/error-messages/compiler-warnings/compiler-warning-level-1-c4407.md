---
title: "Derleyici Uyarısı (düzey 1) C4407 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4407
dev_langs: C++
helpviewer_keywords: C4407
ms.assetid: 32bc2c21-363a-4bb8-b486-725faeaededc
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 736b5f99115d6e2a39ee77005c7b3248ac191453
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4407"></a>Derleyici Uyarısı (düzey 1) C4407
üye Beyanları farklı işaretçi arasında cast, derleyici yanlış kod oluşturabilirsiniz  
  
 Yanlış bir cast algılandı.  
  
 Visual C++ 2005'te yapıldığı derleyici uyumluluğu iş nedeniyle C4407 oluşturulabilir. İşaretçi-üye şimdi gerektirir tam adı ve address-of işleci (&).  
  
 C4407 bir birden çok devralma işaretçi-üye için bir tek devralma işaretçi-üye arasında cast ortaya çıkabilir. Bu bazen çalışabilir, ancak bazı durumlarda tek devralma işaretçi-üye gösterimi yeterli bilgiyi tutmak değil çünkü olamaz. İle derleme **/VMM** yardımcı olabilir (daha fazla bilgi için bkz: [/VMM, / VMs, / vmv (genel amaçlı temsil)](../../build/reference/vmm-vms-vmv-general-purpose-representation.md)). Ayrıca, temel sınıfları yeniden düzenleme deneyin; bir taban sınıf sıfır uzaklığı türetilmiş olduğundan derleyici dönüştürme bilgi kaybına algılıyor.  
  
 Aşağıdaki örnek C4407 oluşturur:  
  
```  
// C4407.cpp  
// compile with: /W1 /c  
struct C1 {};  
struct C2 {};  
struct C3 : C1, C2 {};  
  
typedef void(C3::*PMF_C3)();  
typedef void(C2::*PMF_C2)();  
  
PMF_C2 f1(PMF_C3 pmf) {  
   return (PMF_C2)pmf;   // C4407, change type of cast,  
   // or reverse base class inheritance of C3 (i.e. : C2, C1)  
}  
```