---
title: Statik Const Int bağlantısı değişmez değer artık | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- literal attribute [C++]
- constants, declaring
- integral constant expressions
ms.assetid: d2a5e3d2-ffb0-4b61-8114-bec5993a1195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: cc3f72080c08807026c6458979ac0ba561e298df
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165002"
---
# <a name="static-const-int-linkage-is-no-longer-literal"></a>Statik Const Int Bağlantısı Artık Değişebilir Değerdir
Sabit bir sınıf üyesi bildirim Visual C++ için C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Ancak `static const` tümleşik üyeleri hala desteklenmektedir, kendi bağlantı özniteliği değişmiştir. Önceki bağlantı özniteliği değişmez değer bir tamsayı üye şimdi taşınır. Örneğin, aşağıdaki Yönetilen Uzantılar sınıfını göz önünde bulundurun:  
  
```  
public __gc class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 Bu alanın (Not değişmez değer özniteliğinin) aşağıdaki arka plandaki CIL özniteliklerini oluşturur:  
  
```  
.field public static literal int32   
modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Bu hala yeni sözdizimi altında derlenir:  
  
```  
public ref class Constants {  
public:  
   static const int LOG_DEBUG = 4;  
};  
```  
  
 değişmez değer özniteliğinin artık yayar ve bu nedenle bir sabit değer olarak CLR çalışma zamanı tarafından görüntülenen değil:  
  
```  
.field public static int32 modopt([Microsoft.VisualC]Microsoft.VisualC.IsConstModifier) STANDARD_CLIENT_PRX = int32(0x00000004)  
```  
  
 Aynı diller arası değişmez değer özniteliğine sahip için bildirimi değiştirilmelidir yeni desteklenen `literal` şekilde, veri üyesi  
  
```  
public ref class Constants {  
public:  
   literal int LOG_DEBUG = 4;  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Değişmez değer](../windows/literal-cpp-component-extensions.md)