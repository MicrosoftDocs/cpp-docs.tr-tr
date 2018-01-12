---
title: "Bağlayıcı araçları uyarısı LNK4227 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4227
dev_langs: C++
helpviewer_keywords: LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c603110d77b06fac59a725ba448f058bd4ad7a38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4227"></a>Bağlayıcı Araçları Uyarısı LNK4227  
  
> meta veri işlemi uyarı (*HRESULT*): *warning_message*  
  
Bağlayıcı birleştirilirken meta verileri farklar algıladı:  
  
-   Bir veya daha fazla başvurulan derlemeler derlemeyle şu anda oluşturuluyor.  
  
-   Bir veya daha fazla kaynak kodu dosyaları bir derlemede.  
  
Aynı adlı ancak farklı bildirilen parametre bilgileri ile iki genel işlevler varsa, örneğin, LNK4227 kaynaklanıyor olabilir (diğer bir deyişle, bildirimler içinde tüm derlenecek dosyalar tutarlı değil). İldasm.exe/Text kullanmak metadata *object_file* nasıl türleri farklı görmek için her .obj dosyasında.  
  
LNK4227 de başka bir araçla kaynaklanan sorunları bildirmek için kullanılır. Daha fazla bilgi için uyarı iletisi arayın.  
  
Uyarıyı çözmek için meta veri sorunların düzeltilmesi gerekir.  
  
## <a name="example"></a>Örnek  
  
Başvurulan derlemeyi başvuran derlemenin farklı imzalandığında LNK4227 oluşturulur.  
  
Aşağıdaki örnek LNK4227 oluşturur:  
  
```cpp  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 Ardından,  
  
```cpp  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
## <a name="example"></a>Örnek  
  
Derleme özniteliklerinin sürüm numaraları yanlış biçimde geçirildiğinde LNK4227 de oluşturulabilir.  ' *' Gösterimidir özgü `AssemblyVersionAttribute`.  Bu uyarıyı çözmek için kullanım yalnızca sürüm özniteliklerin dışında sayı `AssemblyVersionAttribute`.  
  
Aşağıdaki örnek LNK4227 oluşturur:  
  
```cpp  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```