---
title: Değişken bağımsız değişken listeleri (...) (C + +/ CLI) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- variable argument lists
- parameter arrays
ms.assetid: db1a27f4-02a8-4318-8690-1f2893f52b38
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eec0e3591da2417137fda3bae4ed9e7860472fb2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889829"
---
# <a name="variable-argument-lists--ccli"></a>Değişken Bağımsız Değişken Listeleri (...) (C++/CLI)
Bu örnek nasıl kullanabileceğinizi gösterir `...` değişken sayıda bağımsız değişken işlevleri uygulamak için Visual C++'ta sözdizimi.  
  
> [!NOTE]
>  Bu konu C + ilgilidir +/ CLI. Kullanma hakkında bilgi için `...` ISO standart C++'da bakın [üç nokta ve Variadic şablonları](../cpp/ellipses-and-variadic-templates.md) ve üç nokta ve varsayılan bağımsız değişkenler [sonek ifadeleri](../cpp/postfix-expressions.md).  
  
 Kullanan parametre `...` parametre listesindeki son parametre olmalıdır.  
  
## <a name="example"></a>Örnek  
  
### <a name="code"></a>Kod  
  
```  
// mcppv2_paramarray.cpp  
// compile with: /clr  
using namespace System;  
double average( ... array<Int32>^ arr ) {  
   int i = arr->GetLength(0);  
   double answer = 0.0;  
  
   for (int j = 0 ; j < i ; j++)  
      answer += arr[j];  
  
   return answer / i;  
}  
  
int main() {  
   Console::WriteLine("{0}", average( 1, 2, 3, 6 ));  
}  
```  
  
### <a name="output"></a>Çıkış  
  
```  
3  
```  
  
## <a name="code-example"></a>Kod Örneği  
 Aşağıdaki örnek, C# ' dan değişken sayıda bağımsız değişken isteyen bir Visual C++ işlevi nasıl çağrılacağını gösterir.  
  
```  
// mcppv2_paramarray2.cpp  
// compile with: /clr:safe /LD  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
```  
  
 İşlev `f` dizinindeymiş gibi değişken sayıda bağımsız değişken gerçekleştirebileceğiniz bir işlev C# veya Visual Basic, örneğin, çağrılabilir.  
  
 C#, geçirilen bağımsız değişken bir `ParamArray` parametre değişken sayıda bağımsız değişken tarafından çağrılabilir. Aşağıdaki kod örneği C# ' dir.  
  
```  
// mcppv2_paramarray3.cs  
// compile with: /r:mcppv2_paramarray2.dll  
// a C# program  
  
public class X {  
   public static void Main() {  
      // Visual C# will generate a String array to match the   
      // ParamArray attribute  
      C myc = new C();  
      myc.f("hello", "there", "world");  
   }  
}  
```  
  
 Çağrı `f` Visual c++'ta başlatılmış bir dizi veya bir değişken uzunluk dizisi geçirebilirsiniz.  
  
```  
// mcpp_paramarray4.cpp  
// compile with: /clr  
using namespace System;  
  
public ref class C {  
public:   
   void f( ... array<String^>^ a ) {}  
};  
  
int main() {  
   C ^ myc = gcnew C();  
   myc->f("hello", "world", "!!!");  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Diziler](../windows/arrays-cpp-component-extensions.md)