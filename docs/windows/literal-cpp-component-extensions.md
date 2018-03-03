---
title: "değişmez değer (C++ bileşen uzantıları) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- literal
- literal_cpp
dev_langs:
- C++
helpviewer_keywords:
- literal keyword [C++]
ms.assetid: 6b1a1f36-2e1d-4a23-8eb6-172f4f3c477f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f858e94bf916c2d441cee607739bb9e08da09b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="literal-c-component-extensions"></a>değişmez değer (C++ Bileşen Uzantıları)
Bir değişken (veri üyesi) olarak işaretlenmiş `literal` içinde bir **/CLR** derleme aynıdır yerel bir `static const` değişkeni.  
  
## <a name="all-platforms"></a>Tüm Platformlar  
 **Açıklamalar**  
  
 (Tüm çalışma zamanları için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
## <a name="windows-runtime"></a>Windows Çalışma Zamanı  
 **Açıklamalar**  
  
 (Yalnızca Windows çalışma zamanı için geçerli hiçbir açıklamalar için bu dil özelliği vardır.)  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  
  
## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı  
  
## <a name="remarks"></a>Açıklamalar  
 Bir veri üyesi olarak işaretlenmiş `literal` bildirirken başlatılması gerekir ve değer sabit Entegral, numaralandırma veya dize türünde olmalıdır. Başlatma ifadesinin türüne dönüştürme statik const veri üyesi türü için kullanıcı tanımlı bir dönüştürme gerekli değil.  
  
 Değişmez değer alanın çalışma zamanında bellek tahsis; Derleyici değerini sınıfı için meta verilerde yalnızca ekler.  
  
 Bir değişken olarak işaretlenmiş `static const` meta verilerinde diğer derleyiciler için kullanılamaz.  
  
 Daha fazla bilgi için bkz: [statik](../cpp/storage-classes-cpp.md) ve [const](../cpp/const-cpp.md).  
  
 `literal`bağlama duyarlı bir anahtar sözcüktür. Bkz: [Context-Sensitive anahtar sözcükleri](../windows/context-sensitive-keywords-cpp-component-extensions.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Bu örnek gösteren bir `literal` değişkeni gelir `static`.  
  
```  
// mcppv2_literal.cpp  
// compile with: /clr  
ref struct X {  
   literal int i = 4;  
};  
  
int main() {  
   int value = X::i;  
}  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, meta verilerde değişmez değer etkilerini gösterir:  
  
```  
// mcppv2_literal2.cpp  
// compile with: /clr /LD  
public ref struct A {  
   literal int lit = 0;  
   static const int sc = 1;  
};  
```  
  
 Meta veriler için fark `sc` ve `lit`: `modopt` yönergesi uygulanan `sc`, yani dikkate diğer derleyiciler tarafından.  
  
```  
.field public static int32 modopt([mscorlib]System.Runtime.CompilerServices.IsConst) sc = int32(0x0000000A)  
```  
  
```  
.field public static literal int32 lit = int32(0x0000000A)  
```  
  
## <a name="example"></a>Örnek  
 C# dilinde yazılan aşağıdaki örnek, önceki örnekte oluşturulan meta veri başvuruyor ve etkilerini gösterir `literal` ve `static const` değişkenleri:  
  
```  
// mcppv2_literal3.cs  
// compile with: /reference:mcppv2_literal2.dll  
// A C# program  
class B {  
   public static void Main() {  
      // OK  
      System.Console.WriteLine(A.lit);  
      System.Console.WriteLine(A.sc);  
  
      // C# does not enforce C++ const  
      A.sc = 9;  
      System.Console.WriteLine(A.sc);  
  
      // C# enforces const for a literal  
      A.lit = 9;   // CS0131  
  
      // you can assign a C++ literal variable to a C# const variable  
      const int i = A.lit;  
      System.Console.WriteLine(i);  
  
      // but you cannot assign a C++ static const variable  
      // to a C# const variable  
      const int j = A.sc;   // CS0133  
      System.Console.WriteLine(j);  
   }  
}  
```  
  
## <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği:   **/CLR**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çalışma Zamanı Platformları için Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)