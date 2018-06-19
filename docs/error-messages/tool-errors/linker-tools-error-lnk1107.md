---
title: Bağlayıcı araçları hatası LNK1107 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1107
dev_langs:
- C++
helpviewer_keywords:
- LNK1107
ms.assetid: a37a893d-5efa-4eba-8f40-6c5518b4b9d0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fee2105cb0c12287cd2b47636f0e47011854a608
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298356"
---
# <a name="linker-tools-error-lnk1107"></a>Bağlayıcı Araçları Hatası LNK1107
geçersiz veya bozuk dosya: konumda okunamıyor  
  
 Aracı dosyası okunamadı. Dosyayı yeniden oluşturun.  
  
 LNK1107 bir modül geçirmeye çalışırsanız da oluşabilir (.dll veya .netmodule uzantısı ile oluşturulan [/clr:noAssembly](../../build/reference/clr-common-language-runtime-compilation.md) veya [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)) bağlayıcıya; bunun yerine .obj dosya geçirme.  
  
 Aşağıdaki örnek derleme ise:  
  
```  
// LNK1107.cpp  
// compile with: /clr /LD  
public ref class MyClass {  
public:  
   void Test(){}  
};  
```  
  
 ve ardından belirtin **LNK1107.dll bağlantı** komut satırında LNK1107 alırsınız.  Hatayı gidermek için belirtmek **LNK1107.obj bağlantı** yerine.