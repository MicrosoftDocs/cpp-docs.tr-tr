---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4247'
title: Bağlayıcı Araçları Uyarısı LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 88cd04e345b798b6927c3a5297380f1eeb3c5f5c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241189"
---
# <a name="linker-tools-warning-lnk4247"></a>Bağlayıcı Araçları Uyarısı LNK4247

' decorated_function_name ' giriş noktasında zaten bir thread özniteliği var; ' Attribute ' yoksayıldı

[/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md)ile belirtilen bir giriş noktasının bir Threading özniteliği vardı, ancak farklı bir iş parçacığı modeliyle [/CLRTHREADATTRıBUTE (Set CLR thread özniteliği)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) de belirtildi.

Bağlayıcı,/CLRTHREADATTRIBUTEILE belirtilen değeri yoksaydı.

Bu uyarıyı çözmek için:

- /CLRTHREADATTRıBUTE 'yi derlemeden kaldırın.

- Kaynak kod dosyanızdaki özniteliği kaldırın.

- Derlemeden hem kaynak hem de/CLRTHREADATTRıBUTE özniteliğini kaldırın ve varsayılan CLR iş parçacığı modelini kabul edin.

- /CLRTHREADATTRıBUTE 'e geçirilen değeri değiştirin, örneğin, kaynak içindeki özniteliğiyle kabul eder.

- Kaynaktaki özniteliği değiştirin, yani/CLRTHREADATTRIBUTETO öğesine geçirilen değeri kabul eder.

Aşağıdaki örnek LNK4247 oluşturur

```cpp
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```
