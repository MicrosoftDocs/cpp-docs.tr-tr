---
title: "Değer türleri için sürüm sorunları yerel türlerin içinde bulunan (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __nogc type declarations
- __value keyword, issues when nesting
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a16b6fd7d166b7a997257bfd6cb741b82911c5bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="version-issues-for-value-types-nested-in-native-types-ccli"></a>Yerel Türlerin İçinde Bulunan Değer Türleri İçin Sürüm Sorunları (C++/CLI)
Bir istemci derleme oluşturmak için kullanılan bir imzalı (tanımlayıcı ad) derleme bileşeninin göz önünde bulundurun. Bileşen istemci türü olarak yerel bir UNION, bir sınıf veya bir dizi üyesi için kullanılan bir değer türü içeriyor. Bileşen gelecek bir sürümünde boyutunu veya değer türü düzenini değiştirirse, istemcinin yeniden derlenmesi gerekiyor.  
  
 Keyfile ile oluşturma [sn.exe](/dotnet/framework/tools/sn-exe-strong-name-tool) (`sn -k mykey.snk`).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek bileşendir.  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## <a name="example"></a>Örnek  
 Bu örnek istemcisi yapılandırılmıştır:  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### <a name="comments"></a>Açıklamalar  
 Ancak, başka bir üyesine eklerseniz `struct S` e içinde (örneğin, `double d;`) ve istemci derlemeden bileşeni yeniden derleyin, işlenmeyen bir özel durum oluşur (türünde <xref:System.IO.FileLoadException?displayProperty=fullName>).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yönetilen türler (C + +/ CLI)](../dotnet/managed-types-cpp-cli.md)