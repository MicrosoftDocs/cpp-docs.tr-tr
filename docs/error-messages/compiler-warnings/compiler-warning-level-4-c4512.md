---
title: "Derleyici Uyarısı (düzey 4) C4512 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4512
dev_langs:
- C++
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: dd2e50f97cfc0242e1ac4af93f2d6609ff4b59cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4512"></a>Derleyici Uyarısı (düzey 4) C4512
'class': atama işleci oluşturulamadı  
  
 Derleyici verilen sınıf için bir atama işleci oluşturulamıyor. Atama işleci oluşturuldu.  
  
 Türetilmiş sınıf tarafından erişilebilir durumda değil taban sınıfı için bir atama işleci bu uyarıyı neden olabilir.  
  
 Bu uyarıyı önlemek için sınıf için bir kullanıcı tarafından tanımlanan atama işleci belirtin.  
  
 Derleyici bir tanımlamıyor bir sınıf için bir atama işleci işlevi de oluşturur. Bu atama işleci bir nesnenin veri üyelerine memberwise bir kopyasıdır. Çünkü `const` veri öğeleri sınıfı içeriyorsa başlatma sonra değiştirilemez bir `const` öğesi, varsayılan atama işleci çalışmaz. Başka bir C4512 uyarı bildirimi başvuru türü statik olmayan veri üyesi nedenidir. Hedefi copyable olmayan bir tür oluşturmak için ise, varsayılan kopya Oluşturucu oluşturulmasını engellemeniz gerekir.  
  
 Üç şekilde kodunuzda için C4512 uyarıyı çözün:  
  
-   Sınıfı için bir atama işleci açıkça tanımlayın.  
  
-   Kaldırma **const** veya sınıfında veri öğesi başvurusu işleci.  
  
-   #Pragma kullanmak [uyarı](../../preprocessor/warning.md) gizlemek için deyimi.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4512 oluşturur.  
  
```  
// C4512.cpp  
// compile with: /EHsc /W4  
// processor: x86  
  
class Base {  
private:  
   const int a;  
  
public:  
   Base(int val = 0) : a(val) {}  
   int get_a() { return a; }  
};   // C4512 warning  
  
class Base2 {  
private:  
   const int a;  
  
public:  
   Base2(int val = 0) : a(val) {}  
   Base2 & operator=( const Base2 & ) { return *this; }  
   int get_a() { return a; }  
};  
  
// Type designer intends this to be non-copyable because it has a   
// reference member  
class Base3  
{  
private:  
   char& cr;  
  
public:  
   Base3(char& r) : cr(r) {}  
   // Uncomment the following line to explicitly disable copying:  
   // Base3(const Base3&) = delete;   
};   // C4512 warning  
  
int main() {  
   Base first;  
   Base second;  
  
   // OK  
   Base2 first2;  
   Base2 second2;  
  
   char c = 'x';  
   Base3 first3(c);  
   Base3 second3 = first3; // C2280 if no default copy ctor  
}  
```