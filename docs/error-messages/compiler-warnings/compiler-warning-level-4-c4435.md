---
title: "Derleyici Uyarısı (düzey 4) C4435 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7136cfb61a7452b7e835030216d08f064874df8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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