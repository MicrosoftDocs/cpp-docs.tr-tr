---
title: Derleyici Uyarısı (düzey 4) C4512 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4512
dev_langs:
- C++
helpviewer_keywords:
- C4512
ms.assetid: afb68995-684a-4be5-a73a-38d7a16dc030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d87a79fcdc4c1ac79b1237032f6cfb5a52b9e269
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33293923"
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