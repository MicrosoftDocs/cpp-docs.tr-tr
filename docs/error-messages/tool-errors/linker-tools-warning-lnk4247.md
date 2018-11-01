---
title: Bağlayıcı Araçları Uyarısı LNK4247
ms.date: 11/04/2016
f1_keywords:
- LNK4247
helpviewer_keywords:
- LNK4247
ms.assetid: 085d7fdf-9eaf-4641-8473-6eaadd073c7b
ms.openlocfilehash: cd4108f8bd06ec7a0b2d2eb9fab13917174b797b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516031"
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