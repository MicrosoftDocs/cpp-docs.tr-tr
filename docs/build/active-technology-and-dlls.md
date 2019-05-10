---
title: Etkin Teknoloji ve DLL'ler
ms.date: 11/04/2016
helpviewer_keywords:
- in-process server DLLs
- Automation [C++], DLLs
- DLLs [C++], Active Technology
- Active technology [C++]
- MFC DLLs [C++], Active Technology
ms.assetid: 3ed27f8d-164a-4562-ad61-9f2333404cc7
ms.openlocfilehash: f67fb9548601ac705ceda08d20d3049f0bf1e0a5
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221004"
---
# <a name="active-technology-and-dlls"></a>Etkin Teknoloji ve DLL'ler

Etkin teknoloji nesne sunucularının DLL içinde tamamen uygulanması sağlar. Sunucu bu tür bir işlem sunucusu olarak adlandırılır. Esas olarak etkin teknoloji kapsayıcının ana ileti döngüsü içinde bağlama bir sunucu için bir yol sağlamaz çünkü MFC tamamen işlem içi sunucular görsel düzenleme, tüm özellikler için desteklemez. MFC kısayol tuşları ve boşta kalma süresi işleme işlemek için kapsayıcı uygulamasının ileti döngüsü erişim gerektirir.

Otomasyon sunucusu yazıyorsanız ve kullanıcı arabirimi olmadan sunucunuz varsa, bir işlem sunucusu sunucunuzun olun ve tamamen bir DLL içine koyabilirsiniz.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [Otomasyon Sunucuları](../mfc/automation-servers.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DLL'leri oluşturma](dlls-in-visual-cpp.md)
