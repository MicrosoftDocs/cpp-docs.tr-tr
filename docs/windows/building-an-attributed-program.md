---
title: "Öznitelikli Program derleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- tlb files
- MIDL
- MIDL, linker output
- IDL files
- tlb files, building attributed programs
- .tlb files, building attributed programs
- IDL files, building
- attributes [C++], building type libraries and .idl files
- .tlb files
- .idl files, building
- type libraries, linker options for building
ms.assetid: 04997b5f-bf2c-46ec-b868-c4adebbef5f4
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e3e39bbd2b630d35942c1c5107041b2fbadf7549
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="building-an-attributed-program"></a>Öznitelikli Program Derleme
Visual C++ öznitelikleri kaynak kodunuz yerleştirdiğiniz sonra sizin için bir tür kitaplığı ve .idl dosya oluşturmak için Visual C++ Derleyici isteyebilirsiniz. Aşağıdaki bağlayıcı .tlb ve .idl dosyalarını derleme yardım seçenekleri:  
  
-   [/ IDLOUT](../build/reference/idlout-name-midl-output-files.md)  
  
-   [/ IGNOREIDL](../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)  
  
-   [/ MIDL](../build/reference/midl-specify-midl-command-line-options.md)  
  
-   [/ TLBOUT](../build/reference/tlbout-name-dot-tlb-file.md)  
  
 Bazı projeleri birden çok bağımsız .idl dosyalarını içerir. Bunlar, iki veya daha fazla .tlb dosyaları üretmek ve isteğe bağlı olarak bunları kaynak bloğuna bağlamak için kullanılır. Bu senaryo, Visual C++'da şu anda desteklenmiyor.  
  
 Ayrıca, Visual C++ bağlayıcı tüm öznitelik IDL ilgili bilgileri tek bir MIDL dosyasına çıkarır. İki tür kitaplıklarının tek bir proje oluşturmak mümkün olacaktır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kavramları](../windows/attributed-programming-concepts.md)