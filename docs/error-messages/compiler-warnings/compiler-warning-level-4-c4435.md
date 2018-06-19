---
title: Derleyici Uyarısı (düzey 4) C4435 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: a04524af-2b71-4ff9-9729-d9d1d1904ed7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72c29bd6d9ffdb4eabb036c61d85a6572cef8fe2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293942"
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
 [/vd (Yapı Yer Değiştirmelerini Devre Dışı Bırak)](../../build/reference/vd-disable-construction-displacements.md)