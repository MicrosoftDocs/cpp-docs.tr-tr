---
title: Bağlayıcı araçları uyarısı LNK4247 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4247
dev_langs:
- C++
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2d84a5964cb8df5d2973b6031da55d48dade584e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078016"
---
# <a name="linker-tools-warning-lnk4247"></a>Bağlayıcı Araçları Uyarısı LNK4247

Giriş Noktası 'decorated_function_name', zaten bir iş parçacığı özniteliğine sahip; 'attribute' yoksayıldı

Belirtilen bir giriş noktası [/Entry (giriş noktası simgesi)](../../build/reference/entry-entry-point-symbol.md), bir iş parçacığı oluşturma özniteliği var ancak [/CLRTHREADATTRIBUTE (CLR iş parçacığı özniteliğini Ayarla)](../../build/reference/clrthreadattribute-set-clr-thread-attribute.md) Ayrıca, farklı bir iş parçacığı modeliyle belirtildi.

Bağlayıcı /CLRTHREADATTRIBUTE ile belirtilen değer geçersiz kılınır.

Bu uyarıyı çözmek için:

- /CLRTHREADATTRIBUTE, derlemeden kaldırın.

- Öznitelik, kaynak kodu dosyanızdan kaldırın.

- Kaynak ve /CLRTHREADATTRIBUTE her iki öznitelik, bir derlemeden kaldırın ve varsayılan CLR iş parçacığı modeli kabul edin.

- /CLRTHREADATTRIBUTE için geçirilen değer, kaynak özniteliğiyle kabul olacağı şekilde değiştirin.

- Özniteliği, kaynakta /CLRTHREADATTRIBUTE için geçirilen değer ile kabul olacağı şekilde değiştirin.

Aşağıdaki örnek LNK4247 oluşturur

```
// LNK4247.cpp
// compile with: /clr /c
// post-build command: link /CLRTHREADATTRIBUTE:STA LNK4247.obj /entry:functionTitle /SUBSYSTEM:Console
[System::MTAThreadAttribute]
void functionTitle (){}
```