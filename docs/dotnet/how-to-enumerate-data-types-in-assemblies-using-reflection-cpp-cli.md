---
title: 'Nasıl yapılır: yansıma kullanarak veri türlerini numaralandırma (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: c3578e6d-bb99-4599-80e1-ab795305f878
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 5a4b85cb5af9d390d92bcca3e0462b0ae5b4d832
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-data-types-in-assemblies-using-reflection-ccli"></a>Nasıl yapılır: Yansıma Kullanarak Derlemelerde Veri Türlerini Numaralandırma (C++/CLI)
Aşağıdaki kodu kullanarak genel tür ve üyelerin listesi gösterir <xref:System.Reflection>.  
  
 Yerel dizindeki veya GAC bir derleme adı verilen, aşağıdaki kodu derleme açın ve açıklamaları almaya çalışır. Başarılı olursa, her tür yerel üyeleriyle görüntülenir.  
  
 Unutmayın <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> hiçbir dosya uzantısı kullanılır gerektirir. Yalnızca "mscorlib" kullanarak .NET Framework türleri görüntüsünü neden olur ancak bu nedenle, "mscorlib.dll" komut satırı bağımsız değişken olarak kullanarak, başarısız olur. Derleme adı sağlanmazsa, kod algılamak ve geçerli derlemedeki türleri (Bu koddan oluşan EXE) rapor.  
  
## <a name="example"></a>Örnek  
  
```  
// self_reflection.cpp  
// compile with: /clr  
using namespace System;  
using namespace System::Reflection;  
using namespace System::Collections;  
  
public ref class ExampleType {  
public:  
   ExampleType() {}  
   void Func() {}  
};  
  
int main() {  
   String^ delimStr = " ";  
   array<Char>^ delimiter = delimStr->ToCharArray( );  
   array<String^>^ args = Environment::CommandLine->Split( delimiter );  
  
// replace "self_reflection.exe" with an assembly from either the local  
// directory or the GAC  
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");  
   Console::WriteLine(a);  
  
   int count = 0;  
   array<Type^>^ types = a->GetTypes();  
   IEnumerator^ typeIter = types->GetEnumerator();  
  
   while ( typeIter->MoveNext() ) {  
      Type^ t = dynamic_cast<Type^>(typeIter->Current);  
      Console::WriteLine("   {0}", t->ToString());  
  
      array<MemberInfo^>^ members = t->GetMembers();  
      IEnumerator^ memberIter = members->GetEnumerator();  
      while ( memberIter->MoveNext() ) {  
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);  
         Console::Write("      {0}", mi->ToString( ) );  
         if (mi->MemberType == MemberTypes::Constructor)  
            Console::Write("   (constructor)");  
  
         Console::WriteLine();  
      }  
      count++;  
   }  
   Console::WriteLine("{0} types found", count);  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yansıma (C++/CLI)](../dotnet/reflection-cpp-cli.md)