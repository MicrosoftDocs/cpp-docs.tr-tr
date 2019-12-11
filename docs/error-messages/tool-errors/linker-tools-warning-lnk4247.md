---
title: Bağlayıcı Araçları Uyarısı LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: 344c219fa1f3daa1e5f9c31431e608f5e7036400
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991159"
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
