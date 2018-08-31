---
title: C/C++ yalıtılmış derleme uygulamalar | Microsoft Docs
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
ms.openlocfilehash: 26a21eb12d9da1caaae3dbd12fe2f3ffd1194bac
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43219099"
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme
Yalıtılmış bir uygulama, yan yana derlemelerini bağlıdır ve bir bildiri kullanarak bağımlılıklarını bağlar. Windows üzerinde düzgün şekilde çalıştırmak için tamamen yalıtılmış olarak uygulamanız için gerekli değildir; Gelecekte uygulamanıza bakım yapmak gerekiyorsa ancak uygulamanızın tam yalıtılmış yaparken yatırım tarafından zamandan tasarruf. Uygulamanızı tamamen yalıtılmış yapma avantajları hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications).  
  
 Visual C++ kullanarak yerel C/C++ uygulamanızı oluştururken, varsayılan olarak Visual Studio Proje sistemi uygulama bağımlılıklarınızın Visual C++ kitaplıklarındaki tanımlayan bir bildirim dosyası oluşturur. Bunların yalnızca bağımlılık olması halinde Visual Studio ile yeniden olarak yalıtılmış bir uygulama haline gelir sonra uygulamanız vardır. Uygulamanızın çalışma zamanında diğer kitaplıkları kullanan sonra yan yana derlemeler içinde açıklanan adımları izleyerek bu kitaplıkları yeniden gerekebilir [C/C++ yan yana derlemeler oluşturuluyor](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derleme kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)