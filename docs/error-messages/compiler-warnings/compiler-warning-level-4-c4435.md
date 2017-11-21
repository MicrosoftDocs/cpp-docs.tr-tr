---
title: "Derleyici Uyarısı (düzey 4) C4435 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs: C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: "2"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3e907aac68727b752ac0516d2b6fbcbc5d4de84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4435"></a>Derleyici Uyarısı (düzey 4) C4435
'class1' : /vd2 altındaki nesne düzeni 'class2' sanal tabanı nedeniyle değişecek  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 / Vd1 seçeneği altında varsayılan derleme, türetilmiş sınıf sahip olmayan bir `vtordisp` belirtilen sanal temel alan.  Varsa /vd2 veya `#pragma vtordisp(2)` etkin olduğu bir `vtordisp` alan nesne düzenini değiştirme mevcut olacaktır.  Etkileşen modülleri farklı derlenmiş ise bu ikili uyumluluğu sorunlarına yol açabilir `vtordisp` ayarlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4435 oluşturur.  
  
```cpp  
// C4435.cpp  
// compile with: /c /W4  
#pragma warning(default : 4435)  
class A  
{  
public:  
    virtual ~A() {}  
};  
  
class B : public virtual A  // C4435  
{};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [vtordisp](../../preprocessor/vtordisp.md)   
 [/VD (yapı yer devre dışı bırak) değiştirmelerini](../../build/reference/vd-disable-construction-displacements.md)