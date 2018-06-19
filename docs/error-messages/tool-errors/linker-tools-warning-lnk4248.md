---
title: Bağlayıcı araçları uyarısı LNK4248 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4248
dev_langs:
- C++
helpviewer_keywords:
- LNK4248
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3b67661d1ad260f388f8425420711ae2f708ce3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302639"
---
# <a name="linker-tools-warning-lnk4248"></a>Bağlayıcı Araçları Uyarısı LNK4248
Itanium tabanlı sistemler için çözümlenmemiş typeref belirteci (belirteç) için 'type'; Görüntü çalışmayabilir  
  
 Bir tür tanımı MSIL meta verilerde yok.  
  
 LNK4248 MSIL modülü türü için yalnızca ileriye dönük bildirimi olduğunda meydana gelebilir (ile derlenmiş **/CLR**), MSIL modülü türü başvurulan burada ve MSIL modülü için bir tanım sahip yerel bir modül ile bağlantılı olduğunda türü.  
  
 Bu durumda, bağlayıcı MSIL meta verileri yerel tür tanımında sağlar ve bu için doğru davranış sağlayabilir.  
  
 Bir iletme türü bildiriminde bir CLR türü ise, ancak ardından bağlayıcı'nın yerel tür tanımı doğru olmayabilir  
  
 Daha fazla bilgi için bkz: [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
### <a name="to-correct-this-error"></a>Bu hatayı düzeltmek için  
  
1.  MSIL modülü tür tanımında sağlar.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK4248 oluşturur. Çözümlemek için yapı A tanımlayın.  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, bir tür iletme tanımını sahiptir.  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek LNK4248 oluşturur.  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```