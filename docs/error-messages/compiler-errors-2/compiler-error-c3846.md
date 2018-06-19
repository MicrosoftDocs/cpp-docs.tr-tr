---
title: Derleyici Hatası C3846 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3846
dev_langs:
- C++
helpviewer_keywords:
- C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97d5650d1743ba379ce065d4051bfed807a1df71
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33268032"
---
# <a name="compiler-error-c3846"></a>Derleyici Hatası C3846
'simgesi': 'assembly2' simgesini alınamıyor: 'simgesi' başka bir derlemeden 'assembly1' içe gibi  
  
 Başvurulan bir derleme önceden içeri aktarılmış olduğundan bir simge başvurulan bir derleme alınamadı.  
  
## <a name="example"></a>Örnek
Aşağıdaki örnek C3846 oluşturur:  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Ve bu derleme:  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
