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
ms.openlocfilehash: 78d14f812700afa4ea0ad66b527a0e3888862f4d
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45716917"
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme

Yalıtılmış bir uygulama, yan yana derlemelerini bağlıdır ve bir bildiri kullanarak bağımlılıklarını bağlar. Windows üzerinde düzgün şekilde çalıştırmak için tamamen yalıtılmış olarak uygulamanız için gerekli değildir; Gelecekte uygulamanıza bakım yapmak gerekiyorsa ancak uygulamanızın tam yalıtılmış yaparken yatırım tarafından zamandan tasarruf. Uygulamanızı tamamen yalıtılmış yapma avantajları hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications).

Visual C++ kullanarak yerel C/C++ uygulamanızı oluştururken, varsayılan olarak Visual Studio Proje sistemi uygulama bağımlılıklarınızın Visual C++ kitaplıklarındaki tanımlayan bir bildirim dosyası oluşturur. Bunların yalnızca bağımlılık olması halinde Visual Studio ile yeniden olarak yalıtılmış bir uygulama haline gelir sonra uygulamanız vardır. Uygulamanızın çalışma zamanında diğer kitaplıkları kullanan sonra yan yana derlemeler içinde açıklanan adımları izleyerek bu kitaplıkları yeniden gerekebilir [C/C++ yan yana derlemeler oluşturuluyor](../build/building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)