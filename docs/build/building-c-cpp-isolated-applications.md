---
title: C/C++ yalıtılmış uygulamaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 69de94159ef792aedff35efe81e8bb663d571105
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32360155"
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme
Yalıtılmış bir uygulama, yalnızca yan yana derlemelerini bağlıdır ve bir bildirim kullanarak bağımlılıklarını bağlar. Windows üzerinde düzgün çalışması için tam yalıtılmış olması, uygulamanız için gerekli değildir; Uygulamanızı gelecekte hizmet gerekiyorsa, ancak, tam olarak yalıtılmış uygulamanızı yaparken yatırım tarafından zamandan tasarruf. Tamamen yalıtılmış uygulamanızı yapmadan avantajları hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190).  
  
 Visual C++ kullanarak yerel C/C++ uygulamanızı oluşturma sırasında varsayılan olarak Visual Studio Proje sistemi Visual C++ kitaplıkları, uygulamanızın bağımlılıkları tanımlayan bir bildirim dosyası oluşturur. Bunlar yalnızca bağımlılıkları ise Visual Studio ile yeniden hemen yalıtılmış bir uygulama olur sonra uygulamanızın yoktur. Uygulamanızın çalışma zamanında diğer kitaplıklarını kullanarak sonra bu kitaplıkları açıklanan adımları izleyerek yan yana derlemeleri olarak yeniden oluşturma gerekebilir [yapı C/C++ yan yana derlemeler](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derlemeler kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)