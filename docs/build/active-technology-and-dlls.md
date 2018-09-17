---
title: Etkin teknoloji ve DLL'ler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efa9a5cf17a4578fc7be9cbadc51605ee32c1650
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45706257"
---
# <a name="active-technology-and-dlls"></a>Etkin Teknoloji ve DLL'ler

Etkin teknoloji nesne sunucularının DLL içinde tamamen uygulanması sağlar. Sunucu bu tür bir işlem sunucusu olarak adlandırılır. Esas olarak etkin teknoloji kapsayıcının ana ileti döngüsü içinde bağlama bir sunucu için bir yol sağlamaz çünkü MFC tamamen işlem içi sunucular görsel düzenleme, tüm özellikler için desteklemez. MFC kısayol tuşları ve boşta kalma süresi işleme işlemek için kapsayıcı uygulamasının ileti döngüsü erişim gerektirir.

Otomasyon sunucusu yazıyorsanız ve kullanıcı arabirimi olmadan sunucunuz varsa, bir işlem sunucusu sunucunuzun olun ve tamamen bir DLL içine koyabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Otomasyon Sunucuları](../mfc/automation-servers.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)